### 题目描述
> 输入一个递增排序的数组和一个数字S，在数组中查找两个数，使得他们的和正好是S，如果有多对数字的和等于S，输出两个数的乘积最小的。
输出描述:
对应每个测试案例，输出两个数，小的先输出。

### 题目分析
双指针  相距最远，乘积最小

### 代码
```javascript
function FindNumbersWithSum(array, sum) {
  if (array.length < 2) return [];
  let left = 0,
    right = array.length - 1;
  const res = [];
  while (left < right) {
    if (array[left] + array[right] < sum) {
      left++;
    } else if (array[left] + array[right] > sum) {
      right--;
    } else {
      res.push(array[left], array[right]);
      break;
    }
  }
  return res;
}
```