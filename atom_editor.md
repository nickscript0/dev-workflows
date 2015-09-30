# Atom Editor First Time Setup
## Install core tools from brew
```bash
brew update
brew upgrade git
brew install npm
brew install python
# The following command links formulae with .app style packages to /Applications
# which adds IDLE to the app list and makes it startable from the Mac OS X GUI
brew linkapps python 
```

## Install editor and packages
1. Install Atom.io
2. Install packages: 
```bash
apm install atom-beautify
apm install language-docker
apm install language-elm # Autocomplete requires config step: https://atom.io/packages/language-elm
apm install linter
apm install linter-eslint
apm install linter-js-yaml
apm install linter-pylint
apm install linter-elm-make # Requires config step: https://atom.io/packages/linter-elm-make
```

## Install npm dependencies for Atom packages
```bash
# Javascript related
npm install jspm -g # for js package management and es6 dev (babel)
## Must run the following per project: (as the atom eslint package doesn't work with global install ??)
npm install --save-dev eslint babel-eslint


# Python related
pip install --upgrade pylint # linter-pylint
pip install --upgrade autopep8 # beautify (python)

# Elm related
npm install --global elm
npm install -g elm-oracle # For autocomplete https://atom.io/packages/language-elm

```
