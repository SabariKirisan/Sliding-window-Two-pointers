## Subarrays with K Different Integers (c++)
Given an integer array nums and an integer k, return the number of good subarrays of nums.

A good array is an array where the number of different integers in that array is exactly k.

For example, [1,2,3,1,2] has 3 different integers: 1, 2, and 3.

A subarray is a contiguous part of an array.
## Example
Input: nums = [1,2,1,2,3], k = 2

Output: 7

Explanation: Subarrays formed with exactly 2 different integers: [1,2], [2,1], [1,2], [2,3], [1,2,1], [2,1,2], [1,2,1,2]
## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int countsubarray(vector<int>& nums, int k)
    {
        int n=nums.size();
        int l=0,r=0,cnt=0;
        map<int,int> mpp;

        while(r<n)
        {
            mpp[nums[r]]++;

            while(mpp.size()>k)
            {
                mpp[nums[l]]--;
                if(mpp[nums[l]]==0) mpp.erase(nums[l]);
                l++;
            }
            cnt=cnt+(r-l+1);
            r++;
        }
        return cnt;
    }
    int subarraysWithKDistinct(vector<int>& nums, int k) 
    {
        return countsubarray(nums, k) - countsubarray(nums, k-1);
    }
};
```
## Complexity
- Time complexity : O(2*2N)

- Space complexity : O(2*N)
