# TelegramAppender - for [log4js-node](https://github.com/log4js-node/log4js-node)

Sample usage:

```
const log4js = require("log4js");
log4js.configure({
    appenders: {
        colouredConsole: { type: 'stdout' },
        telegramAlert: {
            type: '../telegramAppender', // ./telegramAppender
            silentAlertLevel: 'info',
            audioAlertLevel: 'error',
            bottoken: <token>,
            botchatid: <chatid>
        }
    },
    categories: { default: { appenders: ['colouredConsole', 'telegramAlert'], level: 'debug' } }
})
var logger = log4js.getLogger("TEST");
```