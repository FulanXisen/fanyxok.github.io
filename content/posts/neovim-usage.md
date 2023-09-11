---
title: "我的Neovim心得"
date: 2023-09-10T23:18:43+08:00
# weight: 1
# aliases: ["/first"]
tags: ["vim"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: true
hidemeta: false
comments: false
description: "Desc Text."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

VIM的作者去世了,我刚接触编程的时候使用的第一个编辑器就是VIM,但是还不知道VIM插件的存在,在没有任何提示辅助的条件下编写完成了很多个Python程序. 
后来知道了VIM插件, 在一通极其复杂的copy-paste配置之后运行ctags检索符号.
vscode很快发布了, 我也因为vscode大而全又方便使用了很多年的vscode.
再后来我感到编写程序的过程在完成构思之后,最大的限制就是编辑效率, 经常觉得编辑效率跟不上我预期的开发速度. 
在vscode上又启用了VIM键位, 但是VIM插件终究是一个模拟器, 模拟了VIM的键位但是缺少VIM的更多指令.
另一个感受是vscode上插件的日新月异, 与我一次学习终身受用的出发点背道而驰.
我决定重新回归VIM的怀抱.
NeoVim是Vim的现代版本, 社区远比Vim更活跃, 并且可以看到持续的活跃. 以NeoVim作为回归Vim的终点, 应该是最好的选择.

# IDE三大件
## 符号查找
符号查找有两种方案, 第一代的语法树方案, 第二代LSP方案
### 查找声明
局部变量或者全局变量的声明由于局限于一定的作用域, 并不难找. 
### 查找定义
函数的定义可能会出现在不同的位置, 由编译宏开关控制真实采用的定义.
所以查找符号要有确定当前环境宏定义的能力, 才能找到正确的定义.
### 查找引用
与函数有多个定义类似, 相同签名的不同函数定义也分别有其应用. 它们不一定是互斥的, 也可能是相交或者包含等等关系. 
准确的查找引用和查找定义, 背后需要的原理是一样的.
## 重构: 重命名

## 代码补全