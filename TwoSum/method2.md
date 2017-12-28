### 第二种哈希表
查找效率为O(1)
#### 1）两个循环<br>
时间复杂度O(n),空间复杂度O(n)，放在LeetCode上测试，发生Unknow Error:worried:<br>
##### 思路：
先通过一个for循环把键和值存入字典中，然后再通过一个for循环计算x=target-x，最后将值进行判断是否存在并且通过FirstOrDefault查找所有KV与满足条件的值比较再提取出键，true则返回，false则抛出错误提示，注意键和键不想等<br><br>
刚开始我纳闷为什么不用HashTable，百度一查，知道原因了<br>
因为在此程序中，K和V都是值类型，其速度远远超过Hashtable，因为 Hashtable 的元素属于 Object 类型，所以在存储或检索值类型时通常发生装箱和取消装箱操作。<br>
原因来源：[C#中哈希表(HashTable)的用法详解以及和Dictionary比较](https://www.cnblogs.com/zk-zhou/p/6672494.html)
```C#
public static int[] twoSum(int[] nums, int target)
        {
            if (nums.Length < 2)
            {
                throw new Exception();
            }
            Dictionary<int, int> dict = new Dictionary<int, int>();
            for (int i = 0; i <= nums.Length - 1; i++)
            {
                dict.Add(i, nums[i]);
            }
            for (int i = 0; i <= nums.Length - 1; i++)
            {
                int temp = target - nums[i];

                if (dict.ContainsValue(temp) && dict.FirstOrDefault(q => q.Value == temp).Key != i)
                {
                    return new int[] { i,dict.FirstOrDefault(q => q.Value == temp).Key};
                }
            }
            throw new Exception();
        }
```
#### 2）单个循环
时间复杂度和空间复杂度都跟两个循环一样，但是代码量上少了，显得更加简洁<br>
```C#
public static int[] twoSum(int[] nums, int target)
        {
            if (nums.Length < 2)
            {
                throw new Exception();
            }
            Dictionary<int, int> dict = new Dictionary<int, int>();
            for (int i = 0; i <= nums.Length - 1; i++)
            {
                dict.Add(i, nums[i]);               
                int temp = target - nums[i];
                if (dict.ContainsValue(temp) && dict.FirstOrDefault(q => q.Value == temp).Key != i)
                {
                    return new int[] { dict.FirstOrDefault(q => q.Value == temp).Key,i };
                }
            }
            throw new Exception();
        }
```
