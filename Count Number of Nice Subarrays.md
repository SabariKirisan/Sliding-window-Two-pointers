## Count Number of Nice Subarrays (c++)

Given an array of integers nums and an integer k. A continuous subarray is called nice if there are k odd numbers on it.

Return the number of nice sub-arrays.

## Example
Input: nums = [1,1,2,1,1], k = 3

Output: 2

Explanation: The only sub-arrays with 3 odd numbers are [1,1,2,1] and [1,2,1,1].
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
            sum+=(nums[r]%2);
            while(sum>goal)
            {
                sum=sum-(nums[l]%2);
                l++;
            }
            cnt=cnt+(r-l+1);
            r++;
        }
        return cnt;
    }
    int numberOfSubarrays(vector<int>& nums, int k) 
    {
        return numsubarray(nums,k)-numsubarray(nums,k-1);
    }
};
```
## Complexity
- Time complexity : O(2*2N)

- Space complexity : O(1)
