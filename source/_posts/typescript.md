---
title: 深入学习typeScript类型体操
---

在当今前端圈内，如果你如果还不会 typescript，那么你就不是一名合格的前端工程师。有的人说 typescript 有啥难的，不会的直接使用 <font color=#008000>_any_</font>替代，AnyScript 就完事了。

![图片](https://img9.doubanio.com/view/richtext/large/public/p34066865.jpg)

但是 any 一时爽，维护...
## 前言

之前遇到一个问题：
后端同学给的接口返回值是一个范围值，形如：
```
{ aaa300: 300, aaa301: 301, ....,  aaa999: 999 }
```
从结构中就可以看出这个返回值的value和key是有关联的，而且value是有范围的，上面的范围是从[300, 999];
一开始，我是想这样定义的：
```
type A = Record<string, number>;

const a: A = {
    aaa300: 300
};

const value = a.aaa300;
```
这样写的结果就是value推导出来的类型是number(又不是不能用.jpg+1)


那如果我想再准确一点，使推导出来的值是300，该怎么办呢？

如果这个题目对你来说没有一点难度，那恭喜你，下面的内容对你一点作用都没有，可以不用看了

如果你也不会，不妨跟我一起学习一下typescript类型体操


## 基础

工欲善其事必先利其器。我们都知道，一套体操是由多个基础动作组成的，所以，要做typescript类型体操，必须先学习typescript基础。

下面是整个typescript的知识体系：
![typescript思维导图](/source/images/typescript-study.png)


### 基础类型：


## 类型编程（类型体操）

类型编程是针对类型参数，也就是泛型（类型参数）来说的，传入类型参数，经过一系列类型运算逻辑后，返回新的类型就叫做高级类型。这是ts的强大之处，也是复杂之处。类型编程在许多类库中都是必不可少的，因为只有把类型编程写好了，使用者在使用类库的时候才能在IDE中获取到代码提示

如果你对你的类型编程很有兴趣，可以在空余时间刷刷  [type-challenges](https://github.com/type-challenges/type-challenges) 。如果能把里面的题目都搞懂，那我相信今后任何ts类型体操相关的题目都无法再难住你了。

类型体操做多了之后，你就会发现所有的类型体操基本都可以用下面几个方法来实现：

### 使用模式匹配提取值

### 重新构造生成新的类型

### 循环递归

### 使用数组长度作为计数

### 分布式条件运算


  

## 参考文献

[了不起的 TypeScript 入门教程](https://mp.weixin.qq.com/s/0c7XmwHDycdfQHKScSfFeQ)

[typescript史上最强学习入门文章(2w字)](https://juejin.cn/post/7018805943710253086#heading-0)