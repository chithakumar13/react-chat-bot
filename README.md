Customizable Chat Bot Component 

Usage
npm install react--customizable-chat-bot or Yarn add  react--customizable-chat-bot

```js
import { Bot, BotConfig } from 'react--customizable-chat-bot'

<Bot config={BotConfig} />
```

You can add a custom styles to you bot:

```js
<Bot config={botConfig} customStyles={customStyles} />
```


You can alter question to ask using
```js
BotConfig.questions = yourquestionObject
```
