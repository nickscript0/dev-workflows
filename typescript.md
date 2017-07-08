# Typescript Project

## Upgrade to latest
### Check tslint is up to date (better to use a project version but here are steps to do it globally)
```bash
npm list -g --depth=0 | grep "tslint\|typescript"
# Visual Studio Code uses a builtin Typescript compiler but tslint needs a commandline version
npm update -g typescript tslint 
```

## Init a new project
### Step 1
```bash
tslint --init # Required otherwise tslint VSC plugin silently doesn't work for the project
```

### Step 2 - tsconfig.json
In VSC save a file called tsconfig.json. Intellisense will then help you fill it out, a barebones version looks
```json
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "sourceMap": true
    }
}
```

### Step 3 - auto-compilation
The next step is to set up the task configuration. 
To do this open the Command Palette with ⇧⌘P and type in Configure Task Runner,
Select "Typescript - Watch Mode"

## Modules and Imports
### Installing npm modules and corresponding Type Definitions
Lookup Type Definitions here https://microsoft.github.io/TypeSearch/

```bash
# Example for React Native
npm install --save react react-native
npm install --save @types/react @types/react-native
```

### Importing an npm module in a Typescript file
- Module resolution uses similar rules to Node.js' require (https://www.typescriptlang.org/docs/handbook/module-resolution.html#node)

- Import statement docs https://www.typescriptlang.org/docs/handbook/module-resolution.html#relative-vs-non-relative-module-imports.

Import examples:
```bash
# Non-relative import (from an npm module)
import * as moment from "moment";

# Relative import
import * as mymodule from "./lib/mymodule";
```
