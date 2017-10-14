# Globalist

Useful stuff about all the countries on earth. 

## Install
```
npm install globalist --save
```

## Overview

Each country in Globalist is represented by an object with the following keys:

- `name`: Common name and native name in parentheses if available.
- `iso2`: 2 character ISO2 code. Lowercase.
- `dial`: International calling code.
- `format`: Telephone format.

## Quick Example

With Globalist, it's easy to make country select input in React.

```jsx
import React from 'react'
import { getCountries } from 'globalist'

const SelectCountry = (props) => 
  <select {...props}>
    {getCountries().map((c) => 
      <option value={c.iso2}>{c.name}</option>
    )}
  </select>

export default SelectCountry
```

## API

### `getCountry(code: string): Country`

Returns a single country by its ISO2 code. 

```js
const { getCountry } = require('globalist')

const hockeyLand = getCountry('ca')

console.log(hockeyLand.name) // => Canada
console.log(hockeyLand.format) // => Canada
```

### `getCountries(): Country[]`

Returns an array of all countries

```js
const { getCountries } = require('globalist')

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
const { countries } = require('globalist')

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

const { iso2Codes } = require('globalist')

console.log(iso2Codes)

/*
['af', 'al', 'dz', 'as', 'ad', 'ao', ... ]
*/
```


## Author

- Jared Palmer ([@jaredpalmer](https://twitter.com/jaredpalmer))


---

MIT LICENSE.