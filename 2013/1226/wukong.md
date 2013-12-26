# 关于 BDD 的小思考

今天帮 [nodeclub](https://github.com/cnodejs/nodeclub) 加入了 OAuth 登陆的功能。之前 nodeclub 由于受到某个很牛逼的可以穿越验证码的发帖机的影响，暂时关闭了新用户的注册功能。而其实说起来，以个人之力跟 spammer 斗是很无谓的行为，所以干脆让新用户通过 GitHub 来登陆。这样一来，nodeclub 与 spammer 的矛盾就转移成 spammer 与 GitHub 之间的矛盾了。

我相信 spammer 还是斗不过 GitHub 的，顺便 GitHub 还起到了过滤小白的作用。

——

在今天开发的过程中，我是先写代码，然后才打算写测试的。原因在于，我今天写的代码所会导致行为我不能确定，在写代码的过程中，也确实遇到了不同程度的重构。而在行为不确定时，边写测试边写代码，只是更多地增加了写代码的负担，而不是保证了代码的行为。

那么在什么时候该测试先行或者测试并行，什么时候应该测试后行呢？

分两种情况：

1 行为确定时，测试先行是个好选择

我之前看过一篇介绍 BDD 的文章，这篇文章主要测的是一个可以将阿拉伯数字转为罗马数字的函数。它先是通过测试，确定好了转换所需的效果以及各种边界情况：

    XVI     16
    XVII     17
    XVIII     18
    XIX     19

然后一步一步地完善函数，直到测试通过，把函数行为固定。

这个例子中，由于所期待的行为非常确定，所以测试先行在这里是个好选择。

2 行为不确定时，可以选择测试后行

测试这东西，一是有驱动开发的作用，一是有固定行为的作用。

如果测试后行的话，驱动开发的作用自然是没有了，但固定行为的作用仍在。


## 顺便推荐个网站 http://rawgithub.com/

### Before

`https://raw.github.com/user/repo/master/filename.js`

### After

`https://rawgithub.com/user/repo/master/filename.js`

这样就可以在 jsperf 或 jsfiddle 之类的网站直接引用 GitHub 上的文件了。
