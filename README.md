# React Virtualized Select

![NPM version](https://img.shields.io/npm/v/react-virtualized-select.svg?style=flat)
![NPM license](https://img.shields.io/npm/l/react-virtualized-select.svg?style=flat)
![NPM total downloads](https://img.shields.io/npm/dt/react-virtualized-select.svg?style=flat)
![NPM monthly downloads](https://img.shields.io/npm/dm/react-virtualized-select.svg?style=flat)
[![Circle CI badge](https://img.shields.io/circleci/project/bvaughn/react-virtualized-select/master.svg?style=flat)](https://circleci.com/gh/bvaughn/react-virtualized-select)
[![Codecov badge](https://img.shields.io/codecov/c/github/bvaughn/react-virtualized-select/master.svg)](https://codecov.io/github/bvaughn/react-virtualized-select)
[![PayPal donate button](https://img.shields.io/badge/paypal-donate-lightgray.svg?style=flat)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5CVMYQKVPZC72)
[![Patreon donate button](https://img.shields.io/badge/patreon-donate%20once-lightgray.svg?style=flat)](https://www.patreon.com/user?u=2979769)

### Demos available here: http://bvaughn.github.io/react-virtualized-select/

Getting started
---------------

Install `react-virtualized-select` using npm.

```shell
npm install react-virtualized-select --save
```

ES6, CommonJS, and UMD builds are available with each distribution.
For example:

```js
// Make sure to import default styles.
// This only needs to be done once; probably during your application's bootstrapping process.
import 'react-select/dist/react-select.css';
import 'react-virtualized/styles.css';
import 'react-virtualized-select/styles.css';

// Then import the virtualized Select HOC
import VirtualizedSelect from 'react-virtualized-select';
```

Alternately you can load a global-friendly UMD build:

```html
<link rel="stylesheet" href="path-to-react-virtualized-select/styles.css">
<script src="path-to-react-virtualized-select/dist/umd/react-virtualized-select.js"></script>
```

From there one, _react-select-virtualized_ works just like _react-select_. You pass it an array of options, along with any other parameters supported by the [select component](https://github.com/JedWatson/react-select/#usage).

The additional parameters introduced by _react-select-virtualized_ are optional. They are:

| Property | Type | Description |
|:---|:---|:---|
| maxHeight | `PropTypes.number` | Max height of options menu; defaults to 200 pixels. |
| optionHeight | `PropTypes.number` | Option height; defaults to 35 pixels. |
| optionRenderer | `PropTypes.func` | Custom option renderer; (see below for signature). |

## Custom Option Renderer

You can override the built-in option renderer by specifying your own `optionRenderer` property. Your renderer should return a React element that represents the specified option. It will be passed the following named parameters:

| Property | Type | Description |
|:---|:---|:---|
| focusedOption | `PropTypes.object` | The option currently-focused in the dropdown. Use this property to determine if your rendered option should be highlighted or styled differently. |
| focusedOptionIndex | `PropTypes.number` | Index of the currently-focused option. |
| focusOption | `PropTypes.func` | Callback to update the focused option; for example, you may want to call this function on mouse-over. |
| labelKey | `PropTypes.string` | Attribute of option that contains the display text. |
| option | `PropTypes.object` | The option to be rendered. |
| options | `PropTypes.arrayOf(PropTypes.object)` | Array of options (objects) contained in the select menu. |
| selectValue | `PropTypes.func` | Callback to update the selected values; for example, you may want to call this function on click. |
| valueArray | `PropTypes.arrayOf(PropTypes.object)` | Array of the currently-selected options. Use this property to determine if your rendered option should be highlighted or styled differently. |
