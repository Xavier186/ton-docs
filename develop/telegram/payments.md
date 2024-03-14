# Payments



## Bot Payments API

**Telegram Bot Payments** are a free and open platform that allows sellers to accept payments for goods and services from Telegram users. Telegram doesn't collect payment information and takes **no commission**.

> **Note:** This article is intended for bot developers and store owners. If you're looking for a general overview of Telegram Payments, check out the [Telegram blog](https://telegram.org/blog/payments-2-0-scheduled-voice-chats#payments-2-0).

If you are new to Telegram bots and would like to learn how to create and set up a bot, please consult our [**Introduction to Bots**](https://core.telegram.org/bots) and **Bot FAQ**.

#### Introducing Payments 2.0

[Payments 2.0](https://telegram.org/blog/payments-2-0-scheduled-voice-chats) were added in April 2021 with Bot API v.5.2. New features:

* Send invoices to **any chat**, including to groups and channels.
* Create invoices that can be **forwarded** and used by **multiple buyers** to order things.
* Use inline mode to help users show your goods and services to their friends and communities.
* Allow **tips** from users with preset and custom amounts.
* Accept payments from users on mobile or **desktop apps**.
* Try [@ShopBot](https://t.me/shopbot) to create a test invoice – or start a message with `@ShopBot ...` in any chat for an **inline invoice**.
* Check out [Demo Shop](https://t.me/teststore) for an example of a [Telegram Channel](https://telegram.org/tour/channels) used as **virtual storefront**.

> Users need to update to **Telegram 7.7** or higher to use **Payments 2.0** (for [Telegram Desktop](https://desktop.telegram.org/), **2.7.2** or higher). Older _mobile_ apps released after [May 2017](https://telegram.org/blog/payments) support basic payments in chats with bots.

**How does this work?**

You create a **bot** that offers goods and services to Telegram users. Merchant bots can send specially formatted **invoice messages** to users, groups or channels. If your bot supports inline mode, users can also send invoices to other chats _via the bot_, including to one-on-one chats with other users.

Invoice messages feature a **photo** and **description** of the product along with a prominent **Pay** button. Tapping this button opens a special payment interface in the Telegram app. In this interface, users can choose a **tip amount** (if allowed by the merchant) and enter additional details like shipping info, phone number, or email address.

The bot can offer several shipping options for physical goods based on the delivery address. When ready, users enter their credit card info or choose a saved card — and pay for the product. Telegram also supports _Apple Pay_ and _Google Pay_. Once the transaction is done, the merchant bot can send a **receipt message** with payment details, shipping and delivery information.

> [Detailed information](broken-reference) and [step-by-step instructions](broken-reference) are available below.

**Supported Payment Providers**

Telegram does **not** process payments from users and instead relies on different **payment providers** around the world. It is the payment providers that handle and store all sensitive information, like credit card details. Neither Telegram nor the bot developers have access to it.

For the moment we support payments from more than **200 countries** via the following payment providers:

* [Stripe](https://stripe.com/)
* [Smart Glocal](https://smart-glocal.com/)
* [Unlimint](https://www.unlimint.com/)
* [Tranzzo](https://tranzzo.com/)
* [Paykassma](https://paykassma.com/telegram)
* [YooMoney](https://yoomoney.ru/)
* [Sberbank](https://www.sberbank.ru/)
* [PSB](https://www.psbank.ru/Business/Acquiring/Internet)
* [Bank 131](https://developer.131.ru/ru/)
* [Payme](https://payme.uz/)
* [CLICK](http://click.uz/)
* [LiqPay](https://www.liqpay.ua/uk/)
* [LeoGaming](https://leogaming.net/ua/telegram)
* [Cascad](https://cascad.com/)
* [Portmone](https://www.portmone.com.ua/)
* [Paymega](https://paymega.io/)
* [ECOMMPAY](https://ecommpay.com/)
* [PayMaster](https://info.paymaster.ru/)
* [Global Pay UZ](https://gate.global.uz/)
* [iPay88](https://ipay88.com.kh/)
* [PayBox.money](https://paybox.money/)
* [Freedom Pay](https://freedompay.money/)
* [bill\_line](https://billline.net/)
* [Chapa](https://chapa.co/)

We continue expanding this list, follow [@BotNews](https://t.me/botnews) for updates.

> If you work for a company that provides services similar to standalone accounts in [Stripe Connect](https://stripe.com/connect), please let us know via [@BotSupport](https://t.me/botsupport) (include the hashtag `#paymentsprovider` in your message).

***

#### The Payments API

This section explores payments via Telegram's Bot API in more detail.

**Connecting Payments**

To start accepting payments, you need a **Telegram bot**. Use [BotFather](https://t.me/botfather) to create a bot if you don't have one already.

Now you have a merchant bot that can offer goods or services to Telegram users. Let's call it `@merchantbot` in this document. The first stop is to choose and **connect a payment provider**, you can find the [list of supported providers](broken-reference) above.

**Getting a Token**

* Use the `/mybots` command in the chat with [BotFather](https://t.me/botfather) and choose the `@merchantbot` that will be offering goods or services.
* Go to _Bot Settings > Payments_.
* Choose a provider, and you will be redirected to the relevant bot.
* Enter the required details so that the payments provider is connected successfully, go back to the chat with Botfather.
* The message will now show available providers. Each will have a name, a **token**, and the date the provider was connected.
* You will use the **token** when working with the Bot API.

**Implementing Payments**

You will find the necessary methods for building your payment implementation in the [Payments Section of the Bot API Manual](https://core.telegram.org/bots/api#payments).

**Testing Payments: the 'Stripe TEST MODE' Provider**

While you're still developing and testing payments for your bot, use the “Stripe TEST MODE” provider. When in this mode, you can make payments without actually billing any accounts. Real cards can't be used in test mode, but you can use test cards like `4242 4242 4242 4242` ([full list here](https://stripe.com/docs/testing#cards)). You can switch between test mode and live mode as many times as you want, but please see the [live checklist](broken-reference) **before** you go live.

#### Step-by-Step Process

> See [Bot API: Payments](https://core.telegram.org/bots/api#payments) for the complete list of available methods and objects.

**1. Create Invoice**

The user contacts `@merchantbot` and requests to purchase something. The bot forms an invoice message with a description of the goods or service, amount to be paid, and requested shipping info. There are two ways of creating an invoice:

**A. Bot Invoice**

Use the [sendInvoice](https://about/bots/api#sendinvoice) method to generate an invoice and send it to a chat. The _provider\_token_ parameter is where you put the _token_ value that you've [obtained earlier via Botfather](broken-reference). It is possible for one merchant bot to use several different tokens for different users or different goods and services.

As of [Payments 2.0](broken-reference), invoice messages with a pay button can be sent to **chats of any type**: private chats with the user, groups, or channels. The resulting invoice message will look like this:



Bot Invoice

**B. Inline Invoice**

If `@merchantbot` supports inline mode, you can use [inputInvoiceMessageContent](https://about/bots/api#inputinvoicemessagecontent) to allow users to share invoices for your goods and services to their one-on-one chats with friends, or to their groups and channels. These invoices will have a **Pay button** that can be used multiple times.



Inline Invoice

**2. Choose Forwarding Behavior**

As of [Payments 2.0](broken-reference) there are two ways for handling **forwarded copies** of your invoices, controlled by the parameter _start\_parameter_ in the [sendInvoice](https://about/bots/api#sendinvoice) method.

* **A. Multi-chat invoice.** Forwarded copies show a **Pay button**, which multiple users can press and attempt to pay for the goods or services. [Inline invoices](broken-reference) are always multi-chat invoices.
* **B. Single-chat invoice.** Invoice can only be paid from the chat to which it was sent, _forwarded copies_ show a **URL button** with a deep link to the bot. The deep link can be used to generate a similar invoice in the chat with the bot, to show an error message, or for other purposes. [More info on Deep Linking »](https://about/bots#deep-linking)

If a _single-chat invoice_ is sent to the chat with `@merchantbot`, it can only be paid **once**. If a _single-chat invoice_ is sent to any other chat, it can be paid **many times** by many users.

> To get a better understanding of how this works, try toggling the _“Pay from Forwards”_ parameter when creating invoices with our demo [@ShopBot](https://t.me/shopbot).

Regardless of whether or not the **Pay** button is available in an invoice, the merchant bot always has the power to decide whether or not to accept new payments for a particular invoice.

**3. Tips (optional step)**

If the _max\_tip\_amount_ parameter is set to above `0`, users can add a tip to their payment. You can use the parameter _suggested\_tip\_amounts_ to suggest particular amounts that you feel will be relevant for the invoice.



Adding Tips

**4. Shipping info and other details (optional step)**

The user specifies shipping information or other info requested by the bot. This could be the user's full name, an email address, a phone number in international format, or a full postal address for delivery.



Shipping Info

**5. Offer delivery options based on shipping address (optional step)**

If a shipping address was requested and you included the parameter _is\_flexible_, the Bot API will send an [Update](https://about/bots/api#update) with a _shipping\_query_ field to the bot. The bot must respond using [answerShippingQuery](https://about/bots/api#answershippingquery) either with a list of possible delivery options and the relevant delivery prices, or with an error (for example, if delivery to the specified address is not possible).

> **Tip:** It is recommended that the merchant bot confirms availability of the goods/services at this step – to let the user know in case they are no longer available. This is especially important if you are using [multi-chat](broken-reference), [inline](broken-reference) or [single-chat, multi-use](broken-reference) invoices.

**6. Select delivery option (optional step)**

The user selects a delivery option from the list (the overall amount to be paid may change at this point) and proceeds to checkout.



Choose Delivery Option

**7. Pre-Checkout**

The user enters their payment information and presses the final pay button. At this moment the Bot API sends an [Update](https://about/bots/api#update) with the field _pre\_checkout\_query_ to the bot that contains all the available information about the order. Your bot must reply using [answerPrecheckoutQuery](https://about/bots/api#answerprecheckoutquery) within **10 seconds** after receiving this update or the transaction is canceled.

The bot may return an error if it can't process the order for any reason. We highly recommend specifying a reason for failure to complete the order in human readable form (e.g. _"Sorry, we're all out of rubber ducks! Would you be interested in a cast iron bear instead?"_). Telegram will display this reason to the user.

> **Warning:** As of [Payments 2.0](broken-reference), it is critical to make sure your bot **only** accepts multiple payments when the order can be processed correctly. This is especially important if you are using [multi-chat](broken-reference), [inline](broken-reference) or [single-chat, multi-use](broken-reference) invoices.

**8. Checkout**

In case the bot confirms the order, Telegram requests the payment provider to complete the transaction. If the payment information was entered correctly and the payment goes through, the API will send a receipt message of the type [_successful\_payment_](https://about/bots/api#message) from the user. Once your bot receives this message, it should proceed with delivering the goods or services purchased by the user.

If the invoice message was sent in the chat with `@merchantbot`, it becomes a Receipt in the UI for the user — they can open this receipt at any time and see all the details of the transaction:



Receipt

If the message was sent to any other chat, the **Pay button** remains and can be used again. It is up to the merchant bot whether to actually accept multiple payments.

#### Going Live

Once you've tested everything and confirmed that your payments implementation works, you're ready to switch to LIVE MODE. To do this, go to BotFather > /mybots > select `@merchantbot` > Bot Settings / Payments and enable Stripe LIVE MODE. You will get a token that has the string `:LIVE:` in the middle, e.g. `123:LIVE:XXXX`. Do not give this token to any third parties!

Before your merchant bot goes into live mode, please ensure the following:

**Live Checklist**

* We highly recommend turning on [2-step verification](https://telegram.org/faq#q-how-does-2-step-verification-work) for the Telegram account that controls your bot.
* You as the bot owner have **full responsibility** in case any conflicts or disputes arise. You must be prepared to correctly process disputes and chargebacks (in the case of Stripe, see [here](https://stripe.com/docs/disputes)).
* To prevent any misunderstandings and possible legal issues, make sure your bot can respond to a /terms command (or offers a similarly easy way of accessing your Terms and Conditions). Your Terms and Conditions should be written in a clear way and easy to understand for your users. The users must confirm that they have read and agree to your terms before they make the purchase.
* Your bot must provide support for its customers, either by responding to a /support command or by some other clearly communicated means. Users must have a clear way of contacting you about their purchases and you must process their support requests in a timely fashion. You must notify your users that Telegram support or [bot support](https://t.me/botsupport) will not able to help them with purchases made via your bot.
* Make sure that your server hardware and software is stable. Use backups to make sure that you don't lose data about your users' payments.
* Make sure that you have completed the live checklist for your selected **payments provider** as well as this one.

***

#### FAQ

**How do I join as a payment provider?**

If you work for a company that provides services similar to standalone accounts in [Stripe Connect](https://stripe.com/connect), please let us know via [@BotSupport](https://t.me/botsupport) (kindly include the hashtag `#paymentsprovider` in your message).

**How much do you charge?**

Telegram does **not** charge any commission for using the Payments API. Note though, that most payment providers will have their own commissions. For example, Stripe in the US charges 2.9% + 30¢ per successful card charge (see the [Stripe website](https://stripe.com/pricing) for more details on pricing).

**Do I need a bot to accept payments?**

Yes. If you are not a developer, you will need to either hire someone to make a bot for you (recommended), or use a bot created by a third-party company. We advise extreme caution when using services of bots that process payments for you – Telegram doesn't maintain any such bots and doesn't endorse any of the third-party bots offering these services.

**What can my bot sell?**

Telegram does not impose any limits on what products or services your bot can offer. But please note that you **must** comply with the rules of the payments provider you choose in our system. E.g., Stripe has a special page for [prohibited businesses](https://stripe.com/us/prohibited-businesses) – you may want to consult that one before you start selling harvested organs.

**Special Note:** Due to Apple's limitations, bot developers are currently not allowed to accept payments for digital goods and virtual services from **iOS users**.

**How are disputes handled?**

Telegram acts as a messenger between the paying user, the bot developer, and their chosen payment system. The user sends their credit card details directly to the payment system. Then the payment system's response and the shipping details entered by the user are passed to the bot developer so that they can process the order.

Since Telegram doesn‘t process the payments, we don’t store and can‘t access any sensitive data. Due to this structure, it is impossible for Telegram to handle complaints or cashbacks – any disputed payments are the responsibility of the bot developers, payment providers, and banks that participated in the exchange.

> See also: [Telegram Privacy Policy](https://telegram.org/privacy#7-third-party-payment-services)

**How do I support payments in my third-party app that uses the Telegram API?**

You are welcome to study the MTProto payment documentation.

**Supported Currencies**

Telegram payments currently support the currencies listed below (here's a [JSON version](.gitbook/assets/currencies.json) in case you need it).

If you're using Stripe as the payments provider, supported currencies may vary depending on the country you have specified in your Stripe account ([more info](https://support.stripe.com/questions/which-currencies-does-stripe-support)).

The minimum and maximum amounts for each of the currencies roughly correspond to the limit of `US$ 1-10000`. The amount must be expressed in 12 digits or less, so the maximum value will be correspondingly lower for some lower-value currencies. Note that for each currency except USD these limits depend on exchange rates and may change over time (plan ahead for this when you implement limits in your code).

| Code | Title                                 | Min amount    | Max amount         |
| ---- | ------------------------------------- | ------------- | ------------------ |
| AED  | United Arab Emirates Dirham           | AED 3.67      | AED 36,724.98      |
| AFN  | Afghan Afghani                        | AFN70.86      | AFN708,694.42      |
| ALL  | Albanian Lek                          | 94,79ALL      | 947.944,42ALL      |
| AMD  | Armenian Dram                         | 402.92 AMD    | 4,029,235.27 AMD   |
| ARS  | Argentine Peso                        | ARS 849,76    | ARS 8.497.616,33   |
| AUD  | Australian Dollar                     | AU$1.50       | AU$15,096.85       |
| AZN  | Azerbaijani Manat                     | 1,69 AZN      | 16 999,72 AZN      |
| BAM  | Bosnia & Herzegovina Convertible Mark | 1,78 BAM      | 17.870,65 BAM      |
| BDT  | Bangladeshi Taka                      | BDT 109.72    | BDT 1,097,293.54   |
| BGN  | Bulgarian Lev                         | 1,78 BGN      | 17 878,06 BGN      |
| BND  | Brunei Dollar                         | BND1,33       | BND13.320,18       |
| BOB  | Bolivian Boliviano                    | BOB 6,93      | BOB 69.334,80      |
| BRL  | Brazilian Real                        | R$ 4,96       | R$ 49.613,97       |
| BYN  | Belarusian ruble                      | 3,27 BYN      | 32 705,29 BYN      |
| CAD  | Canadian Dollar                       | CA$1.34       | CA$13,464.60       |
| CHF  | Swiss Franc                           | 0.87 CHF      | 8'787.00 CHF       |
| CLP  | Chilean Peso                          | CLP 946       | CLP 9.460.604      |
| CNY  | Chinese Renminbi Yuan                 | CN¥7.18       | CN¥71,892.00       |
| COP  | Colombian Peso                        | COP 3.904,64  | COP 39.046.400,00  |
| CRC  | Costa Rican Colón                     | CRC510,15     | CRC5.101.532,93    |
| CZK  | Czech Koruna                          | 23,01 CZK     | 230 141,05 CZK     |
| DKK  | Danish Krone                          | 6,81 DKK      | 68152,02 DKK       |
| DOP  | Dominican Peso                        | DOP58.99      | DOP589,973.20      |
| DZD  | Algerian Dinar                        | DZD 134.32    | DZD 1,343,284.67   |
| EGP  | Egyptian Pound                        | EGP 47.84     | EGP 478,496.99     |
| ETB  | Ethiopian Birr                        | ETB56.74      | ETB567,419.07      |
| EUR  | Euro                                  | 0,91 €        | 9 139,65 €         |
| GBP  | British Pound                         | £0.78         | £7,807.50          |
| GEL  | Georgian Lari                         | 2,64 GEL      | 26 499,12 GEL      |
| GTQ  | Guatemalan Quetzal                    | GTQ7.80       | GTQ78,080.03       |
| HKD  | Hong Kong Dollar                      | HK$7.82       | HK$78,219.55       |
| HNL  | Honduran Lempira                      | HNL 24.67     | HNL 246,790.91     |
| HRK  | Croatian Kuna                         | 6,88 HRK      | 68.823,75 HRK      |
| HUF  | Hungarian Forint                      | 360,45 HUF    | 3 604 595,45 HUF   |
| IDR  | Indonesian Rupiah                     | IDR15.592,05  | IDR155.920.500,00  |
| ILS  | Israeli New Sheqel                    | ₪ 3.63        | ₪ 36,328.55        |
| INR  | Indian Rupee                          | ₹82.85        | ₹828,501.50        |
| ISK  | Icelandic Króna                       | 135 ISK       | 1.357.298 ISK      |
| JMD  | Jamaican Dollar                       | JMD154.78     | JMD1,547,861.51    |
| JPY  | Japanese Yen                          | ¥147          | ¥1,476,629         |
| KES  | Kenyan Shilling                       | KES134.50     | KES1,345,062.83    |
| KGS  | Kyrgyzstani Som                       | 89-51 KGS     | 895 102-27 KGS     |
| KRW  | South Korean Won                      | ₩1,317        | ₩13,173,102        |
| KZT  | Kazakhstani Tenge                     | KZT449-93     | KZT4 499 374-39    |
| LBP  | Lebanese Pound                        | LBP 89,492.29 | LBP 894,922,963.11 |
| LKR  | Sri Lankan Rupee                      | LKR 305.95    | LKR 3,059,542.35   |
| MAD  | Moroccan Dirham                       | MAD 10.01     | MAD 100,199.92     |
| MDL  | Moldovan Leu                          | 17.53 MDL     | 175,389.41 MDL     |
| MNT  | Mongolian Tögrög                      | MNT3 389,09   | MNT33 890 990,92   |
| MUR  | Mauritian Rupee                       | MUR45.77      | MUR457,769.65      |
| MVR  | Maldivian Rufiyaa                     | 15.52 MVR     | 155,250.12 MVR     |
| MXN  | Mexican Peso                          | MX$16.65      | MX$166,522.00      |
| MYR  | Malaysian Ringgit                     | MYR4.68       | MYR46,860.57       |
| MZN  | Mozambican Metical                    | MZN63.50      | MZN635,046.61      |
| NGN  | Nigerian Naira                        | NGN1,590.25   | NGN15,902,502.37   |
| NIO  | Nicaraguan Córdoba                    | NIO 36.77     | NIO 367,777.67     |
| NOK  | Norwegian Krone                       | NOK 10,47     | NOK 104 775,04     |
| NPR  | Nepalese Rupee                        | NPR132.28     | NPR1,322,800.13    |
| NZD  | New Zealand Dollar                    | NZ$1.62       | NZ$16,207.55       |
| PAB  | Panamanian Balboa                     | PAB 0.99      | PAB 9,998.26       |
| PEN  | Peruvian Nuevo Sol                    | PEN 3.68      | PEN 36,893.01      |
| PHP  | Philippine Peso                       | PHP55.39      | PHP553,994.98      |
| PKR  | Pakistani Rupee                       | PKR275.87     | PKR2,758,710.79    |
| PLN  | Polish Złoty                          | 3,92 PLN      | 39 222,91 PLN      |
| PYG  | Paraguayan Guaraní                    | PYG 7.285     | PYG 72.853.639     |
| QAR  | Qatari Riyal                          | QAR 3.64      | QAR 36,407.50      |
| RON  | Romanian Leu                          | 4,54 RON      | 45.433,05 RON      |
| RSD  | Serbian Dinar                         | 107,14 RSD    | 1.071.435,75 RSD   |
| RUB  | Russian Ruble                         | 95,93 RUB     | 959 332,42 RUB     |
| SAR  | Saudi Riyal                           | SAR 3.75      | SAR 37,502.80      |
| SEK  | Swedish Krona                         | 10,24 SEK     | 102.438,50 SEK     |
| SGD  | Singapore Dollar                      | SGD1.33       | SGD13,319.05       |
| THB  | Thai Baht                             | ฿35.61        | ฿356,197.52        |
| TJS  | Tajikistani Somoni                    | 10;94 TJS     | 109 477;82 TJS     |
| TRY  | Turkish Lira                          | 32,12 TRY     | 321.228,97 TRY     |
| TTD  | Trinidad and Tobago Dollar            | TTD6.78       | TTD67,876.18       |
| TWD  | New Taiwan Dollar                     | NT$31.49      | NT$314,965.04      |
| TZS  | Tanzanian Shilling                    | TZS2,552.00   | TZS25,520,002.75   |
| UAH  | Ukrainian Hryvnia                     | 38,74UAH      | 387 411,01UAH      |
| UGX  | Ugandan Shilling                      | UGX3,894      | UGX38,943,001      |
| USD  | United States Dollar                  | $1.00         | $10,000.00         |
| UYU  | Uruguayan Peso                        | UYU 38,81     | UYU 388.150,80     |
| UZS  | Uzbekistani Som                       | 12 525,68 UZS | 125 256 861,04 UZS |
| VND  | Vietnamese Đồng                       | 24.700 ₫      | 247.000.000 ₫      |
| YER  | Yemeni Rial                           | YER 250.34    | YER 2,503,498.94   |
| ZAR  | South African Rand                    | ZAR 18.61     | ZAR 186,129.94     |
