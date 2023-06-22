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

# 局部也可以但是在使用的时候要用npx(推荐局部安装可以统一版本)
npm install --save-dev commitizen

# 你可以使用 npx 初始化传统的changelog适配器：
# 使用commitizen生成符合AngularJS规范的提交说明
npx commitizen init cz-conventional-changelog --save-dev --save-exact
```

2. 推荐使用方法

```json

// # git cz 将和 git commit 一样工作，

// # npx cz 你需要首先让你的仓库Commitizen友好，

"scripts": {
    "commit": "cz"
},

// # npm run commit

```

3. Cz-customizable=> 客制化自动提交信息
   > cz-customizable 是 Commitizen 的一个插件，可以帮助开发者自定义符合 Angular Commit Message Conventions 的提交信息格式和内容。

```js
    // 1. npm install cz-customizable --save-dev

    // 三种使用方法

    // 1. 独立使用 项目不依赖commitizen

    "scripts" : {
        ...
        "commit": "./node_modules/cz-customizable/standalone.js"
    }

    // 3. 可定制为commitizen插件的形式运行
    "commitizen": {
        // "path": "./node_modules/cz-conventional-changelog"
        "path": "node_modules/cz-customizable"
    },
    "cz-customizable": {
        "config": "config/path/to/my/config.js"
    }

```
