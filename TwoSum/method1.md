### 题目是:
Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution, and you may not use the same element twice<br>
Example:
Given nums = [2, 7, 11, 15], target = 9,
Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].<br><br>
我是第一次在Leetcode做题，首先我题目看不懂，额，半懂吧。而且看了example也不是很懂23333，但是我还是去思考了，思考了三十分钟，憋出了一两行代码，一点思路都没。然后去看了solution，第一个暴力搜索，第二个哈希表，哈希表又有单循环和双循环的写法。<br>
### 第一种：
暴力搜索 用时500ms（829ms） 时间复杂度O(n^2) 空间复杂度O(1)
### 思路：
首先定义一个一个数组用来装结果，然后两个for循环，第一个从0开始，第二个从1开始，接着判断x和target-x是否相等，最后true则返回结果，false则输出无法为target找到结果。慢的原因：比较了一些多余的数据
```c#
 public static  int[] twoSum(int[] nums, int target)
        {
            int[] result = new int[2];   
            for (int i = 0; i < nums.Length; i++)
            {
                for (int j = i + 1; j < nums.Length; j++)
                {
                    if (nums[j]==target-nums[i])
                    {
                        result = new int[] { i,j};
                    }                   
                }
            }
            return result;       
        }
```		
### 第二种哈希表
#### 1）两个循环
#### 2）单个循环
