# Javascript Dev Workflow
**Assumes atom_editor.md is completed.**
## Start a new project
### Install Javascript Package Manager
```
npm install --save-dev eslint babel-eslint
jspm init
```

### Example index.html for loading a Javascript app
Assuming your base module is main.js:
```html
  <script src="jspm_packages/system.js"></script>
  <script src="config.js"></script>
  <script>
    System.import('main');
  </script>
```

## TODO: Flow / Nuclide setup
