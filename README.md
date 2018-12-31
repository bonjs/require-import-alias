# require-import-alias
### A tool which could set an alias for the module's path which is required in the require of nodejs     or import of ES6

It's the alias of `require-alias-node`

#### Install
~~~bash
npm install require-import-alias
~~~

Sometimes, we may use a module with a long path to be required, and the path may contain many level, is's not very intuitive ! 
~~~javascript
const component = require('../../../src/component');
const moduleA = require('../../../src/component/render/moduleA');
~~~

Now we can use this tool `require-import-alias` to set alias for the moduleA, such as :
~~~javascript
const requireImportAlias = require('require-import-alias');
requireImportAlias.setAlias({
	'component': '../../../src/component',
	'moduleA': '../../../src/component/render/moduleA'
});
const moduleA = require('moduleA');
const moduleB = require('component/main/moduleB')'
~~~

### and you can also use it with `import` in ES2015(set an alias is a module, and use the alias in anthor module)

setAlias
~~~javascript
import requireImportAlias from 'require-import-alias'
requireImportAlias.setAlias({
	'component': '../../../src/component',
	'moduleA': '../../../src/component/render/moduleA'
});
~~~

using it 
~~~javascript
import component from 'component'
import moduleA from 'moduleA'
import moduleB from 'component/render/moduleB'
~~~

It's so gracefully !