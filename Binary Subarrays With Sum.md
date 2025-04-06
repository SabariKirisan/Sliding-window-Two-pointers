## Binary Subarrays With Sum (stack) (c++)

Given a binary array nums and an integer goal, return the number of non-empty subarrays with a sum goal.

A subarray is a contiguous part of the array.

## Example
Input: nums = [1,0,1,0,1], goal = 2

Output: 4

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int numsubarray(vector<int>& nums,int goal)
    {
        if(goal<0) return 0;
        int n=nums.size();
        int l=0,r=0,sum=0,cnt=0;

        while(r<n)
        {
            sum+=nums[r];
            while(sum>goal)
            {
                sum=sum-nums[l];
                l++;
            }
            cnt=cnt+(r-l+1);
            r++;
        }
        return cnt;
    }
    int numSubarraysWithSum(vector<int>& nums, int goal) 
    {
        return numsubarray(nums,goal)-numsubarray(nums,goal-1);
    }
};
```
## Complexity
- Time complexity : O(2*2N)

- Space complexity : O(1)
