### download as local module
```sh
npm install --save-dev commitlint-config-yemiancheng @commitlint/lint
```

### make a configurantion file
```sh
echo "module.exports = {extends: ['yemiancheng']};" > commitlint.config.js
```

### run as local module
```js
const load = require('@commitlint/load');
const lint = require('@commitlint/lint');

const CONFIG = require('./commitlint.config.jss');

load(CONFIG)
  .then(opts => lint('foo: bar', opts.rules, opts.parserPreset ? {parserOpts: opts.parserPreset.parserOpts} : {}))
  .then(report => console.log(report));
  /* =>
    { valid: false,
      errors:
      [ { level: 2,
          valid: false,
          name: 'type-enum',
          message: 'type must be one of [build, chore, ci, docs, feat, fix, perf, refactor, revert, style, test]' } ],
      warnings: [] }
    */
```