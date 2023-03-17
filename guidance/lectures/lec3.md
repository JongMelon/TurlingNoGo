# 3月21日上机课

## 怎么调试

qt creator 中内置了调试器，支持单步运行，打断点（在对应行的行标处单击）和查看表达式的值等常见功能，注意好好利用。

除了调试器，我推荐你们在写这份大作业的时候时不时输出一些调试信息，比如进入了哪个函数，或者是进入了哪个分支，以方便你们在开发过程中调试。
qt 提供了分级输出调试信息的方法，比如 `qDebug` 和 `qInfo`，具体见 qt 文档，
推荐他们的原因其一是他们能输出一些 STL 容器，其二是你可以通过类似 `#define QT_NO_DEBUG_OUTPUT` 的方法一次性禁用掉 `qDebug`，
同时保留要正常输出信息的 `qInfo`，方便你们最后提交一个能够干净地运行的项目，
如果利用上面提到的 `#define QT_NO_DEBUG_OUTPUT`，这是很容易实现的。更多可见 https://blog.csdn.net/qq_45662588/article/details/119385969。

另外，少数情况下调试器也会失效，我之前碰到过qt调试器不好使的情况。这时候还有一种原始的方法寻找错误在哪，我称之为二分注释：即，先确定错误的可能范围，这个范围可以很大，
然后把代码段注释掉一半，测试能不能跑，如果能，错误在另一半，否则在这一半，然后递归下去，每次注释掉一半，类似二分法找错在哪。

## 关于多路棋盘

之后的阶段中，你们需要实现多路棋盘，这里我们要求比较低，你可以考虑简单实现成在 $13 \times 13$ 的棋盘图片的中部下 $9 \times 9$ 等各种路数的不围棋。
当然，用画的，或者是截3种棋盘尺寸的图都是可以的，我们保证只出现 9,11,13 路。

## 关于代码风格

**代码需要有注释**：

- 函数和类的简介，一句话或几个字即可
- 注释一些重要函数的实现细节，加分重点参考
- 不要求一定要使用 doxygen，希望你们了解即可

**命名不要太随便**：

尽量不要用 `check1`, `check2` 的方式命名