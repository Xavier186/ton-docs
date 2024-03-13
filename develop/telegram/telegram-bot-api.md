# Telegram Bot API

Telegram Bot API

> The Bot API is an HTTP-based interface created for developers keen on building bots for Telegram.\
> To learn how to create and set up a bot, please consult our **Introduction to Bots** and **Bot FAQ**.

#### Recent changes

> Subscribe to [@BotNews](https://t.me/botnews) to be the first to know about the latest updates and join the discussion in [@BotTalk](https://t.me/bottalk)

**February 16, 2024**

**Bot API 7.1**

* Added support for the administrator rights _can\_post\_stories_, _can\_edit\_stories_, _can\_delete\_stories_ in supergroups.
* Added the class [ChatBoostAdded](broken-reference) and the field _boost\_added_ to the class [Message](broken-reference) for service messages about a user boosting a chat.
* Added the field _sender\_boost\_count_ to the class [Message](broken-reference).
* Added the field _reply\_to\_story_ to the class [Message](broken-reference).
* Added the fields _chat_ and _id_ to the class [Story](broken-reference).
* Added the field _unrestrict\_boost\_count_ to the class [Chat](broken-reference).
* Added the field _custom\_emoji\_sticker\_set\_name_ to the class [Chat](broken-reference).

**December 29, 2023**

**Bot API 7.0**

**Reactions**

* Added the classes [ReactionTypeEmoji](broken-reference) and [ReactionTypeCustomEmoji](broken-reference) representing different types of reaction.
* Added updates about a reaction change on a message with non-anonymous reactions, represented by the class [MessageReactionUpdated](broken-reference) and the field _message\_reaction_ in the class [Update](broken-reference). The bot must explicitly allow the update to receive it.
* Added updates about reaction changes on a message with anonymous reactions, represented by the class [MessageReactionCountUpdated](broken-reference) and the field _message\_reaction\_count_ in the class [Update](broken-reference). The bot must explicitly allow the update to receive it.
* Added the method [setMessageReaction](broken-reference) that allows bots to react to messages.
* Added the field _available\_reactions_ to the class [Chat](broken-reference).

**Replies 2.0**

* Added the ability to reply to messages in other chats or forum topics.
* Added the class [ExternalReplyInfo](broken-reference) and the field _external\_reply_ of type [ExternalReplyInfo](broken-reference) to the class [Message](broken-reference), containing information about a message that is replied to by the current message, but can be from another chat or forum topic.
* Added the ability to quote a part of the replied message.
* Added the class [TextQuote](broken-reference) and the field _quote_ of type [TextQuote](broken-reference) to the class _Message_, which contains the part of the replied message text or caption that is quoted in the current message.
* Added the class [ReplyParameters](broken-reference) and replaced parameters _reply\_to\_message\_id_ and _allow\_sending\_without\_reply_ in the methods [copyMessage](broken-reference), [sendMessage](broken-reference), [sendPhoto](broken-reference), [sendVideo](broken-reference), [sendAnimation](broken-reference), [sendAudio](broken-reference), [sendDocument](broken-reference), [sendSticker](broken-reference), [sendVideoNote](broken-reference), [sendVoice](broken-reference), [sendLocation](broken-reference), [sendVenue](broken-reference), [sendContact](broken-reference), [sendPoll](broken-reference), [sendDice](broken-reference), [sendInvoice](broken-reference), [sendGame](broken-reference), and [sendMediaGroup](broken-reference) with the field _reply\_parameters_ of type [ReplyParameters](broken-reference).

**Link Preview Customization**

* Allowed to explicitly specify the URL that will be used for link preview generation in outgoing text messages.
* Allowed to position link previews above the message text.
* Allowed to choose media size in link previews.
* Added the class [LinkPreviewOptions](broken-reference) and replaced the parameter _disable\_web\_page\_preview_ with _link\_preview\_options_ in the methods [sendMessage](broken-reference) and [editMessageText](broken-reference).
* Replaced the field _disable\_web\_page\_preview_ with _link\_preview\_options_ in the class [InputTextMessageContent](broken-reference).
* Added the field _link\_preview\_options_ to the class [Message](broken-reference) with information about the link preview options used to send the message.

**Block Quotation**

* Added support for “blockquote” entities in received messages.
* Added support for “blockquote” entity parsing in “MarkdownV2” and “HTML” parse modes.
* Allowed to explicitly specify “blockquote” entities in formatted texts.

**Multiple Message Actions**

* Added the method [deleteMessages](broken-reference) to allow the deletion of multiple messages in a single request.
* Added the method [forwardMessages](broken-reference) for forwarding of multiple messages in a single request.
* Added the method [copyMessages](broken-reference) for copying of multiple messages in a single request.

**Request for multiple users**

* Renamed the class _KeyboardButtonRequestUser_ to [KeyboardButtonRequestUsers](broken-reference) and added the field _max\_quantity_ to it.
* Renamed the field _request\_user_ in the class [KeyboardButton](broken-reference) to _request\_users_. The old name will still work for backward compatibility.
* Added the class [UsersShared](broken-reference).
* Replaced the field _user\_shared_ in the class [Message](broken-reference) with the field _users\_shared_.

**Chat Boost**

* Added updates about chat boost changes, represented by the classes [ChatBoostUpdated](broken-reference) and [ChatBoostRemoved](broken-reference) and the fields _chat\_boost_ and _removed\_chat\_boost_ in the class [Update](broken-reference). The bot must be an administrator in the chat to receive these updates.
* Added the classes [ChatBoostSourcePremium](broken-reference), [ChatBoostSourceGiftCode](broken-reference) and [ChatBoostSourceGiveaway](broken-reference), representing different sources of a chat boost.
* Added the method [getUserChatBoosts](broken-reference) for obtaining the list of all active boosts a user has contributed to a chat.

**Giveaway**

* Added the class [Giveaway](broken-reference) and the field _giveaway_ to the class [Message](broken-reference) for messages about scheduled giveaways.
* Added the class [GiveawayCreated](broken-reference) and the field _giveaway\_created_ to the class [Message](broken-reference) for service messages about the creation of a scheduled giveaway.
* Added the class [GiveawayWinners](broken-reference) and the field _giveaway\_winners_ to the class [Message](broken-reference) for messages about the completion of a giveaway with public winners.
* Added the class [GiveawayCompleted](broken-reference) and the field _giveaway\_completed_ to the class [Message](broken-reference) for service messages about the completion of a giveaway without public winners.

**Web App Changes**

* Added the field _SettingsButton_ to the class [WebApp](https://about/bots/webapps#initializing-mini-apps).
* Added the fields _header\_bg\_color_, _accent\_text\_color_, _section\_bg\_color_, _section\_header\_text\_color_, _subtitle\_text\_color_, _destructive\_text\_color_ to the class [ThemeParams](https://about/bots/webapps#themeparams).
* Web Apps no longer close when the method _WebApp.openTelegramLink_ is called.

**Other Changes**

* Added support for the fields _emoji\_status\_custom\_emoji\_id_ and _emoji\_status\_expiration\_date_ in the class [Chat](broken-reference) for non-private chats.
* Added the fields _accent\_color\_id_, _background\_custom\_emoji\_id_, _profile\_accent\_color\_id_, and _profile\_background\_custom\_emoji\_id_ to the class [Chat](broken-reference).
* Added the field _has\_visible\_history_ to the class [Chat](broken-reference).
* Added the class [MessageOrigin](broken-reference) and replaced the fields _forward\_from_, _forward\_from\_chat_, _forward\_from\_message\_id_, _forward\_signature_, _forward\_sender\_name_, and _forward\_date_ with the field _forward\_origin_ of type [MessageOrigin](broken-reference) in the class [Message](broken-reference).
* Improved documentation for the field _message_ of the class [callbackQuery](broken-reference) and the field _pinned\_message_ of the class [Message](broken-reference) by adding the classes [MaybeInaccessibleMessage](broken-reference) and [InaccessibleMessage](broken-reference).

**September 22, 2023**

**Bot API 6.9**

* Added the new administrator privileges _can\_post\_stories_, _can\_edit\_stories_ and _can\_delete\_stories_ to the classes [ChatMemberAdministrator](broken-reference) and [ChatAdministratorRights](broken-reference).
* Added the parameters _can\_post\_stories_, _can\_edit\_stories_ and _can\_delete\_stories_ to the method [promoteChatMember](broken-reference). Currently, bots have no use for these privileges besides assigning them to other administrators.
* Added the ability to set any header color for Web App using the method _setHeaderColor_.
* Added the field _CloudStorage_ to the class [WebApp](https://about/bots/webapps#initializing-mini-apps).
* Added the methods _requestWriteAccess_ and _requestContact_ to the class [WebApp](https://about/bots/webapps#initializing-mini-apps).
* Added Web App events _writeAccessRequested_ and _contactRequested_.
* Added the fields _from\_request_ and _from\_attachment\_menu_ to the class [WriteAccessAllowed](broken-reference).
* Added the fields _added\_to\_attachment\_menu_ and _allows\_write\_to\_pm_ to the class [WebAppUser](https://about/bots/webapps#webappuser).

[**See earlier changes »**](<.gitbook/assets/api changelog>)

#### Authorizing your bot

Each bot is given a unique authentication token [when it is created](https://about/bots/features#botfather). The token looks something like `123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11`, but we'll use simply **\<token>** in this document instead. You can learn about obtaining tokens and generating new ones in [this document](https://about/bots/features#botfather).

#### Making requests

All queries to the Telegram Bot API must be served over HTTPS and need to be presented in this form: `https://api.telegram.org/bot<token>/METHOD_NAME`. Like this for example:

```
https://api.telegram.org/bot123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11/getMe
```

We support **GET** and **POST** HTTP methods. We support four ways of passing parameters in Bot API requests:

* [URL query string](https://en.wikipedia.org/wiki/Query\_string)
* application/x-www-form-urlencoded
* application/json (except for uploading files)
* multipart/form-data (use to upload files)

The response contains a JSON object, which always has a Boolean field 'ok' and may have an optional String field 'description' with a human-readable description of the result. If 'ok' equals _True_, the request was successful and the result of the query can be found in the 'result' field. In case of an unsuccessful request, 'ok' equals false and the error is explained in the 'description'. An Integer 'error\_code' field is also returned, but its contents are subject to change in the future. Some errors may also have an optional field 'parameters' of the type [ResponseParameters](broken-reference), which can help to automatically handle the error.

* All methods in the Bot API are case-insensitive.
* All queries must be made using UTF-8.

**Making requests when getting updates**

If you're using [**webhooks**](broken-reference), you can perform a request to the Bot API while sending an answer to the webhook. Use either _application/json_ or _application/x-www-form-urlencoded_ or _multipart/form-data_ response content type for passing parameters. Specify the method to be invoked in the _method_ parameter of the request. It's not possible to know that such a request was successful or get its result.

> Please see our [FAQ](https://about/bots/faq#how-can-i-make-requests-in-response-to-updates) for examples.

#### Using a Local Bot API Server

The Bot API server source code is available at [telegram-bot-api](https://github.com/tdlib/telegram-bot-api). You can run it locally and send the requests to your own server instead of `https://api.telegram.org`. If you switch to a local Bot API server, your bot will be able to:

* Download files without a size limit.
* Upload files up to 2000 MB.
* Upload files using their local path and [the file URI scheme](https://en.wikipedia.org/wiki/File\_URI\_scheme).
* Use an HTTP URL for the webhook.
* Use any local IP address for the webhook.
* Use any port for the webhook.
* Set _max\_webhook\_connections_ up to 100000.
* Receive the absolute local path as a value of the _file\_path_ field without the need to download the file after a [getFile](broken-reference) request.

**Do I need a Local Bot API Server**

The majority of bots will be OK with the default configuration, running on our servers. But if you feel that you need one of [these features](broken-reference), you're welcome to switch to your own at any time.

#### Getting updates

There are two mutually exclusive ways of receiving updates for your bot - the [getUpdates](broken-reference) method on one hand and [webhooks](broken-reference) on the other. Incoming updates are stored on the server until the bot receives them either way, but they will not be kept longer than 24 hours.

Regardless of which option you choose, you will receive JSON-serialized [Update](broken-reference) objects as a result.

**Update**

This [object](broken-reference) represents an incoming update.\
At most **one** of the optional parameters can be present in any given update.

| Field                    | Type                                            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------ | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| update\_id               | Integer                                         | The update's unique identifier. Update identifiers start from a certain positive number and increase sequentially. This identifier becomes especially handy if you're using [webhooks](broken-reference), since it allows you to ignore repeated updates or to restore the correct update sequence, should they get out of order. If there are no new updates for at least a week, then identifier of the next update will be chosen randomly instead of sequentially. |
| message                  | [Message](broken-reference)                     | _Optional_. New incoming message of any kind - text, photo, sticker, etc.                                                                                                                                                                                                                                                                                                                                                                                              |
| edited\_message          | [Message](broken-reference)                     | _Optional_. New version of a message that is known to the bot and was edited. This update may at times be triggered by changes to message fields that are either unavailable or not actively used by your bot.                                                                                                                                                                                                                                                         |
| channel\_post            | [Message](broken-reference)                     | _Optional_. New incoming channel post of any kind - text, photo, sticker, etc.                                                                                                                                                                                                                                                                                                                                                                                         |
| edited\_channel\_post    | [Message](broken-reference)                     | _Optional_. New version of a channel post that is known to the bot and was edited. This update may at times be triggered by changes to message fields that are either unavailable or not actively used by your bot.                                                                                                                                                                                                                                                    |
| message\_reaction        | [MessageReactionUpdated](broken-reference)      | _Optional_. A reaction to a message was changed by a user. The bot must be an administrator in the chat and must explicitly specify `"message_reaction"` in the list of _allowed\_updates_ to receive these updates. The update isn't received for reactions set by bots.                                                                                                                                                                                              |
| message\_reaction\_count | [MessageReactionCountUpdated](broken-reference) | _Optional_. Reactions to a message with anonymous reactions were changed. The bot must be an administrator in the chat and must explicitly specify `"message_reaction_count"` in the list of _allowed\_updates_ to receive these updates. The updates are grouped and can be sent with delay up to a few minutes.                                                                                                                                                      |
| inline\_query            | [InlineQuery](broken-reference)                 | _Optional_. New incoming [inline](broken-reference) query                                                                                                                                                                                                                                                                                                                                                                                                              |
| chosen\_inline\_result   | [ChosenInlineResult](broken-reference)          | _Optional_. The result of an [inline](broken-reference) query that was chosen by a user and sent to their chat partner. Please see our documentation on the [feedback collecting](https://about/bots/inline#collecting-feedback) for details on how to enable these updates for your bot.                                                                                                                                                                              |
| callback\_query          | [CallbackQuery](broken-reference)               | _Optional_. New incoming callback query                                                                                                                                                                                                                                                                                                                                                                                                                                |
| shipping\_query          | [ShippingQuery](broken-reference)               | _Optional_. New incoming shipping query. Only for invoices with flexible price                                                                                                                                                                                                                                                                                                                                                                                         |
| pre\_checkout\_query     | [PreCheckoutQuery](broken-reference)            | _Optional_. New incoming pre-checkout query. Contains full information about checkout                                                                                                                                                                                                                                                                                                                                                                                  |
| poll                     | [Poll](broken-reference)                        | _Optional_. New poll state. Bots receive only updates about manually stopped polls and polls, which are sent by the bot                                                                                                                                                                                                                                                                                                                                                |
| poll\_answer             | [PollAnswer](broken-reference)                  | _Optional_. A user changed their answer in a non-anonymous poll. Bots receive new votes only in polls that were sent by the bot itself.                                                                                                                                                                                                                                                                                                                                |
| my\_chat\_member         | [ChatMemberUpdated](broken-reference)           | _Optional_. The bot's chat member status was updated in a chat. For private chats, this update is received only when the bot is blocked or unblocked by the user.                                                                                                                                                                                                                                                                                                      |
| chat\_member             | [ChatMemberUpdated](broken-reference)           | _Optional_. A chat member's status was updated in a chat. The bot must be an administrator in the chat and must explicitly specify `"chat_member"` in the list of _allowed\_updates_ to receive these updates.                                                                                                                                                                                                                                                         |
| chat\_join\_request      | [ChatJoinRequest](broken-reference)             | _Optional_. A request to join the chat has been sent. The bot must have the _can\_invite\_users_ administrator right in the chat to receive these updates.                                                                                                                                                                                                                                                                                                             |
| chat\_boost              | [ChatBoostUpdated](broken-reference)            | _Optional_. A chat boost was added or changed. The bot must be an administrator in the chat to receive these updates.                                                                                                                                                                                                                                                                                                                                                  |
| removed\_chat\_boost     | [ChatBoostRemoved](broken-reference)            | _Optional_. A boost was removed from a chat. The bot must be an administrator in the chat to receive these updates.                                                                                                                                                                                                                                                                                                                                                    |

**getUpdates**

Use this method to receive incoming updates using long polling ([wiki](https://en.wikipedia.org/wiki/Push\_technology#Long\_polling)). Returns an Array of [Update](broken-reference) objects.

| Parameter        | Type            | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ---------------- | --------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| offset           | Integer         | Optional | Identifier of the first update to be returned. Must be greater by one than the highest among the identifiers of previously received updates. By default, updates starting with the earliest unconfirmed update are returned. An update is considered confirmed as soon as [getUpdates](broken-reference) is called with an _offset_ higher than its _update\_id_. The negative offset can be specified to retrieve updates starting from _-offset_ update from the end of the updates queue. All previous updates will be forgotten.                                                                                                                                                          |
| limit            | Integer         | Optional | Limits the number of updates to be retrieved. Values between 1-100 are accepted. Defaults to 100.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| timeout          | Integer         | Optional | Timeout in seconds for long polling. Defaults to 0, i.e. usual short polling. Should be positive, short polling should be used for testing purposes only.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| allowed\_updates | Array of String | Optional | <p>A JSON-serialized list of the update types you want your bot to receive. For example, specify <code>["message", "edited_channel_post", "callback_query"]</code> to only receive updates of these types. See <a href="broken-reference">Update</a> for a complete list of available update types. Specify an empty list to receive all update types except <em>chat_member</em>, <em>message_reaction</em>, and <em>message_reaction_count</em> (default). If not specified, the previous setting will be used.</p><p>Please note that this parameter doesn't affect updates created before the call to the getUpdates, so unwanted updates may be received for a short period of time.</p> |

> **Notes**\
> **1.** This method will not work if an outgoing webhook is set up.\
> **2.** In order to avoid getting duplicate updates, recalculate _offset_ after each server response.

**setWebhook**

Use this method to specify a URL and receive incoming updates via an outgoing webhook. Whenever there is an update for the bot, we will send an HTTPS POST request to the specified URL, containing a JSON-serialized [Update](broken-reference). In case of an unsuccessful request, we will give up after a reasonable amount of attempts. Returns _True_ on success.

If you'd like to make sure that the webhook was set by you, you can specify secret data in the parameter _secret\_token_. If specified, the request will contain a header “X-Telegram-Bot-Api-Secret-Token” with the secret token as content.

| Parameter              | Type                          | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ---------------------- | ----------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| url                    | String                        | Yes      | HTTPS URL to send updates to. Use an empty string to remove webhook integration                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| certificate            | [InputFile](broken-reference) | Optional | Upload your public key certificate so that the root certificate in use can be checked. See our self-signed guide for details.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ip\_address            | String                        | Optional | The fixed IP address which will be used to send webhook requests instead of the IP address resolved through DNS                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| max\_connections       | Integer                       | Optional | The maximum allowed number of simultaneous HTTPS connections to the webhook for update delivery, 1-100. Defaults to _40_. Use lower values to limit the load on your bot's server, and higher values to increase your bot's throughput.                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| allowed\_updates       | Array of String               | Optional | <p>A JSON-serialized list of the update types you want your bot to receive. For example, specify <code>["message", "edited_channel_post", "callback_query"]</code> to only receive updates of these types. See <a href="broken-reference">Update</a> for a complete list of available update types. Specify an empty list to receive all update types except <em>chat_member</em>, <em>message_reaction</em>, and <em>message_reaction_count</em> (default). If not specified, the previous setting will be used.<br>Please note that this parameter doesn't affect updates created before the call to the setWebhook, so unwanted updates may be received for a short period of time.</p> |
| drop\_pending\_updates | Boolean                       | Optional | Pass _True_ to drop all pending updates                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| secret\_token          | String                        | Optional | A secret token to be sent in a header “X-Telegram-Bot-Api-Secret-Token” in every webhook request, 1-256 characters. Only characters `A-Z`, `a-z`, `0-9`, `_` and `-` are allowed. The header is useful to ensure that the request comes from a webhook set by you.                                                                                                                                                                                                                                                                                                                                                                                                                         |

> **Notes**\
> **1.** You will not be able to receive updates using [getUpdates](broken-reference) for as long as an outgoing webhook is set up.\
> **2.** To use a self-signed certificate, you need to upload your public key certificate using _certificate_ parameter. Please upload as InputFile, sending a String will not work.\
> **3.** Ports currently supported _for webhooks_: **443, 80, 88, 8443**.
>
> If you're having any trouble setting up webhooks, please check out this amazing guide to webhooks.

**deleteWebhook**

Use this method to remove webhook integration if you decide to switch back to [getUpdates](broken-reference). Returns _True_ on success.

| Parameter              | Type    | Required | Description                             |
| ---------------------- | ------- | -------- | --------------------------------------- |
| drop\_pending\_updates | Boolean | Optional | Pass _True_ to drop all pending updates |

**getWebhookInfo**

Use this method to get current webhook status. Requires no parameters. On success, returns a [WebhookInfo](broken-reference) object. If the bot is using [getUpdates](broken-reference), will return an object with the _url_ field empty.

**WebhookInfo**

Describes the current status of a webhook.

| Field                              | Type            | Description                                                                                                                             |
| ---------------------------------- | --------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| url                                | String          | Webhook URL, may be empty if webhook is not set up                                                                                      |
| has\_custom\_certificate           | Boolean         | _True_, if a custom certificate was provided for webhook certificate checks                                                             |
| pending\_update\_count             | Integer         | Number of updates awaiting delivery                                                                                                     |
| ip\_address                        | String          | _Optional_. Currently used webhook IP address                                                                                           |
| last\_error\_date                  | Integer         | _Optional_. Unix time for the most recent error that happened when trying to deliver an update via webhook                              |
| last\_error\_message               | String          | _Optional_. Error message in human-readable format for the most recent error that happened when trying to deliver an update via webhook |
| last\_synchronization\_error\_date | Integer         | _Optional_. Unix time of the most recent error that happened when trying to synchronize available updates with Telegram datacenters     |
| max\_connections                   | Integer         | _Optional_. The maximum allowed number of simultaneous HTTPS connections to the webhook for update delivery                             |
| allowed\_updates                   | Array of String | _Optional_. A list of update types the bot is subscribed to. Defaults to all update types except _chat\_member_                         |

#### Available types

All types used in the Bot API responses are represented as JSON-objects.

It is safe to use 32-bit signed integers for storing all **Integer** fields unless otherwise noted.

> **Optional** fields may be not returned when irrelevant.

**User**

This object represents a Telegram user or bot.

| Field                           | Type    | Description                                                                                                                                                                                                                                                                                                       |
| ------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                              | Integer | Unique identifier for this user or bot. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a 64-bit integer or double-precision float type are safe for storing this identifier. |
| is\_bot                         | Boolean | _True_, if this user is a bot                                                                                                                                                                                                                                                                                     |
| first\_name                     | String  | User's or bot's first name                                                                                                                                                                                                                                                                                        |
| last\_name                      | String  | _Optional_. User's or bot's last name                                                                                                                                                                                                                                                                             |
| username                        | String  | _Optional_. User's or bot's username                                                                                                                                                                                                                                                                              |
| language\_code                  | String  | _Optional_. [IETF language tag](https://en.wikipedia.org/wiki/IETF\_language\_tag) of the user's language                                                                                                                                                                                                         |
| is\_premium                     | True    | _Optional_. _True_, if this user is a Telegram Premium user                                                                                                                                                                                                                                                       |
| added\_to\_attachment\_menu     | True    | _Optional_. _True_, if this user added the bot to the attachment menu                                                                                                                                                                                                                                             |
| can\_join\_groups               | Boolean | _Optional_. _True_, if the bot can be invited to groups. Returned only in [getMe](broken-reference).                                                                                                                                                                                                              |
| can\_read\_all\_group\_messages | Boolean | _Optional_. _True_, if [privacy mode](https://about/bots/features#privacy-mode) is disabled for the bot. Returned only in [getMe](broken-reference).                                                                                                                                                              |
| supports\_inline\_queries       | Boolean | _Optional_. _True_, if the bot supports inline queries. Returned only in [getMe](broken-reference).                                                                                                                                                                                                               |

**Chat**

This object represents a chat.

| Field                                        | Type                                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------------------------------------------- | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id                                           | Integer                                   | Unique identifier for this chat. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this identifier.                                                                                                                                                        |
| type                                         | String                                    | Type of chat, can be either “private”, “group”, “supergroup” or “channel”                                                                                                                                                                                                                                                                                                                                                                                                |
| title                                        | String                                    | _Optional_. Title, for supergroups, channels and group chats                                                                                                                                                                                                                                                                                                                                                                                                             |
| username                                     | String                                    | _Optional_. Username, for private chats, supergroups and channels if available                                                                                                                                                                                                                                                                                                                                                                                           |
| first\_name                                  | String                                    | _Optional_. First name of the other party in a private chat                                                                                                                                                                                                                                                                                                                                                                                                              |
| last\_name                                   | String                                    | _Optional_. Last name of the other party in a private chat                                                                                                                                                                                                                                                                                                                                                                                                               |
| is\_forum                                    | True                                      | _Optional_. _True_, if the supergroup chat is a forum (has [topics](https://telegram.org/blog/topics-in-groups-collectible-usernames#topics-in-groups) enabled)                                                                                                                                                                                                                                                                                                          |
| photo                                        | [ChatPhoto](broken-reference)             | _Optional_. Chat photo. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                                                                                    |
| active\_usernames                            | Array of String                           | _Optional_. If non-empty, the list of all [active chat usernames](https://telegram.org/blog/topics-in-groups-collectible-usernames#collectible-usernames); for private chats, supergroups and channels. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                    |
| available\_reactions                         | Array of [ReactionType](broken-reference) | _Optional_. List of available reactions allowed in the chat. If omitted, then all [emoji reactions](broken-reference) are allowed. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                         |
| accent\_color\_id                            | Integer                                   | _Optional_. Identifier of the accent color for the chat name and backgrounds of the chat photo, reply header, and link preview. See [accent colors](broken-reference) for more details. Returned only in [getChat](broken-reference). Always returned in [getChat](broken-reference).                                                                                                                                                                                    |
| background\_custom\_emoji\_id                | String                                    | _Optional_. Custom emoji identifier of emoji chosen by the chat for the reply header and link preview background. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                          |
| profile\_accent\_color\_id                   | Integer                                   | _Optional_. Identifier of the accent color for the chat's profile background. See [profile accent colors](broken-reference) for more details. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                              |
| profile\_background\_custom\_emoji\_id       | String                                    | _Optional_. Custom emoji identifier of the emoji chosen by the chat for its profile background. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                            |
| emoji\_status\_custom\_emoji\_id             | String                                    | _Optional_. Custom emoji identifier of the emoji status of the chat or the other party in a private chat. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                  |
| emoji\_status\_expiration\_date              | Integer                                   | _Optional_. Expiration date of the emoji status of the chat or the other party in a private chat, in Unix time, if any. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                    |
| bio                                          | String                                    | _Optional_. Bio of the other party in a private chat. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                                                      |
| has\_private\_forwards                       | True                                      | _Optional_. _True_, if privacy settings of the other party in the private chat allows to use `tg://user?id=<user_id>` links only in chats with the user. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                   |
| has\_restricted\_voice\_and\_video\_messages | True                                      | _Optional_. _True_, if the privacy settings of the other party restrict sending voice and video note messages in the private chat. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                         |
| join\_to\_send\_messages                     | True                                      | _Optional_. _True_, if users need to join the supergroup before they can send messages. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                    |
| join\_by\_request                            | True                                      | _Optional_. _True_, if all users directly joining the supergroup need to be approved by supergroup administrators. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                         |
| description                                  | String                                    | _Optional_. Description, for groups, supergroups and channel chats. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                                        |
| invite\_link                                 | String                                    | _Optional_. Primary invite link, for groups, supergroups and channel chats. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                                |
| pinned\_message                              | [Message](broken-reference)               | _Optional_. The most recent pinned message (by sending date). Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                                              |
| permissions                                  | [ChatPermissions](broken-reference)       | _Optional_. Default chat member permissions, for groups and supergroups. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                                   |
| slow\_mode\_delay                            | Integer                                   | _Optional_. For supergroups, the minimum allowed delay between consecutive messages sent by each unprivileged user; in seconds. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                            |
| unrestrict\_boost\_count                     | Integer                                   | _Optional_. For supergroups, the minimum number of boosts that a non-administrator user needs to add in order to ignore slow mode and chat permissions. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                    |
| message\_auto\_delete\_time                  | Integer                                   | _Optional_. The time after which all messages sent to the chat will be automatically deleted; in seconds. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                  |
| has\_aggressive\_anti\_spam\_enabled         | True                                      | _Optional_. _True_, if aggressive anti-spam checks are enabled in the supergroup. The field is only available to chat administrators. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                      |
| has\_hidden\_members                         | True                                      | _Optional_. _True_, if non-administrators can only get the list of bots and administrators in the chat. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                    |
| has\_protected\_content                      | True                                      | _Optional_. _True_, if messages from the chat can't be forwarded to other chats. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                           |
| has\_visible\_history                        | True                                      | _Optional_. _True_, if new chat members will have access to old messages; available only to chat administrators. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                           |
| sticker\_set\_name                           | String                                    | _Optional_. For supergroups, name of group sticker set. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                                                    |
| can\_set\_sticker\_set                       | True                                      | _Optional_. _True_, if the bot can change the group sticker set. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                                           |
| custom\_emoji\_sticker\_set\_name            | String                                    | _Optional_. For supergroups, the name of the group's custom emoji sticker set. Custom emoji from this set can be used by all users and bots in the group. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                  |
| linked\_chat\_id                             | Integer                                   | _Optional_. Unique identifier for the linked chat, i.e. the discussion group identifier for a channel and vice versa; for supergroups and channel chats. This identifier may be greater than 32 bits and some programming languages may have difficulty/silent defects in interpreting it. But it is smaller than 52 bits, so a signed 64 bit integer or double-precision float type are safe for storing this identifier. Returned only in [getChat](broken-reference). |
| location                                     | [ChatLocation](broken-reference)          | _Optional_. For supergroups, the location to which the supergroup is connected. Returned only in [getChat](broken-reference).                                                                                                                                                                                                                                                                                                                                            |

**Message**

This object represents a message.

| Field                                 | Type                                              | Description                                                                                                                                                                                                                                                                                                                                                                                                          |
| ------------------------------------- | ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| message\_id                           | Integer                                           | Unique message identifier inside this chat                                                                                                                                                                                                                                                                                                                                                                           |
| message\_thread\_id                   | Integer                                           | _Optional_. Unique identifier of a message thread to which the message belongs; for supergroups only                                                                                                                                                                                                                                                                                                                 |
| from                                  | [User](broken-reference)                          | _Optional_. Sender of the message; empty for messages sent to channels. For backward compatibility, the field contains a fake sender user in non-channel chats, if the message was sent on behalf of a chat.                                                                                                                                                                                                         |
| sender\_chat                          | [Chat](broken-reference)                          | _Optional_. Sender of the message, sent on behalf of a chat. For example, the channel itself for channel posts, the supergroup itself for messages from anonymous group administrators, the linked channel for messages automatically forwarded to the discussion group. For backward compatibility, the field _from_ contains a fake sender user in non-channel chats, if the message was sent on behalf of a chat. |
| sender\_boost\_count                  | Integer                                           | _Optional_. If the sender of the message boosted the chat, the number of boosts added by the user                                                                                                                                                                                                                                                                                                                    |
| date                                  | Integer                                           | Date the message was sent in Unix time. It is always a positive number, representing a valid date.                                                                                                                                                                                                                                                                                                                   |
| chat                                  | [Chat](broken-reference)                          | Chat the message belongs to                                                                                                                                                                                                                                                                                                                                                                                          |
| forward\_origin                       | [MessageOrigin](broken-reference)                 | _Optional_. Information about the original message for forwarded messages                                                                                                                                                                                                                                                                                                                                            |
| is\_topic\_message                    | True                                              | _Optional_. _True_, if the message is sent to a forum topic                                                                                                                                                                                                                                                                                                                                                          |
| is\_automatic\_forward                | True                                              | _Optional_. _True_, if the message is a channel post that was automatically forwarded to the connected discussion group                                                                                                                                                                                                                                                                                              |
| reply\_to\_message                    | [Message](broken-reference)                       | _Optional_. For replies in the same chat and message thread, the original message. Note that the Message object in this field will not contain further _reply\_to\_message_ fields even if it itself is a reply.                                                                                                                                                                                                     |
| external\_reply                       | [ExternalReplyInfo](broken-reference)             | _Optional_. Information about the message that is being replied to, which may come from another chat or forum topic                                                                                                                                                                                                                                                                                                  |
| quote                                 | [TextQuote](broken-reference)                     | _Optional_. For replies that quote part of the original message, the quoted part of the message                                                                                                                                                                                                                                                                                                                      |
| reply\_to\_story                      | [Story](broken-reference)                         | _Optional_. For replies to a story, the original story                                                                                                                                                                                                                                                                                                                                                               |
| via\_bot                              | [User](broken-reference)                          | _Optional_. Bot through which the message was sent                                                                                                                                                                                                                                                                                                                                                                   |
| edit\_date                            | Integer                                           | _Optional_. Date the message was last edited in Unix time                                                                                                                                                                                                                                                                                                                                                            |
| has\_protected\_content               | True                                              | _Optional_. _True_, if the message can't be forwarded                                                                                                                                                                                                                                                                                                                                                                |
| media\_group\_id                      | String                                            | _Optional_. The unique identifier of a media message group this message belongs to                                                                                                                                                                                                                                                                                                                                   |
| author\_signature                     | String                                            | _Optional_. Signature of the post author for messages in channels, or the custom title of an anonymous group administrator                                                                                                                                                                                                                                                                                           |
| text                                  | String                                            | _Optional_. For text messages, the actual UTF-8 text of the message                                                                                                                                                                                                                                                                                                                                                  |
| entities                              | Array of [MessageEntity](broken-reference)        | _Optional_. For text messages, special entities like usernames, URLs, bot commands, etc. that appear in the text                                                                                                                                                                                                                                                                                                     |
| link\_preview\_options                | [LinkPreviewOptions](broken-reference)            | _Optional_. Options used for link preview generation for the message, if it is a text message and link preview options were changed                                                                                                                                                                                                                                                                                  |
| animation                             | [Animation](broken-reference)                     | _Optional_. Message is an animation, information about the animation. For backward compatibility, when this field is set, the _document_ field will also be set                                                                                                                                                                                                                                                      |
| audio                                 | [Audio](broken-reference)                         | _Optional_. Message is an audio file, information about the file                                                                                                                                                                                                                                                                                                                                                     |
| document                              | [Document](broken-reference)                      | _Optional_. Message is a general file, information about the file                                                                                                                                                                                                                                                                                                                                                    |
| photo                                 | Array of [PhotoSize](broken-reference)            | _Optional_. Message is a photo, available sizes of the photo                                                                                                                                                                                                                                                                                                                                                         |
| sticker                               | [Sticker](broken-reference)                       | _Optional_. Message is a sticker, information about the sticker                                                                                                                                                                                                                                                                                                                                                      |
| story                                 | [Story](broken-reference)                         | _Optional_. Message is a forwarded story                                                                                                                                                                                                                                                                                                                                                                             |
| video                                 | [Video](broken-reference)                         | _Optional_. Message is a video, information about the video                                                                                                                                                                                                                                                                                                                                                          |
| video\_note                           | [VideoNote](broken-reference)                     | _Optional_. Message is a [video note](https://telegram.org/blog/video-messages-and-telescope), information about the video message                                                                                                                                                                                                                                                                                   |
| voice                                 | [Voice](broken-reference)                         | _Optional_. Message is a voice message, information about the file                                                                                                                                                                                                                                                                                                                                                   |
| caption                               | String                                            | _Optional_. Caption for the animation, audio, document, photo, video or voice                                                                                                                                                                                                                                                                                                                                        |
| caption\_entities                     | Array of [MessageEntity](broken-reference)        | _Optional_. For messages with a caption, special entities like usernames, URLs, bot commands, etc. that appear in the caption                                                                                                                                                                                                                                                                                        |
| has\_media\_spoiler                   | True                                              | _Optional_. _True_, if the message media is covered by a spoiler animation                                                                                                                                                                                                                                                                                                                                           |
| contact                               | [Contact](broken-reference)                       | _Optional_. Message is a shared contact, information about the contact                                                                                                                                                                                                                                                                                                                                               |
| dice                                  | [Dice](broken-reference)                          | _Optional_. Message is a dice with random value                                                                                                                                                                                                                                                                                                                                                                      |
| game                                  | [Game](broken-reference)                          | _Optional_. Message is a game, information about the game. [More about games »](broken-reference)                                                                                                                                                                                                                                                                                                                    |
| poll                                  | [Poll](broken-reference)                          | _Optional_. Message is a native poll, information about the poll                                                                                                                                                                                                                                                                                                                                                     |
| venue                                 | [Venue](broken-reference)                         | _Optional_. Message is a venue, information about the venue. For backward compatibility, when this field is set, the _location_ field will also be set                                                                                                                                                                                                                                                               |
| location                              | [Location](broken-reference)                      | _Optional_. Message is a shared location, information about the location                                                                                                                                                                                                                                                                                                                                             |
| new\_chat\_members                    | Array of [User](broken-reference)                 | _Optional_. New members that were added to the group or supergroup and information about them (the bot itself may be one of these members)                                                                                                                                                                                                                                                                           |
| left\_chat\_member                    | [User](broken-reference)                          | _Optional_. A member was removed from the group, information about them (this member may be the bot itself)                                                                                                                                                                                                                                                                                                          |
| new\_chat\_title                      | String                                            | _Optional_. A chat title was changed to this value                                                                                                                                                                                                                                                                                                                                                                   |
| new\_chat\_photo                      | Array of [PhotoSize](broken-reference)            | _Optional_. A chat photo was change to this value                                                                                                                                                                                                                                                                                                                                                                    |
| delete\_chat\_photo                   | True                                              | _Optional_. Service message: the chat photo was deleted                                                                                                                                                                                                                                                                                                                                                              |
| group\_chat\_created                  | True                                              | _Optional_. Service message: the group has been created                                                                                                                                                                                                                                                                                                                                                              |
| supergroup\_chat\_created             | True                                              | _Optional_. Service message: the supergroup has been created. This field can't be received in a message coming through updates, because bot can't be a member of a supergroup when it is created. It can only be found in reply\_to\_message if someone replies to a very first message in a directly created supergroup.                                                                                            |
| channel\_chat\_created                | True                                              | _Optional_. Service message: the channel has been created. This field can't be received in a message coming through updates, because bot can't be a member of a channel when it is created. It can only be found in reply\_to\_message if someone replies to a very first message in a channel.                                                                                                                      |
| message\_auto\_delete\_timer\_changed | [MessageAutoDeleteTimerChanged](broken-reference) | _Optional_. Service message: auto-delete timer settings changed in the chat                                                                                                                                                                                                                                                                                                                                          |
| migrate\_to\_chat\_id                 | Integer                                           | _Optional_. The group has been migrated to a supergroup with the specified identifier. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this identifier.                                              |
| migrate\_from\_chat\_id               | Integer                                           | _Optional_. The supergroup has been migrated from a group with the specified identifier. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this identifier.                                            |
| pinned\_message                       | [MaybeInaccessibleMessage](broken-reference)      | _Optional_. Specified message was pinned. Note that the Message object in this field will not contain further _reply\_to\_message_ fields even if it itself is a reply.                                                                                                                                                                                                                                              |
| invoice                               | [Invoice](broken-reference)                       | _Optional_. Message is an invoice for a [payment](broken-reference), information about the invoice. [More about payments »](broken-reference)                                                                                                                                                                                                                                                                        |
| successful\_payment                   | [SuccessfulPayment](broken-reference)             | _Optional_. Message is a service message about a successful payment, information about the payment. [More about payments »](broken-reference)                                                                                                                                                                                                                                                                        |
| users\_shared                         | [UsersShared](broken-reference)                   | _Optional_. Service message: users were shared with the bot                                                                                                                                                                                                                                                                                                                                                          |
| chat\_shared                          | [ChatShared](broken-reference)                    | _Optional_. Service message: a chat was shared with the bot                                                                                                                                                                                                                                                                                                                                                          |
| connected\_website                    | String                                            | _Optional_. The domain name of the website on which the user has logged in. More about Telegram Login »                                                                                                                                                                                                                                                                                                              |
| write\_access\_allowed                | [WriteAccessAllowed](broken-reference)            | _Optional_. Service message: the user allowed the bot to write messages after adding it to the attachment or side menu, launching a Web App from a link, or accepting an explicit request from a Web App sent by the method [requestWriteAccess](https://about/bots/webapps#initializing-mini-apps)                                                                                                                  |
| passport\_data                        | [PassportData](broken-reference)                  | _Optional_. Telegram Passport data                                                                                                                                                                                                                                                                                                                                                                                   |
| proximity\_alert\_triggered           | [ProximityAlertTriggered](broken-reference)       | _Optional_. Service message. A user in the chat triggered another user's proximity alert while sharing Live Location.                                                                                                                                                                                                                                                                                                |
| boost\_added                          | [ChatBoostAdded](broken-reference)                | _Optional_. Service message: user boosted the chat                                                                                                                                                                                                                                                                                                                                                                   |
| forum\_topic\_created                 | [ForumTopicCreated](broken-reference)             | _Optional_. Service message: forum topic created                                                                                                                                                                                                                                                                                                                                                                     |
| forum\_topic\_edited                  | [ForumTopicEdited](broken-reference)              | _Optional_. Service message: forum topic edited                                                                                                                                                                                                                                                                                                                                                                      |
| forum\_topic\_closed                  | [ForumTopicClosed](broken-reference)              | _Optional_. Service message: forum topic closed                                                                                                                                                                                                                                                                                                                                                                      |
| forum\_topic\_reopened                | [ForumTopicReopened](broken-reference)            | _Optional_. Service message: forum topic reopened                                                                                                                                                                                                                                                                                                                                                                    |
| general\_forum\_topic\_hidden         | [GeneralForumTopicHidden](broken-reference)       | _Optional_. Service message: the 'General' forum topic hidden                                                                                                                                                                                                                                                                                                                                                        |
| general\_forum\_topic\_unhidden       | [GeneralForumTopicUnhidden](broken-reference)     | _Optional_. Service message: the 'General' forum topic unhidden                                                                                                                                                                                                                                                                                                                                                      |
| giveaway\_created                     | [GiveawayCreated](broken-reference)               | _Optional_. Service message: a scheduled giveaway was created                                                                                                                                                                                                                                                                                                                                                        |
| giveaway                              | [Giveaway](broken-reference)                      | _Optional_. The message is a scheduled giveaway message                                                                                                                                                                                                                                                                                                                                                              |
| giveaway\_winners                     | [GiveawayWinners](broken-reference)               | _Optional_. A giveaway with public winners was completed                                                                                                                                                                                                                                                                                                                                                             |
| giveaway\_completed                   | [GiveawayCompleted](broken-reference)             | _Optional_. Service message: a giveaway without public winners was completed                                                                                                                                                                                                                                                                                                                                         |
| video\_chat\_scheduled                | [VideoChatScheduled](broken-reference)            | _Optional_. Service message: video chat scheduled                                                                                                                                                                                                                                                                                                                                                                    |
| video\_chat\_started                  | [VideoChatStarted](broken-reference)              | _Optional_. Service message: video chat started                                                                                                                                                                                                                                                                                                                                                                      |
| video\_chat\_ended                    | [VideoChatEnded](broken-reference)                | _Optional_. Service message: video chat ended                                                                                                                                                                                                                                                                                                                                                                        |
| video\_chat\_participants\_invited    | [VideoChatParticipantsInvited](broken-reference)  | _Optional_. Service message: new participants invited to a video chat                                                                                                                                                                                                                                                                                                                                                |
| web\_app\_data                        | [WebAppData](broken-reference)                    | _Optional_. Service message: data sent by a Web App                                                                                                                                                                                                                                                                                                                                                                  |
| reply\_markup                         | [InlineKeyboardMarkup](broken-reference)          | _Optional_. Inline keyboard attached to the message. `login_url` buttons are represented as ordinary `url` buttons.                                                                                                                                                                                                                                                                                                  |

**MessageId**

This object represents a unique message identifier.

| Field       | Type    | Description               |
| ----------- | ------- | ------------------------- |
| message\_id | Integer | Unique message identifier |

**InaccessibleMessage**

This object describes a message that was deleted or is otherwise inaccessible to the bot.

| Field       | Type                     | Description                                                                         |
| ----------- | ------------------------ | ----------------------------------------------------------------------------------- |
| chat        | [Chat](broken-reference) | Chat the message belonged to                                                        |
| message\_id | Integer                  | Unique message identifier inside the chat                                           |
| date        | Integer                  | Always 0. The field can be used to differentiate regular and inaccessible messages. |

**MaybeInaccessibleMessage**

This object describes a message that can be inaccessible to the bot. It can be one of

* [Message](broken-reference)
* [InaccessibleMessage](broken-reference)

**MessageEntity**

This object represents one special entity in a text message. For example, hashtags, usernames, URLs, etc.

| Field             | Type                     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type              | String                   | Type of the entity. Currently, can be “mention” (`@username`), “hashtag” (`#hashtag`), “cashtag” (`$USD`), “bot\_command” (`/start@jobs_bot`), “url” (`https://telegram.org`), “email” (`do-not-reply@telegram.org`), “phone\_number” (`+1-212-555-0123`), “bold” (**bold text**), “italic” (_italic text_), “underline” (underlined text), “strikethrough” (strikethrough text), “spoiler” (spoiler message), “blockquote” (block quotation), “code” (monowidth string), “pre” (monowidth block), “text\_link” (for clickable text URLs), “text\_mention” (for users [without usernames](https://telegram.org/blog/edit#new-mentions)), “custom\_emoji” (for inline custom emoji stickers) |
| offset            | Integer                  | Offset in [UTF-16 code units](https://about/api/entities#entity-length) to the start of the entity                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| length            | Integer                  | Length of the entity in [UTF-16 code units](https://about/api/entities#entity-length)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| url               | String                   | _Optional_. For “text\_link” only, URL that will be opened after user taps on the text                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| user              | [User](broken-reference) | _Optional_. For “text\_mention” only, the mentioned user                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| language          | String                   | _Optional_. For “pre” only, the programming language of the entity text                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| custom\_emoji\_id | String                   | _Optional_. For “custom\_emoji” only, unique identifier of the custom emoji. Use [getCustomEmojiStickers](broken-reference) to get full information about the sticker                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

**TextQuote**

This object contains information about the quoted part of a message that is replied to by the given message.

| Field      | Type                                       | Description                                                                                                                                                                        |
| ---------- | ------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| text       | String                                     | Text of the quoted part of a message that is replied to by the given message                                                                                                       |
| entities   | Array of [MessageEntity](broken-reference) | _Optional_. Special entities that appear in the quote. Currently, only _bold_, _italic_, _underline_, _strikethrough_, _spoiler_, and _custom\_emoji_ entities are kept in quotes. |
| position   | Integer                                    | Approximate quote position in the original message in UTF-16 code units as specified by the sender                                                                                 |
| is\_manual | True                                       | _Optional_. True, if the quote was chosen manually by the message sender. Otherwise, the quote was added automatically by the server.                                              |

**ExternalReplyInfo**

This object contains information about a message that is being replied to, which may come from another chat or forum topic.

| Field                  | Type                                   | Description                                                                                                                                   |
| ---------------------- | -------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| origin                 | [MessageOrigin](broken-reference)      | Origin of the message replied to by the given message                                                                                         |
| chat                   | [Chat](broken-reference)               | _Optional_. Chat the original message belongs to. Available only if the chat is a supergroup or a channel.                                    |
| message\_id            | Integer                                | _Optional_. Unique message identifier inside the original chat. Available only if the original chat is a supergroup or a channel.             |
| link\_preview\_options | [LinkPreviewOptions](broken-reference) | _Optional_. Options used for link preview generation for the original message, if it is a text message                                        |
| animation              | [Animation](broken-reference)          | _Optional_. Message is an animation, information about the animation                                                                          |
| audio                  | [Audio](broken-reference)              | _Optional_. Message is an audio file, information about the file                                                                              |
| document               | [Document](broken-reference)           | _Optional_. Message is a general file, information about the file                                                                             |
| photo                  | Array of [PhotoSize](broken-reference) | _Optional_. Message is a photo, available sizes of the photo                                                                                  |
| sticker                | [Sticker](broken-reference)            | _Optional_. Message is a sticker, information about the sticker                                                                               |
| story                  | [Story](broken-reference)              | _Optional_. Message is a forwarded story                                                                                                      |
| video                  | [Video](broken-reference)              | _Optional_. Message is a video, information about the video                                                                                   |
| video\_note            | [VideoNote](broken-reference)          | _Optional_. Message is a [video note](https://telegram.org/blog/video-messages-and-telescope), information about the video message            |
| voice                  | [Voice](broken-reference)              | _Optional_. Message is a voice message, information about the file                                                                            |
| has\_media\_spoiler    | True                                   | _Optional_. _True_, if the message media is covered by a spoiler animation                                                                    |
| contact                | [Contact](broken-reference)            | _Optional_. Message is a shared contact, information about the contact                                                                        |
| dice                   | [Dice](broken-reference)               | _Optional_. Message is a dice with random value                                                                                               |
| game                   | [Game](broken-reference)               | _Optional_. Message is a game, information about the game. [More about games »](broken-reference)                                             |
| giveaway               | [Giveaway](broken-reference)           | _Optional_. Message is a scheduled giveaway, information about the giveaway                                                                   |
| giveaway\_winners      | [GiveawayWinners](broken-reference)    | _Optional_. A giveaway with public winners was completed                                                                                      |
| invoice                | [Invoice](broken-reference)            | _Optional_. Message is an invoice for a [payment](broken-reference), information about the invoice. [More about payments »](broken-reference) |
| location               | [Location](broken-reference)           | _Optional_. Message is a shared location, information about the location                                                                      |
| poll                   | [Poll](broken-reference)               | _Optional_. Message is a native poll, information about the poll                                                                              |
| venue                  | [Venue](broken-reference)              | _Optional_. Message is a venue, information about the venue                                                                                   |

**ReplyParameters**

Describes reply parameters for the message that is being sent.

| Field                          | Type                                       | Description                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------ | ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| message\_id                    | Integer                                    | Identifier of the message that will be replied to in the current chat, or in the chat _chat\_id_ if it is specified                                                                                                                                                                                                                                         |
| chat\_id                       | Integer or String                          | _Optional_. If the message to be replied to is from a different chat, unique identifier for the chat or username of the channel (in the format `@channelusername`)                                                                                                                                                                                          |
| allow\_sending\_without\_reply | Boolean                                    | _Optional_. Pass _True_ if the message should be sent even if the specified message to be replied to is not found; can be used only for replies in the same chat and forum topic.                                                                                                                                                                           |
| quote                          | String                                     | _Optional_. Quoted part of the message to be replied to; 0-1024 characters after entities parsing. The quote must be an exact substring of the message to be replied to, including _bold_, _italic_, _underline_, _strikethrough_, _spoiler_, and _custom\_emoji_ entities. The message will fail to send if the quote isn't found in the original message. |
| quote\_parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the quote. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                            |
| quote\_entities                | Array of [MessageEntity](broken-reference) | _Optional_. A JSON-serialized list of special entities that appear in the quote. It can be specified instead of _quote\_parse\_mode_.                                                                                                                                                                                                                       |
| quote\_position                | Integer                                    | _Optional_. Position of the quote in the original message in UTF-16 code units                                                                                                                                                                                                                                                                              |

**MessageOrigin**

This object describes the origin of a message. It can be one of

* [MessageOriginUser](broken-reference)
* [MessageOriginHiddenUser](broken-reference)
* [MessageOriginChat](broken-reference)
* [MessageOriginChannel](broken-reference)

**MessageOriginUser**

The message was originally sent by a known user.

| Field        | Type                     | Description                                       |
| ------------ | ------------------------ | ------------------------------------------------- |
| type         | String                   | Type of the message origin, always “user”         |
| date         | Integer                  | Date the message was sent originally in Unix time |
| sender\_user | [User](broken-reference) | User that sent the message originally             |

**MessageOriginHiddenUser**

The message was originally sent by an unknown user.

| Field              | Type    | Description                                       |
| ------------------ | ------- | ------------------------------------------------- |
| type               | String  | Type of the message origin, always “hidden\_user” |
| date               | Integer | Date the message was sent originally in Unix time |
| sender\_user\_name | String  | Name of the user that sent the message originally |

**MessageOriginChat**

The message was originally sent on behalf of a chat to a group chat.

| Field             | Type                     | Description                                                                                                    |
| ----------------- | ------------------------ | -------------------------------------------------------------------------------------------------------------- |
| type              | String                   | Type of the message origin, always “chat”                                                                      |
| date              | Integer                  | Date the message was sent originally in Unix time                                                              |
| sender\_chat      | [Chat](broken-reference) | Chat that sent the message originally                                                                          |
| author\_signature | String                   | _Optional_. For messages originally sent by an anonymous chat administrator, original message author signature |

**MessageOriginChannel**

The message was originally sent to a channel chat.

| Field             | Type                     | Description                                           |
| ----------------- | ------------------------ | ----------------------------------------------------- |
| type              | String                   | Type of the message origin, always “channel”          |
| date              | Integer                  | Date the message was sent originally in Unix time     |
| chat              | [Chat](broken-reference) | Channel chat to which the message was originally sent |
| message\_id       | Integer                  | Unique message identifier inside the chat             |
| author\_signature | String                   | _Optional_. Signature of the original post author     |

**PhotoSize**

This object represents one size of a photo or a [file](broken-reference) / [sticker](broken-reference) thumbnail.

| Field            | Type    | Description                                                                                                                                      |
| ---------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| file\_id         | String  | Identifier for this file, which can be used to download or reuse the file                                                                        |
| file\_unique\_id | String  | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file. |
| width            | Integer | Photo width                                                                                                                                      |
| height           | Integer | Photo height                                                                                                                                     |
| file\_size       | Integer | _Optional_. File size in bytes                                                                                                                   |

**Animation**

This object represents an animation file (GIF or H.264/MPEG-4 AVC video without sound).

| Field            | Type                          | Description                                                                                                                                                                                                                                                                         |
| ---------------- | ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| file\_id         | String                        | Identifier for this file, which can be used to download or reuse the file                                                                                                                                                                                                           |
| file\_unique\_id | String                        | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file.                                                                                                                                    |
| width            | Integer                       | Video width as defined by sender                                                                                                                                                                                                                                                    |
| height           | Integer                       | Video height as defined by sender                                                                                                                                                                                                                                                   |
| duration         | Integer                       | Duration of the video in seconds as defined by sender                                                                                                                                                                                                                               |
| thumbnail        | [PhotoSize](broken-reference) | _Optional_. Animation thumbnail as defined by sender                                                                                                                                                                                                                                |
| file\_name       | String                        | _Optional_. Original animation filename as defined by sender                                                                                                                                                                                                                        |
| mime\_type       | String                        | _Optional_. MIME type of the file as defined by sender                                                                                                                                                                                                                              |
| file\_size       | Integer                       | _Optional_. File size in bytes. It can be bigger than 2^31 and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this value. |

**Audio**

This object represents an audio file to be treated as music by the Telegram clients.

| Field            | Type                          | Description                                                                                                                                                                                                                                                                         |
| ---------------- | ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| file\_id         | String                        | Identifier for this file, which can be used to download or reuse the file                                                                                                                                                                                                           |
| file\_unique\_id | String                        | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file.                                                                                                                                    |
| duration         | Integer                       | Duration of the audio in seconds as defined by sender                                                                                                                                                                                                                               |
| performer        | String                        | _Optional_. Performer of the audio as defined by sender or by audio tags                                                                                                                                                                                                            |
| title            | String                        | _Optional_. Title of the audio as defined by sender or by audio tags                                                                                                                                                                                                                |
| file\_name       | String                        | _Optional_. Original filename as defined by sender                                                                                                                                                                                                                                  |
| mime\_type       | String                        | _Optional_. MIME type of the file as defined by sender                                                                                                                                                                                                                              |
| file\_size       | Integer                       | _Optional_. File size in bytes. It can be bigger than 2^31 and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this value. |
| thumbnail        | [PhotoSize](broken-reference) | _Optional_. Thumbnail of the album cover to which the music file belongs                                                                                                                                                                                                            |

**Document**

This object represents a general file (as opposed to [photos](broken-reference), [voice messages](broken-reference) and [audio files](broken-reference)).

| Field            | Type                          | Description                                                                                                                                                                                                                                                                         |
| ---------------- | ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| file\_id         | String                        | Identifier for this file, which can be used to download or reuse the file                                                                                                                                                                                                           |
| file\_unique\_id | String                        | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file.                                                                                                                                    |
| thumbnail        | [PhotoSize](broken-reference) | _Optional_. Document thumbnail as defined by sender                                                                                                                                                                                                                                 |
| file\_name       | String                        | _Optional_. Original filename as defined by sender                                                                                                                                                                                                                                  |
| mime\_type       | String                        | _Optional_. MIME type of the file as defined by sender                                                                                                                                                                                                                              |
| file\_size       | Integer                       | _Optional_. File size in bytes. It can be bigger than 2^31 and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this value. |

**Story**

This object represents a story.

| Field | Type                     | Description                                 |
| ----- | ------------------------ | ------------------------------------------- |
| chat  | [Chat](broken-reference) | Chat that posted the story                  |
| id    | Integer                  | Unique identifier for the story in the chat |

**Video**

This object represents a video file.

| Field            | Type                          | Description                                                                                                                                                                                                                                                                         |
| ---------------- | ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| file\_id         | String                        | Identifier for this file, which can be used to download or reuse the file                                                                                                                                                                                                           |
| file\_unique\_id | String                        | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file.                                                                                                                                    |
| width            | Integer                       | Video width as defined by sender                                                                                                                                                                                                                                                    |
| height           | Integer                       | Video height as defined by sender                                                                                                                                                                                                                                                   |
| duration         | Integer                       | Duration of the video in seconds as defined by sender                                                                                                                                                                                                                               |
| thumbnail        | [PhotoSize](broken-reference) | _Optional_. Video thumbnail                                                                                                                                                                                                                                                         |
| file\_name       | String                        | _Optional_. Original filename as defined by sender                                                                                                                                                                                                                                  |
| mime\_type       | String                        | _Optional_. MIME type of the file as defined by sender                                                                                                                                                                                                                              |
| file\_size       | Integer                       | _Optional_. File size in bytes. It can be bigger than 2^31 and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this value. |

**VideoNote**

This object represents a [video message](https://telegram.org/blog/video-messages-and-telescope) (available in Telegram apps as of [v.4.0](https://telegram.org/blog/video-messages-and-telescope)).

| Field            | Type                          | Description                                                                                                                                      |
| ---------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| file\_id         | String                        | Identifier for this file, which can be used to download or reuse the file                                                                        |
| file\_unique\_id | String                        | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file. |
| length           | Integer                       | Video width and height (diameter of the video message) as defined by sender                                                                      |
| duration         | Integer                       | Duration of the video in seconds as defined by sender                                                                                            |
| thumbnail        | [PhotoSize](broken-reference) | _Optional_. Video thumbnail                                                                                                                      |
| file\_size       | Integer                       | _Optional_. File size in bytes                                                                                                                   |

**Voice**

This object represents a voice note.

| Field            | Type    | Description                                                                                                                                                                                                                                                                         |
| ---------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| file\_id         | String  | Identifier for this file, which can be used to download or reuse the file                                                                                                                                                                                                           |
| file\_unique\_id | String  | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file.                                                                                                                                    |
| duration         | Integer | Duration of the audio in seconds as defined by sender                                                                                                                                                                                                                               |
| mime\_type       | String  | _Optional_. MIME type of the file as defined by sender                                                                                                                                                                                                                              |
| file\_size       | Integer | _Optional_. File size in bytes. It can be bigger than 2^31 and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this value. |

**Contact**

This object represents a phone contact.

| Field         | Type    | Description                                                                                                                                                                                                                                                                                                                  |
| ------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| phone\_number | String  | Contact's phone number                                                                                                                                                                                                                                                                                                       |
| first\_name   | String  | Contact's first name                                                                                                                                                                                                                                                                                                         |
| last\_name    | String  | _Optional_. Contact's last name                                                                                                                                                                                                                                                                                              |
| user\_id      | Integer | _Optional_. Contact's user identifier in Telegram. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a 64-bit integer or double-precision float type are safe for storing this identifier. |
| vcard         | String  | _Optional_. Additional data about the contact in the form of a [vCard](https://en.wikipedia.org/wiki/VCard)                                                                                                                                                                                                                  |

**Dice**

This object represents an animated emoji that displays a random value.

| Field | Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ----- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| emoji | String  | Emoji on which the dice throw animation is based                                                                                                                                                                                                                                                                                                                                                                                     |
| value | Integer | Value of the dice, 1-6 for “![🎲](https://telegram.org/img/emoji/40/F09F8EB2.png)”, “![🎯](https://telegram.org/img/emoji/40/F09F8EAF.png)” and “![🎳](https://telegram.org/img/emoji/40/F09F8EB3.png)” base emoji, 1-5 for “![🏀](https://telegram.org/img/emoji/40/F09F8F80.png)” and “![⚽](https://telegram.org/img/emoji/40/E29ABD.png)” base emoji, 1-64 for “![🎰](https://telegram.org/img/emoji/40/F09F8EB0.png)” base emoji |

**PollOption**

This object contains information about one answer option in a poll.

| Field        | Type    | Description                                |
| ------------ | ------- | ------------------------------------------ |
| text         | String  | Option text, 1-100 characters              |
| voter\_count | Integer | Number of users that voted for this option |

**PollAnswer**

This object represents an answer of a user in a non-anonymous poll.

| Field       | Type                     | Description                                                                            |
| ----------- | ------------------------ | -------------------------------------------------------------------------------------- |
| poll\_id    | String                   | Unique poll identifier                                                                 |
| voter\_chat | [Chat](broken-reference) | _Optional_. The chat that changed the answer to the poll, if the voter is anonymous    |
| user        | [User](broken-reference) | _Optional_. The user that changed the answer to the poll, if the voter isn't anonymous |
| option\_ids | Array of Integer         | 0-based identifiers of chosen answer options. May be empty if the vote was retracted.  |

**Poll**

This object contains information about a poll.

| Field                     | Type                                       | Description                                                                                                                                                                                           |
| ------------------------- | ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                        | String                                     | Unique poll identifier                                                                                                                                                                                |
| question                  | String                                     | Poll question, 1-300 characters                                                                                                                                                                       |
| options                   | Array of [PollOption](broken-reference)    | List of poll options                                                                                                                                                                                  |
| total\_voter\_count       | Integer                                    | Total number of users that voted in the poll                                                                                                                                                          |
| is\_closed                | Boolean                                    | _True_, if the poll is closed                                                                                                                                                                         |
| is\_anonymous             | Boolean                                    | _True_, if the poll is anonymous                                                                                                                                                                      |
| type                      | String                                     | Poll type, currently can be “regular” or “quiz”                                                                                                                                                       |
| allows\_multiple\_answers | Boolean                                    | _True_, if the poll allows multiple answers                                                                                                                                                           |
| correct\_option\_id       | Integer                                    | _Optional_. 0-based identifier of the correct answer option. Available only for polls in the quiz mode, which are closed, or was sent (not forwarded) by the bot or to the private chat with the bot. |
| explanation               | String                                     | _Optional_. Text that is shown when a user chooses an incorrect answer or taps on the lamp icon in a quiz-style poll, 0-200 characters                                                                |
| explanation\_entities     | Array of [MessageEntity](broken-reference) | _Optional_. Special entities like usernames, URLs, bot commands, etc. that appear in the _explanation_                                                                                                |
| open\_period              | Integer                                    | _Optional_. Amount of time in seconds the poll will be active after creation                                                                                                                          |
| close\_date               | Integer                                    | _Optional_. Point in time (Unix timestamp) when the poll will be automatically closed                                                                                                                 |

**Location**

This object represents a point on the map.

| Field                    | Type    | Description                                                                                                                                  |
| ------------------------ | ------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| latitude                 | Float   | Latitude as defined by sender                                                                                                                |
| longitude                | Float   | Longitude as defined by sender                                                                                                               |
| horizontal\_accuracy     | Float   | _Optional_. The radius of uncertainty for the location, measured in meters; 0-1500                                                           |
| live\_period             | Integer | _Optional_. Time relative to the message sending date, during which the location can be updated; in seconds. For active live locations only. |
| heading                  | Integer | _Optional_. The direction in which user is moving, in degrees; 1-360. For active live locations only.                                        |
| proximity\_alert\_radius | Integer | _Optional_. The maximum distance for proximity alerts about approaching another chat member, in meters. For sent live locations only.        |

**Venue**

This object represents a venue.

| Field               | Type                         | Description                                                                                                                                |
| ------------------- | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| location            | [Location](broken-reference) | Venue location. Can't be a live location                                                                                                   |
| title               | String                       | Name of the venue                                                                                                                          |
| address             | String                       | Address of the venue                                                                                                                       |
| foursquare\_id      | String                       | _Optional_. Foursquare identifier of the venue                                                                                             |
| foursquare\_type    | String                       | _Optional_. Foursquare type of the venue. (For example, “arts\_entertainment/default”, “arts\_entertainment/aquarium” or “food/icecream”.) |
| google\_place\_id   | String                       | _Optional_. Google Places identifier of the venue                                                                                          |
| google\_place\_type | String                       | _Optional_. Google Places type of the venue. (See [supported types](https://developers.google.com/places/web-service/supported\_types).)   |

**WebAppData**

Describes data sent from a Web App to the bot.

| Field        | Type   | Description                                                                                                                                 |
| ------------ | ------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| data         | String | The data. Be aware that a bad client can send arbitrary data in this field.                                                                 |
| button\_text | String | Text of the _web\_app_ keyboard button from which the Web App was opened. Be aware that a bad client can send arbitrary data in this field. |

**ProximityAlertTriggered**

This object represents the content of a service message, sent whenever a user in the chat triggers a proximity alert set by another user.

| Field    | Type                     | Description                    |
| -------- | ------------------------ | ------------------------------ |
| traveler | [User](broken-reference) | User that triggered the alert  |
| watcher  | [User](broken-reference) | User that set the alert        |
| distance | Integer                  | The distance between the users |

**MessageAutoDeleteTimerChanged**

This object represents a service message about a change in auto-delete timer settings.

| Field                       | Type    | Description                                               |
| --------------------------- | ------- | --------------------------------------------------------- |
| message\_auto\_delete\_time | Integer | New auto-delete time for messages in the chat; in seconds |

**ChatBoostAdded**

This object represents a service message about a user boosting a chat.

| Field        | Type    | Description                        |
| ------------ | ------- | ---------------------------------- |
| boost\_count | Integer | Number of boosts added by the user |

**ForumTopicCreated**

This object represents a service message about a new forum topic created in the chat.

| Field                   | Type    | Description                                                               |
| ----------------------- | ------- | ------------------------------------------------------------------------- |
| name                    | String  | Name of the topic                                                         |
| icon\_color             | Integer | Color of the topic icon in RGB format                                     |
| icon\_custom\_emoji\_id | String  | _Optional_. Unique identifier of the custom emoji shown as the topic icon |

**ForumTopicClosed**

This object represents a service message about a forum topic closed in the chat. Currently holds no information.

**ForumTopicEdited**

This object represents a service message about an edited forum topic.

| Field                   | Type   | Description                                                                                                                       |
| ----------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------- |
| name                    | String | _Optional_. New name of the topic, if it was edited                                                                               |
| icon\_custom\_emoji\_id | String | _Optional_. New identifier of the custom emoji shown as the topic icon, if it was edited; an empty string if the icon was removed |

**ForumTopicReopened**

This object represents a service message about a forum topic reopened in the chat. Currently holds no information.

**GeneralForumTopicHidden**

This object represents a service message about General forum topic hidden in the chat. Currently holds no information.

**GeneralForumTopicUnhidden**

This object represents a service message about General forum topic unhidden in the chat. Currently holds no information.

**UsersShared**

This object contains information about the users whose identifiers were shared with the bot using a [KeyboardButtonRequestUsers](broken-reference) button.

| Field       | Type             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ----------- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| request\_id | Integer          | Identifier of the request                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| user\_ids   | Array of Integer | Identifiers of the shared users. These numbers may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting them. But they have at most 52 significant bits, so 64-bit integers or double-precision float types are safe for storing these identifiers. The bot may not have access to the users and could be unable to use these identifiers, unless the users are already known to the bot by some other means. |

**ChatShared**

This object contains information about the chat whose identifier was shared with the bot using a [KeyboardButtonRequestChat](broken-reference) button.

| Field       | Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ----------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| request\_id | Integer | Identifier of the request                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| chat\_id    | Integer | Identifier of the shared chat. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a 64-bit integer or double-precision float type are safe for storing this identifier. The bot may not have access to the chat and could be unable to use this identifier, unless the chat is already known to the bot by some other means. |

**WriteAccessAllowed**

This object represents a service message about a user allowing a bot to write messages after adding it to the attachment menu, launching a Web App from a link, or accepting an explicit request from a Web App sent by the method [requestWriteAccess](https://about/bots/webapps#initializing-mini-apps).

| Field                  | Type    | Description                                                                                                                                                                                       |
| ---------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| from\_request          | Boolean | _Optional_. True, if the access was granted after the user accepted an explicit request from a Web App sent by the method [requestWriteAccess](https://about/bots/webapps#initializing-mini-apps) |
| web\_app\_name         | String  | _Optional_. Name of the Web App, if the access was granted when the Web App was launched from a link                                                                                              |
| from\_attachment\_menu | Boolean | _Optional_. True, if the access was granted when the bot was added to the attachment or side menu                                                                                                 |

**VideoChatScheduled**

This object represents a service message about a video chat scheduled in the chat.

| Field       | Type    | Description                                                                                          |
| ----------- | ------- | ---------------------------------------------------------------------------------------------------- |
| start\_date | Integer | Point in time (Unix timestamp) when the video chat is supposed to be started by a chat administrator |

**VideoChatStarted**

This object represents a service message about a video chat started in the chat. Currently holds no information.

**VideoChatEnded**

This object represents a service message about a video chat ended in the chat.

| Field    | Type    | Description                    |
| -------- | ------- | ------------------------------ |
| duration | Integer | Video chat duration in seconds |

**VideoChatParticipantsInvited**

This object represents a service message about new members invited to a video chat.

| Field | Type                              | Description                                     |
| ----- | --------------------------------- | ----------------------------------------------- |
| users | Array of [User](broken-reference) | New members that were invited to the video chat |

**GiveawayCreated**

This object represents a service message about the creation of a scheduled giveaway. Currently holds no information.

**Giveaway**

This object represents a message about a scheduled giveaway.

| Field                               | Type                              | Description                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------------------- | --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chats                               | Array of [Chat](broken-reference) | The list of chats which the user must join to participate in the giveaway                                                                                                                                                                                                                                                                                   |
| winners\_selection\_date            | Integer                           | Point in time (Unix timestamp) when winners of the giveaway will be selected                                                                                                                                                                                                                                                                                |
| winner\_count                       | Integer                           | The number of users which are supposed to be selected as winners of the giveaway                                                                                                                                                                                                                                                                            |
| only\_new\_members                  | True                              | _Optional_. _True_, if only users who join the chats after the giveaway started should be eligible to win                                                                                                                                                                                                                                                   |
| has\_public\_winners                | True                              | _Optional_. _True_, if the list of giveaway winners will be visible to everyone                                                                                                                                                                                                                                                                             |
| prize\_description                  | String                            | _Optional_. Description of additional giveaway prize                                                                                                                                                                                                                                                                                                        |
| country\_codes                      | Array of String                   | _Optional_. A list of two-letter [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2) country codes indicating the countries from which eligible users for the giveaway must come. If empty, then all users can participate in the giveaway. Users with a phone number that was bought on Fragment can always participate in giveaways. |
| premium\_subscription\_month\_count | Integer                           | _Optional_. The number of months the Telegram Premium subscription won from the giveaway will be active for                                                                                                                                                                                                                                                 |

**GiveawayWinners**

This object represents a message about the completion of a giveaway with public winners.

| Field                               | Type                              | Description                                                                                                 |
| ----------------------------------- | --------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| chat                                | [Chat](broken-reference)          | The chat that created the giveaway                                                                          |
| giveaway\_message\_id               | Integer                           | Identifier of the message with the giveaway in the chat                                                     |
| winners\_selection\_date            | Integer                           | Point in time (Unix timestamp) when winners of the giveaway were selected                                   |
| winner\_count                       | Integer                           | Total number of winners in the giveaway                                                                     |
| winners                             | Array of [User](broken-reference) | List of up to 100 winners of the giveaway                                                                   |
| additional\_chat\_count             | Integer                           | _Optional_. The number of other chats the user had to join in order to be eligible for the giveaway         |
| premium\_subscription\_month\_count | Integer                           | _Optional_. The number of months the Telegram Premium subscription won from the giveaway will be active for |
| unclaimed\_prize\_count             | Integer                           | _Optional_. Number of undistributed prizes                                                                  |
| only\_new\_members                  | True                              | _Optional_. _True_, if only users who had joined the chats after the giveaway started were eligible to win  |
| was\_refunded                       | True                              | _Optional_. _True_, if the giveaway was canceled because the payment for it was refunded                    |
| prize\_description                  | String                            | _Optional_. Description of additional giveaway prize                                                        |

**GiveawayCompleted**

This object represents a service message about the completion of a giveaway without public winners.

| Field                   | Type                        | Description                                                                    |
| ----------------------- | --------------------------- | ------------------------------------------------------------------------------ |
| winner\_count           | Integer                     | Number of winners in the giveaway                                              |
| unclaimed\_prize\_count | Integer                     | _Optional_. Number of undistributed prizes                                     |
| giveaway\_message       | [Message](broken-reference) | _Optional_. Message with the giveaway that was completed, if it wasn't deleted |

**LinkPreviewOptions**

Describes the options used for link preview generation.

| Field                | Type    | Description                                                                                                                                                                         |
| -------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| is\_disabled         | Boolean | _Optional_. _True_, if the link preview is disabled                                                                                                                                 |
| url                  | String  | _Optional_. URL to use for the link preview. If empty, then the first URL found in the message text will be used                                                                    |
| prefer\_small\_media | Boolean | _Optional_. _True_, if the media in the link preview is supposed to be shrunk; ignored if the URL isn't explicitly specified or media size change isn't supported for the preview   |
| prefer\_large\_media | Boolean | _Optional_. _True_, if the media in the link preview is supposed to be enlarged; ignored if the URL isn't explicitly specified or media size change isn't supported for the preview |
| show\_above\_text    | Boolean | _Optional_. _True_, if the link preview must be shown above the message text; otherwise, the link preview will be shown below the message text                                      |

**UserProfilePhotos**

This object represent a user's profile pictures.

| Field        | Type                                            | Description                                          |
| ------------ | ----------------------------------------------- | ---------------------------------------------------- |
| total\_count | Integer                                         | Total number of profile pictures the target user has |
| photos       | Array of Array of [PhotoSize](broken-reference) | Requested profile pictures (in up to 4 sizes each)   |

**File**

This object represents a file ready to be downloaded. The file can be downloaded via the link `https://api.telegram.org/file/bot<token>/<file_path>`. It is guaranteed that the link will be valid for at least 1 hour. When the link expires, a new one can be requested by calling [getFile](broken-reference).

> The maximum file size to download is 20 MB

| Field            | Type    | Description                                                                                                                                                                                                                                                                         |
| ---------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| file\_id         | String  | Identifier for this file, which can be used to download or reuse the file                                                                                                                                                                                                           |
| file\_unique\_id | String  | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file.                                                                                                                                    |
| file\_size       | Integer | _Optional_. File size in bytes. It can be bigger than 2^31 and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this value. |
| file\_path       | String  | _Optional_. File path. Use `https://api.telegram.org/file/bot<token>/<file_path>` to get the file.                                                                                                                                                                                  |

**WebAppInfo**

Describes a Web App.

| Field | Type   | Description                                                                                                                                            |
| ----- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| url   | String | An HTTPS URL of a Web App to be opened with additional data as specified in [Initializing Web Apps](https://about/bots/webapps#initializing-mini-apps) |

**ReplyKeyboardMarkup**

This object represents a [custom keyboard](https://about/bots/features#keyboards) with reply options (see [Introduction to bots](https://about/bots/features#keyboards) for details and examples).

| Field                     | Type                                                 | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------- | ---------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| keyboard                  | Array of Array of [KeyboardButton](broken-reference) | Array of button rows, each represented by an Array of [KeyboardButton](broken-reference) objects                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| is\_persistent            | Boolean                                              | _Optional_. Requests clients to always show the keyboard when the regular keyboard is hidden. Defaults to _false_, in which case the custom keyboard can be hidden and opened with a keyboard icon.                                                                                                                                                                                                                                                                                                                                    |
| resize\_keyboard          | Boolean                                              | _Optional_. Requests clients to resize the keyboard vertically for optimal fit (e.g., make the keyboard smaller if there are just two rows of buttons). Defaults to _false_, in which case the custom keyboard is always of the same height as the app's standard keyboard.                                                                                                                                                                                                                                                            |
| one\_time\_keyboard       | Boolean                                              | _Optional_. Requests clients to hide the keyboard as soon as it's been used. The keyboard will still be available, but clients will automatically display the usual letter-keyboard in the chat - the user can press a special button in the input field to see the custom keyboard again. Defaults to _false_.                                                                                                                                                                                                                        |
| input\_field\_placeholder | String                                               | _Optional_. The placeholder to be shown in the input field when the keyboard is active; 1-64 characters                                                                                                                                                                                                                                                                                                                                                                                                                                |
| selective                 | Boolean                                              | <p><em>Optional</em>. Use this parameter if you want to show the keyboard to specific users only. Targets: 1) users that are @mentioned in the <em>text</em> of the <a href="broken-reference">Message</a> object; 2) if the bot's message is a reply to a message in the same chat and forum topic, sender of the original message.</p><p><em>Example:</em> A user requests to change the bot's language, bot replies to the request with a keyboard to select the new language. Other users in the group don't see the keyboard.</p> |

**KeyboardButton**

This object represents one button of the reply keyboard. For simple text buttons, _String_ can be used instead of this object to specify the button text. The optional fields _web\_app_, _request\_users_, _request\_chat_, _request\_contact_, _request\_location_, and _request\_poll_ are mutually exclusive.

| Field             | Type                                           | Description                                                                                                                                                                                                    |
| ----------------- | ---------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| text              | String                                         | Text of the button. If none of the optional fields are used, it will be sent as a message when the button is pressed                                                                                           |
| request\_users    | [KeyboardButtonRequestUsers](broken-reference) | _Optional._ If specified, pressing the button will open a list of suitable users. Identifiers of selected users will be sent to the bot in a “users\_shared” service message. Available in private chats only. |
| request\_chat     | [KeyboardButtonRequestChat](broken-reference)  | _Optional._ If specified, pressing the button will open a list of suitable chats. Tapping on a chat will send its identifier to the bot in a “chat\_shared” service message. Available in private chats only.  |
| request\_contact  | Boolean                                        | _Optional_. If _True_, the user's phone number will be sent as a contact when the button is pressed. Available in private chats only.                                                                          |
| request\_location | Boolean                                        | _Optional_. If _True_, the user's current location will be sent when the button is pressed. Available in private chats only.                                                                                   |
| request\_poll     | [KeyboardButtonPollType](broken-reference)     | _Optional_. If specified, the user will be asked to create a poll and send it to the bot when the button is pressed. Available in private chats only.                                                          |
| web\_app          | [WebAppInfo](broken-reference)                 | _Optional_. If specified, the described Web App will be launched when the button is pressed. The Web App will be able to send a “web\_app\_data” service message. Available in private chats only.             |

**Note:** _request\_users_ and _request\_chat_ options will only work in Telegram versions released after 3 February, 2023. Older clients will display _unsupported message_.

**KeyboardButtonRequestUsers**

This object defines the criteria used to request suitable users. The identifiers of the selected users will be shared with the bot when the corresponding button is pressed. [More about requesting users »](https://about/bots/features#chat-and-user-selection)

| Field             | Type    | Description                                                                                                                                            |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| request\_id       | Integer | Signed 32-bit identifier of the request that will be received back in the [UsersShared](broken-reference) object. Must be unique within the message    |
| user\_is\_bot     | Boolean | _Optional_. Pass _True_ to request bots, pass _False_ to request regular users. If not specified, no additional restrictions are applied.              |
| user\_is\_premium | Boolean | _Optional_. Pass _True_ to request premium users, pass _False_ to request non-premium users. If not specified, no additional restrictions are applied. |
| max\_quantity     | Integer | _Optional_. The maximum number of users to be selected; 1-10. Defaults to 1.                                                                           |

**KeyboardButtonRequestChat**

This object defines the criteria used to request a suitable chat. The identifier of the selected chat will be shared with the bot when the corresponding button is pressed. [More about requesting chats »](https://about/bots/features#chat-and-user-selection)

| Field                       | Type                                        | Description                                                                                                                                                                                                                      |
| --------------------------- | ------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| request\_id                 | Integer                                     | Signed 32-bit identifier of the request, which will be received back in the [ChatShared](broken-reference) object. Must be unique within the message                                                                             |
| chat\_is\_channel           | Boolean                                     | Pass _True_ to request a channel chat, pass _False_ to request a group or a supergroup chat.                                                                                                                                     |
| chat\_is\_forum             | Boolean                                     | _Optional_. Pass _True_ to request a forum supergroup, pass _False_ to request a non-forum chat. If not specified, no additional restrictions are applied.                                                                       |
| chat\_has\_username         | Boolean                                     | _Optional_. Pass _True_ to request a supergroup or a channel with a username, pass _False_ to request a chat without a username. If not specified, no additional restrictions are applied.                                       |
| chat\_is\_created           | Boolean                                     | _Optional_. Pass _True_ to request a chat owned by the user. Otherwise, no additional restrictions are applied.                                                                                                                  |
| user\_administrator\_rights | [ChatAdministratorRights](broken-reference) | _Optional_. A JSON-serialized object listing the required administrator rights of the user in the chat. The rights must be a superset of _bot\_administrator\_rights_. If not specified, no additional restrictions are applied. |
| bot\_administrator\_rights  | [ChatAdministratorRights](broken-reference) | _Optional_. A JSON-serialized object listing the required administrator rights of the bot in the chat. The rights must be a subset of _user\_administrator\_rights_. If not specified, no additional restrictions are applied.   |
| bot\_is\_member             | Boolean                                     | _Optional_. Pass _True_ to request a chat with the bot as a member. Otherwise, no additional restrictions are applied.                                                                                                           |

**KeyboardButtonPollType**

This object represents type of a poll, which is allowed to be created and sent when the corresponding button is pressed.

| Field | Type   | Description                                                                                                                                                                                                                    |
| ----- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| type  | String | _Optional_. If _quiz_ is passed, the user will be allowed to create only polls in the quiz mode. If _regular_ is passed, only regular polls will be allowed. Otherwise, the user will be allowed to create a poll of any type. |

**ReplyKeyboardRemove**

Upon receiving a message with this object, Telegram clients will remove the current custom keyboard and display the default letter-keyboard. By default, custom keyboards are displayed until a new keyboard is sent by a bot. An exception is made for one-time keyboards that are hidden immediately after the user presses a button (see [ReplyKeyboardMarkup](broken-reference)).

| Field            | Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ---------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| remove\_keyboard | True    | Requests clients to remove the custom keyboard (user will not be able to summon this keyboard; if you want to hide the keyboard from sight but keep it accessible, use _one\_time\_keyboard_ in [ReplyKeyboardMarkup](broken-reference))                                                                                                                                                                                                                                                                                                                                     |
| selective        | Boolean | <p><em>Optional</em>. Use this parameter if you want to remove the keyboard for specific users only. Targets: 1) users that are @mentioned in the <em>text</em> of the <a href="broken-reference">Message</a> object; 2) if the bot's message is a reply to a message in the same chat and forum topic, sender of the original message.</p><p><em>Example:</em> A user votes in a poll, bot returns confirmation message in reply to the vote and removes the keyboard for that user, while still showing the keyboard with poll options to users who haven't voted yet.</p> |

**InlineKeyboardMarkup**

This object represents an [inline keyboard](https://about/bots/features#inline-keyboards) that appears right next to the message it belongs to.

| Field            | Type                                                       | Description                                                                                            |
| ---------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| inline\_keyboard | Array of Array of [InlineKeyboardButton](broken-reference) | Array of button rows, each represented by an Array of [InlineKeyboardButton](broken-reference) objects |

**InlineKeyboardButton**

This object represents one button of an inline keyboard. You **must** use exactly one of the optional fields.

| Field                                | Type                                            | Description                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------------ | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| text                                 | String                                          | Label text on the button                                                                                                                                                                                                                                                                                                                                                       |
| url                                  | String                                          | _Optional_. HTTP or tg:// URL to be opened when the button is pressed. Links `tg://user?id=<user_id>` can be used to mention a user by their identifier without using a username, if this is allowed by their privacy settings.                                                                                                                                                |
| callback\_data                       | String                                          | _Optional_. Data to be sent in a [callback query](broken-reference) to the bot when button is pressed, 1-64 bytes                                                                                                                                                                                                                                                              |
| web\_app                             | [WebAppInfo](broken-reference)                  | _Optional_. Description of the Web App that will be launched when the user presses the button. The Web App will be able to send an arbitrary message on behalf of the user using the method [answerWebAppQuery](broken-reference). Available only in private chats between a user and the bot.                                                                                 |
| login\_url                           | [LoginUrl](broken-reference)                    | _Optional_. An HTTPS URL used to automatically authorize the user. Can be used as a replacement for the Telegram Login Widget.                                                                                                                                                                                                                                                 |
| switch\_inline\_query                | String                                          | _Optional_. If set, pressing the button will prompt the user to select one of their chats, open that chat and insert the bot's username and the specified inline query in the input field. May be empty, in which case just the bot's username will be inserted.                                                                                                               |
| switch\_inline\_query\_current\_chat | String                                          | <p><em>Optional</em>. If set, pressing the button will insert the bot's username and the specified inline query in the current chat's input field. May be empty, in which case only the bot's username will be inserted.</p><p>This offers a quick way for the user to open your bot in inline mode in the same chat - good for selecting something from multiple options.</p> |
| switch\_inline\_query\_chosen\_chat  | [SwitchInlineQueryChosenChat](broken-reference) | _Optional_. If set, pressing the button will prompt the user to select one of their chats of the specified type, open that chat and insert the bot's username and the specified inline query in the input field                                                                                                                                                                |
| callback\_game                       | [CallbackGame](broken-reference)                | <p><em>Optional</em>. Description of the game that will be launched when the user presses the button.</p><p><strong>NOTE:</strong> This type of button <strong>must</strong> always be the first button in the first row.</p>                                                                                                                                                  |
| pay                                  | Boolean                                         | <p><em>Optional</em>. Specify <em>True</em>, to send a <a href="broken-reference">Pay button</a>.</p><p><strong>NOTE:</strong> This type of button <strong>must</strong> always be the first button in the first row and can only be used in invoice messages.</p>                                                                                                             |

**LoginUrl**

This object represents a parameter of the inline keyboard button used to automatically authorize a user. Serves as a great replacement for the Telegram Login Widget when the user is coming from Telegram. All the user needs to do is tap/click a button and confirm that they want to log in:



Telegram apps support these buttons as of [version 5.7](https://telegram.org/blog/privacy-discussions-web-bots#meet-seamless-web-bots).

> Sample bot: [@discussbot](https://t.me/discussbot)

| Field                  | Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ---------------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| url                    | String  | <p>An HTTPS URL to be opened with user authorization data added to the query string when the button is pressed. If the user refuses to provide authorization data, the original URL without information about the user will be opened. The data added is the same as described in <a href="https://about/widgets/login#receiving-authorization-data">Receiving authorization data</a>.</p><p><strong>NOTE:</strong> You <strong>must</strong> always check the hash of the received data to verify the authentication and the integrity of the data as described in <a href="https://about/widgets/login#checking-authorization">Checking authorization</a>.</p> |
| forward\_text          | String  | _Optional_. New text of the button in forwarded messages.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| bot\_username          | String  | _Optional_. Username of a bot, which will be used for user authorization. See [Setting up a bot](https://about/widgets/login#setting-up-a-bot) for more details. If not specified, the current bot's username will be assumed. The _url_'s domain must be the same as the domain linked with the bot. See [Linking your domain to the bot](https://about/widgets/login#linking-your-domain-to-the-bot) for more details.                                                                                                                                                                                                                                         |
| request\_write\_access | Boolean | _Optional_. Pass _True_ to request the permission for your bot to send messages to the user.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

**SwitchInlineQueryChosenChat**

This object represents an inline button that switches the current user to inline mode in a chosen chat, with an optional default inline query.

| Field                 | Type    | Description                                                                                                                     |
| --------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------- |
| query                 | String  | _Optional_. The default inline query to be inserted in the input field. If left empty, only the bot's username will be inserted |
| allow\_user\_chats    | Boolean | _Optional_. True, if private chats with users can be chosen                                                                     |
| allow\_bot\_chats     | Boolean | _Optional_. True, if private chats with bots can be chosen                                                                      |
| allow\_group\_chats   | Boolean | _Optional_. True, if group and supergroup chats can be chosen                                                                   |
| allow\_channel\_chats | Boolean | _Optional_. True, if channel chats can be chosen                                                                                |

**CallbackQuery**

This object represents an incoming callback query from a callback button in an [inline keyboard](https://about/bots/features#inline-keyboards). If the button that originated the query was attached to a message sent by the bot, the field _message_ will be present. If the button was attached to a message sent via the bot (in [inline mode](broken-reference)), the field _inline\_message\_id_ will be present. Exactly one of the fields _data_ or _game\_short\_name_ will be present.

| Field               | Type                                         | Description                                                                                                                                                        |
| ------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id                  | String                                       | Unique identifier for this query                                                                                                                                   |
| from                | [User](broken-reference)                     | Sender                                                                                                                                                             |
| message             | [MaybeInaccessibleMessage](broken-reference) | _Optional_. Message sent by the bot with the callback button that originated the query                                                                             |
| inline\_message\_id | String                                       | _Optional_. Identifier of the message sent via the bot in inline mode, that originated the query.                                                                  |
| chat\_instance      | String                                       | Global identifier, uniquely corresponding to the chat to which the message with the callback button was sent. Useful for high scores in [games](broken-reference). |
| data                | String                                       | _Optional_. Data associated with the callback button. Be aware that the message originated the query can contain no callback buttons with this data.               |
| game\_short\_name   | String                                       | _Optional_. Short name of a [Game](broken-reference) to be returned, serves as the unique identifier for the game                                                  |

> **NOTE:** After the user presses a callback button, Telegram clients will display a progress bar until you call [answerCallbackQuery](broken-reference). It is, therefore, necessary to react by calling [answerCallbackQuery](broken-reference) even if no notification to the user is needed (e.g., without specifying any of the optional parameters).

**ForceReply**

Upon receiving a message with this object, Telegram clients will display a reply interface to the user (act as if the user has selected the bot's message and tapped 'Reply'). This can be extremely useful if you want to create user-friendly step-by-step interfaces without having to sacrifice [privacy mode](https://about/bots/features#privacy-mode).

| Field                     | Type    | Description                                                                                                                                                                                                                                                                                          |
| ------------------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| force\_reply              | True    | Shows reply interface to the user, as if they manually selected the bot's message and tapped 'Reply'                                                                                                                                                                                                 |
| input\_field\_placeholder | String  | _Optional_. The placeholder to be shown in the input field when the reply is active; 1-64 characters                                                                                                                                                                                                 |
| selective                 | Boolean | _Optional_. Use this parameter if you want to force reply from specific users only. Targets: 1) users that are @mentioned in the _text_ of the [Message](broken-reference) object; 2) if the bot's message is a reply to a message in the same chat and forum topic, sender of the original message. |

> **Example:** A [poll bot](https://t.me/PollBot) for groups runs in privacy mode (only receives commands, replies to its messages and mentions). There could be two ways to create a new poll:
>
> * Explain the user how to send a command with parameters (e.g. /newpoll question answer1 answer2). May be appealing for hardcore users but lacks modern day polish.
> * Guide the user through a step-by-step process. 'Please send me your question', 'Cool, now let's add the first answer option', 'Great. Keep adding answer options, then send /done when you're ready'.
>
> The last option is definitely more attractive. And if you use [ForceReply](broken-reference) in your bot's questions, it will receive the user's answers even if it only receives replies, commands and mentions - without any extra work for the user.

**ChatPhoto**

This object represents a chat photo.

| Field                   | Type   | Description                                                                                                                                                           |
| ----------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| small\_file\_id         | String | File identifier of small (160x160) chat photo. This file\_id can be used only for photo download and only for as long as the photo is not changed.                    |
| small\_file\_unique\_id | String | Unique file identifier of small (160x160) chat photo, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file. |
| big\_file\_id           | String | File identifier of big (640x640) chat photo. This file\_id can be used only for photo download and only for as long as the photo is not changed.                      |
| big\_file\_unique\_id   | String | Unique file identifier of big (640x640) chat photo, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file.   |

**ChatInviteLink**

Represents an invite link for a chat.

| Field                         | Type                     | Description                                                                                                                                 |
| ----------------------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| invite\_link                  | String                   | The invite link. If the link was created by another chat administrator, then the second part of the link will be replaced with “…”.         |
| creator                       | [User](broken-reference) | Creator of the link                                                                                                                         |
| creates\_join\_request        | Boolean                  | _True_, if users joining the chat via the link need to be approved by chat administrators                                                   |
| is\_primary                   | Boolean                  | _True_, if the link is primary                                                                                                              |
| is\_revoked                   | Boolean                  | _True_, if the link is revoked                                                                                                              |
| name                          | String                   | _Optional_. Invite link name                                                                                                                |
| expire\_date                  | Integer                  | _Optional_. Point in time (Unix timestamp) when the link will expire or has been expired                                                    |
| member\_limit                 | Integer                  | _Optional_. The maximum number of users that can be members of the chat simultaneously after joining the chat via this invite link; 1-99999 |
| pending\_join\_request\_count | Integer                  | _Optional_. Number of pending join requests created using this link                                                                         |

**ChatAdministratorRights**

Represents the rights of an administrator in a chat.

| Field                     | Type    | Description                                                                                                                                                                                                                         |
| ------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| is\_anonymous             | Boolean | _True_, if the user's presence in the chat is hidden                                                                                                                                                                                |
| can\_manage\_chat         | Boolean | _True_, if the administrator can access the chat event log, get boost list, see hidden supergroup and channel members, report spam messages and ignore slow mode. Implied by any other administrator privilege.                     |
| can\_delete\_messages     | Boolean | _True_, if the administrator can delete messages of other users                                                                                                                                                                     |
| can\_manage\_video\_chats | Boolean | _True_, if the administrator can manage video chats                                                                                                                                                                                 |
| can\_restrict\_members    | Boolean | _True_, if the administrator can restrict, ban or unban chat members, or access supergroup statistics                                                                                                                               |
| can\_promote\_members     | Boolean | _True_, if the administrator can add new administrators with a subset of their own privileges or demote administrators that they have promoted, directly or indirectly (promoted by administrators that were appointed by the user) |
| can\_change\_info         | Boolean | _True_, if the user is allowed to change the chat title, photo and other settings                                                                                                                                                   |
| can\_invite\_users        | Boolean | _True_, if the user is allowed to invite new users to the chat                                                                                                                                                                      |
| can\_post\_stories        | Boolean | _True_, if the administrator can post stories to the chat                                                                                                                                                                           |
| can\_edit\_stories        | Boolean | _True_, if the administrator can edit stories posted by other users                                                                                                                                                                 |
| can\_delete\_stories      | Boolean | _True_, if the administrator can delete stories posted by other users                                                                                                                                                               |
| can\_post\_messages       | Boolean | _Optional_. _True_, if the administrator can post messages in the channel, or access channel statistics; for channels only                                                                                                          |
| can\_edit\_messages       | Boolean | _Optional_. _True_, if the administrator can edit messages of other users and can pin messages; for channels only                                                                                                                   |
| can\_pin\_messages        | Boolean | _Optional_. _True_, if the user is allowed to pin messages; for groups and supergroups only                                                                                                                                         |
| can\_manage\_topics       | Boolean | _Optional_. _True_, if the user is allowed to create, rename, close, and reopen forum topics; for supergroups only                                                                                                                  |

**ChatMemberUpdated**

This object represents changes in the status of a chat member.

| Field                           | Type                               | Description                                                                                                        |
| ------------------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| chat                            | [Chat](broken-reference)           | Chat the user belongs to                                                                                           |
| from                            | [User](broken-reference)           | Performer of the action, which resulted in the change                                                              |
| date                            | Integer                            | Date the change was done in Unix time                                                                              |
| old\_chat\_member               | [ChatMember](broken-reference)     | Previous information about the chat member                                                                         |
| new\_chat\_member               | [ChatMember](broken-reference)     | New information about the chat member                                                                              |
| invite\_link                    | [ChatInviteLink](broken-reference) | _Optional_. Chat invite link, which was used by the user to join the chat; for joining by invite link events only. |
| via\_chat\_folder\_invite\_link | Boolean                            | _Optional_. True, if the user joined the chat via a chat folder invite link                                        |

**ChatMember**

This object contains information about one member of a chat. Currently, the following 6 types of chat members are supported:

* [ChatMemberOwner](broken-reference)
* [ChatMemberAdministrator](broken-reference)
* [ChatMemberMember](broken-reference)
* [ChatMemberRestricted](broken-reference)
* [ChatMemberLeft](broken-reference)
* [ChatMemberBanned](broken-reference)

**ChatMemberOwner**

Represents a [chat member](broken-reference) that owns the chat and has all administrator privileges.

| Field         | Type                     | Description                                          |
| ------------- | ------------------------ | ---------------------------------------------------- |
| status        | String                   | The member's status in the chat, always “creator”    |
| user          | [User](broken-reference) | Information about the user                           |
| is\_anonymous | Boolean                  | _True_, if the user's presence in the chat is hidden |
| custom\_title | String                   | _Optional_. Custom title for this user               |

**ChatMemberAdministrator**

Represents a [chat member](broken-reference) that has some additional privileges.

| Field                     | Type                     | Description                                                                                                                                                                                                                         |
| ------------------------- | ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| status                    | String                   | The member's status in the chat, always “administrator”                                                                                                                                                                             |
| user                      | [User](broken-reference) | Information about the user                                                                                                                                                                                                          |
| can\_be\_edited           | Boolean                  | _True_, if the bot is allowed to edit administrator privileges of that user                                                                                                                                                         |
| is\_anonymous             | Boolean                  | _True_, if the user's presence in the chat is hidden                                                                                                                                                                                |
| can\_manage\_chat         | Boolean                  | _True_, if the administrator can access the chat event log, get boost list, see hidden supergroup and channel members, report spam messages and ignore slow mode. Implied by any other administrator privilege.                     |
| can\_delete\_messages     | Boolean                  | _True_, if the administrator can delete messages of other users                                                                                                                                                                     |
| can\_manage\_video\_chats | Boolean                  | _True_, if the administrator can manage video chats                                                                                                                                                                                 |
| can\_restrict\_members    | Boolean                  | _True_, if the administrator can restrict, ban or unban chat members, or access supergroup statistics                                                                                                                               |
| can\_promote\_members     | Boolean                  | _True_, if the administrator can add new administrators with a subset of their own privileges or demote administrators that they have promoted, directly or indirectly (promoted by administrators that were appointed by the user) |
| can\_change\_info         | Boolean                  | _True_, if the user is allowed to change the chat title, photo and other settings                                                                                                                                                   |
| can\_invite\_users        | Boolean                  | _True_, if the user is allowed to invite new users to the chat                                                                                                                                                                      |
| can\_post\_stories        | Boolean                  | _True_, if the administrator can post stories to the chat                                                                                                                                                                           |
| can\_edit\_stories        | Boolean                  | _True_, if the administrator can edit stories posted by other users                                                                                                                                                                 |
| can\_delete\_stories      | Boolean                  | _True_, if the administrator can delete stories posted by other users                                                                                                                                                               |
| can\_post\_messages       | Boolean                  | _Optional_. _True_, if the administrator can post messages in the channel, or access channel statistics; for channels only                                                                                                          |
| can\_edit\_messages       | Boolean                  | _Optional_. _True_, if the administrator can edit messages of other users and can pin messages; for channels only                                                                                                                   |
| can\_pin\_messages        | Boolean                  | _Optional_. _True_, if the user is allowed to pin messages; for groups and supergroups only                                                                                                                                         |
| can\_manage\_topics       | Boolean                  | _Optional_. _True_, if the user is allowed to create, rename, close, and reopen forum topics; for supergroups only                                                                                                                  |
| custom\_title             | String                   | _Optional_. Custom title for this user                                                                                                                                                                                              |

**ChatMemberMember**

Represents a [chat member](broken-reference) that has no additional privileges or restrictions.

| Field  | Type                     | Description                                      |
| ------ | ------------------------ | ------------------------------------------------ |
| status | String                   | The member's status in the chat, always “member” |
| user   | [User](broken-reference) | Information about the user                       |

**ChatMemberRestricted**

Represents a [chat member](broken-reference) that is under certain restrictions in the chat. Supergroups only.

| Field                         | Type                     | Description                                                                                                                 |
| ----------------------------- | ------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| status                        | String                   | The member's status in the chat, always “restricted”                                                                        |
| user                          | [User](broken-reference) | Information about the user                                                                                                  |
| is\_member                    | Boolean                  | _True_, if the user is a member of the chat at the moment of the request                                                    |
| can\_send\_messages           | Boolean                  | _True_, if the user is allowed to send text messages, contacts, giveaways, giveaway winners, invoices, locations and venues |
| can\_send\_audios             | Boolean                  | _True_, if the user is allowed to send audios                                                                               |
| can\_send\_documents          | Boolean                  | _True_, if the user is allowed to send documents                                                                            |
| can\_send\_photos             | Boolean                  | _True_, if the user is allowed to send photos                                                                               |
| can\_send\_videos             | Boolean                  | _True_, if the user is allowed to send videos                                                                               |
| can\_send\_video\_notes       | Boolean                  | _True_, if the user is allowed to send video notes                                                                          |
| can\_send\_voice\_notes       | Boolean                  | _True_, if the user is allowed to send voice notes                                                                          |
| can\_send\_polls              | Boolean                  | _True_, if the user is allowed to send polls                                                                                |
| can\_send\_other\_messages    | Boolean                  | _True_, if the user is allowed to send animations, games, stickers and use inline bots                                      |
| can\_add\_web\_page\_previews | Boolean                  | _True_, if the user is allowed to add web page previews to their messages                                                   |
| can\_change\_info             | Boolean                  | _True_, if the user is allowed to change the chat title, photo and other settings                                           |
| can\_invite\_users            | Boolean                  | _True_, if the user is allowed to invite new users to the chat                                                              |
| can\_pin\_messages            | Boolean                  | _True_, if the user is allowed to pin messages                                                                              |
| can\_manage\_topics           | Boolean                  | _True_, if the user is allowed to create forum topics                                                                       |
| until\_date                   | Integer                  | Date when restrictions will be lifted for this user; Unix time. If 0, then the user is restricted forever                   |

**ChatMemberLeft**

Represents a [chat member](broken-reference) that isn't currently a member of the chat, but may join it themselves.

| Field  | Type                     | Description                                    |
| ------ | ------------------------ | ---------------------------------------------- |
| status | String                   | The member's status in the chat, always “left” |
| user   | [User](broken-reference) | Information about the user                     |

**ChatMemberBanned**

Represents a [chat member](broken-reference) that was banned in the chat and can't return to the chat or view chat messages.

| Field       | Type                     | Description                                                                                           |
| ----------- | ------------------------ | ----------------------------------------------------------------------------------------------------- |
| status      | String                   | The member's status in the chat, always “kicked”                                                      |
| user        | [User](broken-reference) | Information about the user                                                                            |
| until\_date | Integer                  | Date when restrictions will be lifted for this user; Unix time. If 0, then the user is banned forever |

**ChatJoinRequest**

Represents a join request sent to a chat.

| Field          | Type                               | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| -------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat           | [Chat](broken-reference)           | Chat to which the request was sent                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| from           | [User](broken-reference)           | User that sent the join request                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| user\_chat\_id | Integer                            | Identifier of a private chat with the user who sent the join request. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a 64-bit integer or double-precision float type are safe for storing this identifier. The bot can use this identifier for 5 minutes to send messages until the join request is processed, assuming no other administrator contacted the user. |
| date           | Integer                            | Date the request was sent in Unix time                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| bio            | String                             | _Optional_. Bio of the user.                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| invite\_link   | [ChatInviteLink](broken-reference) | _Optional_. Chat invite link that was used by the user to send the join request                                                                                                                                                                                                                                                                                                                                                                                                                         |

**ChatPermissions**

Describes actions that a non-administrator user is allowed to take in a chat.

| Field                         | Type    | Description                                                                                                                             |
| ----------------------------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| can\_send\_messages           | Boolean | _Optional_. _True_, if the user is allowed to send text messages, contacts, giveaways, giveaway winners, invoices, locations and venues |
| can\_send\_audios             | Boolean | _Optional_. _True_, if the user is allowed to send audios                                                                               |
| can\_send\_documents          | Boolean | _Optional_. _True_, if the user is allowed to send documents                                                                            |
| can\_send\_photos             | Boolean | _Optional_. _True_, if the user is allowed to send photos                                                                               |
| can\_send\_videos             | Boolean | _Optional_. _True_, if the user is allowed to send videos                                                                               |
| can\_send\_video\_notes       | Boolean | _Optional_. _True_, if the user is allowed to send video notes                                                                          |
| can\_send\_voice\_notes       | Boolean | _Optional_. _True_, if the user is allowed to send voice notes                                                                          |
| can\_send\_polls              | Boolean | _Optional_. _True_, if the user is allowed to send polls                                                                                |
| can\_send\_other\_messages    | Boolean | _Optional_. _True_, if the user is allowed to send animations, games, stickers and use inline bots                                      |
| can\_add\_web\_page\_previews | Boolean | _Optional_. _True_, if the user is allowed to add web page previews to their messages                                                   |
| can\_change\_info             | Boolean | _Optional_. _True_, if the user is allowed to change the chat title, photo and other settings. Ignored in public supergroups            |
| can\_invite\_users            | Boolean | _Optional_. _True_, if the user is allowed to invite new users to the chat                                                              |
| can\_pin\_messages            | Boolean | _Optional_. _True_, if the user is allowed to pin messages. Ignored in public supergroups                                               |
| can\_manage\_topics           | Boolean | _Optional_. _True_, if the user is allowed to create forum topics. If omitted defaults to the value of can\_pin\_messages               |

**ChatLocation**

Represents a location to which a chat is connected.

| Field    | Type                         | Description                                                                  |
| -------- | ---------------------------- | ---------------------------------------------------------------------------- |
| location | [Location](broken-reference) | The location to which the supergroup is connected. Can't be a live location. |
| address  | String                       | Location address; 1-64 characters, as defined by the chat owner              |

**ReactionType**

This object describes the type of a reaction. Currently, it can be one of

* [ReactionTypeEmoji](broken-reference)
* [ReactionTypeCustomEmoji](broken-reference)

**ReactionTypeEmoji**

The reaction is based on an emoji.

| Field | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ----- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type  | String | Type of the reaction, always “emoji”                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| emoji | String | Reaction emoji. Currently, it can be one of "![👍](https://telegram.org/img/emoji/40/F09F918D.png)", "![👎](https://telegram.org/img/emoji/40/F09F918E.png)", "![❤](https://telegram.org/img/emoji/40/E29DA4.png)", "![🔥](https://telegram.org/img/emoji/40/F09F94A5.png)", "![🥰](https://telegram.org/img/emoji/40/F09FA5B0.png)", "![👏](https://telegram.org/img/emoji/40/F09F918F.png)", "![😁](https://telegram.org/img/emoji/40/F09F9881.png)", "![🤔](https://telegram.org/img/emoji/40/F09FA494.png)", "![🤯](https://telegram.org/img/emoji/40/F09FA4AF.png)", "![😱](https://telegram.org/img/emoji/40/F09F98B1.png)", "![🤬](https://telegram.org/img/emoji/40/F09FA4AC.png)", "![😢](https://telegram.org/img/emoji/40/F09F98A2.png)", "![🎉](https://telegram.org/img/emoji/40/F09F8E89.png)", "![🤩](https://telegram.org/img/emoji/40/F09FA4A9.png)", "![🤮](https://telegram.org/img/emoji/40/F09FA4AE.png)", "![💩](https://telegram.org/img/emoji/40/F09F92A9.png)", "![🙏](https://telegram.org/img/emoji/40/F09F998F.png)", "![👌](https://telegram.org/img/emoji/40/F09F918C.png)", "![🕊](https://telegram.org/img/emoji/40/F09F958A.png)", "![🤡](https://telegram.org/img/emoji/40/F09FA4A1.png)", "![🥱](https://telegram.org/img/emoji/40/F09FA5B1.png)", "![🥴](https://telegram.org/img/emoji/40/F09FA5B4.png)", "![😍](https://telegram.org/img/emoji/40/F09F988D.png)", "![🐳](https://telegram.org/img/emoji/40/F09F90B3.png)", "![❤‍🔥](https://telegram.org/img/emoji/40/E29DA4E2808DF09F94A5.png)", "![🌚](https://telegram.org/img/emoji/40/F09F8C9A.png)", "![🌭](https://telegram.org/img/emoji/40/F09F8CAD.png)", "![💯](https://telegram.org/img/emoji/40/F09F92AF.png)", "![🤣](https://telegram.org/img/emoji/40/F09FA4A3.png)", "![⚡](https://telegram.org/img/emoji/40/E29AA1.png)", "![🍌](https://telegram.org/img/emoji/40/F09F8D8C.png)", "![🏆](https://telegram.org/img/emoji/40/F09F8F86.png)", "![💔](https://telegram.org/img/emoji/40/F09F9294.png)", "![🤨](https://telegram.org/img/emoji/40/F09FA4A8.png)", "![😐](https://telegram.org/img/emoji/40/F09F9890.png)", "![🍓](https://telegram.org/img/emoji/40/F09F8D93.png)", "![🍾](https://telegram.org/img/emoji/40/F09F8DBE.png)", "![💋](https://telegram.org/img/emoji/40/F09F928B.png)", "![🖕](https://telegram.org/img/emoji/40/F09F9695.png)", "![😈](https://telegram.org/img/emoji/40/F09F9888.png)", "![😴](https://telegram.org/img/emoji/40/F09F98B4.png)", "![😭](https://telegram.org/img/emoji/40/F09F98AD.png)", "![🤓](https://telegram.org/img/emoji/40/F09FA493.png)", "![👻](https://telegram.org/img/emoji/40/F09F91BB.png)", "![👨‍💻](https://telegram.org/img/emoji/40/F09F91A8E2808DF09F92BB.png)", "![👀](https://telegram.org/img/emoji/40/F09F9180.png)", "![🎃](https://telegram.org/img/emoji/40/F09F8E83.png)", "![🙈](https://telegram.org/img/emoji/40/F09F9988.png)", "![😇](https://telegram.org/img/emoji/40/F09F9887.png)", "![😨](https://telegram.org/img/emoji/40/F09F98A8.png)", "![🤝](https://telegram.org/img/emoji/40/F09FA49D.png)", "![✍](https://telegram.org/img/emoji/40/E29C8D.png)", "![🤗](https://telegram.org/img/emoji/40/F09FA497.png)", "![🫡](https://telegram.org/img/emoji/40/F09FABA1.png)", "![🎅](https://telegram.org/img/emoji/40/F09F8E85.png)", "![🎄](https://telegram.org/img/emoji/40/F09F8E84.png)", "![☃](https://telegram.org/img/emoji/40/E29883.png)", "![💅](https://telegram.org/img/emoji/40/F09F9285.png)", "![🤪](https://telegram.org/img/emoji/40/F09FA4AA.png)", "![🗿](https://telegram.org/img/emoji/40/F09F97BF.png)", "![🆒](https://telegram.org/img/emoji/40/F09F8692.png)", "![💘](https://telegram.org/img/emoji/40/F09F9298.png)", "![🙉](https://telegram.org/img/emoji/40/F09F9989.png)", "![🦄](https://telegram.org/img/emoji/40/F09FA684.png)", "![😘](https://telegram.org/img/emoji/40/F09F9898.png)", "![💊](https://telegram.org/img/emoji/40/F09F928A.png)", "![🙊](https://telegram.org/img/emoji/40/F09F998A.png)", "![😎](https://telegram.org/img/emoji/40/F09F988E.png)", "![👾](https://telegram.org/img/emoji/40/F09F91BE.png)", "![🤷‍♂](https://telegram.org/img/emoji/40/F09FA4B7E2808DE29982.png)", "![🤷](https://telegram.org/img/emoji/40/F09FA4B7.png)", "![🤷‍♀](https://telegram.org/img/emoji/40/F09FA4B7E2808DE29980.png)", "![😡](https://telegram.org/img/emoji/40/F09F98A1.png)" |

**ReactionTypeCustomEmoji**

The reaction is based on a custom emoji.

| Field             | Type   | Description                                  |
| ----------------- | ------ | -------------------------------------------- |
| type              | String | Type of the reaction, always “custom\_emoji” |
| custom\_emoji\_id | String | Custom emoji identifier                      |

**ReactionCount**

Represents a reaction added to a message along with the number of times it was added.

| Field        | Type                             | Description                            |
| ------------ | -------------------------------- | -------------------------------------- |
| type         | [ReactionType](broken-reference) | Type of the reaction                   |
| total\_count | Integer                          | Number of times the reaction was added |

**MessageReactionUpdated**

This object represents a change of a reaction on a message performed by a user.

| Field         | Type                                      | Description                                                                                |
| ------------- | ----------------------------------------- | ------------------------------------------------------------------------------------------ |
| chat          | [Chat](broken-reference)                  | The chat containing the message the user reacted to                                        |
| message\_id   | Integer                                   | Unique identifier of the message inside the chat                                           |
| user          | [User](broken-reference)                  | _Optional_. The user that changed the reaction, if the user isn't anonymous                |
| actor\_chat   | [Chat](broken-reference)                  | _Optional_. The chat on behalf of which the reaction was changed, if the user is anonymous |
| date          | Integer                                   | Date of the change in Unix time                                                            |
| old\_reaction | Array of [ReactionType](broken-reference) | Previous list of reaction types that were set by the user                                  |
| new\_reaction | Array of [ReactionType](broken-reference) | New list of reaction types that have been set by the user                                  |

**MessageReactionCountUpdated**

This object represents reaction changes on a message with anonymous reactions.

| Field       | Type                                       | Description                                       |
| ----------- | ------------------------------------------ | ------------------------------------------------- |
| chat        | [Chat](broken-reference)                   | The chat containing the message                   |
| message\_id | Integer                                    | Unique message identifier inside the chat         |
| date        | Integer                                    | Date of the change in Unix time                   |
| reactions   | Array of [ReactionCount](broken-reference) | List of reactions that are present on the message |

**ForumTopic**

This object represents a forum topic.

| Field                   | Type    | Description                                                               |
| ----------------------- | ------- | ------------------------------------------------------------------------- |
| message\_thread\_id     | Integer | Unique identifier of the forum topic                                      |
| name                    | String  | Name of the topic                                                         |
| icon\_color             | Integer | Color of the topic icon in RGB format                                     |
| icon\_custom\_emoji\_id | String  | _Optional_. Unique identifier of the custom emoji shown as the topic icon |

**BotCommand**

This object represents a bot command.

| Field       | Type   | Description                                                                                               |
| ----------- | ------ | --------------------------------------------------------------------------------------------------------- |
| command     | String | Text of the command; 1-32 characters. Can contain only lowercase English letters, digits and underscores. |
| description | String | Description of the command; 1-256 characters.                                                             |

**BotCommandScope**

This object represents the scope to which bot commands are applied. Currently, the following 7 scopes are supported:

* [BotCommandScopeDefault](broken-reference)
* [BotCommandScopeAllPrivateChats](broken-reference)
* [BotCommandScopeAllGroupChats](broken-reference)
* [BotCommandScopeAllChatAdministrators](broken-reference)
* [BotCommandScopeChat](broken-reference)
* [BotCommandScopeChatAdministrators](broken-reference)
* [BotCommandScopeChatMember](broken-reference)

**Determining list of commands**

The following algorithm is used to determine the list of commands for a particular user viewing the bot menu. The first list of commands which is set is returned:

**Commands in the chat with the bot**

* botCommandScopeChat + language\_code
* botCommandScopeChat
* botCommandScopeAllPrivateChats + language\_code
* botCommandScopeAllPrivateChats
* botCommandScopeDefault + language\_code
* botCommandScopeDefault

**Commands in group and supergroup chats**

* botCommandScopeChatMember + language\_code
* botCommandScopeChatMember
* botCommandScopeChatAdministrators + language\_code (administrators only)
* botCommandScopeChatAdministrators (administrators only)
* botCommandScopeChat + language\_code
* botCommandScopeChat
* botCommandScopeAllChatAdministrators + language\_code (administrators only)
* botCommandScopeAllChatAdministrators (administrators only)
* botCommandScopeAllGroupChats + language\_code
* botCommandScopeAllGroupChats
* botCommandScopeDefault + language\_code
* botCommandScopeDefault

**BotCommandScopeDefault**

Represents the default [scope](broken-reference) of bot commands. Default commands are used if no commands with a [narrower scope](broken-reference) are specified for the user.

| Field | Type   | Description                   |
| ----- | ------ | ----------------------------- |
| type  | String | Scope type, must be _default_ |

**BotCommandScopeAllPrivateChats**

Represents the [scope](broken-reference) of bot commands, covering all private chats.

| Field | Type   | Description                               |
| ----- | ------ | ----------------------------------------- |
| type  | String | Scope type, must be _all\_private\_chats_ |

**BotCommandScopeAllGroupChats**

Represents the [scope](broken-reference) of bot commands, covering all group and supergroup chats.

| Field | Type   | Description                             |
| ----- | ------ | --------------------------------------- |
| type  | String | Scope type, must be _all\_group\_chats_ |

**BotCommandScopeAllChatAdministrators**

Represents the [scope](broken-reference) of bot commands, covering all group and supergroup chat administrators.

| Field | Type   | Description                                     |
| ----- | ------ | ----------------------------------------------- |
| type  | String | Scope type, must be _all\_chat\_administrators_ |

**BotCommandScopeChat**

Represents the [scope](broken-reference) of bot commands, covering a specific chat.

| Field    | Type              | Description                                                                                                      |
| -------- | ----------------- | ---------------------------------------------------------------------------------------------------------------- |
| type     | String            | Scope type, must be _chat_                                                                                       |
| chat\_id | Integer or String | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |

**BotCommandScopeChatAdministrators**

Represents the [scope](broken-reference) of bot commands, covering all administrators of a specific group or supergroup chat.

| Field    | Type              | Description                                                                                                      |
| -------- | ----------------- | ---------------------------------------------------------------------------------------------------------------- |
| type     | String            | Scope type, must be _chat\_administrators_                                                                       |
| chat\_id | Integer or String | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |

**BotCommandScopeChatMember**

Represents the [scope](broken-reference) of bot commands, covering a specific member of a group or supergroup chat.

| Field    | Type              | Description                                                                                                      |
| -------- | ----------------- | ---------------------------------------------------------------------------------------------------------------- |
| type     | String            | Scope type, must be _chat\_member_                                                                               |
| chat\_id | Integer or String | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |
| user\_id | Integer           | Unique identifier of the target user                                                                             |

**BotName**

This object represents the bot's name.

| Field | Type   | Description    |
| ----- | ------ | -------------- |
| name  | String | The bot's name |

**BotDescription**

This object represents the bot's description.

| Field       | Type   | Description           |
| ----------- | ------ | --------------------- |
| description | String | The bot's description |

**BotShortDescription**

This object represents the bot's short description.

| Field              | Type   | Description                 |
| ------------------ | ------ | --------------------------- |
| short\_description | String | The bot's short description |

**MenuButton**

This object describes the bot's menu button in a private chat. It should be one of

* [MenuButtonCommands](broken-reference)
* [MenuButtonWebApp](broken-reference)
* [MenuButtonDefault](broken-reference)

If a menu button other than [MenuButtonDefault](broken-reference) is set for a private chat, then it is applied in the chat. Otherwise the default menu button is applied. By default, the menu button opens the list of bot commands.

**MenuButtonCommands**

Represents a menu button, which opens the bot's list of commands.

| Field | Type   | Description                            |
| ----- | ------ | -------------------------------------- |
| type  | String | Type of the button, must be _commands_ |

**MenuButtonWebApp**

Represents a menu button, which launches a Web App.

| Field    | Type                           | Description                                                                                                                                                                                                            |
| -------- | ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type     | String                         | Type of the button, must be _web\_app_                                                                                                                                                                                 |
| text     | String                         | Text on the button                                                                                                                                                                                                     |
| web\_app | [WebAppInfo](broken-reference) | Description of the Web App that will be launched when the user presses the button. The Web App will be able to send an arbitrary message on behalf of the user using the method [answerWebAppQuery](broken-reference). |

**MenuButtonDefault**

Describes that no specific value for the menu button was set.

| Field | Type   | Description                           |
| ----- | ------ | ------------------------------------- |
| type  | String | Type of the button, must be _default_ |

**ChatBoostSource**

This object describes the source of a chat boost. It can be one of

* [ChatBoostSourcePremium](broken-reference)
* [ChatBoostSourceGiftCode](broken-reference)
* [ChatBoostSourceGiveaway](broken-reference)

**ChatBoostSourcePremium**

The boost was obtained by subscribing to Telegram Premium or by gifting a Telegram Premium subscription to another user.

| Field  | Type                     | Description                           |
| ------ | ------------------------ | ------------------------------------- |
| source | String                   | Source of the boost, always “premium” |
| user   | [User](broken-reference) | User that boosted the chat            |

**ChatBoostSourceGiftCode**

The boost was obtained by the creation of Telegram Premium gift codes to boost a chat. Each such code boosts the chat 4 times for the duration of the corresponding Telegram Premium subscription.

| Field  | Type                     | Description                              |
| ------ | ------------------------ | ---------------------------------------- |
| source | String                   | Source of the boost, always “gift\_code” |
| user   | [User](broken-reference) | User for which the gift code was created |

**ChatBoostSourceGiveaway**

The boost was obtained by the creation of a Telegram Premium giveaway. This boosts the chat 4 times for the duration of the corresponding Telegram Premium subscription.

| Field                 | Type                     | Description                                                                                                                                 |
| --------------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| source                | String                   | Source of the boost, always “giveaway”                                                                                                      |
| giveaway\_message\_id | Integer                  | Identifier of a message in the chat with the giveaway; the message could have been deleted already. May be 0 if the message isn't sent yet. |
| user                  | [User](broken-reference) | _Optional_. User that won the prize in the giveaway if any                                                                                  |
| is\_unclaimed         | True                     | _Optional_. True, if the giveaway was completed, but there was no user to win the prize                                                     |

**ChatBoost**

This object contains information about a chat boost.

| Field            | Type                                | Description                                                                                                                              |
| ---------------- | ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| boost\_id        | String                              | Unique identifier of the boost                                                                                                           |
| add\_date        | Integer                             | Point in time (Unix timestamp) when the chat was boosted                                                                                 |
| expiration\_date | Integer                             | Point in time (Unix timestamp) when the boost will automatically expire, unless the booster's Telegram Premium subscription is prolonged |
| source           | [ChatBoostSource](broken-reference) | Source of the added boost                                                                                                                |

**ChatBoostUpdated**

This object represents a boost added to a chat or changed.

| Field | Type                          | Description                      |
| ----- | ----------------------------- | -------------------------------- |
| chat  | [Chat](broken-reference)      | Chat which was boosted           |
| boost | [ChatBoost](broken-reference) | Information about the chat boost |

**ChatBoostRemoved**

This object represents a boost removed from a chat.

| Field        | Type                                | Description                                               |
| ------------ | ----------------------------------- | --------------------------------------------------------- |
| chat         | [Chat](broken-reference)            | Chat which was boosted                                    |
| boost\_id    | String                              | Unique identifier of the boost                            |
| remove\_date | Integer                             | Point in time (Unix timestamp) when the boost was removed |
| source       | [ChatBoostSource](broken-reference) | Source of the removed boost                               |

**UserChatBoosts**

This object represents a list of boosts added to a chat by a user.

| Field  | Type                                   | Description                                      |
| ------ | -------------------------------------- | ------------------------------------------------ |
| boosts | Array of [ChatBoost](broken-reference) | The list of boosts added to the chat by the user |

**ResponseParameters**

Describes why a request was unsuccessful.

| Field                 | Type    | Description                                                                                                                                                                                                                                                                                                                                                             |
| --------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| migrate\_to\_chat\_id | Integer | _Optional_. The group has been migrated to a supergroup with the specified identifier. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this identifier. |
| retry\_after          | Integer | _Optional_. In case of exceeding flood control, the number of seconds left to wait before the request can be repeated                                                                                                                                                                                                                                                   |

**InputMedia**

This object represents the content of a media message to be sent. It should be one of

* [InputMediaAnimation](broken-reference)
* [InputMediaDocument](broken-reference)
* [InputMediaAudio](broken-reference)
* [InputMediaPhoto](broken-reference)
* [InputMediaVideo](broken-reference)

**InputMediaPhoto**

Represents a photo to be sent.

| Field             | Type                                       | Description                                                                                                                                                                                                                                                                                                                                     |
| ----------------- | ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type              | String                                     | Type of the result, must be _photo_                                                                                                                                                                                                                                                                                                             |
| media             | String                                     | File to send. Pass a file\_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://\<file\_attach\_name>” to upload a new one using multipart/form-data under \<file\_attach\_name> name. [More information on Sending Files »](broken-reference) |
| caption           | String                                     | _Optional_. Caption of the photo to be sent, 0-1024 characters after entities parsing                                                                                                                                                                                                                                                           |
| parse\_mode       | String                                     | _Optional_. Mode for parsing entities in the photo caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                        |
| caption\_entities | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                |
| has\_spoiler      | Boolean                                    | _Optional_. Pass _True_ if the photo needs to be covered with a spoiler animation                                                                                                                                                                                                                                                               |

**InputMediaVideo**

Represents a video to be sent.

| Field               | Type                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ------------------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type                | String                                     | Type of the result, must be _video_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| media               | String                                     | File to send. Pass a file\_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://\<file\_attach\_name>” to upload a new one using multipart/form-data under \<file\_attach\_name> name. [More information on Sending Files »](broken-reference)                                                                                                                                                                                                                                  |
| thumbnail           | [InputFile](broken-reference) or String    | _Optional_. Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail's width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can't be reused and can be only uploaded as a new file, so you can pass “attach://\<file\_attach\_name>” if the thumbnail was uploaded using multipart/form-data under \<file\_attach\_name>. [More information on Sending Files »](broken-reference) |
| caption             | String                                     | _Optional_. Caption of the video to be sent, 0-1024 characters after entities parsing                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| parse\_mode         | String                                     | _Optional_. Mode for parsing entities in the video caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| caption\_entities   | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| width               | Integer                                    | _Optional_. Video width                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| height              | Integer                                    | _Optional_. Video height                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| duration            | Integer                                    | _Optional_. Video duration in seconds                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| supports\_streaming | Boolean                                    | _Optional_. Pass _True_ if the uploaded video is suitable for streaming                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| has\_spoiler        | Boolean                                    | _Optional_. Pass _True_ if the video needs to be covered with a spoiler animation                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

**InputMediaAnimation**

Represents an animation file (GIF or H.264/MPEG-4 AVC video without sound) to be sent.

| Field             | Type                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type              | String                                     | Type of the result, must be _animation_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| media             | String                                     | File to send. Pass a file\_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://\<file\_attach\_name>” to upload a new one using multipart/form-data under \<file\_attach\_name> name. [More information on Sending Files »](broken-reference)                                                                                                                                                                                                                                  |
| thumbnail         | [InputFile](broken-reference) or String    | _Optional_. Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail's width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can't be reused and can be only uploaded as a new file, so you can pass “attach://\<file\_attach\_name>” if the thumbnail was uploaded using multipart/form-data under \<file\_attach\_name>. [More information on Sending Files »](broken-reference) |
| caption           | String                                     | _Optional_. Caption of the animation to be sent, 0-1024 characters after entities parsing                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| parse\_mode       | String                                     | _Optional_. Mode for parsing entities in the animation caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| caption\_entities | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| width             | Integer                                    | _Optional_. Animation width                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| height            | Integer                                    | _Optional_. Animation height                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| duration          | Integer                                    | _Optional_. Animation duration in seconds                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| has\_spoiler      | Boolean                                    | _Optional_. Pass _True_ if the animation needs to be covered with a spoiler animation                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

**InputMediaAudio**

Represents an audio file to be treated as music to be sent.

| Field             | Type                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type              | String                                     | Type of the result, must be _audio_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| media             | String                                     | File to send. Pass a file\_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://\<file\_attach\_name>” to upload a new one using multipart/form-data under \<file\_attach\_name> name. [More information on Sending Files »](broken-reference)                                                                                                                                                                                                                                  |
| thumbnail         | [InputFile](broken-reference) or String    | _Optional_. Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail's width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can't be reused and can be only uploaded as a new file, so you can pass “attach://\<file\_attach\_name>” if the thumbnail was uploaded using multipart/form-data under \<file\_attach\_name>. [More information on Sending Files »](broken-reference) |
| caption           | String                                     | _Optional_. Caption of the audio to be sent, 0-1024 characters after entities parsing                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| parse\_mode       | String                                     | _Optional_. Mode for parsing entities in the audio caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| caption\_entities | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| duration          | Integer                                    | _Optional_. Duration of the audio in seconds                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| performer         | String                                     | _Optional_. Performer of the audio                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| title             | String                                     | _Optional_. Title of the audio                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

**InputMediaDocument**

Represents a general file to be sent.

| Field                             | Type                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| --------------------------------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type                              | String                                     | Type of the result, must be _document_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| media                             | String                                     | File to send. Pass a file\_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://\<file\_attach\_name>” to upload a new one using multipart/form-data under \<file\_attach\_name> name. [More information on Sending Files »](broken-reference)                                                                                                                                                                                                                                  |
| thumbnail                         | [InputFile](broken-reference) or String    | _Optional_. Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail's width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can't be reused and can be only uploaded as a new file, so you can pass “attach://\<file\_attach\_name>” if the thumbnail was uploaded using multipart/form-data under \<file\_attach\_name>. [More information on Sending Files »](broken-reference) |
| caption                           | String                                     | _Optional_. Caption of the document to be sent, 0-1024 characters after entities parsing                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| parse\_mode                       | String                                     | _Optional_. Mode for parsing entities in the document caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| caption\_entities                 | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| disable\_content\_type\_detection | Boolean                                    | _Optional_. Disables automatic server-side content type detection for files uploaded using multipart/form-data. Always _True_, if the document is sent as part of an album.                                                                                                                                                                                                                                                                                                                                                                                                      |

**InputFile**

This object represents the contents of a file to be uploaded. Must be posted using multipart/form-data in the usual way that files are uploaded via the browser.

**Sending files**

There are three ways to send files (photos, stickers, audio, media, etc.):

1. If the file is already stored somewhere on the Telegram servers, you don't need to reupload it: each file object has a **file\_id** field, simply pass this **file\_id** as a parameter instead of uploading. There are **no limits** for files sent this way.
2. Provide Telegram with an HTTP URL for the file to be sent. Telegram will download and send the file. 5 MB max size for photos and 20 MB max for other types of content.
3. Post the file using multipart/form-data in the usual way that files are uploaded via the browser. 10 MB max size for photos, 50 MB for other files.

**Sending by file\_id**

* It is not possible to change the file type when resending by **file\_id**. I.e. a [video](broken-reference) can't be [sent as a photo](broken-reference), a [photo](broken-reference) can't be [sent as a document](broken-reference), etc.
* It is not possible to resend thumbnails.
* Resending a photo by **file\_id** will send all of its [sizes](broken-reference).
* **file\_id** is unique for each individual bot and **can't** be transferred from one bot to another.
* **file\_id** uniquely identifies a file, but a file can have different valid **file\_id**s even for the same bot.

**Sending by URL**

* When sending by URL the target file must have the correct MIME type (e.g., audio/mpeg for [sendAudio](broken-reference), etc.).
* In [sendDocument](broken-reference), sending by URL will currently only work for **GIF**, **PDF** and **ZIP** files.
* To use [sendVoice](broken-reference), the file must have the type audio/ogg and be no more than 1MB in size. 1-20MB voice notes will be sent as files.
* Other configurations may work but we can't guarantee that they will.

**Accent colors**

Colors with identifiers 0 (red), 1 (orange), 2 (purple/violet), 3 (green), 4 (cyan), 5 (blue), 6 (pink) can be customized by app themes. Additionally, the following colors in RGB format are currently in use.

| Color identifier | Light colors         | Dark colors          |
| ---------------- | -------------------- | -------------------- |
| 7                | E15052 F9AE63        | FF9380 992F37        |
| 8                | E0802B FAC534        | ECB04E C35714        |
| 9                | A05FF3 F48FFF        | C697FF 5E31C8        |
| 10               | 27A910 A7DC57        | A7EB6E 167E2D        |
| 11               | 27ACCE 82E8D6        | 40D8D0 045C7F        |
| 12               | 3391D4 7DD3F0        | 52BFFF 0B5494        |
| 13               | DD4371 FFBE9F        | FF86A6 8E366E        |
| 14               | 247BED F04856 FFFFFF | 3FA2FE E5424F FFFFFF |
| 15               | D67722 1EA011 FFFFFF | FF905E 32A527 FFFFFF |
| 16               | 179E42 E84A3F FFFFFF | 66D364 D5444F FFFFFF |
| 17               | 2894AF 6FC456 FFFFFF | 22BCE2 3DA240 FFFFFF |
| 18               | 0C9AB3 FFAD95 FFE6B5 | 22BCE2 FF9778 FFDA6B |
| 19               | 7757D6 F79610 FFDE8E | 9791FF F2731D FFDB59 |
| 20               | 1585CF F2AB1D FFFFFF | 3DA6EB EEA51D FFFFFF |

**Profile accent colors**

Currently, the following colors in RGB format are in use for profile backgrounds.

| Color identifier | Light colors  | Dark colors   |
| ---------------- | ------------- | ------------- |
| 0                | BA5650        | 9C4540        |
| 1                | C27C3E        | 945E2C        |
| 2                | 956AC8        | 715099        |
| 3                | 49A355        | 33713B        |
| 4                | 3E97AD        | 387E87        |
| 5                | 5A8FBB        | 477194        |
| 6                | B85378        | 944763        |
| 7                | 7F8B95        | 435261        |
| 8                | C9565D D97C57 | 994343 AC583E |
| 9                | CF7244 CC9433 | 8F552F A17232 |
| 10               | 9662D4 B966B6 | 634691 9250A2 |
| 11               | 3D9755 89A650 | 296A43 5F8F44 |
| 12               | 3D95BA 50AD98 | 306C7C 3E987E |
| 13               | 538BC2 4DA8BD | 38618C 458BA1 |
| 14               | B04F74 D1666D | 884160 A65259 |
| 15               | 637482 7B8A97 | 53606E 384654 |

**Inline mode objects**

Objects and methods used in the inline mode are described in the [Inline mode section](broken-reference).

#### Available methods

> All methods in the Bot API are case-insensitive. We support **GET** and **POST** HTTP methods. Use either [URL query string](https://en.wikipedia.org/wiki/Query\_string) or _application/json_ or _application/x-www-form-urlencoded_ or _multipart/form-data_ for passing parameters in Bot API requests.\
> On successful call, a JSON-object containing the result will be returned.

**getMe**

A simple method for testing your bot's authentication token. Requires no parameters. Returns basic information about the bot in form of a [User](broken-reference) object.

**logOut**

Use this method to log out from the cloud Bot API server before launching the bot locally. You **must** log out the bot before running it locally, otherwise there is no guarantee that the bot will receive updates. After a successful call, you can immediately log in on a local server, but will not be able to log in back to the cloud Bot API server for 10 minutes. Returns _True_ on success. Requires no parameters.

**close**

Use this method to close the bot instance before moving it from one local server to another. You need to delete the webhook before calling this method to ensure that the bot isn't launched again after server restart. The method will return error 429 in the first 10 minutes after the bot is launched. Returns _True_ on success. Requires no parameters.

**sendMessage**

Use this method to send text messages. On success, the sent [Message](broken-reference) is returned.

| Parameter              | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                             |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id               | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                              |
| message\_thread\_id    | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                        |
| text                   | String                                                                                                                                                           | Yes      | Text of the message to be sent, 1-4096 characters after entities parsing                                                                                                                                                                                                |
| parse\_mode            | String                                                                                                                                                           | Optional | Mode for parsing entities in the message text. See [formatting options](broken-reference) for more details.                                                                                                                                                             |
| entities               | Array of [MessageEntity](broken-reference)                                                                                                                       | Optional | A JSON-serialized list of special entities that appear in message text, which can be specified instead of _parse\_mode_                                                                                                                                                 |
| link\_preview\_options | [LinkPreviewOptions](broken-reference)                                                                                                                           | Optional | Link preview generation options for the message                                                                                                                                                                                                                         |
| disable\_notification  | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                  |
| protect\_content       | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                    |
| reply\_parameters      | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                  |
| reply\_markup          | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user. |

**Formatting options**

The Bot API supports basic formatting for messages. You can use bold, italic, underlined, strikethrough, spoiler text, block quotations as well as inline links and pre-formatted code in your bots' messages. Telegram clients will render them accordingly. You can specify text entities directly, or use markdown-style or HTML-style formatting.

Note that Telegram clients will display an **alert** to the user before opening an inline link ('Open this link?' together with the full URL).

Message entities can be nested, providing following restrictions are met:\
\- If two entities have common characters, then one of them is fully contained inside another.\
\- _bold_, _italic_, _underline_, _strikethrough_, and _spoiler_ entities can contain and can be part of any other entities, except _pre_ and _code_.\
\- _blockquote_ entities can't be nested.\
\- All other entities can't contain each other.

Links `tg://user?id=<user_id>` can be used to mention a user by their identifier without using a username. Please note:

* These links will work **only** if they are used inside an inline link or in an inline keyboard button. For example, they will not work, when used in a message text.
* Unless the user is a member of the chat where they were mentioned, these mentions are only guaranteed to work if the user has contacted the bot in private in the past or has sent a callback query to the bot via an inline button and doesn't have Forwarded Messages privacy enabled for the bot.

You can find the list of programming and markup languages for which syntax highlighting is supported at [libprisma#supported-languages](https://github.com/TelegramMessenger/libprisma#supported-languages).

**MarkdownV2 style**

To use this mode, pass _MarkdownV2_ in the _parse\_mode_ field. Use the following syntax in your message:

````
*bold \*text*
_italic \*text_
__underline__
~strikethrough~
||spoiler||
*bold _italic bold ~italic bold strikethrough ||italic bold strikethrough spoiler||~ __underline italic bold___ bold*
[inline URL](http://www.example.com/)
[inline mention of a user](tg://user?id=123456789)
![](tg://emoji?id=5368324170671202286)
`inline fixed-width code`
```
pre-formatted fixed-width code block
```
```python
pre-formatted fixed-width code block written in the Python programming language
```
>Block quotation started
>Block quotation continued
>The last line of the block quotation**
>The second block quotation started right after the previous\r
>The third block quotation started right after the previous
````

Please note:

* Any character with code between 1 and 126 inclusively can be escaped anywhere with a preceding '\\' character, in which case it is treated as an ordinary character and not a part of the markup. This implies that '\\' character usually must be escaped with a preceding '\\' character.
* Inside `pre` and `code` entities, all '\`' and '\\' characters must be escaped with a preceding '\\' character.
* Inside the `(...)` part of the inline link and custom emoji definition, all ')' and '\\' must be escaped with a preceding '\\' character.
* In all other places characters '\_', '\*', '\[', ']', '(', ')', '\~', '\`', '>', '#', '+', '-', '=', '|', '{', '}', '.', '!' must be escaped with the preceding character '\\'.
* In case of ambiguity between `italic` and `underline` entities `__` is always greadily treated from left to right as beginning or end of `underline` entity, so instead of `___italic underline___` use `___italic underline_\r__`, where  is a character with code 13, which will be ignored.
* A valid emoji must be provided as an alternative value for the custom emoji. The emoji will be shown instead of the custom emoji in places where a custom emoji cannot be displayed (e.g., system notifications) or if the message is forwarded by a non-premium user. It is recommended to use the emoji from the **emoji** field of the custom emoji [sticker](broken-reference).
* Custom emoji entities can only be used by bots that purchased additional usernames on [Fragment](https://fragment.com/).

**HTML style**

To use this mode, pass _HTML_ in the _parse\_mode_ field. The following tags are currently supported:

```
<b>bold</b>, <strong>bold</strong>
<i>italic</i>, <em>italic</em>
<u>underline</u>, <ins>underline</ins>
<s>strikethrough</s>, <strike>strikethrough</strike>, <del>strikethrough</del>
<span class="tg-spoiler">spoiler</span>, <tg-spoiler>spoiler</tg-spoiler>
<b>bold <i>italic bold <s>italic bold strikethrough <span class="tg-spoiler">italic bold strikethrough spoiler</span></s> <u>underline italic bold</u></i> bold</b>
<a href="http://www.example.com/">inline URL</a>
<a href="tg://user?id=123456789">inline mention of a user</a>
<tg-emoji emoji-id="5368324170671202286"></tg-emoji>
<code>inline fixed-width code</code>
<pre>pre-formatted fixed-width code block</pre>
<pre><code class="language-python">pre-formatted fixed-width code block written in the Python programming language</code></pre>
<blockquote>Block quotation started\nBlock quotation continued\nThe last line of the block quotation</blockquote>
```

Please note:

* Only the tags mentioned above are currently supported.
* All `<`, `>` and `&` symbols that are not a part of a tag or an HTML entity must be replaced with the corresponding HTML entities (`<` with `&lt;`, `>` with `&gt;` and `&` with `&amp;`).
* All numerical HTML entities are supported.
* The API currently supports only the following named HTML entities: `&lt;`, `&gt;`, `&amp;` and `&quot;`.
* Use nested `pre` and `code` tags, to define programming language for `pre` entity.
* Programming language can't be specified for standalone `code` tags.
* A valid emoji must be used as the content of the `tg-emoji` tag. The emoji will be shown instead of the custom emoji in places where a custom emoji cannot be displayed (e.g., system notifications) or if the message is forwarded by a non-premium user. It is recommended to use the emoji from the **emoji** field of the custom emoji [sticker](broken-reference).
* Custom emoji entities can only be used by bots that purchased additional usernames on [Fragment](https://fragment.com/).

**Markdown style**

This is a legacy mode, retained for backward compatibility. To use this mode, pass _Markdown_ in the _parse\_mode_ field. Use the following syntax in your message:

````
*bold text*
_italic text_
[inline URL](http://www.example.com/)
[inline mention of a user](tg://user?id=123456789)
`inline fixed-width code`
```
pre-formatted fixed-width code block
```
```python
pre-formatted fixed-width code block written in the Python programming language
```
````

Please note:

* Entities must not be nested, use parse mode [MarkdownV2](broken-reference) instead.
* There is no way to specify “underline”, “strikethrough”, “spoiler”, “blockquote” and “custom\_emoji” entities, use parse mode [MarkdownV2](broken-reference) instead.
* To escape characters '\_', '\*', '\`', '\[' outside of an entity, prepend the characters '\\' before them.
* Escaping inside entities is not allowed, so entity must be closed first and reopened again: use `_snake_\__case_` for italic `snake_case` and `*2*\**2=4*` for bold `2*2=4`.

**forwardMessage**

Use this method to forward messages of any kind. Service messages and messages with protected content can't be forwarded. On success, the sent [Message](broken-reference) is returned.

| Parameter             | Type              | Required | Description                                                                                                                            |
| --------------------- | ----------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                             |
| message\_thread\_id   | Integer           | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                       |
| from\_chat\_id        | Integer or String | Yes      | Unique identifier for the chat where the original message was sent (or channel username in the format `@channelusername`)              |
| disable\_notification | Boolean           | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound. |
| protect\_content      | Boolean           | Optional | Protects the contents of the forwarded message from forwarding and saving                                                              |
| message\_id           | Integer           | Yes      | Message identifier in the chat specified in _from\_chat\_id_                                                                           |

**forwardMessages**

Use this method to forward multiple messages of any kind. If some of the specified messages can't be found or forwarded, they are skipped. Service messages and messages with protected content can't be forwarded. Album grouping is kept for forwarded messages. On success, an array of [MessageId](broken-reference) of the sent messages is returned.

| Parameter             | Type              | Required | Description                                                                                                                                                        |
| --------------------- | ----------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| chat\_id              | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                         |
| message\_thread\_id   | Integer           | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                   |
| from\_chat\_id        | Integer or String | Yes      | Unique identifier for the chat where the original messages were sent (or channel username in the format `@channelusername`)                                        |
| message\_ids          | Array of Integer  | Yes      | A JSON-serialized list of 1-100 identifiers of messages in the chat _from\_chat\_id_ to forward. The identifiers must be specified in a strictly increasing order. |
| disable\_notification | Boolean           | Optional | Sends the messages [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                            |
| protect\_content      | Boolean           | Optional | Protects the contents of the forwarded messages from forwarding and saving                                                                                         |

**copyMessage**

Use this method to copy messages of any kind. Service messages, giveaway messages, giveaway winners messages, and invoice messages can't be copied. A quiz [poll](broken-reference) can be copied only if the value of the field _correct\_option\_id_ is known to the bot. The method is analogous to the method [forwardMessage](broken-reference), but the copied message doesn't have a link to the original message. Returns the [MessageId](broken-reference) of the sent message on success.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                             |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                              |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                        |
| from\_chat\_id        | Integer or String                                                                                                                                                | Yes      | Unique identifier for the chat where the original message was sent (or channel username in the format `@channelusername`)                                                                                                                                               |
| message\_id           | Integer                                                                                                                                                          | Yes      | Message identifier in the chat specified in _from\_chat\_id_                                                                                                                                                                                                            |
| caption               | String                                                                                                                                                           | Optional | New caption for media, 0-1024 characters after entities parsing. If not specified, the original caption is kept                                                                                                                                                         |
| parse\_mode           | String                                                                                                                                                           | Optional | Mode for parsing entities in the new caption. See [formatting options](broken-reference) for more details.                                                                                                                                                              |
| caption\_entities     | Array of [MessageEntity](broken-reference)                                                                                                                       | Optional | A JSON-serialized list of special entities that appear in the new caption, which can be specified instead of _parse\_mode_                                                                                                                                              |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                  |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                    |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                  |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user. |

**copyMessages**

Use this method to copy messages of any kind. If some of the specified messages can't be found or copied, they are skipped. Service messages, giveaway messages, giveaway winners messages, and invoice messages can't be copied. A quiz [poll](broken-reference) can be copied only if the value of the field _correct\_option\_id_ is known to the bot. The method is analogous to the method [forwardMessages](broken-reference), but the copied messages don't have a link to the original message. Album grouping is kept for copied messages. On success, an array of [MessageId](broken-reference) of the sent messages is returned.

| Parameter             | Type              | Required | Description                                                                                                                                                     |
| --------------------- | ----------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                      |
| message\_thread\_id   | Integer           | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                |
| from\_chat\_id        | Integer or String | Yes      | Unique identifier for the chat where the original messages were sent (or channel username in the format `@channelusername`)                                     |
| message\_ids          | Array of Integer  | Yes      | A JSON-serialized list of 1-100 identifiers of messages in the chat _from\_chat\_id_ to copy. The identifiers must be specified in a strictly increasing order. |
| disable\_notification | Boolean           | Optional | Sends the messages [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                         |
| protect\_content      | Boolean           | Optional | Protects the contents of the sent messages from forwarding and saving                                                                                           |
| remove\_caption       | Boolean           | Optional | Pass _True_ to copy the messages without their captions                                                                                                         |

**sendPhoto**

Use this method to send photos. On success, the sent [Message](broken-reference) is returned.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                                                                        |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                                                                                                                                                                  |
| photo                 | [InputFile](broken-reference) or String                                                                                                                          | Yes      | Photo to send. Pass a file\_id as String to send a photo that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a photo from the Internet, or upload a new photo using multipart/form-data. The photo must be at most 10 MB in size. The photo's width and height must not exceed 10000 in total. Width and height ratio must be at most 20. [More information on Sending Files »](broken-reference) |
| caption               | String                                                                                                                                                           | Optional | Photo caption (may also be used when resending photos by _file\_id_), 0-1024 characters after entities parsing                                                                                                                                                                                                                                                                                                                                    |
| parse\_mode           | String                                                                                                                                                           | Optional | Mode for parsing entities in the photo caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                                                                                                                      |
| caption\_entities     | Array of [MessageEntity](broken-reference)                                                                                                                       | Optional | A JSON-serialized list of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                                                                                                            |
| has\_spoiler          | Boolean                                                                                                                                                          | Optional | Pass _True_ if the photo needs to be covered with a spoiler animation                                                                                                                                                                                                                                                                                                                                                                             |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                                                                                                                                                                            |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                                                                                                                                                                                              |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                                                                                                                                                                                            |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user.                                                                                                                                                                           |

**sendAudio**

Use this method to send audio files, if you want Telegram clients to display them in the music player. Your audio must be in the .MP3 or .M4A format. On success, the sent [Message](broken-reference) is returned. Bots can currently send audio files of up to 50 MB in size, this limit may be changed in the future.

For sending voice messages, use the [sendVoice](broken-reference) method instead.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| audio                 | [InputFile](broken-reference) or String                                                                                                                          | Yes      | Audio file to send. Pass a file\_id as String to send an audio file that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get an audio file from the Internet, or upload a new one using multipart/form-data. [More information on Sending Files »](broken-reference)                                                                                                                                                                                                                                                      |
| caption               | String                                                                                                                                                           | Optional | Audio caption, 0-1024 characters after entities parsing                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| parse\_mode           | String                                                                                                                                                           | Optional | Mode for parsing entities in the audio caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| caption\_entities     | Array of [MessageEntity](broken-reference)                                                                                                                       | Optional | A JSON-serialized list of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| duration              | Integer                                                                                                                                                          | Optional | Duration of the audio in seconds                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| performer             | String                                                                                                                                                           | Optional | Performer                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| title                 | String                                                                                                                                                           | Optional | Track name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| thumbnail             | [InputFile](broken-reference) or String                                                                                                                          | Optional | Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail's width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can't be reused and can be only uploaded as a new file, so you can pass “attach://\<file\_attach\_name>” if the thumbnail was uploaded using multipart/form-data under \<file\_attach\_name>. [More information on Sending Files »](broken-reference) |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                                                                                                                                                                                                                                                                                               |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user.                                                                                                                                                                                                                                                                                              |

**sendDocument**

Use this method to send general files. On success, the sent [Message](broken-reference) is returned. Bots can currently send files of any type of up to 50 MB in size, this limit may be changed in the future.

| Parameter                         | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                          | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| message\_thread\_id               | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| document                          | [InputFile](broken-reference) or String                                                                                                                          | Yes      | File to send. Pass a file\_id as String to send a file that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a file from the Internet, or upload a new one using multipart/form-data. [More information on Sending Files »](broken-reference)                                                                                                                                                                                                                                                                          |
| thumbnail                         | [InputFile](broken-reference) or String                                                                                                                          | Optional | Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail's width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can't be reused and can be only uploaded as a new file, so you can pass “attach://\<file\_attach\_name>” if the thumbnail was uploaded using multipart/form-data under \<file\_attach\_name>. [More information on Sending Files »](broken-reference) |
| caption                           | String                                                                                                                                                           | Optional | Document caption (may also be used when resending documents by _file\_id_), 0-1024 characters after entities parsing                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| parse\_mode                       | String                                                                                                                                                           | Optional | Mode for parsing entities in the document caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| caption\_entities                 | Array of [MessageEntity](broken-reference)                                                                                                                       | Optional | A JSON-serialized list of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| disable\_content\_type\_detection | Boolean                                                                                                                                                          | Optional | Disables automatic server-side content type detection for files uploaded using multipart/form-data                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| disable\_notification             | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                                                                                                                                                                                                                                                                                               |
| protect\_content                  | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| reply\_parameters                 | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| reply\_markup                     | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user.                                                                                                                                                                                                                                                                                              |

**sendVideo**

Use this method to send video files, Telegram clients support MPEG4 videos (other formats may be sent as [Document](broken-reference)). On success, the sent [Message](broken-reference) is returned. Bots can currently send video files of up to 50 MB in size, this limit may be changed in the future.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| video                 | [InputFile](broken-reference) or String                                                                                                                          | Yes      | Video to send. Pass a file\_id as String to send a video that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a video from the Internet, or upload a new video using multipart/form-data. [More information on Sending Files »](broken-reference)                                                                                                                                                                                                                                                                     |
| duration              | Integer                                                                                                                                                          | Optional | Duration of sent video in seconds                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| width                 | Integer                                                                                                                                                          | Optional | Video width                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| height                | Integer                                                                                                                                                          | Optional | Video height                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| thumbnail             | [InputFile](broken-reference) or String                                                                                                                          | Optional | Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail's width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can't be reused and can be only uploaded as a new file, so you can pass “attach://\<file\_attach\_name>” if the thumbnail was uploaded using multipart/form-data under \<file\_attach\_name>. [More information on Sending Files »](broken-reference) |
| caption               | String                                                                                                                                                           | Optional | Video caption (may also be used when resending videos by _file\_id_), 0-1024 characters after entities parsing                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| parse\_mode           | String                                                                                                                                                           | Optional | Mode for parsing entities in the video caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| caption\_entities     | Array of [MessageEntity](broken-reference)                                                                                                                       | Optional | A JSON-serialized list of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| has\_spoiler          | Boolean                                                                                                                                                          | Optional | Pass _True_ if the video needs to be covered with a spoiler animation                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| supports\_streaming   | Boolean                                                                                                                                                          | Optional | Pass _True_ if the uploaded video is suitable for streaming                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                                                                                                                                                                                                                                                                                               |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user.                                                                                                                                                                                                                                                                                              |

**sendAnimation**

Use this method to send animation files (GIF or H.264/MPEG-4 AVC video without sound). On success, the sent [Message](broken-reference) is returned. Bots can currently send animation files of up to 50 MB in size, this limit may be changed in the future.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| animation             | [InputFile](broken-reference) or String                                                                                                                          | Yes      | Animation to send. Pass a file\_id as String to send an animation that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get an animation from the Internet, or upload a new animation using multipart/form-data. [More information on Sending Files »](broken-reference)                                                                                                                                                                                                                                                   |
| duration              | Integer                                                                                                                                                          | Optional | Duration of sent animation in seconds                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| width                 | Integer                                                                                                                                                          | Optional | Animation width                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| height                | Integer                                                                                                                                                          | Optional | Animation height                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| thumbnail             | [InputFile](broken-reference) or String                                                                                                                          | Optional | Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail's width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can't be reused and can be only uploaded as a new file, so you can pass “attach://\<file\_attach\_name>” if the thumbnail was uploaded using multipart/form-data under \<file\_attach\_name>. [More information on Sending Files »](broken-reference) |
| caption               | String                                                                                                                                                           | Optional | Animation caption (may also be used when resending animation by _file\_id_), 0-1024 characters after entities parsing                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| parse\_mode           | String                                                                                                                                                           | Optional | Mode for parsing entities in the animation caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| caption\_entities     | Array of [MessageEntity](broken-reference)                                                                                                                       | Optional | A JSON-serialized list of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| has\_spoiler          | Boolean                                                                                                                                                          | Optional | Pass _True_ if the animation needs to be covered with a spoiler animation                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                                                                                                                                                                                                                                                                                               |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user.                                                                                                                                                                                                                                                                                              |

**sendVoice**

Use this method to send audio files, if you want Telegram clients to display the file as a playable voice message. For this to work, your audio must be in an .OGG file encoded with OPUS (other formats may be sent as [Audio](broken-reference) or [Document](broken-reference)). On success, the sent [Message](broken-reference) is returned. Bots can currently send voice messages of up to 50 MB in size, this limit may be changed in the future.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                                                       |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                        |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                  |
| voice                 | [InputFile](broken-reference) or String                                                                                                                          | Yes      | Audio file to send. Pass a file\_id as String to send a file that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a file from the Internet, or upload a new one using multipart/form-data. [More information on Sending Files »](broken-reference) |
| caption               | String                                                                                                                                                           | Optional | Voice message caption, 0-1024 characters after entities parsing                                                                                                                                                                                                                                   |
| parse\_mode           | String                                                                                                                                                           | Optional | Mode for parsing entities in the voice message caption. See [formatting options](broken-reference) for more details.                                                                                                                                                                              |
| caption\_entities     | Array of [MessageEntity](broken-reference)                                                                                                                       | Optional | A JSON-serialized list of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                                                                                                                            |
| duration              | Integer                                                                                                                                                          | Optional | Duration of the voice message in seconds                                                                                                                                                                                                                                                          |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                            |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                                              |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                                            |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user.                           |

**sendVideoNote**

As of [v.4.0](https://telegram.org/blog/video-messages-and-telescope), Telegram clients support rounded square MPEG4 videos of up to 1 minute long. Use this method to send video messages. On success, the sent [Message](broken-reference) is returned.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| video\_note           | [InputFile](broken-reference) or String                                                                                                                          | Yes      | Video note to send. Pass a file\_id as String to send a video note that exists on the Telegram servers (recommended) or upload a new video using multipart/form-data. [More information on Sending Files »](broken-reference). Sending video notes by a URL is currently unsupported                                                                                                                                                                                                                                                                                 |
| duration              | Integer                                                                                                                                                          | Optional | Duration of sent video in seconds                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| length                | Integer                                                                                                                                                          | Optional | Video width and height, i.e. diameter of the video message                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| thumbnail             | [InputFile](broken-reference) or String                                                                                                                          | Optional | Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail's width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can't be reused and can be only uploaded as a new file, so you can pass “attach://\<file\_attach\_name>” if the thumbnail was uploaded using multipart/form-data under \<file\_attach\_name>. [More information on Sending Files »](broken-reference) |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                                                                                                                                                                                                                                                                                               |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user.                                                                                                                                                                                                                                                                                              |

**sendMediaGroup**

Use this method to send a group of photos, videos, documents or audios as an album. Documents and audio files can be only grouped in an album with messages of the same type. On success, an array of [Messages](broken-reference) that were sent is returned.

| Parameter             | Type                                                                                                                                                              | Required | Description                                                                                                                         |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                 | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                          |
| message\_thread\_id   | Integer                                                                                                                                                           | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                    |
| media                 | Array of [InputMediaAudio](broken-reference), [InputMediaDocument](broken-reference), [InputMediaPhoto](broken-reference) and [InputMediaVideo](broken-reference) | Yes      | A JSON-serialized array describing messages to be sent, must include 2-10 items                                                     |
| disable\_notification | Boolean                                                                                                                                                           | Optional | Sends messages [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound. |
| protect\_content      | Boolean                                                                                                                                                           | Optional | Protects the contents of the sent messages from forwarding and saving                                                               |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                               | Optional | Description of the message to reply to                                                                                              |

**sendLocation**

Use this method to send point on the map. On success, the sent [Message](broken-reference) is returned.

| Parameter                | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                             |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                 | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                              |
| message\_thread\_id      | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                        |
| latitude                 | Float                                                                                                                                                            | Yes      | Latitude of the location                                                                                                                                                                                                                                                |
| longitude                | Float                                                                                                                                                            | Yes      | Longitude of the location                                                                                                                                                                                                                                               |
| horizontal\_accuracy     | Float                                                                                                                                                            | Optional | The radius of uncertainty for the location, measured in meters; 0-1500                                                                                                                                                                                                  |
| live\_period             | Integer                                                                                                                                                          | Optional | Period in seconds for which the location will be updated (see [Live Locations](https://telegram.org/blog/live-locations), should be between 60 and 86400.                                                                                                               |
| heading                  | Integer                                                                                                                                                          | Optional | For live locations, a direction in which the user is moving, in degrees. Must be between 1 and 360 if specified.                                                                                                                                                        |
| proximity\_alert\_radius | Integer                                                                                                                                                          | Optional | For live locations, a maximum distance for proximity alerts about approaching another chat member, in meters. Must be between 1 and 100000 if specified.                                                                                                                |
| disable\_notification    | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                  |
| protect\_content         | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                    |
| reply\_parameters        | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                  |
| reply\_markup            | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user. |

**sendVenue**

Use this method to send information about a venue. On success, the sent [Message](broken-reference) is returned.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                             |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                              |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                        |
| latitude              | Float                                                                                                                                                            | Yes      | Latitude of the venue                                                                                                                                                                                                                                                   |
| longitude             | Float                                                                                                                                                            | Yes      | Longitude of the venue                                                                                                                                                                                                                                                  |
| title                 | String                                                                                                                                                           | Yes      | Name of the venue                                                                                                                                                                                                                                                       |
| address               | String                                                                                                                                                           | Yes      | Address of the venue                                                                                                                                                                                                                                                    |
| foursquare\_id        | String                                                                                                                                                           | Optional | Foursquare identifier of the venue                                                                                                                                                                                                                                      |
| foursquare\_type      | String                                                                                                                                                           | Optional | Foursquare type of the venue, if known. (For example, “arts\_entertainment/default”, “arts\_entertainment/aquarium” or “food/icecream”.)                                                                                                                                |
| google\_place\_id     | String                                                                                                                                                           | Optional | Google Places identifier of the venue                                                                                                                                                                                                                                   |
| google\_place\_type   | String                                                                                                                                                           | Optional | Google Places type of the venue. (See [supported types](https://developers.google.com/places/web-service/supported\_types).)                                                                                                                                            |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                  |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                    |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                  |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user. |

**sendContact**

Use this method to send phone contacts. On success, the sent [Message](broken-reference) is returned.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                             |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                              |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                        |
| phone\_number         | String                                                                                                                                                           | Yes      | Contact's phone number                                                                                                                                                                                                                                                  |
| first\_name           | String                                                                                                                                                           | Yes      | Contact's first name                                                                                                                                                                                                                                                    |
| last\_name            | String                                                                                                                                                           | Optional | Contact's last name                                                                                                                                                                                                                                                     |
| vcard                 | String                                                                                                                                                           | Optional | Additional data about the contact in the form of a [vCard](https://en.wikipedia.org/wiki/VCard), 0-2048 bytes                                                                                                                                                           |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                  |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                    |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                  |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user. |

**sendPoll**

Use this method to send a native poll. On success, the sent [Message](broken-reference) is returned.

| Parameter                 | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                             |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                  | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                              |
| message\_thread\_id       | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                        |
| question                  | String                                                                                                                                                           | Yes      | Poll question, 1-300 characters                                                                                                                                                                                                                                         |
| options                   | Array of String                                                                                                                                                  | Yes      | A JSON-serialized list of answer options, 2-10 strings 1-100 characters each                                                                                                                                                                                            |
| is\_anonymous             | Boolean                                                                                                                                                          | Optional | _True_, if the poll needs to be anonymous, defaults to _True_                                                                                                                                                                                                           |
| type                      | String                                                                                                                                                           | Optional | Poll type, “quiz” or “regular”, defaults to “regular”                                                                                                                                                                                                                   |
| allows\_multiple\_answers | Boolean                                                                                                                                                          | Optional | _True_, if the poll allows multiple answers, ignored for polls in quiz mode, defaults to _False_                                                                                                                                                                        |
| correct\_option\_id       | Integer                                                                                                                                                          | Optional | 0-based identifier of the correct answer option, required for polls in quiz mode                                                                                                                                                                                        |
| explanation               | String                                                                                                                                                           | Optional | Text that is shown when a user chooses an incorrect answer or taps on the lamp icon in a quiz-style poll, 0-200 characters with at most 2 line feeds after entities parsing                                                                                             |
| explanation\_parse\_mode  | String                                                                                                                                                           | Optional | Mode for parsing entities in the explanation. See [formatting options](broken-reference) for more details.                                                                                                                                                              |
| explanation\_entities     | Array of [MessageEntity](broken-reference)                                                                                                                       | Optional | A JSON-serialized list of special entities that appear in the poll explanation, which can be specified instead of _parse\_mode_                                                                                                                                         |
| open\_period              | Integer                                                                                                                                                          | Optional | Amount of time in seconds the poll will be active after creation, 5-600. Can't be used together with _close\_date_.                                                                                                                                                     |
| close\_date               | Integer                                                                                                                                                          | Optional | Point in time (Unix timestamp) when the poll will be automatically closed. Must be at least 5 and no more than 600 seconds in the future. Can't be used together with _open\_period_.                                                                                   |
| is\_closed                | Boolean                                                                                                                                                          | Optional | Pass _True_ if the poll needs to be immediately closed. This can be useful for poll preview.                                                                                                                                                                            |
| disable\_notification     | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                  |
| protect\_content          | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                    |
| reply\_parameters         | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                  |
| reply\_markup             | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user. |

**sendDice**

Use this method to send an animated emoji that will display a random value. On success, the sent [Message](broken-reference) is returned.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| emoji                 | String                                                                                                                                                           | Optional | Emoji on which the dice throw animation is based. Currently, must be one of “![🎲](https://telegram.org/img/emoji/40/F09F8EB2.png)”, “![🎯](https://telegram.org/img/emoji/40/F09F8EAF.png)”, “![🏀](https://telegram.org/img/emoji/40/F09F8F80.png)”, “![⚽](https://telegram.org/img/emoji/40/E29ABD.png)”, “![🎳](https://telegram.org/img/emoji/40/F09F8EB3.png)”, or “![🎰](https://telegram.org/img/emoji/40/F09F8EB0.png)”. Dice can have values 1-6 for “![🎲](https://telegram.org/img/emoji/40/F09F8EB2.png)”, “![🎯](https://telegram.org/img/emoji/40/F09F8EAF.png)” and “![🎳](https://telegram.org/img/emoji/40/F09F8EB3.png)”, values 1-5 for “![🏀](https://telegram.org/img/emoji/40/F09F8F80.png)” and “![⚽](https://telegram.org/img/emoji/40/E29ABD.png)”, and values 1-64 for “![🎰](https://telegram.org/img/emoji/40/F09F8EB0.png)”. Defaults to “![🎲](https://telegram.org/img/emoji/40/F09F8EB2.png)” |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

**sendChatAction**

Use this method when you need to tell the user that something is happening on the bot's side. The status is set for 5 seconds or less (when a message arrives from your bot, Telegram clients clear its typing status). Returns _True_ on success.

> Example: The [ImageBot](https://t.me/imagebot) needs some time to process a request and upload the image. Instead of sending a text message along the lines of “Retrieving image, please wait…”, the bot may use [sendChatAction](broken-reference) with _action_ = _upload\_photo_. The user will see a “sending photo” status for the bot.

We only recommend using this method when a response from the bot will take a **noticeable** amount of time to arrive.

| Parameter           | Type              | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ------------------- | ----------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id            | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| message\_thread\_id | Integer           | Optional | Unique identifier for the target message thread; for supergroups only                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| action              | String            | Yes      | Type of action to broadcast. Choose one, depending on what the user is about to receive: _typing_ for [text messages](broken-reference), _upload\_photo_ for [photos](broken-reference), _record\_video_ or _upload\_video_ for [videos](broken-reference), _record\_voice_ or _upload\_voice_ for [voice notes](broken-reference), _upload\_document_ for [general files](broken-reference), _choose\_sticker_ for [stickers](broken-reference), _find\_location_ for [location data](broken-reference), _record\_video\_note_ or _upload\_video\_note_ for [video notes](broken-reference). |

**setMessageReaction**

Use this method to change the chosen reactions on a message. Service messages can't be reacted to. Automatically forwarded messages from a channel to its discussion group have the same available reactions as messages in the channel. Returns _True_ on success.

| Parameter   | Type                                      | Required | Description                                                                                                                                                                                                                                                                    |
| ----------- | ----------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| chat\_id    | Integer or String                         | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                     |
| message\_id | Integer                                   | Yes      | Identifier of the target message. If the message belongs to a media group, the reaction is set to the first non-deleted message in the group instead.                                                                                                                          |
| reaction    | Array of [ReactionType](broken-reference) | Optional | A JSON-serialized list of reaction types to set on the message. Currently, as non-premium users, bots can set up to one reaction per message. A custom emoji reaction can be used if it is either already present on the message or explicitly allowed by chat administrators. |
| is\_big     | Boolean                                   | Optional | Pass _True_ to set the reaction with a big animation                                                                                                                                                                                                                           |

**getUserProfilePhotos**

Use this method to get a list of profile pictures for a user. Returns a [UserProfilePhotos](broken-reference) object.

| Parameter | Type    | Required | Description                                                                                      |
| --------- | ------- | -------- | ------------------------------------------------------------------------------------------------ |
| user\_id  | Integer | Yes      | Unique identifier of the target user                                                             |
| offset    | Integer | Optional | Sequential number of the first photo to be returned. By default, all photos are returned.        |
| limit     | Integer | Optional | Limits the number of photos to be retrieved. Values between 1-100 are accepted. Defaults to 100. |

**getFile**

Use this method to get basic information about a file and prepare it for downloading. For the moment, bots can download files of up to 20MB in size. On success, a [File](broken-reference) object is returned. The file can then be downloaded via the link `https://api.telegram.org/file/bot<token>/<file_path>`, where `<file_path>` is taken from the response. It is guaranteed that the link will be valid for at least 1 hour. When the link expires, a new one can be requested by calling [getFile](broken-reference) again.

| Parameter | Type   | Required | Description                              |
| --------- | ------ | -------- | ---------------------------------------- |
| file\_id  | String | Yes      | File identifier to get information about |

**Note:** This function may not preserve the original file name and MIME type. You should save the file's MIME type and name (if available) when the File object is received.

**banChatMember**

Use this method to ban a user in a group, a supergroup or a channel. In the case of supergroups and channels, the user will not be able to return to the chat on their own using invite links, etc., unless [unbanned](broken-reference) first. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns _True_ on success.

| Parameter        | Type              | Required | Description                                                                                                                                                                                                                                 |
| ---------------- | ----------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id         | Integer or String | Yes      | Unique identifier for the target group or username of the target supergroup or channel (in the format `@channelusername`)                                                                                                                   |
| user\_id         | Integer           | Yes      | Unique identifier of the target user                                                                                                                                                                                                        |
| until\_date      | Integer           | Optional | Date when the user will be unbanned; Unix time. If user is banned for more than 366 days or less than 30 seconds from the current time they are considered to be banned forever. Applied for supergroups and channels only.                 |
| revoke\_messages | Boolean           | Optional | Pass _True_ to delete all messages from the chat for the user that is being removed. If _False_, the user will be able to see messages in the group that were sent before the user was removed. Always _True_ for supergroups and channels. |

**unbanChatMember**

Use this method to unban a previously banned user in a supergroup or channel. The user will **not** return to the group or channel automatically, but will be able to join via link, etc. The bot must be an administrator for this to work. By default, this method guarantees that after the call the user is not a member of the chat, but will be able to join it. So if the user is a member of the chat they will also be **removed** from the chat. If you don't want this, use the parameter _only\_if\_banned_. Returns _True_ on success.

| Parameter        | Type              | Required | Description                                                                                                               |
| ---------------- | ----------------- | -------- | ------------------------------------------------------------------------------------------------------------------------- |
| chat\_id         | Integer or String | Yes      | Unique identifier for the target group or username of the target supergroup or channel (in the format `@channelusername`) |
| user\_id         | Integer           | Yes      | Unique identifier of the target user                                                                                      |
| only\_if\_banned | Boolean           | Optional | Do nothing if the user is not banned                                                                                      |

**restrictChatMember**

Use this method to restrict a user in a supergroup. The bot must be an administrator in the supergroup for this to work and must have the appropriate administrator rights. Pass _True_ for all permissions to lift restrictions from a user. Returns _True_ on success.

| Parameter                           | Type                                | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ----------------------------------- | ----------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                            | Integer or String                   | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`)                                                                                                                                                                                                                                                                                                                         |
| user\_id                            | Integer                             | Yes      | Unique identifier of the target user                                                                                                                                                                                                                                                                                                                                                                                                     |
| permissions                         | [ChatPermissions](broken-reference) | Yes      | A JSON-serialized object for new user permissions                                                                                                                                                                                                                                                                                                                                                                                        |
| use\_independent\_chat\_permissions | Boolean                             | Optional | Pass _True_ if chat permissions are set independently. Otherwise, the _can\_send\_other\_messages_ and _can\_add\_web\_page\_previews_ permissions will imply the _can\_send\_messages_, _can\_send\_audios_, _can\_send\_documents_, _can\_send\_photos_, _can\_send\_videos_, _can\_send\_video\_notes_, and _can\_send\_voice\_notes_ permissions; the _can\_send\_polls_ permission will imply the _can\_send\_messages_ permission. |
| until\_date                         | Integer                             | Optional | Date when restrictions will be lifted for the user; Unix time. If user is restricted for more than 366 days or less than 30 seconds from the current time, they are considered to be restricted forever                                                                                                                                                                                                                                  |

**promoteChatMember**

Use this method to promote or demote a user in a supergroup or a channel. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Pass _False_ for all boolean parameters to demote a user. Returns _True_ on success.

| Parameter                 | Type              | Required | Description                                                                                                                                                                                                                        |
| ------------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                  | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                         |
| user\_id                  | Integer           | Yes      | Unique identifier of the target user                                                                                                                                                                                               |
| is\_anonymous             | Boolean           | Optional | Pass _True_ if the administrator's presence in the chat is hidden                                                                                                                                                                  |
| can\_manage\_chat         | Boolean           | Optional | Pass _True_ if the administrator can access the chat event log, get boost list, see hidden supergroup and channel members, report spam messages and ignore slow mode. Implied by any other administrator privilege.                |
| can\_delete\_messages     | Boolean           | Optional | Pass _True_ if the administrator can delete messages of other users                                                                                                                                                                |
| can\_manage\_video\_chats | Boolean           | Optional | Pass _True_ if the administrator can manage video chats                                                                                                                                                                            |
| can\_restrict\_members    | Boolean           | Optional | Pass _True_ if the administrator can restrict, ban or unban chat members, or access supergroup statistics                                                                                                                          |
| can\_promote\_members     | Boolean           | Optional | Pass _True_ if the administrator can add new administrators with a subset of their own privileges or demote administrators that they have promoted, directly or indirectly (promoted by administrators that were appointed by him) |
| can\_change\_info         | Boolean           | Optional | Pass _True_ if the administrator can change chat title, photo and other settings                                                                                                                                                   |
| can\_invite\_users        | Boolean           | Optional | Pass _True_ if the administrator can invite new users to the chat                                                                                                                                                                  |
| can\_post\_stories        | Boolean           | Optional | Pass _True_ if the administrator can post stories to the chat                                                                                                                                                                      |
| can\_edit\_stories        | Boolean           | Optional | Pass _True_ if the administrator can edit stories posted by other users                                                                                                                                                            |
| can\_delete\_stories      | Boolean           | Optional | Pass _True_ if the administrator can delete stories posted by other users                                                                                                                                                          |
| can\_post\_messages       | Boolean           | Optional | Pass _True_ if the administrator can post messages in the channel, or access channel statistics; for channels only                                                                                                                 |
| can\_edit\_messages       | Boolean           | Optional | Pass _True_ if the administrator can edit messages of other users and can pin messages; for channels only                                                                                                                          |
| can\_pin\_messages        | Boolean           | Optional | Pass _True_ if the administrator can pin messages; for supergroups only                                                                                                                                                            |
| can\_manage\_topics       | Boolean           | Optional | Pass _True_ if the user is allowed to create, rename, close, and reopen forum topics; for supergroups only                                                                                                                         |

**setChatAdministratorCustomTitle**

Use this method to set a custom title for an administrator in a supergroup promoted by the bot. Returns _True_ on success.

| Parameter     | Type              | Required | Description                                                                                                      |
| ------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id      | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |
| user\_id      | Integer           | Yes      | Unique identifier of the target user                                                                             |
| custom\_title | String            | Yes      | New custom title for the administrator; 0-16 characters, emoji are not allowed                                   |

**banChatSenderChat**

Use this method to ban a channel chat in a supergroup or a channel. Until the chat is [unbanned](broken-reference), the owner of the banned chat won't be able to send messages on behalf of **any of their channels**. The bot must be an administrator in the supergroup or channel for this to work and must have the appropriate administrator rights. Returns _True_ on success.

| Parameter        | Type              | Required | Description                                                                                                |
| ---------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id         | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| sender\_chat\_id | Integer           | Yes      | Unique identifier of the target sender chat                                                                |

**unbanChatSenderChat**

Use this method to unban a previously banned channel chat in a supergroup or channel. The bot must be an administrator for this to work and must have the appropriate administrator rights. Returns _True_ on success.

| Parameter        | Type              | Required | Description                                                                                                |
| ---------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id         | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| sender\_chat\_id | Integer           | Yes      | Unique identifier of the target sender chat                                                                |

**setChatPermissions**

Use this method to set default chat permissions for all members. The bot must be an administrator in the group or a supergroup for this to work and must have the _can\_restrict\_members_ administrator rights. Returns _True_ on success.

| Parameter                           | Type                                | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ----------------------------------- | ----------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                            | Integer or String                   | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`)                                                                                                                                                                                                                                                                                                                         |
| permissions                         | [ChatPermissions](broken-reference) | Yes      | A JSON-serialized object for new default chat permissions                                                                                                                                                                                                                                                                                                                                                                                |
| use\_independent\_chat\_permissions | Boolean                             | Optional | Pass _True_ if chat permissions are set independently. Otherwise, the _can\_send\_other\_messages_ and _can\_add\_web\_page\_previews_ permissions will imply the _can\_send\_messages_, _can\_send\_audios_, _can\_send\_documents_, _can\_send\_photos_, _can\_send\_videos_, _can\_send\_video\_notes_, and _can\_send\_voice\_notes_ permissions; the _can\_send\_polls_ permission will imply the _can\_send\_messages_ permission. |

**exportChatInviteLink**

Use this method to generate a new primary invite link for a chat; any previously generated primary link is revoked. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns the new invite link as _String_ on success.

| Parameter | Type              | Required | Description                                                                                                |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |

> Note: Each administrator in a chat generates their own invite links. Bots can't use invite links generated by other administrators. If you want your bot to work with invite links, it will need to generate its own link using [exportChatInviteLink](broken-reference) or by calling the [getChat](broken-reference) method. If your bot needs to generate a new primary invite link replacing its previous one, use [exportChatInviteLink](broken-reference) again.

**createChatInviteLink**

Use this method to create an additional invite link for a chat. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. The link can be revoked using the method [revokeChatInviteLink](broken-reference). Returns the new invite link as [ChatInviteLink](broken-reference) object.

| Parameter              | Type              | Required | Description                                                                                                                              |
| ---------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id               | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                               |
| name                   | String            | Optional | Invite link name; 0-32 characters                                                                                                        |
| expire\_date           | Integer           | Optional | Point in time (Unix timestamp) when the link will expire                                                                                 |
| member\_limit          | Integer           | Optional | The maximum number of users that can be members of the chat simultaneously after joining the chat via this invite link; 1-99999          |
| creates\_join\_request | Boolean           | Optional | _True_, if users joining the chat via the link need to be approved by chat administrators. If _True_, _member\_limit_ can't be specified |

**editChatInviteLink**

Use this method to edit a non-primary invite link created by the bot. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns the edited invite link as a [ChatInviteLink](broken-reference) object.

| Parameter              | Type              | Required | Description                                                                                                                              |
| ---------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id               | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                               |
| invite\_link           | String            | Yes      | The invite link to edit                                                                                                                  |
| name                   | String            | Optional | Invite link name; 0-32 characters                                                                                                        |
| expire\_date           | Integer           | Optional | Point in time (Unix timestamp) when the link will expire                                                                                 |
| member\_limit          | Integer           | Optional | The maximum number of users that can be members of the chat simultaneously after joining the chat via this invite link; 1-99999          |
| creates\_join\_request | Boolean           | Optional | _True_, if users joining the chat via the link need to be approved by chat administrators. If _True_, _member\_limit_ can't be specified |

**revokeChatInviteLink**

Use this method to revoke an invite link created by the bot. If the primary link is revoked, a new link is automatically generated. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns the revoked invite link as [ChatInviteLink](broken-reference) object.

| Parameter    | Type              | Required | Description                                                                                               |
| ------------ | ----------------- | -------- | --------------------------------------------------------------------------------------------------------- |
| chat\_id     | Integer or String | Yes      | Unique identifier of the target chat or username of the target channel (in the format `@channelusername`) |
| invite\_link | String            | Yes      | The invite link to revoke                                                                                 |

**approveChatJoinRequest**

Use this method to approve a chat join request. The bot must be an administrator in the chat for this to work and must have the _can\_invite\_users_ administrator right. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| user\_id  | Integer           | Yes      | Unique identifier of the target user                                                                       |

**declineChatJoinRequest**

Use this method to decline a chat join request. The bot must be an administrator in the chat for this to work and must have the _can\_invite\_users_ administrator right. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| user\_id  | Integer           | Yes      | Unique identifier of the target user                                                                       |

**setChatPhoto**

Use this method to set a new profile photo for the chat. Photos can't be changed for private chats. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns _True_ on success.

| Parameter | Type                          | Required | Description                                                                                                |
| --------- | ----------------------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String             | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| photo     | [InputFile](broken-reference) | Yes      | New chat photo, uploaded using multipart/form-data                                                         |

**deleteChatPhoto**

Use this method to delete a chat photo. Photos can't be changed for private chats. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |

**setChatTitle**

Use this method to change the title of a chat. Titles can't be changed for private chats. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| title     | String            | Yes      | New chat title, 1-128 characters                                                                           |

**setChatDescription**

Use this method to change the description of a group, a supergroup or a channel. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns _True_ on success.

| Parameter   | Type              | Required | Description                                                                                                |
| ----------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id    | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| description | String            | Optional | New chat description, 0-255 characters                                                                     |

**pinChatMessage**

Use this method to add a message to the list of pinned messages in a chat. If the chat is not a private chat, the bot must be an administrator in the chat for this to work and must have the 'can\_pin\_messages' administrator right in a supergroup or 'can\_edit\_messages' administrator right in a channel. Returns _True_ on success.

| Parameter             | Type              | Required | Description                                                                                                                                                                  |
| --------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                   |
| message\_id           | Integer           | Yes      | Identifier of a message to pin                                                                                                                                               |
| disable\_notification | Boolean           | Optional | Pass _True_ if it is not necessary to send a notification to all chat members about the new pinned message. Notifications are always disabled in channels and private chats. |

**unpinChatMessage**

Use this method to remove a message from the list of pinned messages in a chat. If the chat is not a private chat, the bot must be an administrator in the chat for this to work and must have the 'can\_pin\_messages' administrator right in a supergroup or 'can\_edit\_messages' administrator right in a channel. Returns _True_ on success.

| Parameter   | Type              | Required | Description                                                                                                            |
| ----------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------------- |
| chat\_id    | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)             |
| message\_id | Integer           | Optional | Identifier of a message to unpin. If not specified, the most recent pinned message (by sending date) will be unpinned. |

**unpinAllChatMessages**

Use this method to clear the list of pinned messages in a chat. If the chat is not a private chat, the bot must be an administrator in the chat for this to work and must have the 'can\_pin\_messages' administrator right in a supergroup or 'can\_edit\_messages' administrator right in a channel. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |

**leaveChat**

Use this method for your bot to leave a group, supergroup or channel. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                              |
| --------- | ----------------- | -------- | ------------------------------------------------------------------------------------------------------------------------ |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup or channel (in the format `@channelusername`) |

**getChat**

Use this method to get up to date information about the chat. Returns a [Chat](broken-reference) object on success.

| Parameter | Type              | Required | Description                                                                                                              |
| --------- | ----------------- | -------- | ------------------------------------------------------------------------------------------------------------------------ |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup or channel (in the format `@channelusername`) |

**getChatAdministrators**

Use this method to get a list of administrators in a chat, which aren't bots. Returns an Array of [ChatMember](broken-reference) objects.

| Parameter | Type              | Required | Description                                                                                                              |
| --------- | ----------------- | -------- | ------------------------------------------------------------------------------------------------------------------------ |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup or channel (in the format `@channelusername`) |

**getChatMemberCount**

Use this method to get the number of members in a chat. Returns _Int_ on success.

| Parameter | Type              | Required | Description                                                                                                              |
| --------- | ----------------- | -------- | ------------------------------------------------------------------------------------------------------------------------ |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup or channel (in the format `@channelusername`) |

**getChatMember**

Use this method to get information about a member of a chat. The method is only guaranteed to work for other users if the bot is an administrator in the chat. Returns a [ChatMember](broken-reference) object on success.

| Parameter | Type              | Required | Description                                                                                                              |
| --------- | ----------------- | -------- | ------------------------------------------------------------------------------------------------------------------------ |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup or channel (in the format `@channelusername`) |
| user\_id  | Integer           | Yes      | Unique identifier of the target user                                                                                     |

**setChatStickerSet**

Use this method to set a new group sticker set for a supergroup. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Use the field _can\_set\_sticker\_set_ optionally returned in [getChat](broken-reference) requests to check if the bot can use this method. Returns _True_ on success.

| Parameter          | Type              | Required | Description                                                                                                      |
| ------------------ | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id           | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |
| sticker\_set\_name | String            | Yes      | Name of the sticker set to be set as the group sticker set                                                       |

**deleteChatStickerSet**

Use this method to delete a group sticker set from a supergroup. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Use the field _can\_set\_sticker\_set_ optionally returned in [getChat](broken-reference) requests to check if the bot can use this method. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                      |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |

**getForumTopicIconStickers**

Use this method to get custom emoji stickers, which can be used as a forum topic icon by any user. Requires no parameters. Returns an Array of [Sticker](broken-reference) objects.

**createForumTopic**

Use this method to create a topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the _can\_manage\_topics_ administrator rights. Returns information about the created topic as a [ForumTopic](broken-reference) object.

| Parameter               | Type              | Required | Description                                                                                                                                                                                    |
| ----------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`)                                                                               |
| name                    | String            | Yes      | Topic name, 1-128 characters                                                                                                                                                                   |
| icon\_color             | Integer           | Optional | Color of the topic icon in RGB format. Currently, must be one of 7322096 (0x6FB9F0), 16766590 (0xFFD67E), 13338331 (0xCB86DB), 9367192 (0x8EEE98), 16749490 (0xFF93B2), or 16478047 (0xFB6F5F) |
| icon\_custom\_emoji\_id | String            | Optional | Unique identifier of the custom emoji shown as the topic icon. Use [getForumTopicIconStickers](broken-reference) to get all allowed custom emoji identifiers.                                  |

**editForumTopic**

Use this method to edit name and icon of a topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have _can\_manage\_topics_ administrator rights, unless it is the creator of the topic. Returns _True_ on success.

| Parameter               | Type              | Required | Description                                                                                                                                                                                                                                                |
| ----------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`)                                                                                                                                           |
| message\_thread\_id     | Integer           | Yes      | Unique identifier for the target message thread of the forum topic                                                                                                                                                                                         |
| name                    | String            | Optional | New topic name, 0-128 characters. If not specified or empty, the current name of the topic will be kept                                                                                                                                                    |
| icon\_custom\_emoji\_id | String            | Optional | New unique identifier of the custom emoji shown as the topic icon. Use [getForumTopicIconStickers](broken-reference) to get all allowed custom emoji identifiers. Pass an empty string to remove the icon. If not specified, the current icon will be kept |

**closeForumTopic**

Use this method to close an open topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the _can\_manage\_topics_ administrator rights, unless it is the creator of the topic. Returns _True_ on success.

| Parameter           | Type              | Required | Description                                                                                                      |
| ------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id            | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |
| message\_thread\_id | Integer           | Yes      | Unique identifier for the target message thread of the forum topic                                               |

**reopenForumTopic**

Use this method to reopen a closed topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the _can\_manage\_topics_ administrator rights, unless it is the creator of the topic. Returns _True_ on success.

| Parameter           | Type              | Required | Description                                                                                                      |
| ------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id            | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |
| message\_thread\_id | Integer           | Yes      | Unique identifier for the target message thread of the forum topic                                               |

**deleteForumTopic**

Use this method to delete a forum topic along with all its messages in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the _can\_delete\_messages_ administrator rights. Returns _True_ on success.

| Parameter           | Type              | Required | Description                                                                                                      |
| ------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id            | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |
| message\_thread\_id | Integer           | Yes      | Unique identifier for the target message thread of the forum topic                                               |

**unpinAllForumTopicMessages**

Use this method to clear the list of pinned messages in a forum topic. The bot must be an administrator in the chat for this to work and must have the _can\_pin\_messages_ administrator right in the supergroup. Returns _True_ on success.

| Parameter           | Type              | Required | Description                                                                                                      |
| ------------------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id            | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |
| message\_thread\_id | Integer           | Yes      | Unique identifier for the target message thread of the forum topic                                               |

**editGeneralForumTopic**

Use this method to edit the name of the 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have _can\_manage\_topics_ administrator rights. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                      |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |
| name      | String            | Yes      | New topic name, 1-128 characters                                                                                 |

**closeGeneralForumTopic**

Use this method to close an open 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the _can\_manage\_topics_ administrator rights. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                      |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |

**reopenGeneralForumTopic**

Use this method to reopen a closed 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the _can\_manage\_topics_ administrator rights. The topic will be automatically unhidden if it was hidden. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                      |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |

**hideGeneralForumTopic**

Use this method to hide the 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the _can\_manage\_topics_ administrator rights. The topic will be automatically closed if it was open. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                      |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |

**unhideGeneralForumTopic**

Use this method to unhide the 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the _can\_manage\_topics_ administrator rights. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                      |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |

**unpinAllGeneralForumTopicMessages**

Use this method to clear the list of pinned messages in a General forum topic. The bot must be an administrator in the chat for this to work and must have the _can\_pin\_messages_ administrator right in the supergroup. Returns _True_ on success.

| Parameter | Type              | Required | Description                                                                                                      |
| --------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the target chat or username of the target supergroup (in the format `@supergroupusername`) |

**answerCallbackQuery**

Use this method to send answers to callback queries sent from [inline keyboards](https://about/bots/features#inline-keyboards). The answer will be displayed to the user as a notification at the top of the chat screen or as an alert. On success, _True_ is returned.

> Alternatively, the user can be redirected to the specified Game URL. For this option to work, you must first create a game for your bot via [@BotFather](https://t.me/botfather) and accept the terms. Otherwise, you may use links like `t.me/your_bot?start=XXXX` that open your bot with a parameter.

| Parameter           | Type    | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ------------------- | ------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| callback\_query\_id | String  | Yes      | Unique identifier for the query to be answered                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| text                | String  | Optional | Text of the notification. If not specified, nothing will be shown to the user, 0-200 characters                                                                                                                                                                                                                                                                                                                                                                                 |
| show\_alert         | Boolean | Optional | If _True_, an alert will be shown by the client instead of a notification at the top of the chat screen. Defaults to _false_.                                                                                                                                                                                                                                                                                                                                                   |
| url                 | String  | Optional | <p>URL that will be opened by the user's client. If you have created a <a href="broken-reference">Game</a> and accepted the conditions via <a href="https://t.me/botfather">@BotFather</a>, specify the URL that opens your game - note that this will only work if the query comes from a <a href="broken-reference"><em>callback_game</em></a> button.</p><p>Otherwise, you may use links like <code>t.me/your_bot?start=XXXX</code> that open your bot with a parameter.</p> |
| cache\_time         | Integer | Optional | The maximum amount of time in seconds that the result of the callback query may be cached client-side. Telegram apps will support caching starting in version 3.14. Defaults to 0.                                                                                                                                                                                                                                                                                              |

**getUserChatBoosts**

Use this method to get the list of boosts added to a chat by a user. Requires administrator rights in the chat. Returns a [UserChatBoosts](broken-reference) object.

| Parameter | Type              | Required | Description                                                                                  |
| --------- | ----------------- | -------- | -------------------------------------------------------------------------------------------- |
| chat\_id  | Integer or String | Yes      | Unique identifier for the chat or username of the channel (in the format `@channelusername`) |
| user\_id  | Integer           | Yes      | Unique identifier of the target user                                                         |

**setMyCommands**

Use this method to change the list of the bot's commands. See [this manual](https://about/bots/features#commands) for more details about bot commands. Returns _True_ on success.

| Parameter      | Type                                    | Required | Description                                                                                                                                                    |
| -------------- | --------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| commands       | Array of [BotCommand](broken-reference) | Yes      | A JSON-serialized list of bot commands to be set as the list of the bot's commands. At most 100 commands can be specified.                                     |
| scope          | [BotCommandScope](broken-reference)     | Optional | A JSON-serialized object, describing scope of users for which the commands are relevant. Defaults to [BotCommandScopeDefault](broken-reference).               |
| language\_code | String                                  | Optional | A two-letter ISO 639-1 language code. If empty, commands will be applied to all users from the given scope, for whose language there are no dedicated commands |

**deleteMyCommands**

Use this method to delete the list of the bot's commands for the given scope and user language. After deletion, [higher level commands](broken-reference) will be shown to affected users. Returns _True_ on success.

| Parameter      | Type                                | Required | Description                                                                                                                                                    |
| -------------- | ----------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| scope          | [BotCommandScope](broken-reference) | Optional | A JSON-serialized object, describing scope of users for which the commands are relevant. Defaults to [BotCommandScopeDefault](broken-reference).               |
| language\_code | String                              | Optional | A two-letter ISO 639-1 language code. If empty, commands will be applied to all users from the given scope, for whose language there are no dedicated commands |

**getMyCommands**

Use this method to get the current list of the bot's commands for the given scope and user language. Returns an Array of [BotCommand](broken-reference) objects. If commands aren't set, an empty list is returned.

| Parameter      | Type                                | Required | Description                                                                                                  |
| -------------- | ----------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------ |
| scope          | [BotCommandScope](broken-reference) | Optional | A JSON-serialized object, describing scope of users. Defaults to [BotCommandScopeDefault](broken-reference). |
| language\_code | String                              | Optional | A two-letter ISO 639-1 language code or an empty string                                                      |

**setMyName**

Use this method to change the bot's name. Returns _True_ on success.

| Parameter      | Type   | Required | Description                                                                                                                        |
| -------------- | ------ | -------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| name           | String | Optional | New bot name; 0-64 characters. Pass an empty string to remove the dedicated name for the given language.                           |
| language\_code | String | Optional | A two-letter ISO 639-1 language code. If empty, the name will be shown to all users for whose language there is no dedicated name. |

**getMyName**

Use this method to get the current bot name for the given user language. Returns [BotName](broken-reference) on success.

| Parameter      | Type   | Required | Description                                             |
| -------------- | ------ | -------- | ------------------------------------------------------- |
| language\_code | String | Optional | A two-letter ISO 639-1 language code or an empty string |

**setMyDescription**

Use this method to change the bot's description, which is shown in the chat with the bot if the chat is empty. Returns _True_ on success.

| Parameter      | Type   | Required | Description                                                                                                                                        |
| -------------- | ------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| description    | String | Optional | New bot description; 0-512 characters. Pass an empty string to remove the dedicated description for the given language.                            |
| language\_code | String | Optional | A two-letter ISO 639-1 language code. If empty, the description will be applied to all users for whose language there is no dedicated description. |

**getMyDescription**

Use this method to get the current bot description for the given user language. Returns [BotDescription](broken-reference) on success.

| Parameter      | Type   | Required | Description                                             |
| -------------- | ------ | -------- | ------------------------------------------------------- |
| language\_code | String | Optional | A two-letter ISO 639-1 language code or an empty string |

**setMyShortDescription**

Use this method to change the bot's short description, which is shown on the bot's profile page and is sent together with the link when users share the bot. Returns _True_ on success.

| Parameter          | Type   | Required | Description                                                                                                                                                    |
| ------------------ | ------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| short\_description | String | Optional | New short description for the bot; 0-120 characters. Pass an empty string to remove the dedicated short description for the given language.                    |
| language\_code     | String | Optional | A two-letter ISO 639-1 language code. If empty, the short description will be applied to all users for whose language there is no dedicated short description. |

**getMyShortDescription**

Use this method to get the current bot short description for the given user language. Returns [BotShortDescription](broken-reference) on success.

| Parameter      | Type   | Required | Description                                             |
| -------------- | ------ | -------- | ------------------------------------------------------- |
| language\_code | String | Optional | A two-letter ISO 639-1 language code or an empty string |

**setChatMenuButton**

Use this method to change the bot's menu button in a private chat, or the default menu button. Returns _True_ on success.

| Parameter    | Type                           | Required | Description                                                                                                |
| ------------ | ------------------------------ | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id     | Integer                        | Optional | Unique identifier for the target private chat. If not specified, default bot's menu button will be changed |
| menu\_button | [MenuButton](broken-reference) | Optional | A JSON-serialized object for the bot's new menu button. Defaults to [MenuButtonDefault](broken-reference)  |

**getChatMenuButton**

Use this method to get the current value of the bot's menu button in a private chat, or the default menu button. Returns [MenuButton](broken-reference) on success.

| Parameter | Type    | Required | Description                                                                                                 |
| --------- | ------- | -------- | ----------------------------------------------------------------------------------------------------------- |
| chat\_id  | Integer | Optional | Unique identifier for the target private chat. If not specified, default bot's menu button will be returned |

**setMyDefaultAdministratorRights**

Use this method to change the default administrator rights requested by the bot when it's added as an administrator to groups or channels. These rights will be suggested to users, but they are free to modify the list before adding the bot. Returns _True_ on success.

| Parameter     | Type                                        | Required | Description                                                                                                                                                                       |
| ------------- | ------------------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| rights        | [ChatAdministratorRights](broken-reference) | Optional | A JSON-serialized object describing new default administrator rights. If not specified, the default administrator rights will be cleared.                                         |
| for\_channels | Boolean                                     | Optional | Pass _True_ to change the default administrator rights of the bot in channels. Otherwise, the default administrator rights of the bot for groups and supergroups will be changed. |

**getMyDefaultAdministratorRights**

Use this method to get the current default administrator rights of the bot. Returns [ChatAdministratorRights](broken-reference) on success.

| Parameter     | Type    | Required | Description                                                                                                                                                             |
| ------------- | ------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| for\_channels | Boolean | Optional | Pass _True_ to get default administrator rights of the bot in channels. Otherwise, default administrator rights of the bot for groups and supergroups will be returned. |

**Inline mode methods**

Methods and objects used in the inline mode are described in the [Inline mode section](broken-reference).

#### Updating messages

The following methods allow you to change an existing message in the message history instead of sending a new one with a result of an action. This is most useful for messages with [inline keyboards](https://about/bots/features#inline-keyboards) using callback queries, but can also help reduce clutter in conversations with regular chat bots.

Please note, that it is currently only possible to edit messages without _reply\_markup_ or with [inline keyboards](https://about/bots/features#inline-keyboards).

**editMessageText**

Use this method to edit text and [game](broken-reference) messages. On success, if the edited message is not an inline message, the edited [Message](broken-reference) is returned, otherwise _True_ is returned.

| Parameter              | Type                                       | Required | Description                                                                                                                                                    |
| ---------------------- | ------------------------------------------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id               | Integer or String                          | Optional | Required if _inline\_message\_id_ is not specified. Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| message\_id            | Integer                                    | Optional | Required if _inline\_message\_id_ is not specified. Identifier of the message to edit                                                                          |
| inline\_message\_id    | String                                     | Optional | Required if _chat\_id_ and _message\_id_ are not specified. Identifier of the inline message                                                                   |
| text                   | String                                     | Yes      | New text of the message, 1-4096 characters after entities parsing                                                                                              |
| parse\_mode            | String                                     | Optional | Mode for parsing entities in the message text. See [formatting options](broken-reference) for more details.                                                    |
| entities               | Array of [MessageEntity](broken-reference) | Optional | A JSON-serialized list of special entities that appear in message text, which can be specified instead of _parse\_mode_                                        |
| link\_preview\_options | [LinkPreviewOptions](broken-reference)     | Optional | Link preview generation options for the message                                                                                                                |
| reply\_markup          | [InlineKeyboardMarkup](broken-reference)   | Optional | A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards).                                                               |

**editMessageCaption**

Use this method to edit captions of messages. On success, if the edited message is not an inline message, the edited [Message](broken-reference) is returned, otherwise _True_ is returned.

| Parameter           | Type                                       | Required | Description                                                                                                                                                    |
| ------------------- | ------------------------------------------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id            | Integer or String                          | Optional | Required if _inline\_message\_id_ is not specified. Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| message\_id         | Integer                                    | Optional | Required if _inline\_message\_id_ is not specified. Identifier of the message to edit                                                                          |
| inline\_message\_id | String                                     | Optional | Required if _chat\_id_ and _message\_id_ are not specified. Identifier of the inline message                                                                   |
| caption             | String                                     | Optional | New caption of the message, 0-1024 characters after entities parsing                                                                                           |
| parse\_mode         | String                                     | Optional | Mode for parsing entities in the message caption. See [formatting options](broken-reference) for more details.                                                 |
| caption\_entities   | Array of [MessageEntity](broken-reference) | Optional | A JSON-serialized list of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                         |
| reply\_markup       | [InlineKeyboardMarkup](broken-reference)   | Optional | A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards).                                                               |

**editMessageMedia**

Use this method to edit animation, audio, document, photo, or video messages. If a message is part of a message album, then it can be edited only to an audio for audio albums, only to a document for document albums and to a photo or a video otherwise. When an inline message is edited, a new file can't be uploaded; use a previously uploaded file via its file\_id or specify a URL. On success, if the edited message is not an inline message, the edited [Message](broken-reference) is returned, otherwise _True_ is returned.

| Parameter           | Type                                     | Required | Description                                                                                                                                                    |
| ------------------- | ---------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id            | Integer or String                        | Optional | Required if _inline\_message\_id_ is not specified. Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| message\_id         | Integer                                  | Optional | Required if _inline\_message\_id_ is not specified. Identifier of the message to edit                                                                          |
| inline\_message\_id | String                                   | Optional | Required if _chat\_id_ and _message\_id_ are not specified. Identifier of the inline message                                                                   |
| media               | [InputMedia](broken-reference)           | Yes      | A JSON-serialized object for a new media content of the message                                                                                                |
| reply\_markup       | [InlineKeyboardMarkup](broken-reference) | Optional | A JSON-serialized object for a new [inline keyboard](https://about/bots/features#inline-keyboards).                                                            |

**editMessageLiveLocation**

Use this method to edit live location messages. A location can be edited until its _live\_period_ expires or editing is explicitly disabled by a call to [stopMessageLiveLocation](broken-reference). On success, if the edited message is not an inline message, the edited [Message](broken-reference) is returned, otherwise _True_ is returned.

| Parameter                | Type                                     | Required | Description                                                                                                                                                    |
| ------------------------ | ---------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                 | Integer or String                        | Optional | Required if _inline\_message\_id_ is not specified. Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| message\_id              | Integer                                  | Optional | Required if _inline\_message\_id_ is not specified. Identifier of the message to edit                                                                          |
| inline\_message\_id      | String                                   | Optional | Required if _chat\_id_ and _message\_id_ are not specified. Identifier of the inline message                                                                   |
| latitude                 | Float                                    | Yes      | Latitude of new location                                                                                                                                       |
| longitude                | Float                                    | Yes      | Longitude of new location                                                                                                                                      |
| horizontal\_accuracy     | Float                                    | Optional | The radius of uncertainty for the location, measured in meters; 0-1500                                                                                         |
| heading                  | Integer                                  | Optional | Direction in which the user is moving, in degrees. Must be between 1 and 360 if specified.                                                                     |
| proximity\_alert\_radius | Integer                                  | Optional | The maximum distance for proximity alerts about approaching another chat member, in meters. Must be between 1 and 100000 if specified.                         |
| reply\_markup            | [InlineKeyboardMarkup](broken-reference) | Optional | A JSON-serialized object for a new [inline keyboard](https://about/bots/features#inline-keyboards).                                                            |

**stopMessageLiveLocation**

Use this method to stop updating a live location message before _live\_period_ expires. On success, if the message is not an inline message, the edited [Message](broken-reference) is returned, otherwise _True_ is returned.

| Parameter           | Type                                     | Required | Description                                                                                                                                                    |
| ------------------- | ---------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id            | Integer or String                        | Optional | Required if _inline\_message\_id_ is not specified. Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| message\_id         | Integer                                  | Optional | Required if _inline\_message\_id_ is not specified. Identifier of the message with live location to stop                                                       |
| inline\_message\_id | String                                   | Optional | Required if _chat\_id_ and _message\_id_ are not specified. Identifier of the inline message                                                                   |
| reply\_markup       | [InlineKeyboardMarkup](broken-reference) | Optional | A JSON-serialized object for a new [inline keyboard](https://about/bots/features#inline-keyboards).                                                            |

**editMessageReplyMarkup**

Use this method to edit only the reply markup of messages. On success, if the edited message is not an inline message, the edited [Message](broken-reference) is returned, otherwise _True_ is returned.

| Parameter           | Type                                     | Required | Description                                                                                                                                                    |
| ------------------- | ---------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id            | Integer or String                        | Optional | Required if _inline\_message\_id_ is not specified. Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| message\_id         | Integer                                  | Optional | Required if _inline\_message\_id_ is not specified. Identifier of the message to edit                                                                          |
| inline\_message\_id | String                                   | Optional | Required if _chat\_id_ and _message\_id_ are not specified. Identifier of the inline message                                                                   |
| reply\_markup       | [InlineKeyboardMarkup](broken-reference) | Optional | A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards).                                                               |

**stopPoll**

Use this method to stop a poll which was sent by the bot. On success, the stopped [Poll](broken-reference) is returned.

| Parameter     | Type                                     | Required | Description                                                                                                 |
| ------------- | ---------------------------------------- | -------- | ----------------------------------------------------------------------------------------------------------- |
| chat\_id      | Integer or String                        | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)  |
| message\_id   | Integer                                  | Yes      | Identifier of the original message with the poll                                                            |
| reply\_markup | [InlineKeyboardMarkup](broken-reference) | Optional | A JSON-serialized object for a new message [inline keyboard](https://about/bots/features#inline-keyboards). |

**deleteMessage**

Use this method to delete a message, including service messages, with the following limitations:\
\- A message can only be deleted if it was sent less than 48 hours ago.\
\- Service messages about a supergroup, channel, or forum topic creation can't be deleted.\
\- A dice message in a private chat can only be deleted if it was sent more than 24 hours ago.\
\- Bots can delete outgoing messages in private chats, groups, and supergroups.\
\- Bots can delete incoming messages in private chats.\
\- Bots granted _can\_post\_messages_ permissions can delete outgoing messages in channels.\
\- If the bot is an administrator of a group, it can delete any message there.\
\- If the bot has _can\_delete\_messages_ permission in a supergroup or a channel, it can delete any message there.\
Returns _True_ on success.

| Parameter   | Type              | Required | Description                                                                                                |
| ----------- | ----------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| chat\_id    | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`) |
| message\_id | Integer           | Yes      | Identifier of the message to delete                                                                        |

**deleteMessages**

Use this method to delete multiple messages simultaneously. If some of the specified messages can't be found, they are skipped. Returns _True_ on success.

| Parameter    | Type              | Required | Description                                                                                                                                               |
| ------------ | ----------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id     | Integer or String | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                |
| message\_ids | Array of Integer  | Yes      | A JSON-serialized list of 1-100 identifiers of messages to delete. See [deleteMessage](broken-reference) for limitations on which messages can be deleted |

#### Stickers

The following methods and objects allow your bot to handle stickers and sticker sets.

**Sticker**

This object represents a sticker.

| Field              | Type                             | Description                                                                                                                                                                                                         |
| ------------------ | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| file\_id           | String                           | Identifier for this file, which can be used to download or reuse the file                                                                                                                                           |
| file\_unique\_id   | String                           | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file.                                                                    |
| type               | String                           | Type of the sticker, currently one of “regular”, “mask”, “custom\_emoji”. The type of the sticker is independent from its format, which is determined by the fields _is\_animated_ and _is\_video_.                 |
| width              | Integer                          | Sticker width                                                                                                                                                                                                       |
| height             | Integer                          | Sticker height                                                                                                                                                                                                      |
| is\_animated       | Boolean                          | _True_, if the sticker is [animated](https://telegram.org/blog/animated-stickers)                                                                                                                                   |
| is\_video          | Boolean                          | _True_, if the sticker is a [video sticker](https://telegram.org/blog/video-stickers-better-reactions)                                                                                                              |
| thumbnail          | [PhotoSize](broken-reference)    | _Optional_. Sticker thumbnail in the .WEBP or .JPG format                                                                                                                                                           |
| emoji              | String                           | _Optional_. Emoji associated with the sticker                                                                                                                                                                       |
| set\_name          | String                           | _Optional_. Name of the sticker set to which the sticker belongs                                                                                                                                                    |
| premium\_animation | [File](broken-reference)         | _Optional_. For premium regular stickers, premium animation for the sticker                                                                                                                                         |
| mask\_position     | [MaskPosition](broken-reference) | _Optional_. For mask stickers, the position where the mask should be placed                                                                                                                                         |
| custom\_emoji\_id  | String                           | _Optional_. For custom emoji stickers, unique identifier of the custom emoji                                                                                                                                        |
| needs\_repainting  | True                             | _Optional_. _True_, if the sticker must be repainted to a text color in messages, the color of the Telegram Premium badge in emoji status, white color on chat photos, or another appropriate color in other places |
| file\_size         | Integer                          | _Optional_. File size in bytes                                                                                                                                                                                      |

**StickerSet**

This object represents a sticker set.

| Field         | Type                                 | Description                                                                                                     |
| ------------- | ------------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| name          | String                               | Sticker set name                                                                                                |
| title         | String                               | Sticker set title                                                                                               |
| sticker\_type | String                               | Type of stickers in the set, currently one of “regular”, “mask”, “custom\_emoji”                                |
| is\_animated  | Boolean                              | _True_, if the sticker set contains [animated stickers](https://telegram.org/blog/animated-stickers)            |
| is\_video     | Boolean                              | _True_, if the sticker set contains [video stickers](https://telegram.org/blog/video-stickers-better-reactions) |
| stickers      | Array of [Sticker](broken-reference) | List of all set stickers                                                                                        |
| thumbnail     | [PhotoSize](broken-reference)        | _Optional_. Sticker set thumbnail in the .WEBP, .TGS, or .WEBM format                                           |

**MaskPosition**

This object describes the position on faces where a mask should be placed by default.

| Field    | Type   | Description                                                                                                                                                                           |
| -------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| point    | String | The part of the face relative to which the mask should be placed. One of “forehead”, “eyes”, “mouth”, or “chin”.                                                                      |
| x\_shift | Float  | Shift by X-axis measured in widths of the mask scaled to the face size, from left to right. For example, choosing -1.0 will place mask just to the left of the default mask position. |
| y\_shift | Float  | Shift by Y-axis measured in heights of the mask scaled to the face size, from top to bottom. For example, 1.0 will place the mask just below the default mask position.               |
| scale    | Float  | Mask scaling coefficient. For example, 2.0 means double size.                                                                                                                         |

**InputSticker**

This object describes a sticker to be added to a sticker set.

| Field          | Type                                    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| -------------- | --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sticker        | [InputFile](broken-reference) or String | The added sticker. Pass a _file\_id_ as a String to send a file that already exists on the Telegram servers, pass an HTTP URL as a String for Telegram to get a file from the Internet, upload a new one using multipart/form-data, or pass “attach://\<file\_attach\_name>” to upload a new one using multipart/form-data under \<file\_attach\_name> name. Animated and video stickers can't be uploaded via HTTP URL. [More information on Sending Files »](broken-reference) |
| emoji\_list    | Array of String                         | List of 1-20 emoji associated with the sticker                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| mask\_position | [MaskPosition](broken-reference)        | _Optional_. Position where the mask should be placed on faces. For “mask” stickers only.                                                                                                                                                                                                                                                                                                                                                                                         |
| keywords       | Array of String                         | _Optional_. List of 0-20 search keywords for the sticker with total length of up to 64 characters. For “regular” and “custom\_emoji” stickers only.                                                                                                                                                                                                                                                                                                                              |

**sendSticker**

Use this method to send static .WEBP, [animated](https://telegram.org/blog/animated-stickers) .TGS, or [video](https://telegram.org/blog/video-stickers-better-reactions) .WEBM stickers. On success, the sent [Message](broken-reference) is returned.

| Parameter             | Type                                                                                                                                                             | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id              | Integer or String                                                                                                                                                | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                                                 |
| message\_thread\_id   | Integer                                                                                                                                                          | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                                                                                                                                           |
| sticker               | [InputFile](broken-reference) or String                                                                                                                          | Yes      | Sticker to send. Pass a file\_id as String to send a file that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a .WEBP sticker from the Internet, or upload a new .WEBP or .TGS sticker using multipart/form-data. [More information on Sending Files »](broken-reference). Video stickers can only be sent by a file\_id. Animated stickers can't be sent via an HTTP URL. |
| emoji                 | String                                                                                                                                                           | Optional | Emoji associated with the sticker; only for just uploaded stickers                                                                                                                                                                                                                                                                                                                                                         |
| disable\_notification | Boolean                                                                                                                                                          | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                                                                                                                                                     |
| protect\_content      | Boolean                                                                                                                                                          | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                                                                                                                                                                       |
| reply\_parameters     | [ReplyParameters](broken-reference)                                                                                                                              | Optional | Description of the message to reply to                                                                                                                                                                                                                                                                                                                                                                                     |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) or [ReplyKeyboardMarkup](broken-reference) or [ReplyKeyboardRemove](broken-reference) or [ForceReply](broken-reference) | Optional | Additional interface options. A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards), [custom reply keyboard](https://about/bots/features#keyboards), instructions to remove reply keyboard or to force a reply from the user.                                                                                                                                                    |

**getStickerSet**

Use this method to get a sticker set. On success, a [StickerSet](broken-reference) object is returned.

| Parameter | Type   | Required | Description             |
| --------- | ------ | -------- | ----------------------- |
| name      | String | Yes      | Name of the sticker set |

**getCustomEmojiStickers**

Use this method to get information about custom emoji stickers by their identifiers. Returns an Array of [Sticker](broken-reference) objects.

| Parameter          | Type            | Required | Description                                                                                                |
| ------------------ | --------------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| custom\_emoji\_ids | Array of String | Yes      | A JSON-serialized list of custom emoji identifiers. At most 200 custom emoji identifiers can be specified. |

**uploadStickerFile**

Use this method to upload a file with a sticker for later use in the [createNewStickerSet](broken-reference) and [addStickerToSet](broken-reference) methods (the file can be used multiple times). Returns the uploaded [File](broken-reference) on success.

| Parameter       | Type                          | Required | Description                                                                                                                                                                                                                    |
| --------------- | ----------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| user\_id        | Integer                       | Yes      | User identifier of sticker file owner                                                                                                                                                                                          |
| sticker         | [InputFile](broken-reference) | Yes      | A file with the sticker in .WEBP, .PNG, .TGS, or .WEBM format. See[https://core.telegram.org/stickers](https://core.telegram.org/stickers) for technical requirements. [More information on Sending Files »](broken-reference) |
| sticker\_format | String                        | Yes      | Format of the sticker, must be one of “static”, “animated”, “video”                                                                                                                                                            |

**createNewStickerSet**

Use this method to create a new sticker set owned by a user. The bot will be able to edit the sticker set thus created. Returns _True_ on success.

| Parameter         | Type                                      | Required | Description                                                                                                                                                                                                                                                                                                   |
| ----------------- | ----------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| user\_id          | Integer                                   | Yes      | User identifier of created sticker set owner                                                                                                                                                                                                                                                                  |
| name              | String                                    | Yes      | Short name of sticker set, to be used in `t.me/addstickers/` URLs (e.g., _animals_). Can contain only English letters, digits and underscores. Must begin with a letter, can't contain consecutive underscores and must end in `"_by_<bot_username>"`. `<bot_username>` is case insensitive. 1-64 characters. |
| title             | String                                    | Yes      | Sticker set title, 1-64 characters                                                                                                                                                                                                                                                                            |
| stickers          | Array of [InputSticker](broken-reference) | Yes      | A JSON-serialized list of 1-50 initial stickers to be added to the sticker set                                                                                                                                                                                                                                |
| sticker\_format   | String                                    | Yes      | Format of stickers in the set, must be one of “static”, “animated”, “video”                                                                                                                                                                                                                                   |
| sticker\_type     | String                                    | Optional | Type of stickers in the set, pass “regular”, “mask”, or “custom\_emoji”. By default, a regular sticker set is created.                                                                                                                                                                                        |
| needs\_repainting | Boolean                                   | Optional | Pass _True_ if stickers in the sticker set must be repainted to the color of text when used in messages, the accent color if used as emoji status, white on chat photos, or another appropriate color based on context; for custom emoji sticker sets only                                                    |

**addStickerToSet**

Use this method to add a new sticker to a set created by the bot. The format of the added sticker must match the format of the other stickers in the set. Emoji sticker sets can have up to 200 stickers. Animated and video sticker sets can have up to 50 stickers. Static sticker sets can have up to 120 stickers. Returns _True_ on success.

| Parameter | Type                             | Required | Description                                                                                                                                                   |
| --------- | -------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| user\_id  | Integer                          | Yes      | User identifier of sticker set owner                                                                                                                          |
| name      | String                           | Yes      | Sticker set name                                                                                                                                              |
| sticker   | [InputSticker](broken-reference) | Yes      | A JSON-serialized object with information about the added sticker. If exactly the same sticker had already been added to the set, then the set isn't changed. |

**setStickerPositionInSet**

Use this method to move a sticker in a set created by the bot to a specific position. Returns _True_ on success.

| Parameter | Type    | Required | Description                                 |
| --------- | ------- | -------- | ------------------------------------------- |
| sticker   | String  | Yes      | File identifier of the sticker              |
| position  | Integer | Yes      | New sticker position in the set, zero-based |

**deleteStickerFromSet**

Use this method to delete a sticker from a set created by the bot. Returns _True_ on success.

| Parameter | Type   | Required | Description                    |
| --------- | ------ | -------- | ------------------------------ |
| sticker   | String | Yes      | File identifier of the sticker |

**setStickerEmojiList**

Use this method to change the list of emoji assigned to a regular or custom emoji sticker. The sticker must belong to a sticker set created by the bot. Returns _True_ on success.

| Parameter   | Type            | Required | Description                                                      |
| ----------- | --------------- | -------- | ---------------------------------------------------------------- |
| sticker     | String          | Yes      | File identifier of the sticker                                   |
| emoji\_list | Array of String | Yes      | A JSON-serialized list of 1-20 emoji associated with the sticker |

**setStickerKeywords**

Use this method to change search keywords assigned to a regular or custom emoji sticker. The sticker must belong to a sticker set created by the bot. Returns _True_ on success.

| Parameter | Type            | Required | Description                                                                                             |
| --------- | --------------- | -------- | ------------------------------------------------------------------------------------------------------- |
| sticker   | String          | Yes      | File identifier of the sticker                                                                          |
| keywords  | Array of String | Optional | A JSON-serialized list of 0-20 search keywords for the sticker with total length of up to 64 characters |

**setStickerMaskPosition**

Use this method to change the [mask position](broken-reference) of a mask sticker. The sticker must belong to a sticker set that was created by the bot. Returns _True_ on success.

| Parameter      | Type                             | Required | Description                                                                                                                          |
| -------------- | -------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| sticker        | String                           | Yes      | File identifier of the sticker                                                                                                       |
| mask\_position | [MaskPosition](broken-reference) | Optional | A JSON-serialized object with the position where the mask should be placed on faces. Omit the parameter to remove the mask position. |

**setStickerSetTitle**

Use this method to set the title of a created sticker set. Returns _True_ on success.

| Parameter | Type   | Required | Description                        |
| --------- | ------ | -------- | ---------------------------------- |
| name      | String | Yes      | Sticker set name                   |
| title     | String | Yes      | Sticker set title, 1-64 characters |

**setStickerSetThumbnail**

Use this method to set the thumbnail of a regular or mask sticker set. The format of the thumbnail file must match the format of the stickers in the set. Returns _True_ on success.

| Parameter | Type                                    | Required | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| --------- | --------------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name      | String                                  | Yes      | Sticker set name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| user\_id  | Integer                                 | Yes      | User identifier of the sticker set owner                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| thumbnail | [InputFile](broken-reference) or String | Optional | A **.WEBP** or **.PNG** image with the thumbnail, must be up to 128 kilobytes in size and have a width and height of exactly 100px, or a **.TGS** animation with a thumbnail up to 32 kilobytes in size (see[https://core.telegram.org/stickers#animated-sticker-requirements](https://core.telegram.org/stickers#animated-sticker-requirements) for animated sticker technical requirements), or a **WEBM** video with the thumbnail up to 32 kilobytes in size; see[https://core.telegram.org/stickers#video-sticker-requirements](https://core.telegram.org/stickers#video-sticker-requirements) for video sticker technical requirements. Pass a _file\_id_ as a String to send a file that already exists on the Telegram servers, pass an HTTP URL as a String for Telegram to get a file from the Internet, or upload a new one using multipart/form-data. [More information on Sending Files »](broken-reference). Animated and video sticker set thumbnails can't be uploaded via HTTP URL. If omitted, then the thumbnail is dropped and the first sticker is used as the thumbnail. |

**setCustomEmojiStickerSetThumbnail**

Use this method to set the thumbnail of a custom emoji sticker set. Returns _True_ on success.

| Parameter         | Type   | Required | Description                                                                                                                                       |
| ----------------- | ------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| name              | String | Yes      | Sticker set name                                                                                                                                  |
| custom\_emoji\_id | String | Optional | Custom emoji identifier of a sticker from the sticker set; pass an empty string to drop the thumbnail and use the first sticker as the thumbnail. |

**deleteStickerSet**

Use this method to delete a sticker set that was created by the bot. Returns _True_ on success.

| Parameter | Type   | Required | Description      |
| --------- | ------ | -------- | ---------------- |
| name      | String | Yes      | Sticker set name |

#### Inline mode

The following methods and objects allow your bot to work in inline mode.\
Please see our Introduction to Inline bots for more details.

To enable this option, send the `/setinline` command to [@BotFather](https://t.me/botfather) and provide the placeholder text that the user will see in the input field after typing your bot's name.

**InlineQuery**

This object represents an incoming inline query. When the user sends an empty query, your bot could return some default or trending results.

| Field      | Type                         | Description                                                                                                                                                                                                                                                                                                                                          |
| ---------- | ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id         | String                       | Unique identifier for this query                                                                                                                                                                                                                                                                                                                     |
| from       | [User](broken-reference)     | Sender                                                                                                                                                                                                                                                                                                                                               |
| query      | String                       | Text of the query (up to 256 characters)                                                                                                                                                                                                                                                                                                             |
| offset     | String                       | Offset of the results to be returned, can be controlled by the bot                                                                                                                                                                                                                                                                                   |
| chat\_type | String                       | _Optional_. Type of the chat from which the inline query was sent. Can be either “sender” for a private chat with the inline query sender, “private”, “group”, “supergroup”, or “channel”. The chat type should be always known for requests sent from official clients and most third-party clients, unless the request was sent from a secret chat |
| location   | [Location](broken-reference) | _Optional_. Sender location, only for bots that request user location                                                                                                                                                                                                                                                                                |

**answerInlineQuery**

Use this method to send answers to an inline query. On success, _True_ is returned.\
No more than **50** results per query are allowed.

| Parameter         | Type                                           | Required | Description                                                                                                                                                                                                                        |
| ----------------- | ---------------------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| inline\_query\_id | String                                         | Yes      | Unique identifier for the answered query                                                                                                                                                                                           |
| results           | Array of [InlineQueryResult](broken-reference) | Yes      | A JSON-serialized array of results for the inline query                                                                                                                                                                            |
| cache\_time       | Integer                                        | Optional | The maximum amount of time in seconds that the result of the inline query may be cached on the server. Defaults to 300.                                                                                                            |
| is\_personal      | Boolean                                        | Optional | Pass _True_ if results may be cached on the server side only for the user that sent the query. By default, results may be returned to any user who sends the same query.                                                           |
| next\_offset      | String                                         | Optional | Pass the offset that a client should send in the next query with the same text to receive more results. Pass an empty string if there are no more results or if you don't support pagination. Offset length can't exceed 64 bytes. |
| button            | [InlineQueryResultsButton](broken-reference)   | Optional | A JSON-serialized object describing a button to be shown above inline query results                                                                                                                                                |

**InlineQueryResultsButton**

This object represents a button to be shown above inline query results. You **must** use exactly one of the optional fields.

| Field            | Type                           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ---------------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| text             | String                         | Label text on the button                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| web\_app         | [WebAppInfo](broken-reference) | _Optional_. Description of the Web App that will be launched when the user presses the button. The Web App will be able to switch back to the inline mode using the method [switchInlineQuery](https://about/bots/webapps#initializing-mini-apps) inside the Web App.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| start\_parameter | String                         | <p><em>Optional</em>. <a href="https://about/bots/features#deep-linking">Deep-linking</a> parameter for the /start message sent to the bot when a user presses the button. 1-64 characters, only <code>A-Z</code>, <code>a-z</code>, <code>0-9</code>, <code>_</code> and <code>-</code> are allowed.</p><p><em>Example:</em> An inline bot that sends YouTube videos can ask the user to connect the bot to their YouTube account to adapt search results accordingly. To do this, it displays a 'Connect your YouTube account' button above the results, or even before showing any. The user presses the button, switches to a private chat with the bot and, in doing so, passes a start parameter that instructs the bot to return an OAuth link. Once done, the bot can offer a <a href="broken-reference"><em>switch_inline</em></a> button so that the user can easily return to the chat where they wanted to use the bot's inline capabilities.</p> |

**InlineQueryResult**

This object represents one result of an inline query. Telegram clients currently support results of the following 20 types:

* [InlineQueryResultCachedAudio](broken-reference)
* [InlineQueryResultCachedDocument](broken-reference)
* [InlineQueryResultCachedGif](broken-reference)
* [InlineQueryResultCachedMpeg4Gif](broken-reference)
* [InlineQueryResultCachedPhoto](broken-reference)
* [InlineQueryResultCachedSticker](broken-reference)
* [InlineQueryResultCachedVideo](broken-reference)
* [InlineQueryResultCachedVoice](broken-reference)
* [InlineQueryResultArticle](broken-reference)
* [InlineQueryResultAudio](broken-reference)
* [InlineQueryResultContact](broken-reference)
* [InlineQueryResultGame](broken-reference)
* [InlineQueryResultDocument](broken-reference)
* [InlineQueryResultGif](broken-reference)
* [InlineQueryResultLocation](broken-reference)
* [InlineQueryResultMpeg4Gif](broken-reference)
* [InlineQueryResultPhoto](broken-reference)
* [InlineQueryResultVenue](broken-reference)
* [InlineQueryResultVideo](broken-reference)
* [InlineQueryResultVoice](broken-reference)

**Note:** All URLs passed in inline query results will be available to end users and therefore must be assumed to be **public**.

**InlineQueryResultArticle**

Represents a link to an article or web page.

| Field                   | Type                                     | Description                                                                                         |
| ----------------------- | ---------------------------------------- | --------------------------------------------------------------------------------------------------- |
| type                    | String                                   | Type of the result, must be _article_                                                               |
| id                      | String                                   | Unique identifier for this result, 1-64 Bytes                                                       |
| title                   | String                                   | Title of the result                                                                                 |
| input\_message\_content | [InputMessageContent](broken-reference)  | Content of the message to be sent                                                                   |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference) | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message |
| url                     | String                                   | _Optional_. URL of the result                                                                       |
| hide\_url               | Boolean                                  | _Optional_. Pass _True_ if you don't want the URL to be shown in the message                        |
| description             | String                                   | _Optional_. Short description of the result                                                         |
| thumbnail\_url          | String                                   | _Optional_. Url of the thumbnail for the result                                                     |
| thumbnail\_width        | Integer                                  | _Optional_. Thumbnail width                                                                         |
| thumbnail\_height       | Integer                                  | _Optional_. Thumbnail height                                                                        |

**InlineQueryResultPhoto**

Represents a link to a photo. By default, this photo will be sent by the user with optional caption. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the photo.

| Field                   | Type                                       | Description                                                                                                              |
| ----------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| type                    | String                                     | Type of the result, must be _photo_                                                                                      |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                            |
| photo\_url              | String                                     | A valid URL of the photo. Photo must be in **JPEG** format. Photo size must not exceed 5MB                               |
| thumbnail\_url          | String                                     | URL of the thumbnail for the photo                                                                                       |
| photo\_width            | Integer                                    | _Optional_. Width of the photo                                                                                           |
| photo\_height           | Integer                                    | _Optional_. Height of the photo                                                                                          |
| title                   | String                                     | _Optional_. Title for the result                                                                                         |
| description             | String                                     | _Optional_. Short description of the result                                                                              |
| caption                 | String                                     | _Optional_. Caption of the photo to be sent, 0-1024 characters after entities parsing                                    |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the photo caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_         |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                      |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the photo                                                       |

**InlineQueryResultGif**

Represents a link to an animated GIF file. By default, this animated GIF file will be sent by the user with optional caption. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the animation.

| Field                   | Type                                       | Description                                                                                                                |
| ----------------------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| type                    | String                                     | Type of the result, must be _gif_                                                                                          |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                              |
| gif\_url                | String                                     | A valid URL for the GIF file. File size must not exceed 1MB                                                                |
| gif\_width              | Integer                                    | _Optional_. Width of the GIF                                                                                               |
| gif\_height             | Integer                                    | _Optional_. Height of the GIF                                                                                              |
| gif\_duration           | Integer                                    | _Optional_. Duration of the GIF in seconds                                                                                 |
| thumbnail\_url          | String                                     | URL of the static (JPEG or GIF) or animated (MPEG4) thumbnail for the result                                               |
| thumbnail\_mime\_type   | String                                     | _Optional_. MIME type of the thumbnail, must be one of “image/jpeg”, “image/gif”, or “video/mp4”. Defaults to “image/jpeg” |
| title                   | String                                     | _Optional_. Title for the result                                                                                           |
| caption                 | String                                     | _Optional_. Caption of the GIF file to be sent, 0-1024 characters after entities parsing                                   |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the caption. See [formatting options](broken-reference) for more details.         |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_           |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                        |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the GIF animation                                                 |

**InlineQueryResultMpeg4Gif**

Represents a link to a video animation (H.264/MPEG-4 AVC video without sound). By default, this animated MPEG-4 file will be sent by the user with optional caption. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the animation.

| Field                   | Type                                       | Description                                                                                                                |
| ----------------------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| type                    | String                                     | Type of the result, must be _mpeg4\_gif_                                                                                   |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                              |
| mpeg4\_url              | String                                     | A valid URL for the MPEG4 file. File size must not exceed 1MB                                                              |
| mpeg4\_width            | Integer                                    | _Optional_. Video width                                                                                                    |
| mpeg4\_height           | Integer                                    | _Optional_. Video height                                                                                                   |
| mpeg4\_duration         | Integer                                    | _Optional_. Video duration in seconds                                                                                      |
| thumbnail\_url          | String                                     | URL of the static (JPEG or GIF) or animated (MPEG4) thumbnail for the result                                               |
| thumbnail\_mime\_type   | String                                     | _Optional_. MIME type of the thumbnail, must be one of “image/jpeg”, “image/gif”, or “video/mp4”. Defaults to “image/jpeg” |
| title                   | String                                     | _Optional_. Title for the result                                                                                           |
| caption                 | String                                     | _Optional_. Caption of the MPEG-4 file to be sent, 0-1024 characters after entities parsing                                |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the caption. See [formatting options](broken-reference) for more details.         |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_           |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                        |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the video animation                                               |

**InlineQueryResultVideo**

Represents a link to a page containing an embedded video player or a video file. By default, this video file will be sent by the user with an optional caption. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the video.

> If an InlineQueryResultVideo message contains an embedded video (e.g., YouTube), you **must** replace its content using _input\_message\_content_.

| Field                   | Type                                       | Description                                                                                                                                                                                |
| ----------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| type                    | String                                     | Type of the result, must be _video_                                                                                                                                                        |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                                                                                              |
| video\_url              | String                                     | A valid URL for the embedded video player or video file                                                                                                                                    |
| mime\_type              | String                                     | MIME type of the content of the video URL, “text/html” or “video/mp4”                                                                                                                      |
| thumbnail\_url          | String                                     | URL of the thumbnail (JPEG only) for the video                                                                                                                                             |
| title                   | String                                     | Title for the result                                                                                                                                                                       |
| caption                 | String                                     | _Optional_. Caption of the video to be sent, 0-1024 characters after entities parsing                                                                                                      |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the video caption. See [formatting options](broken-reference) for more details.                                                                   |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_                                                                           |
| video\_width            | Integer                                    | _Optional_. Video width                                                                                                                                                                    |
| video\_height           | Integer                                    | _Optional_. Video height                                                                                                                                                                   |
| video\_duration         | Integer                                    | _Optional_. Video duration in seconds                                                                                                                                                      |
| description             | String                                     | _Optional_. Short description of the result                                                                                                                                                |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                                                                                        |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the video. This field is **required** if InlineQueryResultVideo is used to send an HTML-page as a result (e.g., a YouTube video). |

**InlineQueryResultAudio**

Represents a link to an MP3 audio file. By default, this audio file will be sent by the user. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the audio.

| Field                   | Type                                       | Description                                                                                                              |
| ----------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| type                    | String                                     | Type of the result, must be _audio_                                                                                      |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                            |
| audio\_url              | String                                     | A valid URL for the audio file                                                                                           |
| title                   | String                                     | Title                                                                                                                    |
| caption                 | String                                     | _Optional_. Caption, 0-1024 characters after entities parsing                                                            |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the audio caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_         |
| performer               | String                                     | _Optional_. Performer                                                                                                    |
| audio\_duration         | Integer                                    | _Optional_. Audio duration in seconds                                                                                    |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                      |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the audio                                                       |

**InlineQueryResultVoice**

Represents a link to a voice recording in an .OGG container encoded with OPUS. By default, this voice recording will be sent by the user. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the the voice message.

| Field                   | Type                                       | Description                                                                                                                      |
| ----------------------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| type                    | String                                     | Type of the result, must be _voice_                                                                                              |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                                    |
| voice\_url              | String                                     | A valid URL for the voice recording                                                                                              |
| title                   | String                                     | Recording title                                                                                                                  |
| caption                 | String                                     | _Optional_. Caption, 0-1024 characters after entities parsing                                                                    |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the voice message caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_                 |
| voice\_duration         | Integer                                    | _Optional_. Recording duration in seconds                                                                                        |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                              |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the voice recording                                                     |

**InlineQueryResultDocument**

Represents a link to a file. By default, this file will be sent by the user with an optional caption. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the file. Currently, only **.PDF** and **.ZIP** files can be sent using this method.

| Field                   | Type                                       | Description                                                                                                                 |
| ----------------------- | ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| type                    | String                                     | Type of the result, must be _document_                                                                                      |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                               |
| title                   | String                                     | Title for the result                                                                                                        |
| caption                 | String                                     | _Optional_. Caption of the document to be sent, 0-1024 characters after entities parsing                                    |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the document caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_            |
| document\_url           | String                                     | A valid URL for the file                                                                                                    |
| mime\_type              | String                                     | MIME type of the content of the file, either “application/pdf” or “application/zip”                                         |
| description             | String                                     | _Optional_. Short description of the result                                                                                 |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. Inline keyboard attached to the message                                                                         |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the file                                                           |
| thumbnail\_url          | String                                     | _Optional_. URL of the thumbnail (JPEG only) for the file                                                                   |
| thumbnail\_width        | Integer                                    | _Optional_. Thumbnail width                                                                                                 |
| thumbnail\_height       | Integer                                    | _Optional_. Thumbnail height                                                                                                |

**InlineQueryResultLocation**

Represents a location on a map. By default, the location will be sent by the user. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the location.

| Field                    | Type                                     | Description                                                                                                                                                          |
| ------------------------ | ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type                     | String                                   | Type of the result, must be _location_                                                                                                                               |
| id                       | String                                   | Unique identifier for this result, 1-64 Bytes                                                                                                                        |
| latitude                 | Float                                    | Location latitude in degrees                                                                                                                                         |
| longitude                | Float                                    | Location longitude in degrees                                                                                                                                        |
| title                    | String                                   | Location title                                                                                                                                                       |
| horizontal\_accuracy     | Float                                    | _Optional_. The radius of uncertainty for the location, measured in meters; 0-1500                                                                                   |
| live\_period             | Integer                                  | _Optional_. Period in seconds for which the location can be updated, should be between 60 and 86400.                                                                 |
| heading                  | Integer                                  | _Optional_. For live locations, a direction in which the user is moving, in degrees. Must be between 1 and 360 if specified.                                         |
| proximity\_alert\_radius | Integer                                  | _Optional_. For live locations, a maximum distance for proximity alerts about approaching another chat member, in meters. Must be between 1 and 100000 if specified. |
| reply\_markup            | [InlineKeyboardMarkup](broken-reference) | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                                                                  |
| input\_message\_content  | [InputMessageContent](broken-reference)  | _Optional_. Content of the message to be sent instead of the location                                                                                                |
| thumbnail\_url           | String                                   | _Optional_. Url of the thumbnail for the result                                                                                                                      |
| thumbnail\_width         | Integer                                  | _Optional_. Thumbnail width                                                                                                                                          |
| thumbnail\_height        | Integer                                  | _Optional_. Thumbnail height                                                                                                                                         |

**InlineQueryResultVenue**

Represents a venue. By default, the venue will be sent by the user. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the venue.

| Field                   | Type                                     | Description                                                                                                                                          |
| ----------------------- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| type                    | String                                   | Type of the result, must be _venue_                                                                                                                  |
| id                      | String                                   | Unique identifier for this result, 1-64 Bytes                                                                                                        |
| latitude                | Float                                    | Latitude of the venue location in degrees                                                                                                            |
| longitude               | Float                                    | Longitude of the venue location in degrees                                                                                                           |
| title                   | String                                   | Title of the venue                                                                                                                                   |
| address                 | String                                   | Address of the venue                                                                                                                                 |
| foursquare\_id          | String                                   | _Optional_. Foursquare identifier of the venue if known                                                                                              |
| foursquare\_type        | String                                   | _Optional_. Foursquare type of the venue, if known. (For example, “arts\_entertainment/default”, “arts\_entertainment/aquarium” or “food/icecream”.) |
| google\_place\_id       | String                                   | _Optional_. Google Places identifier of the venue                                                                                                    |
| google\_place\_type     | String                                   | _Optional_. Google Places type of the venue. (See [supported types](https://developers.google.com/places/web-service/supported\_types).)             |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference) | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                                                  |
| input\_message\_content | [InputMessageContent](broken-reference)  | _Optional_. Content of the message to be sent instead of the venue                                                                                   |
| thumbnail\_url          | String                                   | _Optional_. Url of the thumbnail for the result                                                                                                      |
| thumbnail\_width        | Integer                                  | _Optional_. Thumbnail width                                                                                                                          |
| thumbnail\_height       | Integer                                  | _Optional_. Thumbnail height                                                                                                                         |

**InlineQueryResultContact**

Represents a contact with a phone number. By default, this contact will be sent by the user. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the contact.

| Field                   | Type                                     | Description                                                                                                               |
| ----------------------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| type                    | String                                   | Type of the result, must be _contact_                                                                                     |
| id                      | String                                   | Unique identifier for this result, 1-64 Bytes                                                                             |
| phone\_number           | String                                   | Contact's phone number                                                                                                    |
| first\_name             | String                                   | Contact's first name                                                                                                      |
| last\_name              | String                                   | _Optional_. Contact's last name                                                                                           |
| vcard                   | String                                   | _Optional_. Additional data about the contact in the form of a [vCard](https://en.wikipedia.org/wiki/VCard), 0-2048 bytes |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference) | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                       |
| input\_message\_content | [InputMessageContent](broken-reference)  | _Optional_. Content of the message to be sent instead of the contact                                                      |
| thumbnail\_url          | String                                   | _Optional_. Url of the thumbnail for the result                                                                           |
| thumbnail\_width        | Integer                                  | _Optional_. Thumbnail width                                                                                               |
| thumbnail\_height       | Integer                                  | _Optional_. Thumbnail height                                                                                              |

**InlineQueryResultGame**

Represents a [Game](broken-reference).

| Field             | Type                                     | Description                                                                                         |
| ----------------- | ---------------------------------------- | --------------------------------------------------------------------------------------------------- |
| type              | String                                   | Type of the result, must be _game_                                                                  |
| id                | String                                   | Unique identifier for this result, 1-64 bytes                                                       |
| game\_short\_name | String                                   | Short name of the game                                                                              |
| reply\_markup     | [InlineKeyboardMarkup](broken-reference) | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message |

**InlineQueryResultCachedPhoto**

Represents a link to a photo stored on the Telegram servers. By default, this photo will be sent by the user with an optional caption. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the photo.

| Field                   | Type                                       | Description                                                                                                              |
| ----------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| type                    | String                                     | Type of the result, must be _photo_                                                                                      |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                            |
| photo\_file\_id         | String                                     | A valid file identifier of the photo                                                                                     |
| title                   | String                                     | _Optional_. Title for the result                                                                                         |
| description             | String                                     | _Optional_. Short description of the result                                                                              |
| caption                 | String                                     | _Optional_. Caption of the photo to be sent, 0-1024 characters after entities parsing                                    |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the photo caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_         |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                      |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the photo                                                       |

**InlineQueryResultCachedGif**

Represents a link to an animated GIF file stored on the Telegram servers. By default, this animated GIF file will be sent by the user with an optional caption. Alternatively, you can use _input\_message\_content_ to send a message with specified content instead of the animation.

| Field                   | Type                                       | Description                                                                                                        |
| ----------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| type                    | String                                     | Type of the result, must be _gif_                                                                                  |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                      |
| gif\_file\_id           | String                                     | A valid file identifier for the GIF file                                                                           |
| title                   | String                                     | _Optional_. Title for the result                                                                                   |
| caption                 | String                                     | _Optional_. Caption of the GIF file to be sent, 0-1024 characters after entities parsing                           |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_   |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the GIF animation                                         |

**InlineQueryResultCachedMpeg4Gif**

Represents a link to a video animation (H.264/MPEG-4 AVC video without sound) stored on the Telegram servers. By default, this animated MPEG-4 file will be sent by the user with an optional caption. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the animation.

| Field                   | Type                                       | Description                                                                                                        |
| ----------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| type                    | String                                     | Type of the result, must be _mpeg4\_gif_                                                                           |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                      |
| mpeg4\_file\_id         | String                                     | A valid file identifier for the MPEG4 file                                                                         |
| title                   | String                                     | _Optional_. Title for the result                                                                                   |
| caption                 | String                                     | _Optional_. Caption of the MPEG-4 file to be sent, 0-1024 characters after entities parsing                        |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_   |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the video animation                                       |

**InlineQueryResultCachedSticker**

Represents a link to a sticker stored on the Telegram servers. By default, this sticker will be sent by the user. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the sticker.

| Field                   | Type                                     | Description                                                                                         |
| ----------------------- | ---------------------------------------- | --------------------------------------------------------------------------------------------------- |
| type                    | String                                   | Type of the result, must be _sticker_                                                               |
| id                      | String                                   | Unique identifier for this result, 1-64 bytes                                                       |
| sticker\_file\_id       | String                                   | A valid file identifier of the sticker                                                              |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference) | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message |
| input\_message\_content | [InputMessageContent](broken-reference)  | _Optional_. Content of the message to be sent instead of the sticker                                |

**InlineQueryResultCachedDocument**

Represents a link to a file stored on the Telegram servers. By default, this file will be sent by the user with an optional caption. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the file.

| Field                   | Type                                       | Description                                                                                                                 |
| ----------------------- | ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| type                    | String                                     | Type of the result, must be _document_                                                                                      |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                               |
| title                   | String                                     | Title for the result                                                                                                        |
| document\_file\_id      | String                                     | A valid file identifier for the file                                                                                        |
| description             | String                                     | _Optional_. Short description of the result                                                                                 |
| caption                 | String                                     | _Optional_. Caption of the document to be sent, 0-1024 characters after entities parsing                                    |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the document caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_            |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                         |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the file                                                           |

**InlineQueryResultCachedVideo**

Represents a link to a video file stored on the Telegram servers. By default, this video file will be sent by the user with an optional caption. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the video.

| Field                   | Type                                       | Description                                                                                                              |
| ----------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| type                    | String                                     | Type of the result, must be _video_                                                                                      |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                            |
| video\_file\_id         | String                                     | A valid file identifier for the video file                                                                               |
| title                   | String                                     | Title for the result                                                                                                     |
| description             | String                                     | _Optional_. Short description of the result                                                                              |
| caption                 | String                                     | _Optional_. Caption of the video to be sent, 0-1024 characters after entities parsing                                    |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the video caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_         |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                      |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the video                                                       |

**InlineQueryResultCachedVoice**

Represents a link to a voice message stored on the Telegram servers. By default, this voice message will be sent by the user. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the voice message.

| Field                   | Type                                       | Description                                                                                                                      |
| ----------------------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| type                    | String                                     | Type of the result, must be _voice_                                                                                              |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                                    |
| voice\_file\_id         | String                                     | A valid file identifier for the voice message                                                                                    |
| title                   | String                                     | Voice message title                                                                                                              |
| caption                 | String                                     | _Optional_. Caption, 0-1024 characters after entities parsing                                                                    |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the voice message caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_                 |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                              |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the voice message                                                       |

**InlineQueryResultCachedAudio**

Represents a link to an MP3 audio file stored on the Telegram servers. By default, this audio file will be sent by the user. Alternatively, you can use _input\_message\_content_ to send a message with the specified content instead of the audio.

| Field                   | Type                                       | Description                                                                                                              |
| ----------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| type                    | String                                     | Type of the result, must be _audio_                                                                                      |
| id                      | String                                     | Unique identifier for this result, 1-64 bytes                                                                            |
| audio\_file\_id         | String                                     | A valid file identifier for the audio file                                                                               |
| caption                 | String                                     | _Optional_. Caption, 0-1024 characters after entities parsing                                                            |
| parse\_mode             | String                                     | _Optional_. Mode for parsing entities in the audio caption. See [formatting options](broken-reference) for more details. |
| caption\_entities       | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in the caption, which can be specified instead of _parse\_mode_         |
| reply\_markup           | [InlineKeyboardMarkup](broken-reference)   | _Optional_. [Inline keyboard](https://about/bots/features#inline-keyboards) attached to the message                      |
| input\_message\_content | [InputMessageContent](broken-reference)    | _Optional_. Content of the message to be sent instead of the audio                                                       |

**InputMessageContent**

This object represents the content of a message to be sent as a result of an inline query. Telegram clients currently support the following 5 types:

* [InputTextMessageContent](broken-reference)
* [InputLocationMessageContent](broken-reference)
* [InputVenueMessageContent](broken-reference)
* [InputContactMessageContent](broken-reference)
* [InputInvoiceMessageContent](broken-reference)

**InputTextMessageContent**

Represents the [content](broken-reference) of a text message to be sent as the result of an inline query.

| Field                  | Type                                       | Description                                                                                                             |
| ---------------------- | ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| message\_text          | String                                     | Text of the message to be sent, 1-4096 characters                                                                       |
| parse\_mode            | String                                     | _Optional_. Mode for parsing entities in the message text. See [formatting options](broken-reference) for more details. |
| entities               | Array of [MessageEntity](broken-reference) | _Optional_. List of special entities that appear in message text, which can be specified instead of _parse\_mode_       |
| link\_preview\_options | [LinkPreviewOptions](broken-reference)     | _Optional_. Link preview generation options for the message                                                             |

**InputLocationMessageContent**

Represents the [content](broken-reference) of a location message to be sent as the result of an inline query.

| Field                    | Type    | Description                                                                                                                                                          |
| ------------------------ | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| latitude                 | Float   | Latitude of the location in degrees                                                                                                                                  |
| longitude                | Float   | Longitude of the location in degrees                                                                                                                                 |
| horizontal\_accuracy     | Float   | _Optional_. The radius of uncertainty for the location, measured in meters; 0-1500                                                                                   |
| live\_period             | Integer | _Optional_. Period in seconds for which the location can be updated, should be between 60 and 86400.                                                                 |
| heading                  | Integer | _Optional_. For live locations, a direction in which the user is moving, in degrees. Must be between 1 and 360 if specified.                                         |
| proximity\_alert\_radius | Integer | _Optional_. For live locations, a maximum distance for proximity alerts about approaching another chat member, in meters. Must be between 1 and 100000 if specified. |

**InputVenueMessageContent**

Represents the [content](broken-reference) of a venue message to be sent as the result of an inline query.

| Field               | Type   | Description                                                                                                                                          |
| ------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| latitude            | Float  | Latitude of the venue in degrees                                                                                                                     |
| longitude           | Float  | Longitude of the venue in degrees                                                                                                                    |
| title               | String | Name of the venue                                                                                                                                    |
| address             | String | Address of the venue                                                                                                                                 |
| foursquare\_id      | String | _Optional_. Foursquare identifier of the venue, if known                                                                                             |
| foursquare\_type    | String | _Optional_. Foursquare type of the venue, if known. (For example, “arts\_entertainment/default”, “arts\_entertainment/aquarium” or “food/icecream”.) |
| google\_place\_id   | String | _Optional_. Google Places identifier of the venue                                                                                                    |
| google\_place\_type | String | _Optional_. Google Places type of the venue. (See [supported types](https://developers.google.com/places/web-service/supported\_types).)             |

**InputContactMessageContent**

Represents the [content](broken-reference) of a contact message to be sent as the result of an inline query.

| Field         | Type   | Description                                                                                                               |
| ------------- | ------ | ------------------------------------------------------------------------------------------------------------------------- |
| phone\_number | String | Contact's phone number                                                                                                    |
| first\_name   | String | Contact's first name                                                                                                      |
| last\_name    | String | _Optional_. Contact's last name                                                                                           |
| vcard         | String | _Optional_. Additional data about the contact in the form of a [vCard](https://en.wikipedia.org/wiki/VCard), 0-2048 bytes |

**InputInvoiceMessageContent**

Represents the [content](broken-reference) of an invoice message to be sent as the result of an inline query.

| Field                             | Type                                      | Description                                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------- | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| title                             | String                                    | Product name, 1-32 characters                                                                                                                                                                                                                                                                                                                                            |
| description                       | String                                    | Product description, 1-255 characters                                                                                                                                                                                                                                                                                                                                    |
| payload                           | String                                    | Bot-defined invoice payload, 1-128 bytes. This will not be displayed to the user, use for your internal processes.                                                                                                                                                                                                                                                       |
| provider\_token                   | String                                    | Payment provider token, obtained via [@BotFather](https://t.me/botfather)                                                                                                                                                                                                                                                                                                |
| currency                          | String                                    | Three-letter ISO 4217 currency code, see [more on currencies](https://about/bots/payments#supported-currencies)                                                                                                                                                                                                                                                          |
| prices                            | Array of [LabeledPrice](broken-reference) | Price breakdown, a JSON-serialized list of components (e.g. product price, tax, discount, delivery cost, delivery tax, bonus, etc.)                                                                                                                                                                                                                                      |
| max\_tip\_amount                  | Integer                                   | _Optional_. The maximum accepted amount for tips in the _smallest units_ of the currency (integer, **not** float/double). For example, for a maximum tip of `US$ 1.45` pass `max_tip_amount = 145`. See the _exp_ parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). Defaults to 0 |
| suggested\_tip\_amounts           | Array of Integer                          | _Optional_. A JSON-serialized array of suggested amounts of tip in the _smallest units_ of the currency (integer, **not** float/double). At most 4 suggested tip amounts can be specified. The suggested tip amounts must be positive, passed in a strictly increased order and must not exceed _max\_tip\_amount_.                                                      |
| provider\_data                    | String                                    | _Optional_. A JSON-serialized object for data about the invoice, which will be shared with the payment provider. A detailed description of the required fields should be provided by the payment provider.                                                                                                                                                               |
| photo\_url                        | String                                    | _Optional_. URL of the product photo for the invoice. Can be a photo of the goods or a marketing image for a service.                                                                                                                                                                                                                                                    |
| photo\_size                       | Integer                                   | _Optional_. Photo size in bytes                                                                                                                                                                                                                                                                                                                                          |
| photo\_width                      | Integer                                   | _Optional_. Photo width                                                                                                                                                                                                                                                                                                                                                  |
| photo\_height                     | Integer                                   | _Optional_. Photo height                                                                                                                                                                                                                                                                                                                                                 |
| need\_name                        | Boolean                                   | _Optional_. Pass _True_ if you require the user's full name to complete the order                                                                                                                                                                                                                                                                                        |
| need\_phone\_number               | Boolean                                   | _Optional_. Pass _True_ if you require the user's phone number to complete the order                                                                                                                                                                                                                                                                                     |
| need\_email                       | Boolean                                   | _Optional_. Pass _True_ if you require the user's email address to complete the order                                                                                                                                                                                                                                                                                    |
| need\_shipping\_address           | Boolean                                   | _Optional_. Pass _True_ if you require the user's shipping address to complete the order                                                                                                                                                                                                                                                                                 |
| send\_phone\_number\_to\_provider | Boolean                                   | _Optional_. Pass _True_ if the user's phone number should be sent to provider                                                                                                                                                                                                                                                                                            |
| send\_email\_to\_provider         | Boolean                                   | _Optional_. Pass _True_ if the user's email address should be sent to provider                                                                                                                                                                                                                                                                                           |
| is\_flexible                      | Boolean                                   | _Optional_. Pass _True_ if the final price depends on the shipping method                                                                                                                                                                                                                                                                                                |

**ChosenInlineResult**

Represents a [result](broken-reference) of an inline query that was chosen by the user and sent to their chat partner.

| Field               | Type                         | Description                                                                                                                                                                                                                                                          |
| ------------------- | ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| result\_id          | String                       | The unique identifier for the result that was chosen                                                                                                                                                                                                                 |
| from                | [User](broken-reference)     | The user that chose the result                                                                                                                                                                                                                                       |
| location            | [Location](broken-reference) | _Optional_. Sender location, only for bots that require user location                                                                                                                                                                                                |
| inline\_message\_id | String                       | _Optional_. Identifier of the sent inline message. Available only if there is an [inline keyboard](broken-reference) attached to the message. Will be also received in [callback queries](broken-reference) and can be used to [edit](broken-reference) the message. |
| query               | String                       | The query that was used to obtain the result                                                                                                                                                                                                                         |

**Note:** It is necessary to enable [inline feedback](https://about/bots/inline#collecting-feedback) via [@BotFather](https://t.me/botfather) in order to receive these objects in updates.

**answerWebAppQuery**

Use this method to set the result of an interaction with a Web App and send a corresponding message on behalf of the user to the chat from which the query originated. On success, a [SentWebAppMessage](broken-reference) object is returned.

| Parameter           | Type                                  | Required | Description                                                |
| ------------------- | ------------------------------------- | -------- | ---------------------------------------------------------- |
| web\_app\_query\_id | String                                | Yes      | Unique identifier for the query to be answered             |
| result              | [InlineQueryResult](broken-reference) | Yes      | A JSON-serialized object describing the message to be sent |

**SentWebAppMessage**

Describes an inline message sent by a Web App on behalf of a user.

| Field               | Type   | Description                                                                                                                                   |
| ------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| inline\_message\_id | String | _Optional_. Identifier of the sent inline message. Available only if there is an [inline keyboard](broken-reference) attached to the message. |

#### Payments

Your bot can accept payments from Telegram users. Please see the introduction to payments for more details on the process and how to set up payments for your bot.

**sendInvoice**

Use this method to send invoices. On success, the sent [Message](broken-reference) is returned.

| Parameter                         | Type                                      | Required | Description                                                                                                                                                                                                                                                                                                                                                                                  |
| --------------------------------- | ----------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| chat\_id                          | Integer or String                         | Yes      | Unique identifier for the target chat or username of the target channel (in the format `@channelusername`)                                                                                                                                                                                                                                                                                   |
| message\_thread\_id               | Integer                                   | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                                                                                                                                                                                                             |
| title                             | String                                    | Yes      | Product name, 1-32 characters                                                                                                                                                                                                                                                                                                                                                                |
| description                       | String                                    | Yes      | Product description, 1-255 characters                                                                                                                                                                                                                                                                                                                                                        |
| payload                           | String                                    | Yes      | Bot-defined invoice payload, 1-128 bytes. This will not be displayed to the user, use for your internal processes.                                                                                                                                                                                                                                                                           |
| provider\_token                   | String                                    | Yes      | Payment provider token, obtained via [@BotFather](https://t.me/botfather)                                                                                                                                                                                                                                                                                                                    |
| currency                          | String                                    | Yes      | Three-letter ISO 4217 currency code, see [more on currencies](https://about/bots/payments#supported-currencies)                                                                                                                                                                                                                                                                              |
| prices                            | Array of [LabeledPrice](broken-reference) | Yes      | Price breakdown, a JSON-serialized list of components (e.g. product price, tax, discount, delivery cost, delivery tax, bonus, etc.)                                                                                                                                                                                                                                                          |
| max\_tip\_amount                  | Integer                                   | Optional | The maximum accepted amount for tips in the _smallest units_ of the currency (integer, **not** float/double). For example, for a maximum tip of `US$ 1.45` pass `max_tip_amount = 145`. See the _exp_ parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). Defaults to 0                                 |
| suggested\_tip\_amounts           | Array of Integer                          | Optional | A JSON-serialized array of suggested amounts of tips in the _smallest units_ of the currency (integer, **not** float/double). At most 4 suggested tip amounts can be specified. The suggested tip amounts must be positive, passed in a strictly increased order and must not exceed _max\_tip\_amount_.                                                                                     |
| start\_parameter                  | String                                    | Optional | Unique deep-linking parameter. If left empty, **forwarded copies** of the sent message will have a _Pay_ button, allowing multiple users to pay directly from the forwarded message, using the same invoice. If non-empty, forwarded copies of the sent message will have a _URL_ button with a deep link to the bot (instead of a _Pay_ button), with the value used as the start parameter |
| provider\_data                    | String                                    | Optional | JSON-serialized data about the invoice, which will be shared with the payment provider. A detailed description of required fields should be provided by the payment provider.                                                                                                                                                                                                                |
| photo\_url                        | String                                    | Optional | URL of the product photo for the invoice. Can be a photo of the goods or a marketing image for a service. People like it better when they see what they are paying for.                                                                                                                                                                                                                      |
| photo\_size                       | Integer                                   | Optional | Photo size in bytes                                                                                                                                                                                                                                                                                                                                                                          |
| photo\_width                      | Integer                                   | Optional | Photo width                                                                                                                                                                                                                                                                                                                                                                                  |
| photo\_height                     | Integer                                   | Optional | Photo height                                                                                                                                                                                                                                                                                                                                                                                 |
| need\_name                        | Boolean                                   | Optional | Pass _True_ if you require the user's full name to complete the order                                                                                                                                                                                                                                                                                                                        |
| need\_phone\_number               | Boolean                                   | Optional | Pass _True_ if you require the user's phone number to complete the order                                                                                                                                                                                                                                                                                                                     |
| need\_email                       | Boolean                                   | Optional | Pass _True_ if you require the user's email address to complete the order                                                                                                                                                                                                                                                                                                                    |
| need\_shipping\_address           | Boolean                                   | Optional | Pass _True_ if you require the user's shipping address to complete the order                                                                                                                                                                                                                                                                                                                 |
| send\_phone\_number\_to\_provider | Boolean                                   | Optional | Pass _True_ if the user's phone number should be sent to provider                                                                                                                                                                                                                                                                                                                            |
| send\_email\_to\_provider         | Boolean                                   | Optional | Pass _True_ if the user's email address should be sent to provider                                                                                                                                                                                                                                                                                                                           |
| is\_flexible                      | Boolean                                   | Optional | Pass _True_ if the final price depends on the shipping method                                                                                                                                                                                                                                                                                                                                |
| disable\_notification             | Boolean                                   | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                                                                                                                                                                                                       |
| protect\_content                  | Boolean                                   | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                                                                                                                                                                                                         |
| reply\_parameters                 | [ReplyParameters](broken-reference)       | Optional | Description of the message to reply to                                                                                                                                                                                                                                                                                                                                                       |
| reply\_markup                     | [InlineKeyboardMarkup](broken-reference)  | Optional | A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards). If empty, one 'Pay `total price`' button will be shown. If not empty, the first button must be a Pay button.                                                                                                                                                                                |

**createInvoiceLink**

Use this method to create a link for an invoice. Returns the created invoice link as _String_ on success.

| Parameter                         | Type                                      | Required | Description                                                                                                                                                                                                                                                                                                                                                  |
| --------------------------------- | ----------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| title                             | String                                    | Yes      | Product name, 1-32 characters                                                                                                                                                                                                                                                                                                                                |
| description                       | String                                    | Yes      | Product description, 1-255 characters                                                                                                                                                                                                                                                                                                                        |
| payload                           | String                                    | Yes      | Bot-defined invoice payload, 1-128 bytes. This will not be displayed to the user, use for your internal processes.                                                                                                                                                                                                                                           |
| provider\_token                   | String                                    | Yes      | Payment provider token, obtained via [BotFather](https://t.me/botfather)                                                                                                                                                                                                                                                                                     |
| currency                          | String                                    | Yes      | Three-letter ISO 4217 currency code, see [more on currencies](https://about/bots/payments#supported-currencies)                                                                                                                                                                                                                                              |
| prices                            | Array of [LabeledPrice](broken-reference) | Yes      | Price breakdown, a JSON-serialized list of components (e.g. product price, tax, discount, delivery cost, delivery tax, bonus, etc.)                                                                                                                                                                                                                          |
| max\_tip\_amount                  | Integer                                   | Optional | The maximum accepted amount for tips in the _smallest units_ of the currency (integer, **not** float/double). For example, for a maximum tip of `US$ 1.45` pass `max_tip_amount = 145`. See the _exp_ parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). Defaults to 0 |
| suggested\_tip\_amounts           | Array of Integer                          | Optional | A JSON-serialized array of suggested amounts of tips in the _smallest units_ of the currency (integer, **not** float/double). At most 4 suggested tip amounts can be specified. The suggested tip amounts must be positive, passed in a strictly increased order and must not exceed _max\_tip\_amount_.                                                     |
| provider\_data                    | String                                    | Optional | JSON-serialized data about the invoice, which will be shared with the payment provider. A detailed description of required fields should be provided by the payment provider.                                                                                                                                                                                |
| photo\_url                        | String                                    | Optional | URL of the product photo for the invoice. Can be a photo of the goods or a marketing image for a service.                                                                                                                                                                                                                                                    |
| photo\_size                       | Integer                                   | Optional | Photo size in bytes                                                                                                                                                                                                                                                                                                                                          |
| photo\_width                      | Integer                                   | Optional | Photo width                                                                                                                                                                                                                                                                                                                                                  |
| photo\_height                     | Integer                                   | Optional | Photo height                                                                                                                                                                                                                                                                                                                                                 |
| need\_name                        | Boolean                                   | Optional | Pass _True_ if you require the user's full name to complete the order                                                                                                                                                                                                                                                                                        |
| need\_phone\_number               | Boolean                                   | Optional | Pass _True_ if you require the user's phone number to complete the order                                                                                                                                                                                                                                                                                     |
| need\_email                       | Boolean                                   | Optional | Pass _True_ if you require the user's email address to complete the order                                                                                                                                                                                                                                                                                    |
| need\_shipping\_address           | Boolean                                   | Optional | Pass _True_ if you require the user's shipping address to complete the order                                                                                                                                                                                                                                                                                 |
| send\_phone\_number\_to\_provider | Boolean                                   | Optional | Pass _True_ if the user's phone number should be sent to the provider                                                                                                                                                                                                                                                                                        |
| send\_email\_to\_provider         | Boolean                                   | Optional | Pass _True_ if the user's email address should be sent to the provider                                                                                                                                                                                                                                                                                       |
| is\_flexible                      | Boolean                                   | Optional | Pass _True_ if the final price depends on the shipping method                                                                                                                                                                                                                                                                                                |

**answerShippingQuery**

If you sent an invoice requesting a shipping address and the parameter _is\_flexible_ was specified, the Bot API will send an [Update](broken-reference) with a _shipping\_query_ field to the bot. Use this method to reply to shipping queries. On success, _True_ is returned.

| Parameter           | Type                                        | Required | Description                                                                                                                                                                                                                                 |
| ------------------- | ------------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| shipping\_query\_id | String                                      | Yes      | Unique identifier for the query to be answered                                                                                                                                                                                              |
| ok                  | Boolean                                     | Yes      | Pass _True_ if delivery to the specified address is possible and _False_ if there are any problems (for example, if delivery to the specified address is not possible)                                                                      |
| shipping\_options   | Array of [ShippingOption](broken-reference) | Optional | Required if _ok_ is _True_. A JSON-serialized array of available shipping options.                                                                                                                                                          |
| error\_message      | String                                      | Optional | Required if _ok_ is _False_. Error message in human readable form that explains why it is impossible to complete the order (e.g. "Sorry, delivery to your desired address is unavailable'). Telegram will display this message to the user. |

**answerPreCheckoutQuery**

Once the user has confirmed their payment and shipping details, the Bot API sends the final confirmation in the form of an [Update](broken-reference) with the field _pre\_checkout\_query_. Use this method to respond to such pre-checkout queries. On success, _True_ is returned. **Note:** The Bot API must receive an answer within 10 seconds after the pre-checkout query was sent.

| Parameter                | Type    | Required | Description                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------ | ------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| pre\_checkout\_query\_id | String  | Yes      | Unique identifier for the query to be answered                                                                                                                                                                                                                                                                                                                     |
| ok                       | Boolean | Yes      | Specify _True_ if everything is alright (goods are available, etc.) and the bot is ready to proceed with the order. Use _False_ if there are any problems.                                                                                                                                                                                                         |
| error\_message           | String  | Optional | Required if _ok_ is _False_. Error message in human readable form that explains the reason for failure to proceed with the checkout (e.g. "Sorry, somebody just bought the last of our amazing black T-shirts while you were busy filling out your payment details. Please choose a different color or garment!"). Telegram will display this message to the user. |

**LabeledPrice**

This object represents a portion of the price for goods or services.

| Field  | Type    | Description                                                                                                                                                                                                                                                                                                                                                          |
| ------ | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| label  | String  | Portion label                                                                                                                                                                                                                                                                                                                                                        |
| amount | Integer | Price of the product in the _smallest units_ of the [currency](https://about/bots/payments#supported-currencies) (integer, **not** float/double). For example, for a price of `US$ 1.45` pass `amount = 145`. See the _exp_ parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |

**Invoice**

This object contains basic information about an invoice.

| Field            | Type    | Description                                                                                                                                                                                                                                                                                             |
| ---------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| title            | String  | Product name                                                                                                                                                                                                                                                                                            |
| description      | String  | Product description                                                                                                                                                                                                                                                                                     |
| start\_parameter | String  | Unique bot deep-linking parameter that can be used to generate this invoice                                                                                                                                                                                                                             |
| currency         | String  | Three-letter ISO 4217 [currency](https://about/bots/payments#supported-currencies) code                                                                                                                                                                                                                 |
| total\_amount    | Integer | Total price in the _smallest units_ of the currency (integer, **not** float/double). For example, for a price of `US$ 1.45` pass `amount = 145`. See the _exp_ parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |

**ShippingAddress**

This object represents a shipping address.

| Field         | Type   | Description                                                                                      |
| ------------- | ------ | ------------------------------------------------------------------------------------------------ |
| country\_code | String | Two-letter [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2) country code |
| state         | String | State, if applicable                                                                             |
| city          | String | City                                                                                             |
| street\_line1 | String | First line for the address                                                                       |
| street\_line2 | String | Second line for the address                                                                      |
| post\_code    | String | Address post code                                                                                |

**OrderInfo**

This object represents information about an order.

| Field             | Type                                | Description                       |
| ----------------- | ----------------------------------- | --------------------------------- |
| name              | String                              | _Optional_. User name             |
| phone\_number     | String                              | _Optional_. User's phone number   |
| email             | String                              | _Optional_. User email            |
| shipping\_address | [ShippingAddress](broken-reference) | _Optional_. User shipping address |

**ShippingOption**

This object represents one shipping option.

| Field  | Type                                      | Description                |
| ------ | ----------------------------------------- | -------------------------- |
| id     | String                                    | Shipping option identifier |
| title  | String                                    | Option title               |
| prices | Array of [LabeledPrice](broken-reference) | List of price portions     |

**SuccessfulPayment**

This object contains basic information about a successful payment.

| Field                         | Type                          | Description                                                                                                                                                                                                                                                                                             |
| ----------------------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| currency                      | String                        | Three-letter ISO 4217 [currency](https://about/bots/payments#supported-currencies) code                                                                                                                                                                                                                 |
| total\_amount                 | Integer                       | Total price in the _smallest units_ of the currency (integer, **not** float/double). For example, for a price of `US$ 1.45` pass `amount = 145`. See the _exp_ parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| invoice\_payload              | String                        | Bot specified invoice payload                                                                                                                                                                                                                                                                           |
| shipping\_option\_id          | String                        | _Optional_. Identifier of the shipping option chosen by the user                                                                                                                                                                                                                                        |
| order\_info                   | [OrderInfo](broken-reference) | _Optional_. Order information provided by the user                                                                                                                                                                                                                                                      |
| telegram\_payment\_charge\_id | String                        | Telegram payment identifier                                                                                                                                                                                                                                                                             |
| provider\_payment\_charge\_id | String                        | Provider payment identifier                                                                                                                                                                                                                                                                             |

**ShippingQuery**

This object contains information about an incoming shipping query.

| Field             | Type                                | Description                     |
| ----------------- | ----------------------------------- | ------------------------------- |
| id                | String                              | Unique query identifier         |
| from              | [User](broken-reference)            | User who sent the query         |
| invoice\_payload  | String                              | Bot specified invoice payload   |
| shipping\_address | [ShippingAddress](broken-reference) | User specified shipping address |

**PreCheckoutQuery**

This object contains information about an incoming pre-checkout query.

| Field                | Type                          | Description                                                                                                                                                                                                                                                                                             |
| -------------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                   | String                        | Unique query identifier                                                                                                                                                                                                                                                                                 |
| from                 | [User](broken-reference)      | User who sent the query                                                                                                                                                                                                                                                                                 |
| currency             | String                        | Three-letter ISO 4217 [currency](https://about/bots/payments#supported-currencies) code                                                                                                                                                                                                                 |
| total\_amount        | Integer                       | Total price in the _smallest units_ of the currency (integer, **not** float/double). For example, for a price of `US$ 1.45` pass `amount = 145`. See the _exp_ parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| invoice\_payload     | String                        | Bot specified invoice payload                                                                                                                                                                                                                                                                           |
| shipping\_option\_id | String                        | _Optional_. Identifier of the shipping option chosen by the user                                                                                                                                                                                                                                        |
| order\_info          | [OrderInfo](broken-reference) | _Optional_. Order information provided by the user                                                                                                                                                                                                                                                      |

#### Telegram Passport

**Telegram Passport** is a unified authorization method for services that require personal identification. Users can upload their documents once, then instantly share their data with services that require real-world ID (finance, ICOs, etc.). Please see the manual for details.

**PassportData**

Describes Telegram Passport data shared with the bot by the user.

| Field       | Type                                                  | Description                                                                                              |
| ----------- | ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| data        | Array of [EncryptedPassportElement](broken-reference) | Array with information about documents and other Telegram Passport elements that was shared with the bot |
| credentials | [EncryptedCredentials](broken-reference)              | Encrypted credentials required to decrypt the data                                                       |

**PassportFile**

This object represents a file uploaded to Telegram Passport. Currently all Telegram Passport files are in JPEG format when decrypted and don't exceed 10MB.

| Field            | Type    | Description                                                                                                                                      |
| ---------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| file\_id         | String  | Identifier for this file, which can be used to download or reuse the file                                                                        |
| file\_unique\_id | String  | Unique identifier for this file, which is supposed to be the same over time and for different bots. Can't be used to download or reuse the file. |
| file\_size       | Integer | File size in bytes                                                                                                                               |
| file\_date       | Integer | Unix time when the file was uploaded                                                                                                             |

**EncryptedPassportElement**

Describes documents or other Telegram Passport elements shared with the bot by the user.

| Field         | Type                                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------- | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| type          | String                                    | Element type. One of “personal\_details”, “passport”, “driver\_license”, “identity\_card”, “internal\_passport”, “address”, “utility\_bill”, “bank\_statement”, “rental\_agreement”, “passport\_registration”, “temporary\_registration”, “phone\_number”, “email”.                                                                                                                                                            |
| data          | String                                    | _Optional_. Base64-encoded encrypted Telegram Passport element data provided by the user; available only for “personal\_details”, “passport”, “driver\_license”, “identity\_card”, “internal\_passport” and “address” types. Can be decrypted and verified using the accompanying [EncryptedCredentials](broken-reference).                                                                                                    |
| phone\_number | String                                    | _Optional_. User's verified phone number; available only for “phone\_number” type                                                                                                                                                                                                                                                                                                                                              |
| email         | String                                    | _Optional_. User's verified email address; available only for “email” type                                                                                                                                                                                                                                                                                                                                                     |
| files         | Array of [PassportFile](broken-reference) | _Optional_. Array of encrypted files with documents provided by the user; available only for “utility\_bill”, “bank\_statement”, “rental\_agreement”, “passport\_registration” and “temporary\_registration” types. Files can be decrypted and verified using the accompanying [EncryptedCredentials](broken-reference).                                                                                                       |
| front\_side   | [PassportFile](broken-reference)          | _Optional_. Encrypted file with the front side of the document, provided by the user; available only for “passport”, “driver\_license”, “identity\_card” and “internal\_passport”. The file can be decrypted and verified using the accompanying [EncryptedCredentials](broken-reference).                                                                                                                                     |
| reverse\_side | [PassportFile](broken-reference)          | _Optional_. Encrypted file with the reverse side of the document, provided by the user; available only for “driver\_license” and “identity\_card”. The file can be decrypted and verified using the accompanying [EncryptedCredentials](broken-reference).                                                                                                                                                                     |
| selfie        | [PassportFile](broken-reference)          | _Optional_. Encrypted file with the selfie of the user holding a document, provided by the user; available if requested for “passport”, “driver\_license”, “identity\_card” and “internal\_passport”. The file can be decrypted and verified using the accompanying [EncryptedCredentials](broken-reference).                                                                                                                  |
| translation   | Array of [PassportFile](broken-reference) | _Optional_. Array of encrypted files with translated versions of documents provided by the user; available if requested for “passport”, “driver\_license”, “identity\_card”, “internal\_passport”, “utility\_bill”, “bank\_statement”, “rental\_agreement”, “passport\_registration” and “temporary\_registration” types. Files can be decrypted and verified using the accompanying [EncryptedCredentials](broken-reference). |
| hash          | String                                    | Base64-encoded element hash for using in [PassportElementErrorUnspecified](broken-reference)                                                                                                                                                                                                                                                                                                                                   |

**EncryptedCredentials**

Describes data required for decrypting and authenticating [EncryptedPassportElement](broken-reference). See the [Telegram Passport Documentation](https://about/passport#receiving-information) for a complete description of the data decryption and authentication processes.

| Field  | Type   | Description                                                                                                                                                                               |
| ------ | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| data   | String | Base64-encoded encrypted JSON-serialized data with unique user's payload, data hashes and secrets required for [EncryptedPassportElement](broken-reference) decryption and authentication |
| hash   | String | Base64-encoded data hash for data authentication                                                                                                                                          |
| secret | String | Base64-encoded secret, encrypted with the bot's public RSA key, required for data decryption                                                                                              |

**setPassportDataErrors**

Informs a user that some of the Telegram Passport elements they provided contains errors. The user will not be able to re-submit their Passport to you until the errors are fixed (the contents of the field for which you returned the error must change). Returns _True_ on success.

Use this if the data submitted by the user doesn't satisfy the standards your service requires for any reason. For example, if a birthday date seems invalid, a submitted document is blurry, a scan shows evidence of tampering, etc. Supply some details in the error message to make sure the user knows how to correct the issues.

| Parameter | Type                                              | Required | Description                                   |
| --------- | ------------------------------------------------- | -------- | --------------------------------------------- |
| user\_id  | Integer                                           | Yes      | User identifier                               |
| errors    | Array of [PassportElementError](broken-reference) | Yes      | A JSON-serialized array describing the errors |

**PassportElementError**

This object represents an error in the Telegram Passport element which was submitted that should be resolved by the user. It should be one of:

* [PassportElementErrorDataField](broken-reference)
* [PassportElementErrorFrontSide](broken-reference)
* [PassportElementErrorReverseSide](broken-reference)
* [PassportElementErrorSelfie](broken-reference)
* [PassportElementErrorFile](broken-reference)
* [PassportElementErrorFiles](broken-reference)
* [PassportElementErrorTranslationFile](broken-reference)
* [PassportElementErrorTranslationFiles](broken-reference)
* [PassportElementErrorUnspecified](broken-reference)

**PassportElementErrorDataField**

Represents an issue in one of the data fields that was provided by the user. The error is considered resolved when the field's value changes.

| Field       | Type   | Description                                                                                                                                                                   |
| ----------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| source      | String | Error source, must be _data_                                                                                                                                                  |
| type        | String | The section of the user's Telegram Passport which has the error, one of “personal\_details”, “passport”, “driver\_license”, “identity\_card”, “internal\_passport”, “address” |
| field\_name | String | Name of the data field which has the error                                                                                                                                    |
| data\_hash  | String | Base64-encoded data hash                                                                                                                                                      |
| message     | String | Error message                                                                                                                                                                 |

**PassportElementErrorFrontSide**

Represents an issue with the front side of a document. The error is considered resolved when the file with the front side of the document changes.

| Field      | Type   | Description                                                                                                                                   |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| source     | String | Error source, must be _front\_side_                                                                                                           |
| type       | String | The section of the user's Telegram Passport which has the issue, one of “passport”, “driver\_license”, “identity\_card”, “internal\_passport” |
| file\_hash | String | Base64-encoded hash of the file with the front side of the document                                                                           |
| message    | String | Error message                                                                                                                                 |

**PassportElementErrorReverseSide**

Represents an issue with the reverse side of a document. The error is considered resolved when the file with reverse side of the document changes.

| Field      | Type   | Description                                                                                                 |
| ---------- | ------ | ----------------------------------------------------------------------------------------------------------- |
| source     | String | Error source, must be _reverse\_side_                                                                       |
| type       | String | The section of the user's Telegram Passport which has the issue, one of “driver\_license”, “identity\_card” |
| file\_hash | String | Base64-encoded hash of the file with the reverse side of the document                                       |
| message    | String | Error message                                                                                               |

**PassportElementErrorSelfie**

Represents an issue with the selfie with a document. The error is considered resolved when the file with the selfie changes.

| Field      | Type   | Description                                                                                                                                   |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| source     | String | Error source, must be _selfie_                                                                                                                |
| type       | String | The section of the user's Telegram Passport which has the issue, one of “passport”, “driver\_license”, “identity\_card”, “internal\_passport” |
| file\_hash | String | Base64-encoded hash of the file with the selfie                                                                                               |
| message    | String | Error message                                                                                                                                 |

**PassportElementErrorFile**

Represents an issue with a document scan. The error is considered resolved when the file with the document scan changes.

| Field      | Type   | Description                                                                                                                                                                          |
| ---------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| source     | String | Error source, must be _file_                                                                                                                                                         |
| type       | String | The section of the user's Telegram Passport which has the issue, one of “utility\_bill”, “bank\_statement”, “rental\_agreement”, “passport\_registration”, “temporary\_registration” |
| file\_hash | String | Base64-encoded file hash                                                                                                                                                             |
| message    | String | Error message                                                                                                                                                                        |

**PassportElementErrorFiles**

Represents an issue with a list of scans. The error is considered resolved when the list of files containing the scans changes.

| Field        | Type            | Description                                                                                                                                                                          |
| ------------ | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| source       | String          | Error source, must be _files_                                                                                                                                                        |
| type         | String          | The section of the user's Telegram Passport which has the issue, one of “utility\_bill”, “bank\_statement”, “rental\_agreement”, “passport\_registration”, “temporary\_registration” |
| file\_hashes | Array of String | List of base64-encoded file hashes                                                                                                                                                   |
| message      | String          | Error message                                                                                                                                                                        |

**PassportElementErrorTranslationFile**

Represents an issue with one of the files that constitute the translation of a document. The error is considered resolved when the file changes.

| Field      | Type   | Description                                                                                                                                                                                                                                                     |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| source     | String | Error source, must be _translation\_file_                                                                                                                                                                                                                       |
| type       | String | Type of element of the user's Telegram Passport which has the issue, one of “passport”, “driver\_license”, “identity\_card”, “internal\_passport”, “utility\_bill”, “bank\_statement”, “rental\_agreement”, “passport\_registration”, “temporary\_registration” |
| file\_hash | String | Base64-encoded file hash                                                                                                                                                                                                                                        |
| message    | String | Error message                                                                                                                                                                                                                                                   |

**PassportElementErrorTranslationFiles**

Represents an issue with the translated version of a document. The error is considered resolved when a file with the document translation change.

| Field        | Type            | Description                                                                                                                                                                                                                                                     |
| ------------ | --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| source       | String          | Error source, must be _translation\_files_                                                                                                                                                                                                                      |
| type         | String          | Type of element of the user's Telegram Passport which has the issue, one of “passport”, “driver\_license”, “identity\_card”, “internal\_passport”, “utility\_bill”, “bank\_statement”, “rental\_agreement”, “passport\_registration”, “temporary\_registration” |
| file\_hashes | Array of String | List of base64-encoded file hashes                                                                                                                                                                                                                              |
| message      | String          | Error message                                                                                                                                                                                                                                                   |

**PassportElementErrorUnspecified**

Represents an issue in an unspecified place. The error is considered resolved when new data is added.

| Field         | Type   | Description                                                         |
| ------------- | ------ | ------------------------------------------------------------------- |
| source        | String | Error source, must be _unspecified_                                 |
| type          | String | Type of element of the user's Telegram Passport which has the issue |
| element\_hash | String | Base64-encoded element hash                                         |
| message       | String | Error message                                                       |

#### Games

Your bot can offer users **HTML5 games** to play solo or to compete against each other in groups and one-on-one chats. Create games via [@BotFather](https://t.me/botfather) using the _/newgame_ command. Please note that this kind of power requires responsibility: you will need to accept the terms for each game that your bots will be offering.

* Games are a new type of content on Telegram, represented by the [Game](broken-reference) and [InlineQueryResultGame](broken-reference) objects.
* Once you've created a game via [BotFather](https://t.me/botfather), you can send games to chats as regular messages using the [sendGame](broken-reference) method, or use [inline mode](broken-reference) with [InlineQueryResultGame](broken-reference).
* If you send the game message without any buttons, it will automatically have a 'Play _GameName_' button. When this button is pressed, your bot gets a [CallbackQuery](broken-reference) with the _game\_short\_name_ of the requested game. You provide the correct URL for this particular user and the app opens the game in the in-app browser.
* You can manually add multiple buttons to your game message. Please note that the first button in the first row **must always** launch the game, using the field _callback\_game_ in [InlineKeyboardButton](broken-reference). You can add extra buttons according to taste: e.g., for a description of the rules, or to open the game's official community.
* To make your game more attractive, you can upload a GIF animation that demostrates the game to the users via [BotFather](https://t.me/botfather) (see [Lumberjack](https://t.me/gamebot?game=lumberjack) for example).
* A game message will also display high scores for the current chat. Use [setGameScore](broken-reference) to post high scores to the chat with the game, add the _edit\_message_ parameter to automatically update the message with the current scoreboard.
* Use [getGameHighScores](broken-reference) to get data for in-game high score tables.
* You can also add an extra [sharing button](https://about/bots/games#sharing-your-game-to-telegram-chats) for users to share their best score to different chats.
* For examples of what can be done using this new stuff, check the [@gamebot](https://t.me/gamebot) and [@gamee](https://t.me/gamee) bots.

**sendGame**

Use this method to send a game. On success, the sent [Message](broken-reference) is returned.

| Parameter             | Type                                     | Required | Description                                                                                                                                                                                                  |
| --------------------- | ---------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| chat\_id              | Integer                                  | Yes      | Unique identifier for the target chat                                                                                                                                                                        |
| message\_thread\_id   | Integer                                  | Optional | Unique identifier for the target message thread (topic) of the forum; for forum supergroups only                                                                                                             |
| game\_short\_name     | String                                   | Yes      | Short name of the game, serves as the unique identifier for the game. Set up your games via [@BotFather](https://t.me/botfather).                                                                            |
| disable\_notification | Boolean                                  | Optional | Sends the message [silently](https://telegram.org/blog/channels-2-0#silent-messages). Users will receive a notification with no sound.                                                                       |
| protect\_content      | Boolean                                  | Optional | Protects the contents of the sent message from forwarding and saving                                                                                                                                         |
| reply\_parameters     | [ReplyParameters](broken-reference)      | Optional | Description of the message to reply to                                                                                                                                                                       |
| reply\_markup         | [InlineKeyboardMarkup](broken-reference) | Optional | A JSON-serialized object for an [inline keyboard](https://about/bots/features#inline-keyboards). If empty, one 'Play game\_title' button will be shown. If not empty, the first button must launch the game. |

**Game**

This object represents a game. Use BotFather to create and edit games, their short names will act as unique identifiers.

| Field          | Type                                       | Description                                                                                                                                                                                                                                                                                          |
| -------------- | ------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| title          | String                                     | Title of the game                                                                                                                                                                                                                                                                                    |
| description    | String                                     | Description of the game                                                                                                                                                                                                                                                                              |
| photo          | Array of [PhotoSize](broken-reference)     | Photo that will be displayed in the game message in chats.                                                                                                                                                                                                                                           |
| text           | String                                     | _Optional_. Brief description of the game or high scores included in the game message. Can be automatically edited to include current high scores for the game when the bot calls [setGameScore](broken-reference), or manually edited using [editMessageText](broken-reference). 0-4096 characters. |
| text\_entities | Array of [MessageEntity](broken-reference) | _Optional_. Special entities that appear in _text_, such as usernames, URLs, bot commands, etc.                                                                                                                                                                                                      |
| animation      | [Animation](broken-reference)              | _Optional_. Animation that will be displayed in the game message in chats. Upload via [BotFather](https://t.me/botfather)                                                                                                                                                                            |

**CallbackGame**

A placeholder, currently holds no information. Use [BotFather](https://t.me/botfather) to set up your game.

**setGameScore**

Use this method to set the score of the specified user in a game message. On success, if the message is not an inline message, the [Message](broken-reference) is returned, otherwise _True_ is returned. Returns an error, if the new score is not greater than the user's current score in the chat and _force_ is _False_.

| Parameter              | Type    | Required | Description                                                                                                       |
| ---------------------- | ------- | -------- | ----------------------------------------------------------------------------------------------------------------- |
| user\_id               | Integer | Yes      | User identifier                                                                                                   |
| score                  | Integer | Yes      | New score, must be non-negative                                                                                   |
| force                  | Boolean | Optional | Pass _True_ if the high score is allowed to decrease. This can be useful when fixing mistakes or banning cheaters |
| disable\_edit\_message | Boolean | Optional | Pass _True_ if the game message should not be automatically edited to include the current scoreboard              |
| chat\_id               | Integer | Optional | Required if _inline\_message\_id_ is not specified. Unique identifier for the target chat                         |
| message\_id            | Integer | Optional | Required if _inline\_message\_id_ is not specified. Identifier of the sent message                                |
| inline\_message\_id    | String  | Optional | Required if _chat\_id_ and _message\_id_ are not specified. Identifier of the inline message                      |

**getGameHighScores**

Use this method to get data for high score tables. Will return the score of the specified user and several of their neighbors in a game. Returns an Array of [GameHighScore](broken-reference) objects.

> This method will currently return scores for the target user, plus two of their closest neighbors on each side. Will also return the top three users if the user and their neighbors are not among them. Please note that this behavior is subject to change.

| Parameter           | Type    | Required | Description                                                                                  |
| ------------------- | ------- | -------- | -------------------------------------------------------------------------------------------- |
| user\_id            | Integer | Yes      | Target user id                                                                               |
| chat\_id            | Integer | Optional | Required if _inline\_message\_id_ is not specified. Unique identifier for the target chat    |
| message\_id         | Integer | Optional | Required if _inline\_message\_id_ is not specified. Identifier of the sent message           |
| inline\_message\_id | String  | Optional | Required if _chat\_id_ and _message\_id_ are not specified. Identifier of the inline message |

**GameHighScore**

This object represents one row of the high scores table for a game.

| Field    | Type                     | Description                               |
| -------- | ------------------------ | ----------------------------------------- |
| position | Integer                  | Position in high score table for the game |
| user     | [User](broken-reference) | User                                      |
| score    | Integer                  | Score                                     |

***

And that's about all we've got for now.\
If you've got any questions, please check out our **Bot FAQ »**
