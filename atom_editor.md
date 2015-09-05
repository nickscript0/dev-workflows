# Atom Editor First Time Setup
## Install core tools from brew
```bash
brew update
brew upgrade git
brew install npm
```

## Install editor and packages
1. Install Atom.io
2. Install packages: 
```bash
apm install atom-beautify
apm install language-docker
apm install language-elm
apm install linter
apm install linter-eslint
apm install linter-js-yaml
apm install linter-pylint
```

## Install npm dependencies for Atom packages
```bash
# Javascript related
npm install jspm -g # for js package management and es6 dev (babel)
## Must run the following per project: (as the atom eslint package doesn't work with global install ??)
npm install --save-dev eslint babel-eslint


# Other languages
pip install --upgrade pylint # linter-pylint
pip install --upgrade autopep8 # beautify (python)
npm install --global elm
```
