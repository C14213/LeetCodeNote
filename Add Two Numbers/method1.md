### 题目
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

#### Example

Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
Explanation: 342 + 465 = 807.

题目我是看懂了，但是我还是不会写，代码憋出了三行，我刚开始的想法是，建立三个链表，存放数据，然后相加。问题是怎么逆序存放呢？存放之后怎么相加呀？相加之后进位怎么办呢？一长一短怎么解决呢？这些问题一点都不会啊。:weary:<br>
无奈只能看答案了。solution里给出了一种答案还是java的，看了里面的解释，依然有点懵懂啊。<br>
所以百度了一下，有三种方法，迭代和递归和九章算法。<br>
接下来先看迭代那种吧
#### 第一种：迭代
