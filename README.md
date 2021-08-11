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

## 项目运行结果和原来不同

- 样式错乱
- 有些事件执行顺序不一样了

### 解决

检查各个依赖项目的版本是否一致。版本号不要遗漏 `^` `~` 之类的符号，确保完全一致  
如果 package 的依赖必须要不同版本，可以使用 `--hosit --nohoist=package`,将需要保持不同的版本保留在本地  
建议始终使用 `--hoist`,可以方便排查问题  

### 参考
[npm 的语义版本控制](http://nodejs.cn/learn/semantic-versioning-using-npm)  
[Lerna Hoisting](https://github.com/lerna/lerna/blob/main/doc/hoist.md)
