---
layout: post
title: Gundam-cli：前端项目创建发布流程解决方案
data: 2018-04-26
tags: 前端资源
comments: true
---

# Gundam-cli：前端项目创建发布流程解决方案

**文档版本号：1.0.0**

> Github地址：[https://github.com/JohnsenZhou/gundam-cli](https://github.com/JohnsenZhou/gundam-cli)

**Gundam-cli**是一个前端项目创建发布流程解决方案，通过命令行工具来减少开发流程中的重复劳动。

大多数的前端团队都会有一套自己的开发脚手架，在一个新的项目启动时，至少要进行以下步骤：

* 从远端仓库克隆脚手架
* 改好后推送到新的仓库

当项目数一多，在这些繁琐的工作上所花费的时间也是不容小觑的。

下图是我司在使用cli前后的对比图：

![](http://os9glxm8s.bkt.clouddn.com/gundam-cli.jpg)

> gundam-cli 是在原有为公司开发的cli基础上做了功能拓展，可参见[317hu-cli](https://www.npmjs.com/package/317hu-cli)，具体流程类似

## 开始

### 安装

```
$ npm install -g gundam-cli
```

### 使用

```
$ gundam new <project-name>
```

执行后主要有以下需要输入的选项：

1. 仓库类型（github、gitlab）
2. 模板地址

   1. 若仓库类型选择github填写格式为：`owner/name`, 例如 `JohnsenZhou/gundam-cli`

   2. 若仓库类型选择gitlab填写格式为：`custom.com:owner/name`, 例如`gitlab.johnsenzhou.com:example/test-projects`

3. 项目名称（默认`project-name`）

4. 项目版本号（默认为模板的版本号）

5. 项目描述

6. 开发人员名称

7. 是否进行`git push`操作（若选是，则进行下一项操作，否则跳出，开发人员后续手动进行`git`操作）

8. 输入新项目远端`git remote` 地址

具体操作流程可参见下图：![](http://os9glxm8s.bkt.clouddn.com/gundam-cli.gif)

### 开发

> gundam-cli为了达到社区的通用性，稍微增加了一部分功能，如果想针对自己公司开发一套对应的cli工具，可以对gundam-cli进行定制

#### 克隆到本地

```
$ git clone https://github.com/JohnsenZhou/gundam-cli.git
```

#### 软链接\`gundam-cli\`到开发环境

```
$ cd gundam-cli
$ npm link
```

#### 开源支持

* [commander.js](https://github.com/tj/commander.js)：nodejs命令行交互框架

* [inquirer](https://github.com/SBoudrias/Inquirer.js)：nodejs交互式命令行工具

* [download-git-repo](https://github.com/flipxfx/download-git-repo)：nodejs中获取git项目的工具

* [fs-extra](https://github.com/jprichardson/node-fs-extra)：nodejs`fs`文件系统扩展

#### 文章推荐

* [Building a simple command line tool with npm](https://blog.npmjs.org/post/118810260230/building-a-simple-command-line-tool-with-npm)
* [Node.js 命令行程序开发教程](http://www.ruanyifeng.com/blog/2015/05/command-line-with-node.html)

## API

```
Usage: gundam <command> [options]

  Options:

    -v, --version  output the version number
    -h, --help     output usage information

  Commands:

    new <string>   Creates a new application
```

## License

[MIT](https://github.com/JohnsenZhou/gundam-cli/blob/master/LICENSE)

