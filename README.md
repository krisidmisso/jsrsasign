nativescript-jsrsasign
=========

#### This repo is forked only for showing implementation of RSA encryption on {N} Nativescript (Since I couldn't find any sample)

## Installation
```
npm install jsrsasign
```
## Usage in {N} Angular
#### Import Lib in your .ts:
```
import { KJUR, KEYUTIL } from 'jsrsasign';
```
#### Declare Private and Public keys (NOT SECURE - Only for testing purposes):

```
const pub = `-----BEGIN PUBLIC KEY-----

            CONTENT OF YOUR PUBLIC KEY

            -----END PUBLIC KEY-----`;

const prv = `-----BEGIN RSA PRIVATE KEY-----

            CONTENT OF YOUR PRIVATE KEY

            -----END RSA PRIVATE KEY-----`;
```

#### Import/Convert keys to object:
```
let pvKey = KEYUTIL.getKey(prv,'your passphrase'); // remove passphrase ("your passphrase") if not any
let pbKey = KEYUTIL.getKey(pub);
```
[KEYUTIL DOCUMENTATION](https://kjur.github.io/jsrsasign/api/symbols/KEYUTIL.html)

#### Encrypt message:
```
console.log('encrypted: ' + KJUR.crypto.Cipher.encrypt('YOUR MESSAGE STRING', pbKey, 'RSAOAEP'));    
```
[KJUR.crypto.Cipher DOCUMENTATION](https://kjur.github.io/jsrsasign/api/symbols/KJUR.crypto.Cipher.html)

#### Decrypt message:
```
console.log('dec: ' + KJUR.crypto.Cipher.decrypt(msg, pvKey, 'RSAOAEP'))
```
[KJUR.crypto.Cipher DOCUMENTATION](https://kjur.github.io/jsrsasign/api/symbols/KJUR.crypto.Cipher.html)



[![license](https://img.shields.io/badge/license-MIT-green.svg?style=flat)](https://github.com/kjur/jsrsasign/blob/master/LICENSE.txt)
[![bower](https://img.shields.io/bower/v/jsrsasign.svg?maxAge=2592000)](https://libraries.io/bower/jsrsasign)
[![npm version](https://badge.fury.io/js/jsrsasign.svg)](https://badge.fury.io/js/jsrsasign)
[![CDNJS](https://img.shields.io/cdnjs/v/jsrsasign.svg)](https://cdnjs.com/libraries/jsrsasign)

The 'jsrsasign' (RSA-Sign JavaScript Library) is an opensource free cryptography library supporting RSA/RSAPSS/ECDSA/DSA signing/validation, ASN.1, PKCS#1/5/8 private/public key, X.509 certificate, CRL, OCSP, CMS SignedData, TimeStamp, CAdES JSON Web Signature/Token/Key in pure JavaScript.

Public page is https://kjur.github.io/jsrsasign .

Your bugfix and pull request contribution are always welcomed :)
