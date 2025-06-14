# Wij zijn handig - Static landingpage


Minimal 11ty starter project that build css with tailwindcss cli and [esbuild](https://esbuild.github.io/) for javascript.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/digitalpassenger/wijzijnhandig/)

## Stack

* TailwindCSS v3
* Apline.js v3

## Install

```
npm install
```

## Local dev

```
npm run start
```

## Build

Minified production build

```
npm run build
```

## Assets versioning

This starter includes a small js script to which can add a hash to your assets when building for production builds.
The script will look for files to include a hash (based on the md5 of the built file content) eg: ```styles.734a7607648afdb.css``` instead of ```styles.css```.

The entry point for matching regular file path to versionned path is generated as an 11ty global data object in ```_data/hash.json``` with the simple structure
```js
{
  '/path/to/resource.css': '/path/to/resource.hash.css'
}
```

In your 11ty template, you can then simply retrieve the versioned path from the array ```{{ hash['/path/to/resource.css'] | url }}```

If you want to add other assets to this generated data array, simply include the path in the ```assets``` const in the ```hash.js``` file in the root directory (files listed below are already included).

```js
const assets = [
  '/css/styles.css',
  '/js/scripts.js'
];
```
