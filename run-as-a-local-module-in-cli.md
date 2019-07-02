### download as local module
```sh
npm install --save-dev commitlint-config-yemiancheng @commitlint/cli
```

### make a configurantion file
```sh
echo "module.exports = {extends: ['commitlint-config-yemiancheng']};" > commitlint.config.js
```

### run as local module
```sh
# with an incorret git commit message
echo "fix(SCOPE): some message" | ./node_modules/.bin/commitlint
# with an corret git commit message
echo "fix(scope): some message" | ./node_modules/.bin/commitlint
```