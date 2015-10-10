# Javascript Dev Workflow
**Assumes atom_editor.md is completed.**
## Start a new project
### Install Javascript Package Manager and ES6 support
```
npm install --save-dev eslint babel-eslint

# The following step is required specifically for "parser": "babel-eslint"
curl https://raw.githubusercontent.com/nickscript0/dev-workflows/master/dot_rc_files/.eslintrc > .eslintrc
jspm init

# Install dependencies
jspm install github:lhorie/mithril.js
```

### Example index.html for loading a Javascript app (called main.js)
```html
  <script src="jspm_packages/system.js"></script>
  <script src="config.js"></script>
  <script>
    System.import('main');
  </script>
```

### Example main.js imports
```js
import m from "lhorie/mithril.js";
```

## Flow (using Atom Nuclide)
### First time setup
```bash
brew install flow
apm install nuclide-installer

# Start the server
flow
```

### Per project setup
```bash
flow init
# Add /* @flow */ to the top of files to type check
```

