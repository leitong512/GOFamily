### 如何计算时间和空间的复杂度。

公式：`T(n) = O(fn(n))` 平时我们看到的样子是这样的`O(n)`

#### 时间复杂度

求解的时候要注意一个原则：去掉低阶，去掉常数，去掉最高阶的常数，例如：`2n^2 + 2n + 1` 它的时间复杂度就是 `O(n^2)`
所以说啊，时间复杂度就是一个估计值，举个例子
```go
for i := 0;i < n ;i++ {
  for j := i;j <n;j++ {

  }
}
```
外层循环那么肯定是N 因为是循环那么那么的中间肯定是`x`，所以说外层是N，内层，因为根据i的变化而变化，比如第一次循环就是n次，第二次就是n-1次，第三次就是n-2次那么结果就是`(n^2-n)*0.5` 所以最后取大头就等于`n^2`

列举几个平时经常看到的时间空间复杂度，按照速度顺序列举，越靠前，时间越少，速度越快。

`1 > logn > n > nlogn > n^2 > n^3 > 2^n > n! > n^n`

计算的时候通常简单的可以猜出来，比如说，寻找一个数组中的一个数，那么需要遍历所有的数据，时间复杂度就是O(n),即便是有序的使用二分法查找，结果也是 O(logn)，而且是log2 n ，但是如果说，我们要随机的按照下表来搞出来一个数，那么这个时间复杂度就是O(1)了，因为你直接就把他抽出来了嘛。

意思就是说，随着数量的增加，我们让这个算法成功的时间是多少。或者是n的多少倍。

#### 空间复杂度

那么空间复杂度就是随着n的增加要消耗多少内存空间。