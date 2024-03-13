# Bots

## Bots: An introduction for developers

Bots are **small applications** that run entirely within the Telegram app. Users interact with bots through **flexible interfaces** that can support **any kind of task or service**. For more information, see:

* [Detailed Guide to Bot Features](https://core.telegram.org/bots/features)
* [Full API Reference for Developers](https://core.telegram.org/bots/api)
* [Basic Tutorial: From @BotFather to 'Hello World'](https://core.telegram.org/bots/tutorial)

The **Telegram Bot Platform** hosts more than **10 million** bots and is **free** for both users and developers.

## What Can You Do with Bots?

* [Replace Entire Websites](https://github.com/Xavier186/ton\_docs\_cn/blob/main/develop/telegram/readme/README.md#dai-ti-replace-entire-websites66-zheng-ge-wang-zhan-66)
* [Receive Payments](https://github.com/Xavier186/ton\_docs\_cn/blob/main/develop/telegram/readme/README.md)
* [Create Custom Tools](https://github.com/Xavier186/ton\_docs\_cn/blob/main/develop/telegram/readme/README.md#create-custom-tools)
* [Integrate with Other Services](./#integrate-with-other-services)
* [Host Games](./#host-games)
* [Build Social Networks](./#build-social-networks)
* [Anything Else!](./#anything-else)

### 代替(Replace Entire Websites66)整个网站66

Telegram bots can host [Mini Apps](https://core.telegram.org/bots/webapps) built with _JavaScript_. This allows for **infinitely flexible** interfaces that can power everything from online stores to arcade games. Unlike websites, bots support [seamless authorization](https://core.telegram.org/api/url-authorization) and notifications through Telegram out of the box.

> Try [@DurgerKingBot](https://t.me/durgerkingbot) – or check out the [dedicated guide to Web Apps](https://core.telegram.org/bots/webapps) to build your own.

### **Receive Payments**

Bots can [receive payments](https://core.telegram.org/bots/payments) from more than **200 countries** through more than **20** integrated payment providers (which include support for _Apple Pay_ and _Google Pay_). These payments are securely processed by the providers and Telegram takes no commission.

> Try [@ShopBot](https://t.me/shopbot) – or check out the [Bot Payments Manual](https://core.telegram.org/bots/payments) to build your own.

### **Create Custom Tools**

Increase your productivity by creating bots for **specific tasks** – like converting files, managing chats or fetching today’s forecast. Users can chat directly with bots, or add them to groups and channels to introduce extra features.

> Try [@QuizBot](https://t.me/quizbot) to combine several quiz-style polls into a [proper quiz](https://telegram.org/tour/quizbot).

### **Integrate with Other Services**

Many popular platforms already have official Telegram bots, which allow users to comfortably access content in one app – or perform quick searches using [inline mode](https://core.telegram.org/bots/inline).

> Try [@GMailBot](https://t.me/gmailbot), [@GitHubBot](https://t.me/githubbot), [@Bing](https://t.me/bing), [@YouTube](https://t.me/youtube), [@wiki](https://t.me/wiki) and more.

### **Host Games**

Using [HTML5](https://core.telegram.org/bots/games), developers can create immersive single or multi-player games that allow users to **team up** or **compete** for the highest score.

> Try [@Gamee](https://t.me/gamee) and [@GameBot](https://t.me/gamebot) – or check out the [HTML5 Games Manual](https://core.telegram.org/bots/games) to build your own.

### **Build Social Networks**

Bots can serve as an intermediary to connect users based on shared interests, location, and more. Coordinate meetups, show local services, or help people sell second-hand items.

### **Anything Else**

The possibilities for bots are endless – from simple scripts to complex mini apps. Whether you’re a beginner or professional programmer, you can create personalized tools with the help of the [Bot Platform](https://core.telegram.org/bots/api).

***

## How Do Bots Work?

> For a detailed explanation of Bot Features, see [this guide](https://core.telegram.org/bots/features)

Telegram bots are special accounts that do not need a phone number to set up. Bots are connected to their owner’s server, which processes inputs and requests from users.

Telegram’s intermediary server handles all encryption and communication with the Telegram API. Developers communicate with this server via an easy HTTPS-interface with a simplified version of the [Telegram API](https://core.telegram.org/api) – known as the [Bot API](https://core.telegram.org/bots/api).

### **How Are Bots Different from Users?**

Bots are able to process inputs and requests in ways that user accounts can’t, but there are several differences between a bot and a normal user.

* Bots don’t have ‘last seen’ or online statuses – instead they show a ‘bot’ label in the chat.
* Bots have limited cloud storage – older messages may be removed by the server shortly after they have been processed.
* Bots can't start conversations with users. A user must either add them to a group or send them a message first. People can search for your bot’s username or start a chat via its unique t.me/bot\_username link.
* By default, bots added to groups **only see relevant messages** in the chat (see [Privacy Mode](https://core.telegram.org/bots/features#privacy-mode)).
* Bots never eat, sleep or complain (unless expressly programmed otherwise).

### **Bot Links**

Bot usernames normally require a ‘bot’ suffix, but some bots don’t have them – such as [@stickers](https://t.me/stickers), [@gif](https://t.me/gif), [@wiki](https://t.me/wiki) or [@bing](https://t.me/bing).

Anyone can [assign collectible usernames](https://telegram.org/blog/shareable-folders-custom-wallpapers#bot-links-and-telegram-premium-on-fragment) to bots, including those without the 'bot' suffix.

## How Do I Create a Bot?

Creating Telegram bots is super-easy, but you will need at least some skills in **computer programming**.

Creating a bot is streamlined by Telegram’s Bot API, which gives the tools and framework required to integrate your code. To get started, message [@BotFather](https://t.me/botfather) on Telegram to register your bot and receive its authentication token.

> Your **bot token** is its unique identifier – store it in a **secure place**, and only share it with people who need direct access to the bot. Everyone who has your token will have **full control** over your bot.

### **What Next?**

We recommend that you check out our guide to Bot Features to see what you can teach your bot to do:

* [Detailed Guide to Bot Features](https://core.telegram.org/bots/features)
* [Full API Reference for Developers](https://core.telegram.org/bots/api)
* [Basic Tutorial: From @BotFather to 'Hello World'](https://core.telegram.org/bots/tutorial)
* [Code Examples](https://core.telegram.org/bots/samples)
