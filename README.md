Derby Lang FS
=============

Load a [Derby Lang](https://github.com/psirenny/derby-lang) dictionary from the file system.

[![Build Status](https://travis-ci.org/psirenny/derby-lang-fs.png?branch=master)](https://travis-ci.org/psirenny/derby-lang-fs)

Installation
------------

    $ npm install derby-lang-fs --save

Usage
-----

Add the middleware to your server file:

    var langFs = require('derby-lang-fs');

    expressApp
      // ...
      // ...
      .use(lang())
      .use(langFs({
        dir: '/path/to/dir'
      }))

Options
-------

`dir` — The directory containing the language files.  
`path` — The path to set the dictionary. Defaults to **$lang.dict**.

Example
-------

Folder structure:

    locale/
    +-- en/
      +-- app/
        +-- index.json
    +-- es/
      +-- app/
        +-- index.json

Model output:

    {
      "$lang": {
        "dict": {
          "en": {
            "app": { /* index.json */ }
          },
          "es": {
            "app": { /* index.json */ }
          },
        }
      }
    }
