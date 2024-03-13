# Telegram Bot Features

## Telegram Bot Features

This page describes individual **bot elements** and **features** in detail. See also:

* A General Bot Platform Overview
* Full API Reference for Developers

#### What features do bots have?

* [**Inputs**](broken-reference)
  * [Text](broken-reference)
  * [Commands](broken-reference)
  * [Buttons](broken-reference)
  * [Chat and User Selection](broken-reference)
* [**Interactions**](broken-reference)
  * [Inline](broken-reference)
  * [Deep Linking](broken-reference)
  * [Attachment Menu](broken-reference)
* [**Integration**](broken-reference)
  * [Web Apps](broken-reference)
  * [Payments](broken-reference)
  * [Web Login](broken-reference)
  * [HTML5 Games](broken-reference)
  * [Stickers](broken-reference)
* [**Language Support**](broken-reference)
* [**Bot Management**](broken-reference)
  * [Privacy Mode](broken-reference)
  * [Testing Your Bot](broken-reference)
  * [Status Alerts](broken-reference)
  * [Local API](broken-reference)
* [**BotFather, creating and managing bots**](broken-reference)

***

#### Inputs

Users can send **messages of all types** to bots, including text, files, locations, stickers, voice messages and even [dice](https://about/bots/api#dice) if they're feeling lucky. However, Telegram bots offer many other tools for building flexible interfaces tailored to your specific needs:

* [Commands](broken-reference) that are highlighted in messages and can be selected from a list after typing `/`.
* [Keyboards](broken-reference) that replace the user's keyboard with predefined answer options.
* [Buttons](broken-reference) that are shown next to messages from the bot.

For even more flexibility, [Web Apps](broken-reference) support 100% custom interfaces with JavaScript.



> **Note:** Telegram bots can support [multiple languages](broken-reference) that adapt to the users' language settings in the app.

**Commands**

A command is a simple `/keyword` that tells the bot what to do. Telegram apps will:

* **Highlight** commands in messages. When the user taps a highlighted command, that command is immediately sent again.
* Suggest a **list of supported commands** with descriptions when the user enters a `/` (for this to work, you need to have provided a list of commands to [@BotFather](https://t.me/botfather) or via the [appropriate API method](https://about/bots/api#setmycommands)). Selecting a command from the list immediately sends it.
* Show a [menu button](broken-reference) containing all or some of a bot’s commands (which you set via [@BotFather](https://t.me/botfather)).

Commands must always start with the `/` symbol and contain **up to 32 characters**. They can use **Latin letters**, **numbers** and **underscores**, though simple lowercase text is recommended for a cleaner look.

Here are a few examples:

* /next
* /cancel
* /newlocation
* /newrule

Commands should be **as specific as possible** – for example `/newlocation` or `/newrule` **is better** than a `/new` command that then requires an additional parameter from the user like "_location_“ or ”_rule_".



> We require **all developers** to support several [Global Commands](broken-reference) to make sure Telegram bots offer a consistent and user-friendly experience.

**Command Scopes**

Your bot is able to **show different commands** to different users and groups – you can control this using [scopes](https://about/bots/api#botcommandscope). For example, your bot could show additional commands to group admins or translate the list based on the user’s [language\_code](https://about/bots/api#user).

> Keep in mind that Bot API [updates](https://about/bots/api#update) **will not contain any information** about the scope of a command sent by the user – in fact, they may contain commands that don’t exist at all in your bot. Your backend should **always** verify that received commands are valid and that the user was authorized to use them regardless of scope.
>
> Bots with privacy mode enabled will only receive commands in groups under special conditions, [see here](broken-reference).

**Keyboards**

Bots are able to interpret free text input from users, but offering **specific suggestions** is often more intuitive – this is where **custom keyboards** can be extremely useful.

Whenever your bot sends a message, it can **display a special keyboard** with predefined reply options (see [ReplyKeyboardMarkup](https://about/bots/api#replykeyboardmarkup)). Telegram apps that receive the message will display your keyboard to the user. Using any of the buttons will immediately send the respective text. This way you can drastically **simplify** and **streamline** user interaction with your bot.



> Check out the [one\_time\_keyboard](https://about/bots/api#replykeyboardmarkup) parameter to automatically hide your bot's keyboard as soon as it's been used.

You can also **customize the text placeholder** in the input field by setting the `input_field_placeholder` parameter.

**Inline Keyboards**

There are times when you'd prefer to do things **without sending any messages** to the chat – like when a user is changing settings, toggling options or navigating search results. In such cases, you can use [Inline Keyboards](https://about/bots/api#inlinekeyboardmarkup) that are shown directly below their relevant messages.

Unlike with custom reply keyboards, pressing buttons on inline keyboards **doesn't send messages to the chat**. Instead, inline keyboards support buttons that can work behind the scenes or open different interfaces: [callback buttons](https://about/bots/api#inlinekeyboardbutton), [URL buttons](https://about/bots/api#inlinekeyboardbutton), [switch-to-inline buttons](https://about/bots/api#inlinekeyboardbutton), [game buttons](https://about/bots/api#inlinekeyboardbutton) and [payment buttons](https://about/bots/api#inlinekeyboardbutton).



> To provide a **better user experience**, consider [editing your keyboard](https://about/bots/api#editmessagereplymarkup) when the user toggles a setting button or navigates to a new page – this is both **faster** and **smoother** than sending a whole new message and deleting the previous one.

**Menu Button**

In all bot chats, a menu button appears near the message field. By default, tapping this button **opens a menu** that can hold some or all of a bot's commands, including a short description for each. Users can then **select a command from the menu** without needing to type it out.

You can set different texts of the menu button and its command descriptions for various **individual users** or **groups of users** – for example, showing translated text based on the user’s language, as explained [here](broken-reference).

The **menu button** can alternatively be used to launch a [Web App](broken-reference).

**Global Commands**

To make basic interactions more uniform, we ask all developers to support a few **basic commands**. Telegram apps will have interface shortcuts for these commands.

* /start - begins the interaction with the user, like sending an introductory message. This command can also be used to pass additional parameters to the bot (see [Deep Linking](broken-reference)).
* /help - returns a help message, like a short text about what your bot can do and a list of commands.
* /settings - (if applicable) shows the bot's settings for this user and suggests commands to edit them.

Users will see a **Start** button the first time they open a chat with your bot. **Help** and **Settings** links will be available in the menu on the bot's profile page if you add them in [@BotFather](https://t.me/botfather).

#### Chat and User Selection

Bots can present the user with a **friendly** and **intuitive** interface that lists any number of groups, channels or other users according to a custom set of **criteria**. Tapping on a chat will send its identifier to the bot in a service message and seamlessly close the interface.

A group management bot is the **perfect example**: an admin could select a chat the bot should manage, and then select a user it should promote – this would happen without ever typing any text.

Here is a **quick start guide** to use this feature:

* Pick a set of criteria and store them in a [KeyboardButtonRequestChat](https://core.telegram.org/bots/api#keyboardbuttonrequestchat) object (or [KeyboardButtonRequestUser](https://core.telegram.org/bots/api#keyboardbuttonrequestuser) for users).
* Create a [KeyboardButton](https://core.telegram.org/bots/api#keyboardbutton) and store the criteria under `request_chat` or `request_user` respectively.
* Send a [ReplyKeyboardMarkup](https://core.telegram.org/bots/api#replykeyboardmarkup) that contains the button you just created.
* When the user selects a chat, you'll receive its identifier in a `chat_shared` or `user_shared` service message.

> Keep in mind that the bot may not be able to use the identifier it receives if the corresponding chat or user is not already known or accessible by some other means.

***

#### Interactions

In addition to sending commands and messages to the chat with the bot, there are several ways of interacting with them without opening any specific chat or group.

* [**Inline mode**](broken-reference) allows sending requests to bots right from the input field – from any chat on Telegram.
* [**Deep linking**](broken-reference) allows special links that send certain parameters to the bot when opened.
* [**Attachment menu**](broken-reference) integration makes it possible to use bots from the attachment menu in chats.

**Inline Requests**

Users can interact with your bot via **inline queries** straight from the message field **in any chat**. All they need to do is start a message with your bot's _@username_ and enter a keyword.

Having received the query, your bot can return some results. As soon as the user selects one, it is sent to the **relevant chat**. This way, people can request and send content from your bot in any of their chats, groups or channels.

Remember that inline functionality has to be enabled via [@BotFather](https://t.me/botfather), or your bot will not receive inline [Updates](https://about/bots/api#update).



> Examples of inline bots include [@gif](https://gif.t.me/), [@bing](https://bing.t.me/) and [@wiki](https://wiki.t.me/). [Web App](broken-reference) bots can also be used inline – try typing [@durgerkingbot](https://durgerkingbot.t.me/) in any chat.

**Deep Linking**

Telegram bots have a deep linking mechanism that allows **additional parameters** to be passed to the bot on startup. It could be a command that launches the bot – or an authentication token to connect the user's Telegram account to their account on another platform.

Each bot has a link that **opens a conversation** with it in Telegram – `https://t.me/<bot_username>`. Parameters can be added directly to this link to let your bot work with additional information on the fly, without any user input.

> A-Z, a-z, 0-9, \_ and - are allowed. We recommend using base64url to encode parameters with binary and other types of content. The parameter can be up to 64 characters long.

**Private Chats**\
In private chats, you can use the `start` parameter to automatically pass any value to your bot whenever a user presses the link. For example, you could use:

```
https://t.me/your_bot?start=airplane
```

When someone opens a chat with your bot via this link, you will receive:

```
/start airplane
```

**Groups**\
In groups, you can add the parameter `startgroup` to this link. For example:

```
https://t.me/your_bot?startgroup=spaceship
```

Following a link with this parameter prompts the user to select a group to add the bot to – the resulting update will contain text in the form:

```
/start@your_bot spaceship
```

> [Web Apps](broken-reference) also support deep linking, for more information check out our [dedicated guide](https://about/bots/webapps#adding-bots-to-the-attachment-menu).

**Attachment Menu**

Certain bots can be added directly to a user’s **attachment menu** – giving them easy access to the bot in any chat. Currently, this option is restricted to certain [approved bots](https://about/bots/webapps#launching-web-apps-from-the-attachment-menu), but may be expanded later.

> Try adding [@DurgerKingBot](https://t.me/durgerkingbot?startattach) to your attachment menu.

***

#### Integration

There are various ways of futher integrating bots with Telegram and other services.

* Use [Web Apps](broken-reference) to replace any website.
* Accept [Payments](broken-reference) via dozens of integrated third-party payment providers.
* Connect to Telegram using the [Web Login](broken-reference) functionality.
* Create gaming bots by integrating [HTML5 Games](broken-reference).
* Help users create and manage [Telegram Stickers](broken-reference).

#### Web Apps

Bots can easily process **complex inputs** of any kind and **dynamic interaction flows** via Web Apps. With this unique feature, you can develop any number of flexible, streamlined interfaces in **JavaScript**.

> Web Apps are covered in detail in our dedicated guide – you should read it carefully to learn the wide variety of features they can offer.

If you develop a **Web App**, be sure to follow our [design guidelines](about:blank/webapps#design-guidelines) – you'll want your custom interface to **seamlessly integrate** into the app to provide users the best possible experience.

#### Payments

Telegram bots can accept payments with a sleek, streamlined interface that collects all necessary data from the user. Telegram **doesn't collect** any payment data – like the user's credit card information – and sends it directly to one of the supported [payment providers](about:blank/payments#supported-payment-providers).

Here is a **quick start guide** to implement payments:

* Pick a [provider](about:blank/payments#supported-payment-providers) and obtain the [proper token](about:blank/payments#getting-a-token) as well as a **test token** from the "**Stripe TEST MODE**" provider.
* Implement payments via the [appropriate API methods](https://about/bots/api#payments).
* Test your implementation by using your **test token** along with a [test credit card](https://stripe.com/docs/testing#cards).

Then, to issue an **invoice** and process the order flow:

* [Send an invoice](https://about/bots/api#sendinvoice) to the user for the goods or services you are offering.
* Validate the order and accept the checkout via [answerPreCheckoutQuery](https://about/bots/api#answerprecheckoutquery).
* Confirm the payment by checking for a [successful payment service message](https://about/bots/api#successfulpayment).
* Ship the goods or provide the services.

A full and exhaustive guide, including live checklist, parameters and in-depth method descriptions is available here. We **strongly recommend** that you read the full guide before going live.



> Telegram does not directly process the payments, does not store data about orders and does not collect any fees. Invoices are forwarded directly to the payment provider.\
> For this reason, disputes must be solved between the user, the bot developer and the payment provider. You can read more about this in the [Privacy Policy](https://telegram.org/privacy#7-third-party-payment-services).

#### Web Login

Telegram offers a **flexible**, **lightweight** and **free** framework to authenticate users on any website and app. This can be used to bridge your platform with Telegram, providing a smooth experience to your users. You can also freely rely on this framework to implement a **fast** and **signup-free** login on your site, regardless of its connection to Telegram.

**Widgets**

The Telegram login widget is a **simple and secure way to authorize users** on your website.

1. Choose a bot – ideally its name and profile pic **should match** the website title and logo.
2. Use the `/setdomain` command in [@BotFather](https://t.me/botfather) to pair the bot with your website domain.
3. Configure your widget using [our dedicated tool](https://about/widgets/login#widget-configuration) and embed it on your website.

**Inline Login**

When users open your website via an **inline button**, you can use the [login\_url](https://about/bots/api#loginurl) parameter as an alternative to login widgets. This way, you'll be able to [seamlessly authorize](https://telegram.org/blog/privacy-discussions-web-bots#meet-seamless-web-bots) them on your website or app before the page even loads.



> Make sure to review our [guide](https://about/widgets/login#checking-authorization) on authenticating the received data as well as our [sample code](https://gist.github.com/anonymous/6516521b1fb3b464534fbc30ea3573c2).

#### HTML5 Games

Bots can serve as **standalone gaming platforms** – with our [HTML5 Gaming API](https://about/bots/api#games) you can develop multiplayer or single-player games and let your users have fun comparing **ranks**, **scores** and much more.

To get started, follow these simple steps:

* Send the `/newgame` command to [@BotFather](https://t.me/botfather)
* Provide a **description text**, an **image** or an **optional gif** to showcase its gameplay
* Send the game to users via the [sendGame](https://about/bots/api#sendgame) method or via an [inline query](https://about/bots/api#inlinequeryresultgame)
* When someone wants to play, you'll receive the appropriate `game_short_name` in a [CallbackQuery](https://about/bots/api#callbackquery)
* To launch the game, provide the **HTML5 Game URL** as the `url` param of [answerCallbackQuery](https://about/bots/api#answercallbackquery)

Then, to handle **highscores**:

* Use [setGameScore](https://about/bots/api#setgamescore) to post high scores in the chat with the game
* Use [getGameHighScores](https://about/bots/api#getgamehighscores) to get in-game high score tables

You can also **embed a share button** within your game, play around with **custom inline buttons**, **URL parameters** and much more. To get a better idea, make sure to check out:

* HTML5 Games Manual
* [HTML5 Games Bot API Docs](https://about/bots/api#games)



> Check out [@GameBot](https://t.me/gamebot) and [@gamee](https://t.me/gamee) for examples of what you can do using our Gaming Platform.

#### Stickers and Custom Emoji

[Stickers](https://core.telegram.org/stickers) and [Custom Emoji](https://telegram.org/blog/custom-emoji) are a distinctive Telegram feature used by millions of users to share artwork every day. Stickers and custom emoji take many forms – ranging from **basic images** to smooth **vector animations** and high-detail **.WEBM videos**.

All these formats are supported by our [Bot API](about:blank/api#stickers), which allows bots to **create**, **edit**, **delete** and **share** new artwork packs on the fly. Telegram's [Import API](https://core.telegram.org/import-stickers) lets users **migrate packs** from other platforms and sticker apps.

**Creating a new pack**\
To create a **new pack**, simply:

* **Prepare** your artwork following our [technical requirements](https://core.telegram.org/stickers).
* **Create** a new sticker pack via [createStickerSet](about:blank/api#createnewstickerset). Set `sticker_type` to _regular_ to create a sticker pack or to _custom emoji_ to create a pack of custom emoji. Attach the [files](about:blank/api#file) you wish to include in the pack as an array of [InputSticker](https://core.telegram.org/bots#inputsticker)
* You can use [addStickerToSet](about:blank/api#addstickertoset) to add stickers or emoji later on.

**Additional features**\
Regular stickers and custom emoji support **keywords** that users can type to quickly find the respective artwork – this can be useful when a sticker doesn't have obvious ties to a specific emoji. You can use the `keywords` parameter in [InputSticker](https://core.telegram.org/bots#inputsticker) to specify them.

Custom emoji additionally support **adaptive colors** – they will always match the current context (e.g., white on photos, accent color when used as status, etc.); to enable this feature, use the `needs_repainting` parameter in [createStickerSet](about:blank/api#createnewstickerset).

Once you're done creating and sharing your artwork, don't forget to check out our [remaining sticker methods](about:blank/api#stickers) to find out how to [edit](about:blank/api#setstickersetthumb), [delete](about:blank/api#deletestickerfromset) and even [reorder](about:blank/api#setstickerpositioninset) your pack.

> Note that these methods will only work on packs **created by the bot that is calling them**.

#### Language Support

Bots can tailor their interfaces to **support multiple languages** – updating inputs and information on the fly. A user’s [language\_code](https://about/bots/api#user) is included in every relevant [update](https://about/bots/api#update) as an [IETF language tag](https://en.wikipedia.org/wiki/IETF\_language\_tag), allowing bots to adapt accordingly.

We recommend that you follow our guidelines to provide **the best user experience**.

* Your interfaces, texts and [inline results](https://about/bots/api#answerinlinequery) should adapt seamlessly to the _language\_code_, without user intervention.
* Connected WebApps will receive the user's _language\_code_ – your HTML page should account for it.
* HTML5 Games can obtain language information if you specify it as a [URL parameter](https://about/bots/games#using-url-parameters). You can generate this parameter from the _language\_code_ field in the [User](https://about/bots/api#user) object served with the initial game [CallbackQuery](https://about/bots/api#callbackquery).
* The bot's **Name**, **Description** and **About text** can be natively localized with the respective [methods](https://core.telegram.org/bots/api#setmydescription).
* Command lists can also be specified for individual languages – more on this [here](broken-reference).

> The _language\_code_ is an **optional field** – it could be empty.\
> If you target the general public, your code should always fall back to either the last recorded language tag or English (in this order) when the field is missing for a specific user.

***

#### Bot Management

**Privacy Mode**

Bots are frequently added to groups to perform basic tasks or assist moderators – like automatically posting company announcements or even celebrating birthdays. By default, **all bots** added to groups run in Privacy Mode and only see relevant messages and commands:

* Commands explicitly meant for them (e.g., `/command@this_bot`).
* General commands (e.g. `/start`) if the bot was the last bot to send a message to the group.
* Inline messages sent [via](https://about/bots/api#inline-mode) the bot.
* Replies to any messages implicitly or explicitly meant for this bot.

All bots will also receive, **regardless of privacy mode**:

* All service messages.
* All messages from private chats.
* All messages from channels where they are a member.

Privacy mode is **enabled by default** for all bots, except bots that were added to a group as admins (bot admins always receive **all messages**). It can be disabled so that the bot receives all messages like an ordinary user (the bot will need to be re-added to the group for this change to take effect). We only recommend doing this in cases where it is **absolutely necessary** for your bot to work. In most cases, using the force reply option for the bot's messages should be more than enough.



> This mode not only increases user privacy, but also makes the bot more efficient by reducing the number of inputs it needs to process. Users can always see a bot’s current privacy setting in the list of group members.

#### Testing your bot

You can quickly test your bot **without interfering** with its users by simply running another instance of your code on a different bot account. To do so, create a _new bot_ via [@BotFather](https://t.me/botfather), obtain its token and use it in the testing instance of your code.

All further testing and debugging can happen privately on the new bot, without affecting the original instance.

> If you need to share file references across bots, note that the `file_id` field is tied to a single bot id, so your test instance cannot use a shared `file_id` database to quickly send media – files must be individually reuploaded.

**Dedicated test environment**

Telegram also offers a dedicated **test environment** suitable for more advanced testing. Bots and users in this environment generally have more flexible restrictions – for example:

* When working with the test environment, you may use HTTP links without TLS to test your [Web Apps](broken-reference) or [Web Login](broken-reference).

> **Flood limits** are not raised in the test environment, and may at times be stricter. To minimize how this impacts your bot, you should make sure that it handles errors with retry policies and does not depend on hardcoded limit values.

**Creating a bot in the test environment**

The test environment is **completely separate** from the main environment, so you will need to create a new user account and a new bot with [@BotFather](https://t.me/botfather).

To create an account and log in, use either of the following:

* **iOS**: tap 10 times on the Settings icon > Accounts > Login to another account > Test.
* **Telegram Desktop**: open ☰ Settings > Shift + Alt + Right click 'Add Account' and select 'Test Server'.
* **macOS**: click the Settings icon 10 times to open the Debug Menu, ⌘ + click 'Add Account' and log in via phone number.

After logging in, simply [create a new bot](broken-reference) following the standard procedure and send your requests to the Test Bot API in this format:

```
https://api.telegram.org/bot<token>/test/METHOD_NAME
```

> When working with the test environment, you may use HTTP links without TLS in the `url` field of both [LoginUrl](https://about/bots/api#loginurl) and [WebAppInfo](https://about/bots/api#webappinfo).

**Status alerts**

Millions choose Telegram for its speed. To best benefit users, your bot also **needs to be responsive**. In order to help developers keep their bots in shape, [@BotFather](https://t.me/botfather) will send **status alerts** if it sees something is wrong.

We check the number of replies and the _request/response_ conversion rate for popular bots (\~300 requests per minute, this value may change in the future). If your bot returns an **abnormally low number**, you will receive a notification from [@BotFather](https://t.me/botfather).

**Responding to alerts**

By default, **you will only get one alert per bot per hour**.

Each alert has the following buttons:

* **Fixed** - Use this if you found an issue with your bot and fixed it. If you press the fix button, we will resume sending alerts in the regular way so that you can see if your fix worked within 5-10 minutes instead of having to wait for an hour.
* **Support** - Use this to open a chat with [@BotSupport](https://t.me/botsupport) if you don't see any issues with your bot or if you think the problem is on our side.
* **Mute for 8h/1w** - Use this if you can't fix your bot at the moment. This will disable all alerts for the bot in question for the specified period of time. **We do not recommend** using this option since your users may migrate to a more stable bot. You can unmute alerts in your bot's settings via [@BotFather](https://t.me/botfather).

**Monitored issues**

We currently notify you about the following issues:

* **Too few private messages are sent.** Value: **{value}** - Your bot is sending far fewer messages than it did in previous weeks. This is useful for newsletter-style bots that send messages without prompts from users. The larger the value, the more significant the difference.
* **Too few replies to incoming private messages**. Conversion rate: **{value}** - Your bot is not replying to all messages that are being sent to it (the request/response conversion rate for your bot was too low for at least two of the last three 5-minute periods).

> To provide a good user experience, please respond to all messages that are sent to your bot. Respond to message updates by calling send… methods (e.g. [sendMessage](https://about/bots/api#sendmessage)).

* **Too few answers to inline queries**. Conversion rate: **{value}** - Your bot is not replying to all inline queries that are being sent to it, calculated in the same way as above. Respond to `inline_query` updates by calling [answerInlineQuery](https://about/bots/api#answerinlinequery).
* **Too few answers to callback queries**. Conversion rate: **{value}**
* **Too few answers to callback game queries**. Conversion rate: **{value}** - Your bot is not replying to all callback queries that are being sent to it (with or without games), calculated in the same way as above. Respond to `callback_query` updates by calling [answerCallbackQuery](https://about/bots/api#answercallbackquery).

**Local Bot API**

You can host and work with **your own instance** of our open-source Bot API.\
The **source code** is available [here](https://github.com/tdlib/telegram-bot-api), along with a quick [installation guide](https://github.com/tdlib/telegram-bot-api#installation).

After **installing the server**, remember to use the [logOut](https://about/bots/api#logout) method before **redirecting requests** to your new local API URL.

> Your local instance runs on port `8081` by default and will only accept HTTP requests, so a TLS termination proxy has to be used to handle remote HTTPS requests.

By hosting our API locally you'll gain access to **some upgrades**, including:

| API                                                          | Max File Download | Max File Upload | WHook URL | WHook Port     | WHook Max Connections |
| ------------------------------------------------------------ | ----------------- | --------------- | --------- | -------------- | --------------------- |
| [Official](https://about/bots/api#making-requests)           | 20MB              | 50MB            | HTTPS     | 443,80,88,8443 | 1-100                 |
| [Local](https://about/bots/api#using-a-local-bot-api-server) | Unlimited         | 2000MB          | HTTP      | Any port       | 1-100000              |

> You can find an exhaustive list [here](https://about/bots/api#using-a-local-bot-api-server).\
> All limits may be subject to change in the future, so make sure to follow [@BotNews](https://t.me/botnews).

***

#### BotFather

Below is a detailed guide to using [@BotFather](https://t.me/botfather), Telegram’s tool for **creating** and **managing** bots.

**Creating a new bot**

Use the `/newbot` command to create a new bot. [@BotFather](https://t.me/botfather) will ask you for a name and username, then generate an authentication token for your new bot.

* The **name** of your bot is displayed in contact details and elsewhere.
* The **username** is a short name, used in search, mentions and t.me links. Usernames are 5-32 characters long and not case sensitive – but may only include Latin characters, numbers, and underscores. Your bot's username must end in 'bot’, like 'tetris\_bot' or 'TetrisBot'.
* The **token** is a string, like `110201543:AAHdqTcvCH1vGWJxfSeofSAs0K5PALDsaw`, which is required to authorize the bot and send requests to the Bot API. Keep your token secure and store it safely, it can be used by anyone to control your bot.

> Unlike the bot’s name, the username cannot be changed later – so choose it carefully.\
> When sending a request to api.telegram.org, remember to prefix the word ‘bot’ to your token.

**About text, description and profile media**

When new users open your bot, they will be met with a helpful description in a box titled “What can this bot do?”.

Properly [setting this field](broken-reference) in [@BotFather](https://t.me/botfather) allows everyone to immediately get an idea of what your bot can do – your description should be **brief**, **to the point** and **on topic**.

> You can also add a photo or video to this field with `Edit Description Picture` in [@BotFather](https://t.me/botfather).

Additionally, just like normal users, bots also come with a **short bio** available on their profile. If you didn't specify this field while first creating your bot, you can set it at any time with the `/setabouttext` command in [@BotFather](https://t.me/botfather). Users can interact with many bots and they won't have access to their description after starting them – having a quick reminder of the bot's purpose can be very useful.

> Note that both the **Description** and the **About text** can be [natively localized](https://core.telegram.org/bots/api#setmydescription) – each user will automatically see the correct translation for their language.

Bots can also have a **profile picture** – you should pick something unique and original so that users can find it in their chat list at a glance.

> Starting from April 21, 2023 ([Telegram 9.6](https://telegram.org/blog/shareable-folders-custom-wallpapers)), you can edit your bot directly from its profile page – including setting a custom **profile video**.

**Generating an authentication token**

If your existing token is **compromised** or **you lost it** for some reason, use the `/token` command to generate a new one.

**Transfer ownership**

You can transfer ownership of your bot **to another user**.\
To do this, send `/mybots`, select your bot, then _transfer ownership_.\
You can only transfer a bot to users who have interacted with it at least once.

> Transferring ownership will give full control of the bot to another user – they will be able to access the bot’s messages and even delete it. The transfer is permanent, so please consider it carefully.

**BotFather commands**

The remaining commands are pretty self-explanatory:

* /mybots – returns a list of your bots with handy controls to edit their settings.
* /mygames – does the same for your games.

**Edit bots**

To edit your bot, you have two options.

You can use the available commands:

* /setname – change your bot's **name**.
* /setdescription – change the bot's **description** (short text up to 512 characters). Users will see this text at the beginning of the conversation with the bot, titled '_What can this bot do?_'.
* /setabouttext – change the bot's **about info**, a shorter text up to 120 characters. Users will see this text on the bot's profile page. When they share your bot with someone, this text is sent together with the link.
* /setuserpic – change the bot's **profile picture**.
* /setcommands – change the list of **commands** supported by your bot. Users will see these commands as suggestions when they type `/` in the chat with your bot. See [commands](broken-reference) for more info.
* /setdomain – link a **website domain** to your bot. See the [login widget](broken-reference) section.
* /deletebot – delete your bot and **free its username**. Cannot be undone.

Or you can use the `/mybots` command, tap on your bot and use the modern inline interface to edit it.

> Starting from April 21, 2023 ([Telegram 9.6](https://telegram.org/blog/shareable-folders-custom-wallpapers)), you can edit your bot's public-facing info directly from its profile page – including setting a custom **profile video**.

**Edit settings**

* /setinline – toggle **inline mode** for your bot.
* /setinlinegeo – request **location data** to provide location-based inline results.
* /setjoingroups – toggle whether your bot can be **added to groups** or not. All bots must be able to process direct messages, but if your bot was not designed to work in groups, you can disable this.
* /setinlinefeedback – toggle whether the API should **send updates about the results** chosen by users. See an in-depth explanation [here](https://about/bots/inline#collecting-feedback).
* /setprivacy – set which messages your bot will receive when added to a group. See [privacy-mode](broken-reference) for more info.

**Manage games**

* /newgame – create a new game.
* /listgames – see a list of your games.
* /editgame – edit a game.
* /deletegame – delete an existing game.

> Please note that it may take a few minutes for changes to take effect.

***

With this information, you are ready to proceed to our Full API Reference for Developers.

* If you have any questions, check out our Bot FAQ.
* If you're experiencing issues with our API, please contact [@BotSupport](https://t.me/botsupport) on Telegram.
