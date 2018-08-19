# TelegramAppender - for [log4js-node](https://github.com/log4js-node/log4js-node)

Install peer dependency log4js:
`npm install log4js`

Installation:
```
npm install git+ssh://git@github.com:liangwp/log4js-node-telegramAppender.git
```
OR
```
npm install git+https://git@github.com:liangwp/log4js-node-telegramAppender.git```

Sample usage:
```
'use strict';

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

logger.debug(`This logs to console only`);
logger.info(`This logs to console and telegram, without telegram notification sound`);
logger.error(`This logs to console and telegram, with telegram notification sound`);
```