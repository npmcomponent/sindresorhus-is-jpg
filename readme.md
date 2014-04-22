*This repository is a mirror of the [component](http://component.io) module [sindresorhus/is-jpg](http://github.com/sindresorhus/is-jpg). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/sindresorhus-is-jpg`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# is-jpg [![Build Status](https://travis-ci.org/sindresorhus/is-jpg.svg?branch=master)](https://travis-ci.org/sindresorhus/is-jpg)

> Check if a Buffer/Uint8Array is a [JPEG](http://en.wikipedia.org/wiki/JPEG) image

Used by [image-type](https://github.com/sindresorhus/image-type).


## Install

```sh
$ npm install --save is-jpg
```

```sh
$ bower install --save is-jpg
```

```sh
$ component install sindresorhus/is-jpg
```


## Usage

##### Node.js

```js
var readChunk = require('read-chunk'); // npm install read-chunk
var isJpg = require('is-jpg');
var buffer = readChunk('unicorn.jpg', 0, 4);

isJpg(buffer);
//=> true
```

##### Browser

```js
var xhr = new XMLHttpRequest();
xhr.open('GET', 'unicorn.jpg');
xhr.responseType = 'arraybuffer';

xhr.onload = function () {
	isJpg(new Uint8Array(this.response));
	//=> true
};

xhr.send();
```


## API

### isJpg(buffer)

Accepts a Buffer (Node.js) or Uint8Array.

It only needs the first 4 bytes.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
