# http-traceroute

A command line tool for following and showing HTTP redirects for a given
URL. Similar to the `traceroute` unix tool. Forked from original to support
authenticated requests.

![screen shot 2016-02-22 at 12 43 13](https://cloud.githubusercontent.com/assets/10602/13217317/ec317342-d961-11e5-9810-9773569387e0.png)

[![Build status](https://travis-ci.org/watson/http-traceroute.svg?branch=master)](https://travis-ci.org/watson/http-traceroute)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat)](https://github.com/feross/standard)

## Installation

Install globally as a CLI:

```
npm install http-traceroute -g
```

Install as a module:

```
npm install --save http-traceroute
```

## CLI Usage

```
http-traceroute [url] [authorization header value]
```

## Module Usage

```js
var TraceRoute = require('http-traceroute')
```

```js
var trace = new TraceRoute('https://github.com', 'Bearer BLAHBLAHBLAHBLAH')

trace.on('readable', function () {
  var hop = null
  while (hop = this.read()) {
    console.log(hop)
  }
})

trace.on('error', function () {})
trace.on('end', function () {})
```

## License

MIT
