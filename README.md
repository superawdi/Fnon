# 𝔉𝔫𝔬𝔫

Fnon is the name of my late mother, It's an Arabic name which means Art, I created this library in honor of her name.

Fnon is a client-side JavaScript library for models, loading indicators, notifications, and alerts which makes your web projects much better.

Colors are based on Bootstrap main categories: Light, Primary, Info, Warning, Danger and Dark.


##### Current Version : [1.0.0](https://github.com/superawdi/fnon/ReleaseNotes.md "Release Notes")



## Installation  : # 1

[pip](https://pip.pypa.io/en/stable/) to install fnon.

```bash
pip install fnon
```

[npm](https://pip.pypa.io/en/stable/) :

```bash
npm i fnon
```

[yarn](https://pip.pypa.io/en/stable/) :

```bash
yarn add fnon
```


Import

```jsx
// all modules
import Fnon from "fnon";

// one by one
import { Hint, Wait, Box, Dialogue, Alert, Ask} from "fnon";
```

## Installation  : # 2

Add to HTML (css and js)
```html
<link rel="stylesheet" href="dist/fnon.min.css" />

<script src="dist/fnon.min.js"></script>
```



## Usage
#### 1- Hint

```js

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

//



Notiflix.Notify.Success('Success message text');

Notiflix.Notify.Failure('Failure message text');

Notiflix.Notify.Warning('Warning message text');

Notiflix.Notify.Info('Info message text');

// e.g. Message with a callback
Notiflix.Notify.Success(
  'Click Me',
  function(){
    // callback
  },
);

// e.g. Message with the new options (v2.3.1 and the next versions)
Notiflix.Notify.Success(
  'Click Me',
  {
    timeout: 6000,
  },
);

// e.g. Message with callback, and the new options (v2.3.1 and the next versions)
Notiflix.Notify.Success(
  'Click Me',
  function(){
    // callback
  },
  {
    timeout: 4000,
  },
);
```







## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
