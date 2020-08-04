# 𝔉𝔫𝔬𝔫

Fnon is the name of my late mother, It's an Arabic word which means Art, I created this library in honor of her name.

Fnon is a client-side JavaScript library for models, loading indicators, notifications, and alerts which makes your web projects much better.

Colors are based on Bootstrap main categories:

![](https://via.placeholder.com/15/ffffff/000000?text=+) `Light`
![](https://via.placeholder.com/15/029eff/000000?text=+) `Primary`
![](https://via.placeholder.com/15/39DA8A/000000?text=+) `Success`
![](https://via.placeholder.com/15/f55260/000000?text=+) `Danger`
![](https://via.placeholder.com/15/fdd347/000000?text=+) `Warning`
![](https://via.placeholder.com/15/56b6f7/000000?text=+) `Info`
![](https://via.placeholder.com/15/222f3e/000000?text=+) `Dark`


##### Current Version : [1.0.0](https://github.com/superawdi/fnon/ReleaseNotes.md "Release Notes")



## Installation  : 

>[Use node package manager](https://www.npmjs.com/package/fnon) :

```bash
npm i fnon
```


>Add direct to HTML (css and js)
```html
<link rel="stylesheet" href="dist/fnon.min.css" />

<script src="dist/fnon.min.js"></script>
```



## Usage
>### 1- Hint
Hint has 7 themed functions named as bootstrap's colors![](https://via.placeholder.com/15/ffffff/000000?text=+) `Light`
![](https://via.placeholder.com/15/029eff/000000?text=+) `Primary`
![](https://via.placeholder.com/15/39DA8A/000000?text=+) `Success`
![](https://via.placeholder.com/15/f55260/000000?text=+) `Danger`
![](https://via.placeholder.com/15/fdd347/000000?text=+) `Warning`
![](https://via.placeholder.com/15/56b6f7/000000?text=+) `Info`
![](https://via.placeholder.com/15/222f3e/000000?text=+) `Dark`

```js
// @param1 {string}: Required, message text in String format[it's not a plane text, means you could add your own HTML syntax].
// @param2 {Object}: Optional,update the initialize options with new options for current hint.

// Just a message
Fnon.Hint.Light("Your Message comes here");

// Message with settings
Fnon.Hint.Dark('Rest in peace',{
    position: 'right-top',
    fontSize: '14px',
    width: '300px'
});

// Message with a callback
Fnon.Hint.Info('God have mercy on you, my mother',{
    callback:function(){
       console.log('Do not stop praying to your parents');
    }
});
// rest of functions....
//Fnon.Hint.Success("Your Message comes here");
//Fnon.Hint.Primary("Your Message comes here");
//Fnon.Hint.Danger("Your Message comes here");
//Fnon.Hint.Warning("Your Message comes here");
```
>If you want to modify the **default Hint settings**, you can use the **Init** function. Below is the list of all available properties you could change.
```js
Fnon.Hint.Init({
        fontFamily:'"Quicksand", sans-serif',
        position: 'right-top',
        spacing: '16px',
        svgSize: { w: '16px', h: '16px' },
        textColor: '#fff',
        fontSize: '14px',
        backgroundColor: '#029eff',
        shadowColor: 'rgba(2, 158, 255, 0.3)',
        width: '300px',
        zindex: 4000,
        animation: 'slide-left',
        animationDuration: 500,
        displayDuration: 3000,
        progressColor: 'rgba(255,255,255,0.9)',
        callback:undefined,
    });
```
> Hint positioning can be set using the position property with any of the following options:
- right-top
- right-center
- right-bottom
- left-top
- left-center
- left-bottom
- center-top
- center-center
- center-bottom
> Below is the list of available animation effects:
- fade
- slide-left 
- slide-right 
- slide-bottom 
- slide-top
---
>### 2- Wait
The wait functions are simply a block screens that blocks the user from interacting with the page until further notice. Wait simply displays an animated SVG icon and a text if provided.

The Wait object contains 19 functions, 16 of them are named after the icons used in it.

```js
// @param1 {string}: Optional, message text in String format[it's not a plane text, means you could add your own HTML syntax].
// @param2 {Object}: Optional,update the initialize options with new options for current wait block.
// Simple call
Fnon.Wait.Infinity();
// Call with a message
Fnon.Wait.Ripple('Loading'); 
// call with a message and change some options
Fnon.Wait.Liquid('Please Wait',{
     textSize: '14px',
     clickToClose: true,
}); 
// The rest of displaying functions
//Fnon.Wait.ColorBar()
//Fnon.Wait.ProgressBar()
//Fnon.Wait.CurveBar()
//Fnon.Wait.LineDots()
//Fnon.Wait.Circle() 
//Fnon.Wait.CircleDots()
//Fnon.Wait.Bricks() 
//Fnon.Wait.Interwind() 
//Fnon.Wait.Typing() 
//Fnon.Wait.Gear()
//Fnon.Wait.Gears()
//Fnon.Wait.Rainbow()
//Fnon.Wait.CurveBar()
```
> There are two more functions which are **Change** and **Remove**

**Change** function is going to change or add a text to the running Wait function:
```js
Fnon.Wait.Change('Downloading 77%');
```
**Remove** function will remove the current waiting block. You can also delay the remove function by provide time param.
```
// Remove instantly
Fnon.Wait.Remove();
// Remove after 3 seconds
Fnon.Wait.Remove(3000);
```
>If you want to modify the **default Wait settings**, you can use the **Init** function. Below is the list of all available properties you could change.
```js
Fnon.Wait.Init({
        fontFamily:'"Quicksand", sans-serif',
        svgSize: { w: '100px', h: '100px' },
        svgColor: '#029eff',
        textColor: '#029eff',
        textSize: '16px',
        clickToClose: false,
        background: 'rgba(255,255,255,0.5)',
        zindex: 4000,
        containerSize: '350px'});
```
---
>### 3- Box
well, it's basically similar to **Wait**, but it is used for blocking **specific HTML** element where **Wait** will block everything. You simply have to provide the function with an element or with the respective selector.
```js
// @param1 {string or element}: required, HTML element or respective selector.
// @param2 {string}: optional, message text in String format[it's not a plane text, means you could add your own HTML syntax].
// @param3 {Object}: Optional,update the initialize options with new options for current wait block.
// Simple call
Fnon.Wait.Infinity('div.className');
// Call with a message
Fnon.Wait.Ripple('form.login','Loading'); 
// call with html element, message and change some options
const form= document.querySelector('form#login');
Fnon.Wait.Liquid(form,'Please Wait',{
     textSize: '14px',
     textColor: '#029eff',
}); 
```
>**Change** and **Remove** works similar to **Wait**.

>**Init** also, works the same but below are the list of settings you can change:

```
Fnon.Box.Init({
        fontFamily:'"Quicksand", sans-serif',
        svgSize: { w: '100px', h: '100px' },
        svgColor: GColors.Primary,
        background: 'rgba(255,255,255,0.8)',
        zindex: 4000,
        textColor: '#029eff',
        textSize: '16px'
});
```
---
>### 4- Alert
A simple alert dialog with a single button. Click the close button to dismisses it.

Alert functions are based on bootstrap basic colors ![](https://via.placeholder.com/15/ffffff/000000?text=+) `Light`
![](https://via.placeholder.com/15/029eff/000000?text=+) `Primary`
![](https://via.placeholder.com/15/39DA8A/000000?text=+) `Success`
![](https://via.placeholder.com/15/f55260/000000?text=+) `Danger`
![](https://via.placeholder.com/15/fdd347/000000?text=+) `Warning`
![](https://via.placeholder.com/15/56b6f7/000000?text=+) `Info`
![](https://via.placeholder.com/15/222f3e/000000?text=+) `Dark`

```js
// @param1 {string or object}: required, message or an object will all settings.
// @param2 {string}: optional, title || if not provided title section won't be displayed.
// @param3 {string}: Optional, ok button text || default is Ok.
// @param4 {function}: Optional, a callback function if needed.
// Simple use
Fnon.Alert.Success('Message','Title','Ok Button',()=>{
   console.log('I am a callback');
});
// Display by providing setting object
Fnon.Alert.Danger({
     title:'Confirmation',
     message:'Are you sure?',
     callback:()=>{
       // do some thing
       console.log('Dismissed');
     }
});

// remaining functions are:
// Fnon.Alert.Primary(.....);
// Fnon.Alert.Warning(.....);
// Fnon.Alert.Dark(.....);
// Fnon.Alert.Light(.....);
// Fnon.Alert.Info(.....);
```
> Here also you can use the **Init** function to change the default settings, but when it comes to theme and colors, this will effect the **Light** function only.
```js
Fnon.Alert.Init({
    message: '',
    title: '',    
    titleColor: GColors.Dark,
    titleBackground: GColors.Light,
    color: '#2b2b2b',
    background: 'rgba(0, 0, 0, 0.1)',
    fontFamily: '"Quicksand", sans-serif',
    width: 'nl',
    closeButton: true,
    animation: 'slide-top',
    closeButton: false,
    callback: undefined,
    icon: undefined,
    iconColor: '#000',
    showIcon: false,
    btnOkText: 'Ok',
    btnOkColor: '#d4d4d4',
    btnOkBackground: '#d4d4d4',
    btnOkShadow: 'rgba(0, 0, 0, 0.2)',
    btnOkBorderColor: '#d4d4d4',
    
    zIndex:4000,

    // Functions
    beforeShow: undefined,
    afterShow: undefined,
});
```
> **Width**: Normarl 'nl', Small 'sm', Large 'lg', X-Large 'xl'.

> **Animartion Effects** 'fade', 'slide-top', 'slide-bottom', 'slide-right' and 'slide-left'.
---
>### 5- Ask
It's a dialogue similar to **Alert** but it comes with an extra cancel button, and its callback function returns whatever a user clicks `true` or `false`.
```js
// @param1 {string or object}: required, HTML element or respective selector.
// @param2 {string}: optional, title || if not provided title section won't be displayed.
// @param3 {string}: Optional, ok button text || default is Ok.
// @param4 {string}: Optional, cancel button text || default is Cancel.
// @param5 {function}: Optional, a callback function.
// Simple use
Fnon.Ask.Success('Message','Title','Sure','Naah',(result)=>{
   console.log('result is: ',result);
});
// Display by providing setting object
Fnon.Alert.Danger({
     title:'Confirmation',
     message:'Are you sure?',
     callback:(result)=>{
       // do some thing
       console.log('result is: ',result);
     }
});

// remaining functions are:
// Fnon.Ask.Primary(.....);
// Fnon.Ask.Warning(.....);
// Fnon.Ask.Dark(.....);
// Fnon.Ask.Light(.....);
// Fnon.Ask.Info(.....);
```
> **Init** Function works the same as **Alert**.
```js
Fnon.Ask.Init({
    fontFamily: defaultFont,
    width: 'nl', // sm//lg//nl//xl
    closeButton: true,
    animation: 'slide-top',//'fade', 'slide-top', 'slide-bottom', 'slide-right' and 'slide-left'
    closeButton: false,
    callback: undefined,
    icon: undefined,
    iconColor: '#fff',
    showIcon: false,
    message: '',

    title: '',
    titleColor: '#fff',
    titleBackground: '#fff',

    btnOkText: 'Ok',
    btnOkColor: '#fff',
    btnOkBackground: '#fff',
    btnOkShadow: 'rgba(0, 0, 0, 0.2)',
    btnOkBorderColor: '#d4d4d4',

    btnCancelText: 'Cancel',
    btnCancelColor: '#fff',
    btnCancelBackground: '#fff',
    btnCancelShadow: 'rgba(0, 0, 0, 0.1)',
    btnCancelBorderColor: '#d4d4d4',

    color: '#2b2b2b',
    background: 'rgba(0, 0, 0, 0.1)',
    
    zIndex:4000,

    // Functions
    beforeShow: undefined,
    afterShow: undefined,

});
```
> **Width** and **Animation Effects** are similar to **Alert**.
---
>### 6- Dialogue
well, one last time :) it's similar to **Ask** and **alert** but in Dialogue there are no icons and it comes with two callbacks if needed for `ok` and `cancel`. You can **avoid closing** the model by simply returning `false` in callback function.
```js
// @param1 {string or object}: required, HTML element or respective selector.
// @param2 {string}: optional, title || if not provided title section won't be displayed.
// @param3 {string}: Optional, ok button text || default is Ok.
// @param4 {string}: Optional, cancel button text || default is Cancel.
// @param5 {function}: Optional, Ok callback function.
// @param5 {function}: Optional, Cancel callback function.
// Simple use
Fnon.Dialogue.Success('Message','Title','Sure','Naah',()=>{
   console.log('Ok callback');
},()=>{
   console.log('cancel callback');
};
// Display by providing setting object
Fnon.Dialogue.Danger({
     title:'Login',
     message:'Login Form Html',
     callback:(result)=>{
       // do ....
       // ......
       // if you return false that would forbid the model from closing itself
     }
});
// remaining functions are:
// Fnon.Dialogue.Primary(.....);
// Fnon.Dialogue.Warning(.....);
// Fnon.Dialogue.Dark(.....);
// Fnon.Dialogue.Light(.....);
// Fnon.Dialogue.Info(.....);
```
> **callback** of Ok button returns two params ( **closer** function and **html of dialogue** body). If you decid to return `false` to avoid closing the model, you can simply call the **closer** fuciton.
```js
Fnon.Dialogue.Success('Message','Title','Sure','Naah',(closer,html)=>{
   return false; // this will avoid closing the model.
   closer();// will force the closing.
   // html is simply the body container where you can use it to do some validation, querying,...etc.
});
```

> **Width** and **Animation Effects** are similar to **Alert**.

>**Init** function also here works the same as **Alert** and **Ask**.
```js
Fnon.Dialogue.Init({
    fontFamily: defaultFont,
    width: 'nl', // sm//lg//nl//xl
    closeButton: true,
    animation: 'slide-top',//'fade', 'slide-top', 'slide-bottom', 'slide-right' and 'slide-left'
    closeButton: false,
    callback: undefined,
    cancelCallback: undefined,
    message: '',
    title: '',
    titleColor: '#fff',
    titleBackground: '#fff',
    btnOkText: 'Ok',
    btnOkColor: '#fff',
    btnOkBackground: '#fff',
    btnOkShadow: 'rgba(0, 0, 0, 0.2)',
    btnOkBorderColor: '#d4d4d4',
    btnCancelText: 'Cancel',
    btnCancelColor: '#fff',
    btnCancelBackground: '#fff',
    btnCancelShadow: 'rgba(0, 0, 0, 0.1)',
    btnCancelBorderColor: '#d4d4d4',
    color: '#2b2b2b',
    background: 'rgba(0, 0, 0, 0.1)',
    
    zIndex:4000,

    // Functions
    beforeShow: undefined,
    afterShow: undefined,
});

```
---
> **Functions** : Alert,Ask and Dialogue have two simple functions.

`beforeShow` function : after html is rendered but not appened to body.
`afterShow` function : after html appened to body.
Both functions pass the HTML content in param.

```
Fnon.Dialogue.Primary({
  title:'title',
  message:'content',
  callback:(closer, html)=>{

  },
  beforeShow:(html)=>{

  },
  afterShow:(html)=>{

  }
});

```
---


## Final Word
Mother is an excellent example of love, affection, and sacrifice. So show the love to your mothers before it's too late.

**I love you 𝔉𝔫𝔬𝔫**





---

## License
[MIT License](https://opensource.org/licenses/MIT)
