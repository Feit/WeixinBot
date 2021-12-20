```
__    __       _        _           ___         _
/ / /\ \ \ ___ (_)__  __(_) _ __    / __\  ___  | |_
\ \/  \/ // _ \| |\ \/ /| || '_ \  /__\// / _ \ | __|
 \  /\  /|  __/| | >  < | || | | |/ \/  \| (_) || |_
  \/  \/  \___||_|/_/\_\|_||_| |_|\_____/ \___/  \__|
```

## Deprecated

[![NPM version](https://badge.fury.io/js/weixinbot.png)](http://badge.fury.io/js/weixinbot)

### Install
```
npm install weixinbot --save
```

### Usage
```js
// Require Nodejs v8+

// index.js
const Weixinbot = require('weixinbot')

// will send qrcode to your email address
const bot = new Weixinbot({ receiver: 'your@email.com' })

// will emit when bot fetch a new qrcodeUrl
bot.on('qrcode', (qrcodeUrl) => {
  console.log(qrcodeUrl)
})

bot.on('friend', (msg) => {
  console.log(msg.Member.NickName + ': ' + msg.Content)
  bot.sendText(msg.FromUserName, 'Got it')
})

bot.run()

```

### Run
```bash
# We recommend show debug message under development
DEBUG=weixinbot node index.js
```

### Feature
Remember previous login secret, when secret is valid, we can direct login without scan qrcode

### [API Doc](https://github.com/feit/weixinbot/tree/master/docs/API.md)

### License
The MIT license.
