---
title: Calculate SHA-256 from a Given String
modified: 2019-04-15
language: JavaScript
scripts: [precode_selector.js]
description: This snippet calculates SHA-256 hash from a given string using native SubtleCrypto interface.
---

This snippet calculates SHA-256 hash from a given string using native SubtleCrypto interface.

```javascript
const sha256 = str => {
    let buffer = new TextEncoder().encode(str);
    return crypto.subtle.digest("SHA-256", buffer).then(hash => toHex(new Uint8Array(hash)));
};

const toHex = bytes => bytes.reduce((str, byte) => (str + byte.toString(16).padStart(2, "0")), "");
```