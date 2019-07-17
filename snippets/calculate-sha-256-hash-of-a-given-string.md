---
title: Calculate SHA-256 Hash of a Given String
date: 2019-07-17
languages: [JavaScript]
description: This snippet uses SubtleCrypto interface to calculate SHA-256 hash of a given string.
---

This snippet uses SubtleCrypto interface to calculate SHA-256 hash of a given string.

## Code

```javascript
const bufferToHex = buffer => {
    return [...new Uint8Array(buffer)]
    .map(x => x.toString(16).padStart(2, "0"))
    .join("");
}

const sha256 = text => {
    let buffer = new TextEncoder().encode(text);
    return crypto.subtle.digest("SHA-256", buffer).then(hash => bufferToHex(hash));
};
```

Example usage:

```javascript
sha256("Hello").then(hash => console.log(hash));
// 185f8db32271fe25f561a6fc938b2e264306ec304eda518007d1764826381969

### Algorithm

How `bufferToHex` function works:
1. Convert buffer to array.
2. Convert each `x` element in an array to a hex string (e.g. `12` becomes `c`).
3. Pad every converted element with zeros (e.g. `c` becomes `0c`).
4. Take all of the hex values and join them into a single string.

How `sha256` function works:
1. Create a buffer from given text.
2. Call `crypto.subtle.digest` function with required parameters. After the returned Promise is resolved, convert the resulting buffer to a hex string.
