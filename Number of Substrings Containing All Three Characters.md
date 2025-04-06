## Number of Substrings Containing All Three Characters (c++)
Given a string s consisting only of characters a, b and c.

Return the number of substrings containing at least one occurrence of all these characters a, b and c.
## Example
Input: s = "aaacb"

Output: 3

Explanation: The substrings containing at least one occurrence of the characters a, b and c are "aaacb", "aacb" and "acb". 
## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int numberOfSubstrings(string s) 
    {
        int n=s.size();
        int lastseen[3]={-1,-1,-1};
        int cnt=0;

        for(int i=0;i<n;i++) 
        {
            lastseen[s[i]-'a']=i;

            if(lastseen[0]!=-1 && lastseen[1]!=-1 && lastseen[2]!=-1)
            {
                cnt=cnt+(1+min({lastseen[0],lastseen[1],lastseen[2]}));
            }
        }    
        return cnt;   
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)
