# eslint-plugin-richlab

The custom rules created by richlab

## Installation

You'll first need to install [ESLint](http://eslint.org):

```
$ npm i eslint --save-dev
```

Next, install `eslint-plugin-richlab`:

```
$ npm install eslint-plugin-richlab --save-dev
```

**Note:** If you installed ESLint globally (using the `-g` flag) then you must also install `eslint-plugin-richlab` globally.

## Usage

Add `richlab` to the plugins section of your `.eslintrc` configuration file. You can omit the `eslint-plugin-` prefix:

```json
{
    "plugins": [
        "richlab"
    ]
}
```


Then configure the rules you want to use under the rules section.

```json
{
    "rules": {
        "richlab/rule-name": 2
    }
}
```

## Supported Rules

### `avoid-ios9-viewport-bug`

`window.innerWidth` and `window.innerHeight` may have unexpected value in iOS9
Mobile Saferi because [the bug](https://forums.developer.apple.com/thread/13510).
This rule resticts to use `window.innerWidth` and `window.innerHeight` and
recommends to use `document.documentElement.clientWidth` or `document.Element.clientHeight`
instead of that properties.

```javascript
var innerWidth = window.innerWidth; // error
var innerHeight = window.innerHeight; // error

var innerWidth = document.documentElement.clientWidth; // not error
var innerHeight = document.documentElement.clientHeight; // not error
```
