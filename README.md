# coffea-telegram

_telegram plugin for [coffea](https://github.com/caffeinery/coffea/)_


## Setup

 * Make sure to use the latest *unstable* version of coffea by specifying: `"coffea": "caffeinery/coffea#plugin-manager"` in your dependencies
 * Install `coffea-telegram`: `npm install coffea-telegram`

__NOTE: The latest unstable coffea version uses ES6 proxies, make sure to run your programs with the `--harmony_proxies` flag and ideally on the latest io.js version (that's what I'm testing with): `node --harmony_proxies script.js`__


## Usage

Specify the telegram protocol in your network config:

 * Short `string` config: `"telegram://TOKEN"`
 * Long `object` config: `{"protocol": "telegram", "token": "TOKEN"}`

coffea will automatically load `coffea-telegram` when it's needed! Thus, using telegram (or other protocols) this way should work on **any** coffea project, **without any tweaks** (other than installing `coffea-telegram` and specifying the config).

`coffea-telegram` aims to be compatible with coffea. Of course, features that telegram doesn't have (like joining channels) aren't available for telegram protocols and will result in an error if called on a telegram stream. (If `join` is called in the `motd` event it shouldn't make a difference though, as telegram doesn't emit that event)


## Telegram API

Until https://github.com/caffeinery/coffea-telegram/issues/1 is done, use `client.streams[event.network]` to use the telegram api. (the "stream" is a `TelegramBot` object, so you can use everything that [node-telegram-bot-api](https://github.com/yagop/node-telegram-bot-api) lets you do)
