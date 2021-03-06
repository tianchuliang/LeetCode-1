### 754.Reach-a-Number

此题在数学方法上有巧妙的思路．

假设目标是１１，我们自然会尝试+1+2+3+4+5...这样尝试下去，发现这样操作了５次，之后得到的是１５，超过了目标１１，多了４，该怎么办呢？其实策略非常简单，我们将刚才的操作里面的+2变成-2，一正一反就降了４．也就是说+1-2+3+4+5，就能得到11．显然，这样的操作肯定是最简洁的了．所以我们的基本思路就是，+1+2+3...一路不停地加过去，一旦sum超过了target，那么我们就将之前＂加上＂的(sum-target)/2这个数，改为＂减去＂即可．

那么我们自然会问，如果target是12，当我们将sum加到15的时候，相差是3，不是二的倍数怎么办呢？解决方法是：我们就继续累加+6+7，将sum积累到28．此时sum和target之间的差是16，终于是偶数了，意味着我们将之前的+8改为-8即可．

可以分析得到，当sum超过target时，最多再多加两次，一定能保证sum-target是偶数，即得到最优的解决方案．
