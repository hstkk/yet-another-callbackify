# Yet another callbackify

[![Build Status](https://travis-ci.org/hstkk/yet-another-callbackify.svg?branch=master)](https://travis-ci.org/hstkk/yet-another-callbackify)
[![NPM](https://img.shields.io/npm/v/yet-another-callbackify.svg)](https://www.npmjs.com/package/yet-another-callbackify)

*It's probably good idea to check Node util.callbackify or Bluebird.asCallback instead of using this*

Are you tired of using old fashioned callbacks? Callbackify saves your code as it converts your promises to callbacks

## Installation

```sh
yarn add yet-another-callbackify
# -or-
npm install --save yet-another-callbackify
```

## Usage

```javascript
exports.handler = callbackify(event => {
    return Promise.resolve('Hello world');
});

// This is more or less same using callbacks
exports.handler = (event, context, callback) => {
    callback(null, 'Hello world');
};
```

## API

```typescript
callbackify(fn: () => Promise<any>): (callback: Function) => Promise<any>
callbackify(fn: () => Promise<any>): (...args: any[], callback: Function) => Promise<any>
```