# Python Basic and my leetcode's trainning

## Leetcode 1:Two sum
 ```class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        mapp = {}

        for i, n in enumerate(nums):
            complement = target - n
            if complement in mapp:
                return [i, mapp[complement]]

            mapp[n] = i

        return []
```

Command enumerate(nums) is very special beacause it give `i` and `n` `index` and `value` 

## Leetcode 2: Add Two Numbers

This code can run with 1 ms

```
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode()
        cur = dummy
        carryover = 0

        while l1 or l2 or carryover:
            # calculate values
            v1 = l1.val if l1 else 0
            v2 = l2.val if l2 else 0
            sum = v1 + v2 + carryover
            carryover = sum // 10
            sum = sum % 10
            cur.next = ListNode(sum)

            # update pointers
            cur = cur.next
            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None

        return dummy.next
```

And this is my code whichs can run with 5 ms

```
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
                a,b = 0,0
                mu = 0
                e = []
                while l1:
                    a += l1.val * (10 ** mu)
                    mu += 1
                    l1 = l1.next
                mu = 0
                while l2:
                    b += l2.val * (10 ** mu)
                    mu += 1
                    l2 = l2.next
                c = a + b
                ls = ListNode(0)
                lse = ls
                if c > 0:
                    while c > 0:
                        lse.next = ListNode(c%10)
                        lse = lse.next
                        c//=10
                    return ls.next
                elif c == 0: 
                    return ls
```

And I learn ListNode in this Leetcode 2

LeetNode is not a list,it is a 



