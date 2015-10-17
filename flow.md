# [Flow](http://flowtype.org/)
Nuclide is too heavyweight and takes forever to startup Atom, instead use https://atom.io/packages/linter-flow
## First time setup
```bash
brew install flow
apm install linter-flow

# Start the server
flow
```

## Per project setup
```bash
flow init
# Add /* @flow */ to the top of files to type check
```

## Flow limitations I ran into (Updated Oct. 16, 2015)
### JSPM and ES6 imports
- Does not support external JSPM ES6 imports, e.g., ```import m from "lhorie/mithril.js";``` gives "Required module not found". 
 **Workaround**: add ```module.name_mapper= 'lhorie/mithril.js' -> 'mithril'``` to .flowconfig [options] and run ```npm install --save-dev mithril``` (because flow looks in node_modules/package_name)
- Only supports relative local ES6 imports, e.g., ```import {m} from "models/mymodel"``` must be written as ```import {m} from "./models/mymodel"```

### Getters and Setters
Only "unsafely" supports getters/setters https://github.com/facebook/flow/issues/444

### Autobinding ES6 class methods
Because ES6 class methods aren't lexically bound to this, I regularly have to do this using one of 2 ways: (1) manually bind to this or (2) autobind with es7 property initializers and an arrow function. The former causes a flowtype error/warning, the latter is not supported (see https://github.com/facebook/flow/pull/861):

1. In the constructor ```this.someMethod = this.someMethod.bind(this);```
  - **Workaround**:
  ```javascript
  class C {
    myBoundMethod: Function;
    
    constructor() {
      this.myBoundMethod = this.myBoundMethod.bind(this);
    }
    
    myBoundMethod() {
    }
  }
  ```
1. Or more cleanly auto-bind class properties (requires es7.classProperties enabled in Babel config) ```someMethod = () => {...}```
