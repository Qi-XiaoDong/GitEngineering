# git

## git 路径大小写问题

```js
// 由于git 大小写不敏感 导致文件/文件名大小写发生变化后不能追踪，导致本地和远程代码不一致
git config core.ignorecase false
```

## git 工程化

- [约定式提交规范](https://www.conventionalcommits.org/zh-hans/v1.0.0/#%e7%ba%a6%e5%ae%9a%e5%bc%8f%e6%8f%90%e4%ba%a4%e8%a7%84%e8%8c%83)

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

- commitizen + husky + commitlint 实践

1.  commitizen 使用
    > 当您使用 Commitizen 提交时，系统会在提交时提示您填写任何必需的提交字段。不再需要等到 git commit 钩子运行并拒绝你的提交（尽管这仍然是有帮助的）。

```shell
# 全局安装 局部也可以但是在使用的时候要用npx 
npm install -g commitizen
```
