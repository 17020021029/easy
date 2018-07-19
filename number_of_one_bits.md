## Problem
Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).

Example 1:

Input: 11
Output: 3
Explanation: Integer 11 has binary representation 00000000000000000000000000001011 
Example 2:

Input: 128
Output: 1
Explanation: Integer 128 has binary representation 00000000000000000000000010000000
## 问题分析&解题思路
很简单计算二进制中的1的个数，就是用的uint32_t一下子有点蒙
## 代码实现
```C++
class Solution {
public:
    int hammingWeight(uint32_t n) {
       int res=0;
       uint32_t t=n,temp=0;
        while(t!=0){
            temp=t%2;
            t/=2;
            if(temp==1)
                res++;
        }
        return res;
    }
};
```
