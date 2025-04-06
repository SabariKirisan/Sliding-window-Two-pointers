## Max Consecutive Ones III (c++)

Given a binary array nums and an integer k, return the maximum number of consecutive 1's in the array if you can flip at most k 0's.

## Example
Input: nums = [1,1,1,0,0,0,1,1,1,1,0], k = 2

Output: 6

Explanation: [1,1,1,0,0,1,1,1,1,1,1]

Bolded numbers were flipped from 0 to 1. The longest subarray is underlined.
## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int longestOnes(vector<int>& nums, int k) 
    {
        int n=nums.size();
        int m_len=0,l=0,r=0;
        int zeros=0;

        while(r<n)
        {
            if(nums[r]==0) zeros++;

            if(zeros>k)
            {
                if(nums[l]==0) zeros--;
                l++;
            }
            if(zeros<=k)
            {
                int len=r-l+1;
                m_len=max(len,m_len);
            }
            r++;
        }
        return m_len;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
