### 826.Most-Profit-Assigning-Work

此题不难想到正确的贪心解法。

我们将所有的任务ｔａｓｋｓ按照难度从小到大进行排序然后遍历。如果难度小的任务的收益是ｐ，那么比之难度更大的任务的收益理论上不应该比ｐ更小，否则我们可以选择用难度小收益大的项目替代更划算。所以我们将这些任务的收益重新赋值，使得ｔａｓｋｓ按照难度从小到大排列后，收益也是递增的。

接下来对于任何一个工人，我们在这个ｔａｓｋｓ序列中找到他所能接受的最大难度ｄ的任务，那么这个任务对应的（重新赋值后的）收益，就是这个工人所能创造的最大收益。因为这个收益，本质对应了所以难度小于等于ｄ的任务中的最高收益。每个工人都是如此计算，得到的总收益就是答案。

本题的ｃｐｐ解法要注意下面这句：
```
auto iter = upper_bound(tasks.begin(),tasks.end(),make_pair(x,INT_MAX));
```
这里的第三个参数一定要用make_pair来生成，不能用{x,INT_MAX}，否则编译器不能自动正确地转化。
