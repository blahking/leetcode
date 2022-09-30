# 前缀和

## 1. 一维数组的动态和
写法一
```javascript
//preSum[i]表示数组区间[0,i]的和
//preSum长度与原数组长度相同
var runningSum = function(nums) {
	const preSum = [];

	for(let i = 0; i < nums.length; i++) {
		if(i == 0) {//防止数组越界
			preSum[i] = nums[i];
		} else {
			preSum[i] = preSum[i - 1] + nums[i];
		}
	}

	return preSum;
}
```

写法二
题目中要求preSum长度与原数组长度相同，此问题只可用写法一。
写法二在这里只代表求前缀和的另外一种写法。
```javascript
//preSum[i]表示数组区间[0,i-1]的和
//preSum长度 = 原数组长度 + 1
var runningSum = function(nums) {
	const preSum = [];
	preSum[0] = 0;

	for(let i = 1; i <= nums.length; i++) {
		preSum[i] = preSum[i - 1] + nums[i - 1]
	}

	return preSum;
}
```