# Inline

## Inline Bots <a href="#dev_page_title" id="dev_page_title"></a>

Beyond sending commands in private messages or groups, users can interact with your bot via [**inline queries**](https://about/bots/api#inline-mode). If inline queries are enabled, users can call your bot by typing its username and a query in the **text input field** in **any** chat. The query is sent to your bot in an update. This way, people can request content from your bot in **any** of their chats, groups, or channels without sending any messages at all.

\


To enable this option, send the `/setinline` command to [@BotFather](https://telegram.me/botfather) and provide the placeholder text that the user will see in the input field after typing your bot’s name.

> See the [Bot API Manual](https://about/bots/api#inline-mode) for the relevant methods and objects.

#### Inline results

Inline bots support **all types of content** available in Telegram (20 in all). They are capable of sending stickers, videos, music, locations, documents and more.

\


Clients can display the results with vertical or horizontal scrolling, depending on the type of content:

As soon as the user taps on an item, it's immediately sent to the recipient, and the input field is cleared.

#### Switching inline/PM modes

Some inline bots can benefit from an initial setup process, like connecting them to an account on an external service (e.g., YouTube). We've added an easy way of switching between the private chat with a bot and whatever chat the user wants to share inline results in.

\


You can display a special 'Switch to PM' button above the inline results (or instead of them). This button will open a private chat with the bot and pass a parameter of your choosing, so that you can prompt the user for the relevant setup actions. Once done, you can use an inline keyboard with a [_switch\_inline\_query_](https://about/bots/api#inlinekeyboardmarkup) button to send the user back to the original chat.

**Sample bots**\
[@youtube](https://telegram.me/youtube) – Shows a 'Sign in to YouTube' button, then suggests personalized results.

> [Manual: Switch to PM](https://about/bots/api#answerinlinequery)

#### Location-based results

Inline bots can request location data from their users. Use the `/setinlinegeo` command with [@BotFather](https://telegram.me/botfather) to enable this. Your bot will ask the user for permission to access their location whenever they send an inline request.

**Sample bot**\
[@foursquare](https://telegram.me/foursquare) – This bot will ask for permission to access the user's location, then provide geo-targeted results.

#### Spreading virally

Messages sent with the help of your bot will show its username next to the sender's name.

&#x20;

When a user taps on the bot username in the message header, the mention is automatically inserted into the input field. Entering the `@` symbol in the input field brings up a list of suggestions, featuring recently used inline bots.

**Collecting feedback**

To know which of the provided results your users are sending to their chat partners, send [@Botfather](https://telegram.me/botfather) the `/setinlinefeedback` command. With this enabled, you will receive updates on the results chosen by your users.

Please note that this can create load issues for popular bots – you may receive more results than actual requests due to caching (see the _cache\_time_ parameter in [answerInlineQuery](https://about/bots/api#answerinlinequery)). For these cases, we recommend adjusting the probability setting to receive 1/10, 1/100 or 1/1000 of the results.

#### Inline bot samples

Here are some sample inline bots, in case you’re curious to see one in action. Try any of these:\
[@gif](https://telegram.me/gif) – GIF search\
[@vid](https://telegram.me/vid) – Video search\
[@pic](https://telegram.me/pic) – Yandex image search\
[@bing](https://telegram.me/bing) – Bing image search\
[@wiki](https://telegram.me/wiki) – Wikipedia search\
[@imdb](https://telegram.me/imdb) – IMDB search\
[@bold](https://telegram.me/bold) – Make bold, italic or fixed sys text

**NEW**\
[@youtube](https://telegram.me/youtube) - Connect your account for personalized results\
[@music](https://telegram.me/music) - Search and send classical music\
[@foursquare](https://telegram.me/foursquare) – Find and send venue addresses\
[@sticker](https://telegram.me/sticker) – Find and send stickers based on emoji
