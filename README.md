### 字节第六期青训营项目一 - 包的分析工具

#### 说明

​	此文件为npm-cli-bytetech-ys 包的源代码

​	项目NPM官网地址: https://www.npmjs.com/package/npm-cli-bytetech-ys

#### 背景

**一款npm包依赖分析工具,通过NPM命令行方式生成依赖关系,以json文件的形式存储到某个目录,或者将他以页面的形式在浏览器打开**

依赖分析工具是npm包管理系统中的重要组成部分，它们提供了许多优势。首先，依赖分析工具能够帮助开发人员**快速了解项目中的依赖关系**，包括**依赖的版本**、**依赖的依赖**、**循环依赖的问题**等。这有助于避免潜在的冲突或安全漏洞，并确保项目的稳定性和安全性。

其次，依赖分析工具能够**提供可视化的依赖图表**，使开发人员更直观地了解整个项目的结构。这有助于快速定位问题，优化依赖关系，并**提高代码的可维护性和可扩展性**。

此外，依赖分析工具还能够以json的文件输出到目录当中，能够及时分析和讨论。这有助于保持项目的最新状态，**提高代码质量，并及时修复潜在的漏洞**。

总之，依赖分析工具在npm包管理中具有重要的优势，包括帮助开发人员了解依赖关系、提供可视化图表。它们是现代软件开发中不可或缺的工具，有助于提高项目的稳定性、安全性和可维护性。

#### 安装
```
    npm install npm-cli-bytetech-ys -g       /*必须全局安装此工具*/
```

#### 用法

- 全局变量：`npm-cli`
##### 支持命令
* `-n/--name ` 获取包名
```
    npm-cli -n/--name
```



* `-v/--version ` 获取版本号
```
    npm-cli -v/--version
```



* `-a/--analyze ` 打开可视化依赖面板，通过生成可视化图表并且在浏览器显示（默认递归到最后一层）

```
    npm-cli -a/--analyze
```



* -h/--help ` 获取所有可执行的命令
```
    npm-cli -h/--help
```

##### 支持命令参数


* `analyze -d, --depth=<nmbers> ` 允许携带数字,只展示指定深度的依赖

执行如下命令：

```
    npm-cli analyze -d, --depth=<nmbers>
```

<numbers> 填数字，该数字决定了依赖分析的深度，分析完成后会生成依赖图并且在浏览器中打开，能够更加直观的浏览各个依赖之间的关系。



* `analyze -a, --json=<filepath> ` 允许携带路径,将依赖关键图存入指定路径

**注意：如果存在--json，那么将不在生成依赖图在浏览器中。**

执行如下命令：

```
    npm-cli analyze analyze -a, --json=<filepath>
```

<filepath>可为绝对路径或者相对路径

绝对路径的格式类似于这样：**D:/dependencies/dependenciesTree.json**或者**D:\dependencies\dependenciesTree.json**.

相对路径的格式类似于这样：**dist/dependenciesTree.json**或者**../dist/dependenciesTree.json**

注：你可以选择既可以自己命名，也可以省略后面的文件名，我们默认其文件名为**'dependenciesTree.json'**



- 生成指定深度的json依赖分析文件

执行如下命令：

```
    npm-cli analyze --depth=<number> --json=<filepath>
```

工具会生成指定深度的json文件并且保存到指定的路径当中。