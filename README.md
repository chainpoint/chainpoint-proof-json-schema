# IMPORTANT

The package is for the Chainpont v4 proof schema. If you're looking to validate proofs schemas from the older Chainpoint V3 Network (chainpoint-services), use version 1.1.0.

This package does _not_ validate that the hashes in a proof are valid up to an anchor (e.g. BTC, ETH). In fact this package doesn't know what a hash is! It only validates that the proof you provide it with is a well formed proof according to its schema. Nothing more, nothing less.

# Chainpoint Proof v4 JSON Schema Validator

[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

[![npm version](https://badge.fury.io/js/chainpoint-proof-json-schema.svg)](https://badge.fury.io/js/chainpoint-proof-json-schema)

A simple npm package to validate a Chainpoint v4 Proof, in JSON format, against a JSON Schema (Draft 04).

Take a look here to learn more about [https://chainpoint.org](https://chainpoint.org)

## Learn More About JSON Schema:

[http://json-schema.org/](http://json-schema.org/)

[https://spacetelescope.github.io/understanding-json-schema/index.html](https://spacetelescope.github.io/understanding-json-schema/index.html)

## Usage

### Node.js

```
yarn add chainpoint-proof-json-schema
```

```
const chainpointProofSchema = require('chainpoint-proof-json-schema')
let objectToValidate = {}
let res = chainpointProofSchema.validate(objectToValidate)

// {valid: true, errors: null}
if (res.valid) {
    console.log('valid')
} else {
    console.log(res.errors)
}
```

### Browser

You can copy `docs/bundle.js` into your app to include in a script tag.

Or install the npm package in a place available to your web pages and set the script `src` tag to something like the following. A window global function `chainpointProofSchema.validate()` will be available and operate the same as the Node.js example above.

```
<script src="./node_modules/chainpoint-proof-json-schema/docs/bundle.js">

```

## Development

### Test

```
yarn test
```

### Browser Packaging

Will store a browserify bundle to `docs/bundle.js` which can also be used
from directly within the `<script>` tag in an HTML page.

```
yarn bundle
```

### Open a local copy of the test page in your browser after bundling

```
yarn browser
```
