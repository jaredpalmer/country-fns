
# country-fns

Useful country data for forms and stuff.

## Install
```
npm install country-fns --save
```

## Overview

Each country in country-fns is represented by an object with the following keys:

- `name`: Common name and native name in parentheses if available.
- `iso2`: 2 character ISO2 code. Lowercase.
- `dial`: International calling code.
- `format`: Telephone format.

## Quick Example

Imagine you need to make a "Select Country" input.

```jsx
import React from 'react'
import { getCountries } from 'country-fns'

const SelectCountry = (props) => 
  <select {...props}>
    {getCountries().map((c) => 
      <option value={c.iso2}>{c.name}</option>
    )}
  </select>

export default SelectCountry
```

#### Other use cases

- Intelligent telephone placeholder and input masks
- Telephone number validation
- Localized `tel:` and `sms:` `<a>` elements
- Other annoying stuff I never want to lookup again.

## API

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [API](#api)
  - [`getCountry(code: string): Country`](#getcountrycode-string-country)
  - [`getCountries(): Country[]`](#getcountries-country)
  - [`countries = { [code: string]: Country }`](#countries---code-string-country-)
  - [`iso2Codes = string[]`](#iso2codes--string)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

### `getCountry(code: string): Country`

Returns a single country by its ISO2 code. 

```js
const { getCountry } = require('country-fns')

const hockeyLand = getCountry('ca')

console.log(hockeyLand.name) // => Canada
console.log(hockeyLand.format) // => Canada
```

### `getCountries(): Country[]`

Returns an array of all countries

```js
const { getCountries } = require('country-fns')

const allCountries = getCountries()

console.log(allCountries)

/*
[
   {
    name: 'Afghanistan (‫افغانستان‬‎)',
    iso2: 'af',
    dial: '93',
    format: '+..-..-...-....',
  },
   {
    name: 'Albania (Shqipëri)',
    iso2: 'al',
    dial: '355',
    format: '+...(...)...-...',
  },
  {
    name: 'Algeria (‫الجزائر‬‎)',
    iso2: 'dz',
    dial: '213',
    format: '+...-..-...-....',
  },
  ...
]
*/
```
### `countries = { [code: string]: Country }`

An object containing all countries, keyed by lowercase ISO2 code.

```js
const { countries } = require('country-fns')

console.log(countries)

/*
{
  af: {
    name: 'Afghanistan (‫افغانستان‬‎)',
    iso2: 'af',
    dial: '93',
    format: '+..-..-...-....',
  },
  al: {
    name: 'Albania (Shqipëri)',
    iso2: 'al',
    dial: '355',
    format: '+...(...)...-...',
  },
  dz: {
    name: 'Algeria (‫الجزائر‬‎)',
    iso2: 'dz',
    dial: '213',
    format: '+...-..-...-....',
  },

  ...
}
*/

```

### `iso2Codes = string[]`

An array of all ISO2 Codes (lowercase).

```js

const { iso2Codes } = require('country-fns')

console.log(iso2Codes)

/*
['af', 'al', 'dz', 'as', 'ad', 'ao', ... ]
*/
```


## Author

- Jared Palmer ([@jaredpalmer](https://twitter.com/jaredpalmer))


---

MIT LICENSE.