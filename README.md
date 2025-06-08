# read-catalogue

This is a directory that can read all files and can be written to a file

# Usage

install with npm

```js
npm i read-catalogue
```

How is it used in nod Note that this tool only supports commonjs environments

```js
// load using commonjs
import { readCatalogue } from "read-catalogue";
const { readCatalogue } = require("read-catalogue");

//Basic tool Usage By default, it looks for all js currently nested 5 levels

//Note that the absolute path of patn.resolve is used for the first and second arguments

// The file location to look for
const findPosition = path.resolve(__dirname, "../typescript");
// File location to write to
const writingPosition = path.resolve(__dirname, "../TypeScrpit.js");

readCatalogue(findPosition, writingPosition);

//You can also configure optopns to use the.ext suffix to find the files you need
readCatalogue(findPosition, writingPosition, { ext: ".ts" });

//You can also configure to enable sorting
readCatalogue(findPosition, writingPosition, { sort: true });

//It is also possible to configure the level of nesting to look for.The default is five levels
readCatalogue(findPosition, writingPosition, { hierarchy: 3 });

//It is also possible to configure the exclusion of some files, passing in a regex
readCatalogue(findPosition, writingPosition, { exclude: /\.d\.ts$/ });

//It is also possible to configure folders to be excluded by passing a folder name, which defaults to node_modules
readCatalogue(findPosition, writingPosition, { overlookFile: "node_modules" });
```

# Command Line Interface

```js
It can be installed globally using npm i-g read-catalogue or locally using npm i read-catalogue

Usage:

  readCatalogue [findFilePath] [options]

Options:

  -w --write The destination file path

  -e --ext The file extension to look for The default value is.md file

  --excl The file name to exclude
```
