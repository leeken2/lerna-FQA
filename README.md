# lerna-test

## 子项目编译报错

### 解决
```
config.resolve.set('symlinks', false)
```
or
```
module.exports = {
    resolve: {
        symlinks: false
    }
};
```
### 参考

[npm link with webpack - cannot find module](https://stackoverflow.com/questions/37769228/npm-link-with-webpack-cannot-find-module)
[webpack中对symlinks的warning](https://webpack.docschina.org/configuration/module/#rule-conditions)

keyword：webpack link package
