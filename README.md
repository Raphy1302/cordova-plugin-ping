
# cordova-plugin-ping

[![NPM version](https://img.shields.io/npm/v/cordova-plugin-ping.svg)](https://www.npmjs.org/package/cordova-plugin-ping)

This plugin implements the [`ping` software utility](https://en.wikipedia.org/wiki/Ping_%28networking_utility%29).

## Installation

> cordova plugin add https://github.com/t1st3/cordova-plugin-ping.git

## Usage

This plugin defines a global `ping` object.
Although the object is in the global scope, it is not available until after the `deviceready` event.

### Ping a domain

```js
document.addEventListener('deviceready', onDeviceReady, false);
function onDeviceReady() {
  var p = new ping(['github.com']);
  setTimeout(function () {
    console.log(p.results);
  }, 1000);
}
```

### Ping an IPv4 address

```js
document.addEventListener('deviceready', onDeviceReady, false);
function onDeviceReady() {
  var p = new ping(['192.168.1.1']);
  setTimeout(function () {
    console.log(p.results);
  }, 1000);
}
```

### Ping multiple domains or IP addresses

```js
document.addEventListener('deviceready', onDeviceReady, false);
function onDeviceReady() {
  var p = new ping(['github.com', 'undefineddomain.com', '192.168.1.1']);
  setTimeout(function () {
    console.log(p.results);
  }, 1000);
}
```

## Properties

- ping.results

## ping.results

Get the the results of the`ping`.

Results look like this:

```json
[
  {
    "ip": "github.com",
    "status": "success",
    "avg": 40.131
  },
  {
    "ip": "undefineddomain.com",
    "status": "timeout",
    "avg": 0
  },
  {
    "ip": "192.168.1.1",
    "status": "success",
    "avg": 35.654
  }
]
```

### Supported Platforms

- Android
