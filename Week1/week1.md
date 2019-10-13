## 1. Algorithm
### Problems 
- [two-sum](https://leetcode-cn.com/problems/two-sum/)
  
### solution
- brute force easy subject.
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] result = new int[2];
        for(int i = 0; i < nums.length - 1; i++) {
            for(int j = i + 1; j < nums.length; j++) {
                if(nums[i] + nums[j] == target) {
                    result[0] = i;
                    result[1] = j;
                    return result;
                }
            }
        }
        return result;
    }
}
```
## 2. Review
- [Goodbye, Object Oriented Programming](https://medium.com/@cscalfani/goodbye-object-oriented-programming-a59cda4c0e53)
  
**my view:**
- front the examples of common mistakes, i think the problem lies more in the way OOP is used here, those problems can be solved by using composition over inheritance or make use of immutability

## 3. Tip
- Stream API
  
## 4. Share
[Character Encoding](https://www.cnblogs.com/leesf456/p/5317574.html)