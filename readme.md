
又到了每周解析一个实战项目的时候，本周解析的项目是用 AI 玩王者荣耀，Github上 1.4k star。该项目包括训练数据收集、数据处理、模型训练和模型应用完整开发流程。

该项目用后裔的100多局对战数据训练了一个模型作为演示，大家学会以后可以自己收集数据，训练自己的AI英雄。“阅读原文”有该项目链接，大家可以下载源码。

接下来我们就来拆解下这个项目，我讲解项目的原则一贯是简洁、通俗，尽量做到小白也能看懂。

先来考虑下大致的实现思路，看到这个项目的第一眼我是比较懵的，完全不知道怎么搞。其实换个角度，想想我们玩游戏的过程，或许就能找到一些思路。

我们玩游戏的时候，大脑会根据当前的游戏画面来判断该进行什么样操作。游戏画面其实就是一张图片，如果把图片和图片对应的操作输入到算法模型，让算法自己去学习图片与操作之间的关系。当给出新的图片，如果算法能正确输出对应的操作，那我们就可以在游戏开始后，把游戏画面不断输入到算法模型中，算法模型不断产生对应操作并执行，这样便实现了程序自动玩游戏的功能。

所以，我们就把AI玩游戏的问题抽象成了计算机视觉（cv）的问题。那么要解决的核心问题有两个，第一，图片和图片的操作怎么收集，第二，用什么算法模型。

在后面的讲解中会解决这两个问题。

## 1. 收集训练数据

训练数据就是我们在玩游戏的时候把游戏画面以及操作记录下来。

代码在“训练数据截取_A.py”源文件中。

### 1.1 获取游戏画面

首先需要在 Windows 电脑上安装 scrcpy，它能将安卓手机投射到电脑，这样我们就可以在电脑上截取游戏画面了。





![wom](https://gitee.com/duma-repo/imgs/raw/master/640.png)




我们的

