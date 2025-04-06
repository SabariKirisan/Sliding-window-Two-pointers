## Longest Substring Without Repeating Characters (stack) (c++)

Given a string s, find the length of the longest substring without duplicate characters.

## Example
Input: s = "abcabcbb"

Output: 3

Explanation: The answer is "abc", with the length of 3.
## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int lengthOfLongestSubstring(string s) 
    {
        int n=s.size();
        int hash[256];
        fill(hash, hash + 256, -1);
        int l=0,r=0,max_l=0;
        while(r<n)
        {
            if(hash[s[r]]!=-1)
            {
                if(hash[s[r]]>=l)
                {
                    l=hash[s[r]]+1;
                }
            }
            int len=r-l+1;
            max_l=max(max_l,len);
            hash[s[r]]=r;
            r++;
        }
        return max_l;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
