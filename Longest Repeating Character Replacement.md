## Longest Repeating Character Replacement (stack) (c++)

You are given a string s and an integer k. You can choose any character of the string and change it to any other uppercase English character. You can perform this operation at most k times.

Return the length of the longest substring containing the same letter you can get after performing the above operations.

## Example
Input: s = "AABABBA", k = 1

Output: 4

Explanation: Replace the one 'A' in the middle with 'B' and form "AABBBBA".
The substring "BBBB" has the longest repeating letters, which is 4.
There may exists other ways to achieve this answer too.
## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int characterReplacement(string s, int k) 
    {
        int n=s.size();
        int l=0,r=0,max_f=0,max_l=0;
        map<char,int> mpp;

        while(r<n)
        {
            mpp[s[r]]++;
            max_f=max(max_f,mpp[s[r]]);

            if((r-l+1) - max_f > k)
            {
                mpp[s[l]]--;
                l++;
            } 
            max_l=max(max_l,r-l+1);
            r++;
        }
        return max_l;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
