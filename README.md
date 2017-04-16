# api documentation for  [cookies (v0.7.0)](https://github.com/pillarjs/cookies#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-cookies.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-cookies) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-cookies.svg)](https://travis-ci.org/npmdoc/node-npmdoc-cookies)
#### Cookies, optionally signed using Keygrip.

[![NPM](https://nodei.co/npm/cookies.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/cookies)

[![apidoc](https://npmdoc.github.io/node-npmdoc-cookies/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-cookies/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-cookies/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-cookies/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Jed Schmidt",
        "url": "http://jed.is"
    },
    "bugs": {
        "url": "https://github.com/pillarjs/cookies/issues"
    },
    "contributors": [
        {
            "name": "Douglas Christopher Wilson"
        }
    ],
    "dependencies": {
        "depd": "~1.1.0",
        "keygrip": "~1.0.1"
    },
    "description": "Cookies, optionally signed using Keygrip.",
    "devDependencies": {
        "express": "4.9.8",
        "istanbul": "0.4.5",
        "mocha": "2.5.3",
        "restify": "2.8.1",
        "supertest": "1.1.0"
    },
    "directories": {},
    "dist": {
        "shasum": "0bc961d910c35254980fc7c9eff5da12011bbf00",
        "tarball": "https://registry.npmjs.org/cookies/-/cookies-0.7.0.tgz"
    },
    "engines": {
        "node": ">= 0.8"
    },
    "files": [
        "HISTORY.md",
        "LICENSE",
        "README.md",
        "index.js"
    ],
    "gitHead": "c582e55ef687d869ddfb50fa6cde4598164ed00e",
    "homepage": "https://github.com/pillarjs/cookies#readme",
    "license": "MIT",
    "maintainers": [
        {
            "name": "dougwilson"
        },
        {
            "name": "fishrock123"
        },
        {
            "name": "jed"
        },
        {
            "name": "jongleberry"
        }
    ],
    "name": "cookies",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/pillarjs/cookies.git"
    },
    "scripts": {
        "test": "mocha --require test/support/env --reporter spec --bail --check-leaks test/",
        "test-ci": "istanbul cover node_modules/mocha/bin/_mocha --report lcovonly -- --require test/support/env --reporter spec --check-leaks test/",
        "test-cov": "istanbul cover node_modules/mocha/bin/_mocha -- --require test/support/env --reporter dot --check-leaks test/"
    },
    "version": "0.7.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module cookies](#apidoc.module.cookies)
1.  [function <span class="apidocSignatureSpan"></span>cookies (request, response, options)](#apidoc.element.cookies.cookies)
1.  [function <span class="apidocSignatureSpan">cookies.</span>Cookie (name, value, attrs)](#apidoc.element.cookies.Cookie)
1.  [function <span class="apidocSignatureSpan">cookies.</span>connect (keys)](#apidoc.element.cookies.connect)
1.  [function <span class="apidocSignatureSpan">cookies.</span>express (keys)](#apidoc.element.cookies.express)
1.  [function <span class="apidocSignatureSpan">cookies.</span>toString ()](#apidoc.element.cookies.toString)
1.  object <span class="apidocSignatureSpan">cookies.</span>Cookie.prototype

#### [module cookies.Cookie](#apidoc.module.cookies.Cookie)
1.  [function <span class="apidocSignatureSpan">cookies.</span>Cookie (name, value, attrs)](#apidoc.element.cookies.Cookie.Cookie)

#### [module cookies.Cookie.prototype](#apidoc.module.cookies.Cookie.prototype)
1.  boolean <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>httpOnly
1.  boolean <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>overwrite
1.  boolean <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>sameSite
1.  boolean <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>secure
1.  [function <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>toHeader ()](#apidoc.element.cookies.Cookie.prototype.toHeader)
1.  [function <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>toString ()](#apidoc.element.cookies.Cookie.prototype.toString)
1.  string <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>path
1.  undefined <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>domain



# <a name="apidoc.module.cookies"></a>[module cookies](#apidoc.module.cookies)

#### <a name="apidoc.element.cookies.cookies"></a>[function <span class="apidocSignatureSpan"></span>cookies (request, response, options)](#apidoc.element.cookies.cookies)
- description and source-code
```javascript
function Cookies(request, response, options) {
  if (!(this instanceof Cookies)) return new Cookies(request, response, options)

  this.secure = undefined
  this.request = request
  this.response = response

  if (options) {
    if (Array.isArray(options)) {
      // array of key strings
      deprecate('"keys" argument; provide using options {"keys": [...]}')
      this.keys = new Keygrip(options)
    } else if (options.constructor && options.constructor.name === 'Keygrip') {
      // any keygrip constructor to allow different versions
      deprecate('"keys" argument; provide using options {"keys": keygrip}')
      this.keys = options
    } else {
      this.keys = Array.isArray(options.keys) ? new Keygrip(options.keys) : options.keys
      this.secure = options.secure
    }
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.cookies.Cookie"></a>[function <span class="apidocSignatureSpan">cookies.</span>Cookie (name, value, attrs)](#apidoc.element.cookies.Cookie)
- description and source-code
```javascript
function Cookie(name, value, attrs) {
  if (!fieldContentRegExp.test(name)) {
    throw new TypeError('argument name is invalid');
  }

  if (value && !fieldContentRegExp.test(value)) {
    throw new TypeError('argument value is invalid');
  }

  value || (this.expires = new Date(0))

  this.name = name
  this.value = value || ""

  for (var name in attrs) {
    this[name] = attrs[name]
  }

  if (this.path && !fieldContentRegExp.test(this.path)) {
    throw new TypeError('option path is invalid');
  }

  if (this.domain && !fieldContentRegExp.test(this.domain)) {
    throw new TypeError('option domain is invalid');
  }

  if (this.sameSite && this.sameSite !== true && !sameSiteRegExp.test(this.sameSite)) {
    throw new TypeError('option sameSite is invalid')
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.cookies.connect"></a>[function <span class="apidocSignatureSpan">cookies.</span>connect (keys)](#apidoc.element.cookies.connect)
- description and source-code
```javascript
connect = function (keys) {
  return function(req, res, next) {
    req.cookies = res.cookies = new Cookies(req, res, {
      keys: keys
    })

    next()
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.cookies.express"></a>[function <span class="apidocSignatureSpan">cookies.</span>express (keys)](#apidoc.element.cookies.express)
- description and source-code
```javascript
express = function (keys) {
  return function(req, res, next) {
    req.cookies = res.cookies = new Cookies(req, res, {
      keys: keys
    })

    next()
  }
}
```
- example usage
```shell
...

A [Keygrip](https://www.npmjs.com/package/keygrip) object or an array of keys can optionally be passed as _options.keys_ to enable
 cryptographic signing based on SHA1 HMAC, using rotated credentials.

A Boolean can optionally be passed as _options.secure_ to explicitally specify if the connection is secure, rather than this module
 examining _request_.

Note that since this only saves parameters without any other processing, it is very lightweight. Cookies are only parsed on demand
 when they are accessed.

### express.createServer( Cookies.express( keys ) )

This adds cookie support as a Connect middleware layer for use in Express apps, allowing inbound cookies to be read using 'req.cookies
.get' and outbound cookies to be set using 'res.cookies.set'.

### cookies.get( name, [ options ] )

This extracts the cookie with the given name from the 'Cookie' header in the request. If such a cookie exists, its value is returned
. Otherwise, nothing is returned.
...
```

#### <a name="apidoc.element.cookies.toString"></a>[function <span class="apidocSignatureSpan">cookies.</span>toString ()](#apidoc.element.cookies.toString)
- description and source-code
```javascript
toString = function () {
    return toString;
}
```
- example usage
```shell
...
  cookie.secure = opts.secureProxy
}

headers = pushCookie(headers, cookie)

if (opts && signed) {
  if (!this.keys) throw new Error('.keys required for signed cookies');
  cookie.value = this.keys.sign(cookie.toString())
  cookie.name += ".sig"
  headers = pushCookie(headers, cookie)
}

var setHeader = res.set ? http.OutgoingMessage.prototype.setHeader : res.setHeader
setHeader.call(res, 'Set-Cookie', headers)
return this
...
```



# <a name="apidoc.module.cookies.Cookie"></a>[module cookies.Cookie](#apidoc.module.cookies.Cookie)

#### <a name="apidoc.element.cookies.Cookie.Cookie"></a>[function <span class="apidocSignatureSpan">cookies.</span>Cookie (name, value, attrs)](#apidoc.element.cookies.Cookie.Cookie)
- description and source-code
```javascript
function Cookie(name, value, attrs) {
  if (!fieldContentRegExp.test(name)) {
    throw new TypeError('argument name is invalid');
  }

  if (value && !fieldContentRegExp.test(value)) {
    throw new TypeError('argument value is invalid');
  }

  value || (this.expires = new Date(0))

  this.name = name
  this.value = value || ""

  for (var name in attrs) {
    this[name] = attrs[name]
  }

  if (this.path && !fieldContentRegExp.test(this.path)) {
    throw new TypeError('option path is invalid');
  }

  if (this.domain && !fieldContentRegExp.test(this.domain)) {
    throw new TypeError('option domain is invalid');
  }

  if (this.sameSite && this.sameSite !== true && !sameSiteRegExp.test(this.sameSite)) {
    throw new TypeError('option sameSite is invalid')
  }
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.cookies.Cookie.prototype"></a>[module cookies.Cookie.prototype](#apidoc.module.cookies.Cookie.prototype)

#### <a name="apidoc.element.cookies.Cookie.prototype.toHeader"></a>[function <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>toHeader ()](#apidoc.element.cookies.Cookie.prototype.toHeader)
- description and source-code
```javascript
toHeader = function () {
  var header = this.toString()

  if (this.maxAge) this.expires = new Date(Date.now() + this.maxAge);

  if (this.path     ) header += "; path=" + this.path
  if (this.expires  ) header += "; expires=" + this.expires.toUTCString()
  if (this.domain   ) header += "; domain=" + this.domain
  if (this.sameSite ) header += "; samesite=" + (this.sameSite === true ? 'strict' : this.sameSite.toLowerCase())
  if (this.secure   ) header += "; secure"
  if (this.httpOnly ) header += "; httponly"

  return header
}
```
- example usage
```shell
...
)
}

function pushCookie(cookies, cookie) {
if (cookie.overwrite) {
  cookies = cookies.filter(function(c) { return c.indexOf(cookie.name+'=') !== 0 })
}
cookies.push(cookie.toHeader())
return cookies
}

Cookies.connect = Cookies.express = function(keys) {
return function(req, res, next) {
  req.cookies = res.cookies = new Cookies(req, res, {
    keys: keys
...
```

#### <a name="apidoc.element.cookies.Cookie.prototype.toString"></a>[function <span class="apidocSignatureSpan">cookies.Cookie.prototype.</span>toString ()](#apidoc.element.cookies.Cookie.prototype.toString)
- description and source-code
```javascript
toString = function () {
  return this.name + "=" + this.value
}
```
- example usage
```shell
...
  cookie.secure = opts.secureProxy
}

headers = pushCookie(headers, cookie)

if (opts && signed) {
  if (!this.keys) throw new Error('.keys required for signed cookies');
  cookie.value = this.keys.sign(cookie.toString())
  cookie.name += ".sig"
  headers = pushCookie(headers, cookie)
}

var setHeader = res.set ? http.OutgoingMessage.prototype.setHeader : res.setHeader
setHeader.call(res, 'Set-Cookie', headers)
return this
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
