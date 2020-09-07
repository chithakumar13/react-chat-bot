***Build your own chatbot with minimal changes***

**Live Demo [live demo](https://chithakumar13.github.io/bot-example)**
**Real life implementation as [Icalia Labs](http://www.icalialabs.com) Virtual Sales Assisstant [here](http://quotient.icalialabs.com)**

**Comes with 5 predefined styles and you can define your own styles as well**

## **Installation**
npm install react--customizable-chat-bot or Yarn add  react--customizable-chat-bot
 
## **Usage**

List of questions to be asked by bot the can be passed . Take a look at example questions structure here `src/config/Question/Questionnare.ts`

```
import { Bot, BotConfig } from 'react--customizable-chat-bot'
```
BotConfig has some default set of questions and styles which you can override

```
const dateReg = /^\d{2}[./-]\d{2}[./-]\d{4}$/;
const dateRegNeg = /^((?!\d{2}[./-]\d{2}[./-]\d{4}).)*$/;
const validateEmail = (email: string) => {
    var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(String(email).toLowerCase());
}
const validateEmailNeg = (email: string) => { return !validateEmail(email) }

BotConfig.questions = [{'dob': {
            id: 1,
            message: "What's your Date of Birth (DD/MM/YYYY)?",
            questionKey : 'dob',
            handlers: [
                {
                    validators: dateReg,
                    nextQuestion: 'email',
                },
                {
                    validators: dateRegNeg,
                    nextQuestion: 'dobWrong',
                },
            ],
        }},'dobWrong': {
            id: 2,
            message: "Please enter a valid date of birth",
            questionKey : 'dob',
            handlers: [
                {
                    validators: dateReg,
                    nextQuestion: 'email',
                },
                {
                    validators: dateRegNeg,
                    nextQuestion: 'dobWrong',
                },
            ],
        }];
 ```
 
**Customizing the Styles**

By Default there are 5 themes available 

    1.)Default,
    2.)GoogleAssitant,
    3.)Facebook,
    4.)WhatsApp, 
    5.)GradientGreen   
    
You can chose any of these themes as below    
```
import { Bot, BotConfig } from 'react--customizable-chat-bot'
import { Themes } from 'react--customizable-chat-bot/lib/config/config';

BotConfig.Theme = Themes.GoogleAssitant;
```

You can entirely redefine the ui styles based on your brand.
Take a look at List of custom style option available [here!](https://github.com/chithakumar13/react-chat-bot/blob/master/src/config/style.ts)

Once your styling is ready you can pass it as a props to the bot component

```
import { Bot, BotConfig , IStyles } from 'react--customizable-chat-bot' 

const myStyles: IStyles = {
    primaryColor: "#4870df",
    sendButtonColor: "#4870df",
    userAvatar: '',
    userAvatarColor: '#4870df',
    userAvatarTextColor: '#fff',
    botAvatar: "https://i.ibb.co/NxZqGVN/bot-avatar.png",
    botAvatarColor: '#e6e5eb',
    botAvatarTextColor: '#000',
    bubbleRadius: "0",
    botMessageBubbleColor: '#4870df',
    botMessageTextColor: '#fff',
    userMessageBubbleColor: '#e6e5eb',
    userMessageTextColor: '#000',
    inputBoxBorderRadius: '40px',
    primaryLabelColor: '#000',
}

export const MyFunc() => <Bot config={BotConfig}  customStyles={myStyles}/>
```




