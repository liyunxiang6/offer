把《[剑指 offer](https://book.douban.com/subject/25910559/)》的题目用 Java 语言（书中是 C++）实现了一遍，希望能给大家一些参考。

[GitHub 地址](https://github.com/hackhu2019/offer)：https://github.com/hackhu2019/offer

注：我的看的是 2014 年出版的，题目序号和 2017 版有差异，2017 中的贪婪算法部分在 2014 版中没有。

我的代码和其他人的有什么不同：

我的代码中不仅包括解题的代码，还有我解题的思路分析，你可以根据我的分析来理解代码。在比较复杂的地方我也添加了相应的注释。
![我的代码](https://img-blog.csdnimg.cn/20190815170937732.png)
每一题我都有对应的主程序，里面有相应的测试案例，可以独立运行，所有题目我都有相应测试。（当时忘了分出单独的单元测试有点小缺陷）
![主程序](https://img-blog.csdnimg.cn/20190815171220216.png)
我的项目结构，都位于 com.hack 包下，每一题都是 **Question+题号** 命名，还包含部分题目需要的数据结构，例如：BinaryTree（二叉树）、Node （链表）。
![项目结构](https://img-blog.csdnimg.cn/20190815171353773.png)
我的运行环境：

编译器：Intelli IDEA （你只要能跑起 Java 程序就好了，别的都不重要）

Java 版本：1.8  （不同版本对我项目的使用影响不大，1.5 以上即可）

# 介绍

书中的题目大致可以分为数据结构、算法两大部分。根据题目的特点我做了张思维导图，你可以根据题目的特点进行针对性做题，思维导图里也指出了一些相关知识点、技巧。![剑指offer 2014](https://github.com/hackhu2019/offer/blob/master/%E5%89%91%E6%8C%87%20offer%EF%BC%882014%20%E7%89%88%EF%BC%89.png)
# 数据结构篇
数据结构系列包括：数组、字符串、链表、栈&队列、Hash、树、堆以及位运算。

数据结构篇的主要考察点在于每一种特定数据结构的特性，尤其是：**栈&队列**，通常在题目中出现：「**后进先出**」、「**先进先出**」等关键字。

对于 **链表** 和 **树** 很容易和他们的操作以及特性结合出题，当然也会有一定的解题技巧。

例如：删除链表中的结点。使用「**哨兵结点**」可以帮我们处理「**头结点删除**」、「**尾结点删除**」等边界问题。

使用「快慢指针/双指针」可以很容易处理：「**找出链表中环的入口结点**」、「**删除倒数第 K 个结点**」等问题。

而树的「前序遍历」、「中序遍历」、「后序遍历」都有不同的特点，前序遍历和中序遍历的结合可以帮我们解决「**NO6.重建二叉树**」问题。

查找二叉树的中序遍历可以输出一个有序列。那它的「后序遍历」又有怎样的特点呢？去 **NO.24** 找找答案。

# 算法篇
书中对于算法方面考察的知识点不多，2014 版出现的算法类题目涉及：递归、排序、二分查找、回溯、动态规划。

以「二分查找」为例，每种算法大都有特定的使用场景，而「二分查找」适用于有序数组，所以通常题目中出现：有序数组、查找等关键字，很可能就是用二分了。（不是只有二分才能解，而是用了二分更高效）

算法的核心思想不变，但是题目能够变化的就有很多，将二分查找法改变下就可以变成：**数字在排序数组中出现的次数（NO.38）**—— 可以用二分法查找该数字首次出现、最后出现的位置，索引值之差+1 就可以求出次数了。

# 总结
**正难则反**。对于部分题目，我们反过来看可能更容易得出结果。例如：**NO.37 两个链表的第一个公共结点**。从起点找两个链表的公共结点并不容易，但是倒过来看，链表相交类似于「Y」，两个链表倒序遍历（结合栈），当下一个结点不相同时，当前结点就是第一个公共结点了。

**解题 != 最优解**。例如递归类经典题：**NO9.斐波那契数列**。使用递归：f(n)=f(n-1)+f(n-2)。存在大量重复计算、递归层数过多堆栈溢出等问题，你怎么解决递归中的重复计算问题呢？**哈希表**（存储已计算值） or **循环**（所有递归都可以换成循环来做）。

**分解问题，找出规律**。例如：位运算一类的题，很考验问题的分解和归纳分析。**NO47.不使用加减乘除做加法**。
你需要先将加法的运算过程分解为：相同位的数字变化、进位。
1. 联想二进制加法 1、0 变化，只有当二者为（1、0）或（0，1）时相加结果为 1，其余都为 0,与异或运算相似。
2. 进位发生在二者都是 1 的时候，同与运算一致，进位操作可以看作左移。

这样分解问题并一步步找到规律可以帮我们更好的解题。

我的代码中也有一些自己的思路，如果出现错误你可以直接提交你的代码到我的仓库，或直接 [联系我](https://www.zhihu.com/people/hu-hao-77-99/activities) 都可以。祝大家和我都能收获自己心仪的 offer。

如果你喜欢我的题解风格也欢迎你关注我的另一个项目 [LeetCode 题解](https://github.com/hackhu2019/LeetCode):https://github.com/hackhu2019/LeetCode