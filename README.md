# Chainpoint Proof v3 JSON Schema Validator

[![npm version](https://badge.fury.io/js/chainpoint-proof-json-schema.svg)](https://badge.fury.io/js/chainpoint-proof-json-schema)

A simple npm package to validate a Chainpoint v3 Proof, in JSON format, against a JSON Schema (Draft 04).

Take a look here to learn more about [https://chainpoint.org](https://chainpoint.org)

## IMPORTANT

This package does *not* validate that the hashes in a proof are valid up to an anchor (e.g. BTC, ETH). In fact this package doesn't know what a hash is! It only validates that the proof you provide it with is a well formed proof according to its schema. Nothing more, nothing less.

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

Note : You can copy `docs/bundle.js` into your app to include in a script tag, or use the [http://rawgit.com/](http://rawgit.com/) CDN version (make sure the Git commit SHA1 in the URL is current). Rawgit is a free service and makes no guarantees for uptime.

```
  <script src="https://cdn.rawgit.com/chainpoint/chainpoint-proof-json-schema/495732a06654615f2b2d4c5716c59f769a99d3c2/docs/bundle.js"></script>

```

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
