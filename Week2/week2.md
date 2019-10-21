## 1. Algorithm
### Problems 
- [add-two-numbers](https://leetcode-cn.com/problems/add-two-numbers/)
  
### solution
- recursion.

```java
class Solution {
    
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        return addTwoNumbers(l1, l2, null, false);
    }

    private static ListNode addTwoNumbers(ListNode l1, ListNode l2, ListNode resultNode, boolean carryFlag) {
        if (l1 == null && l2 == null) {
            if (carryFlag) {
                setResultNodeNext(resultNode, 1);
            }
            return resultNode;
        }
        
        if(l1 == null) {
            l1 = new ListNode(0);
        }
        
        if(l2 == null) {
            l2 = new ListNode(0);
        }

        int decade = 10;
        int sum = l1.val + l2.val;
        if (carryFlag) {
            sum++;
            carryFlag = false;
        }
        int resultVal = sum;
        if (sum >= decade) {
            resultVal = sum % decade;
            carryFlag = true;
        }

        if (resultNode == null) {
            resultNode = new ListNode(resultVal);
        } else {
            setResultNodeNext(resultNode, resultVal);
        }

        return addTwoNumbers(l1.next, l2.next, resultNode, carryFlag);
    }

    private static void setResultNodeNext(ListNode resultNode, int resultVal) {
        ListNode targetNode = resultNode;
        while (targetNode.next != null) {
            targetNode = targetNode.next;
        }
        targetNode.next = new ListNode(resultVal);
    }
}
```
## 2. Review
- [How Sharding Works](https://medium.com/@jeeyoungk/how-sharding-works-b4dec46b3f6)
  

## 3. Tip
- [分布式锁和同步器](https://github.com/redisson/redisson/wiki/8.-%E5%88%86%E5%B8%83%E5%BC%8F%E9%94%81%E5%92%8C%E5%90%8C%E6%AD%A5%E5%99%A8)
  
## 4. Share
[关于MySQL的lock wait timeout exceeded解决方案](https://segmentfault.com/a/1190000015314171?utm_source=tag-newest)