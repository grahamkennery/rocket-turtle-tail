# rocket-turtle-tail

[![Build Status](https://travis-ci.org/grahamkennery/rocket-turtle-tail.svg?branch=master)](https://travis-ci.org/grahamkennery/rocket-turtle-tail) [![js-semistandard-style](https://img.shields.io/badge/code%20style-semistandard-brightgreen.svg?style=plastic)](https://github.com/Flet/semistandard) [![Greenkeeper badge](https://badges.greenkeeper.io/grahamkennery/rocket-turtle-tail.svg)](https://greenkeeper.io/)

Ever wanted to tail a file in node? Me too! Wow! Fun!

## Installation
```
yarn add rocket-turtle-tail
```

or

```
npm install --save rocket-turtle-tail
```

## Usage
```javascript
const RocketTurtleTail = require('rocket-turtle-tail');
const tail = new RocketTurtleTail('path-to-file-you-want-to-watch');

tail.on('line', (line) => {
  console.log('OH LOOK, A LINE!', line);
});

tail.on('error', (err) => {
  console.log('Boooooo an error:', err);
});

tail.start();
```


## Other things
The constructor takes an optional second parameter of options as follows (defaults are shown):

``` javascript
new RocketTurtleTail('path-to-file', {
  useWatchFile: false, // Use fs.watchFile instead of fs.watch
  interval: 5000, // Specifies the interval for useWatchFile
  fromBeginning: false // Read the file from the beginning
});
```

---

This project was inspired by [node-tail](https://github.com/lucagrulla/node-tail). I made this repo for my own use since it couldn't do something and I don't like coffeescript enough to fix it ;)
