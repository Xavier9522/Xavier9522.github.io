---
layout: post
title: 对南邮ctf Crypto的一次writeup
date: 2019-03-17
categories: test
tags: Crypto
---
> 对南邮ctf Crypto的一次writeup

**0x00  前言**

说出来我自己都不信..居然有这么久没有用过博客了(域名都能差点忘了，我也是佩服我自己..)；web小白最近迷上了Crypto也就是密码学啦。在一位大佬的怂恿下去玩耍了一下南邮ctf顺便写一下一万年没有动过的blog...

**0x01easy!!**

先看一下题目

![jekyll]({{ "/assets/img/easy.png" }})

emmmm典型的base64(但神奇的是用md5也能得到答案)

![jekyll]({{ "/assets/img/easy1.png" }})

得到答案。

**0x02  KeyBoard**

![jekyll]({{ "/assets/img/keyboard.png" }})

看到题目提示KeyBoard，身经百战的我（caiji）低头就往键盘上看（手动滑稽护体）

发现空格提示了很多，每一串字符串都在键盘上围成了一个字母...（这脑洞...）

得到flag为areuhack...

**0x03  base64全家桶**

![jekyll]({{ "/assets/img/全家桶1.png" }})

题目很清楚的提示..全家桶...那就先base64一哈。

![jekyll]({{ "/assets/img/全家桶2.png" }})

得到一串这个..根据一个菜鸡总结的base经验这串没有1！那就大概率是base32，先丢进去再说！

![jekyll]({{ "/assets/img/全家桶3.png" }})

再次根据一个菜鸡总结的base经验，这串最多只到F，base16解码得到flag...

![jekyll]({{ "/assets/img/全家桶4.png" }})

**0x04  n次base64**

![jekyll]({{ "/assets/img/base64.png" }})

python？不存在的...（主要是因为不会...）网页在线解码不好吗（再次滑稽）反正就是多几次（也就才14次），最后得到flag

![jekyll]({{ "/assets/img/base642.png" }})

**0x05  mixed base64**

看题目指的是base64 base32 base16 的乱序加密方法

![jekyll]({{ "/assets/img/base1.png" }})

根据一个菜鸡总结的base经验来说，base64作为常见，base32没有1，base16只有0-9和A-F。根据每一次解密后的特点就可以解决，得到flag：nctf{rot13_and_base64_and_strrev}

>番外篇

**Misc图种**

![jekyll]({{ "/assets/img/图种1.png" }})

下载文件后是一张gif，改为.txt打开发现还有一个233333.gif

![jekyll]({{ "/assets/img/图种2.png" }})

将文件改为.zip发现确实有一个233333.gif打开后等到最后一句话，取首字母得到flag

![jekyll]({{ "/assets/img/图种3.png" }})

>完结撒花