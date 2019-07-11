---
title: Calculate SHA-256 Hash of a Given String
date: 2019-07-11
languages: [JavaScript]
scripts: [relative_date.js, code_selector.js]
styles: [prism.css]
description: This snippet uses SubtleCrypto interface to calculate SHA-256 hash of a given string.
---

This snippet uses SubtleCrypto interface to calculate SHA-256 hash of a given string.

```javascript
const sha256 = str => {
    let buffer = new TextEncoder().encode(str);
    return crypto.subtle.digest("SHA-256", buffer).then(hash => toHex(new Uint8Array(hash)));
};

const toHex = bytes => bytes.reduce((str, byte) => (str + byte.toString(16).padStart(2, "0")), "");
```