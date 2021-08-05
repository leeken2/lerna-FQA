# lerna-test

准备使用 lerna 将公司项目整合，此项目用于测试

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
### 结论

可以通过 resolve.symlinks 关闭符号链接解析（以便将资源解析为符号链接路径）。

### 参考

[npm link with webpack - cannot find module](https://stackoverflow.com/questions/37769228/npm-link-with-webpack-cannot-find-module)  
[webpack中对symlinks的warning](https://webpack.docschina.org/configuration/module/#rule-conditions)

> keyword：webpack link package
