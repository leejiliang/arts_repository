## # leetcode-两数之和

> https://leetcode-cn.com/problems/two-sum/

给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那两个整数，并返回他们的数组下标。

你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。

**示例:**

```java
给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]
```

**第一题解**

```java
public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
			for (int j = i+1; j < nums.length; j++) {
				if (nums[i] + nums[j] == target) {
					return new int[]{i, j};
				}
			}
		}
		return null;
}


public static int[] twoSum(int[] nums, int target) {
		Map<Integer, Integer> map = new HashMap<>();
		for (int i = 0; i < nums.length; i++) {
			if (map.containsKey(target - nums[i])) {
				return new int[]{map.get(target-nums[i]),i};
			}
			map.put(nums[i], i);
		}
		return null;
	}
```

**解题思路**

暴力解法，通过遍历循环数组，逐个探测结果是否OK，可优化。

利用hashMap的containsKey方法。巧妙。

# Review-Your Guide to Java 8 Optional

[Your Guide to Java 8 Optional](https://dzone.com/articles/java-8-optional-1)

