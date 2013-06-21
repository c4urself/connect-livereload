connect-livereload
==================
connect middleware for adding the livereload script to the response.
no browser plugin is needed.
if you are happy with a browser plugin, then you don't need this middleware.

[![Build Status](https://travis-ci.org/intesso/connect-livereload.png)](https://travis-ci.org/intesso/connect-livereload)
[![NPM version](https://badge.fury.io/js/connect-livereload.png)](http://badge.fury.io/js/connect-livereload)
install
=======
```bash
npm install connect-livereload --save-dev
```

use
===
this middleware can be used with a LiveReload server e.g. [grunt-reload](https://github.com/webxl/grunt-reload) or [grunt-contrib-watch](https://github.com/gruntjs/grunt-contrib-watch).

In your connect or express application add this after the static and before the dynamic routes.
If you need liveReload on static html files, then place it before the static routes.
The `excludeList` gives you the possibility to exclude certain files or url's from being handled by `connect-livereload`.

```javascript
  var liveReloadPort = 35729;
  var excludeList = ['.woff', '.flv'];

  app.use(require('connect-livereload')({
    port: liveReloadPort,
    excludeList: excludeList
  }));
```

please see the [examples](https://github.com/intesso/connect-livereload/tree/master/examples) for the app and Grunt configuration.

grunt
=====

For use as middleware in grunt simply add the following to the **top** of your array of middleware.

```javascript
  require('connect-livereload')(),
```

You can pass in options to this call if you do not want the defaults.

alternative
===========
An alternative would be to install the [LiveReload browser plugin](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei).


credits
=======
* The middleware code is mainly extracted from: [grunt-contrib-livereload/util.js](https://github.com/gruntjs/grunt-contrib-livereload/blob/master/lib/utils.js)
* [LiveReload Creator](http://livereload.com/)

tests
=====
run the tests with
```
mocha
```

license
=======
[MIT License](https://github.com/intesso/connect-livereload/blob/master/LICENSE)
