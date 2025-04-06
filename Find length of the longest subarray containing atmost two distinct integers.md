## Find length of the longest subarray containing atmost two distinct integers (c++)

Given an array arr[] containing positive elements, the task is to find the length of the longest subarray of an input array containing at most two distinct integers.

## Example
Input: arr[] = [3, 1, 2, 2, 2, 2]

Output: 5

Explanation: The longest subarray containing at most two distinct integers is [1, 2, 2, 2, 2], which has a length of 5. The subarray starts at the second element 1 and ends at the last element. It contains at most two distinct integers (1 and 2).

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    int totalElements(vector<int> &arr) 
    {
        int k=2;
        int n=arr.size();
        int l=0,r=0,max_l=0;
        map<int,int> mpp;
        
        while(r<n)
        {
            mpp[arr[r]]++;
            if(mpp.size()>k)
            {
                mpp[arr[l]]--;
                if(mpp[arr[l]]==0) mpp.erase(arr[l]);
                l++;
            }
            if(mpp.size()<=k)
            {
                int len=r-l+1;
                max_l=max(max_l,len);
            }
            r++;
        }
        return max_l;
       
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
