# fxa-common-password-list

Check whether a password is common.

## Installation:
> npm install fxa-common-password-list

## Usage:
```js
const commonPassworList = require('fxa-common-password-list');

// returns true
commonPassworList.test('password');

// returns false
commonPasswordList.test('@!#^GDSAQ@#^Q#@^$YAESFDAS');
```

## Tagging a release

One command to do it all:

> npm version &lt;version&gt;

* Creates a release branch
* Updates version number in package.json, package-lock.json
* Updates CHANGELOG.md
* Commits changes
* Creates a tag
* Pushes release branch and tag to origin

## Generating bloomfilter data
Bloom filter data can be generated from a list
of passwords. The input list is expected to be
sorted from most to least common, one password
per line. The output file is a JSON file
that can be included in `./src/passwordcheck.js`

> node scripts/plaintext2bloom.js ./source_data/10_million_password_list_top_1M.txt ./src/bloomdata-top-10k 10000

## License:
MPL-2.0

