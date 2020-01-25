Customizable Chat Bot Component 

Usage
npm install react--customizable-chat-bot or Yarn add  react--customizable-chat-bot

```js
import { Bot, BotConfig } from 'react--customizable-chat-bot'

<Bot config={BotConfig} />
```
You can take a look at list of config option available [here!](https://github.com/chithakumar13/react-chat-bot/blob/master/src/config/config.ts)

You can add a custom styles to you bot:

```js
<Bot config={botConfig} customStyles={customStyles} />
```
You can take a look at list of custom style option available [here!](https://github.com/chithakumar13/react-chat-bot/blob/master/src/config/style.ts)

You can alter question to ask using 
```js
BotConfig.questions = yourquestionObject
```

You can take a look [here!](https://github.com/chithakumar13/react-chat-bot/blob/master/src/config/Question/Questionnare.ts)  on how to form questions 

Live Demo of the App - https://chithakumar13.github.io/bot-example