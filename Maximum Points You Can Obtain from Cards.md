## Maximum Points You Can Obtain from Cards (c++)

There are several cards arranged in a row, and each card has an associated number of points. The points are given in the integer array cardPoints.

In one step, you can take one card from the beginning or from the end of the row. You have to take exactly k cards.

Your score is the sum of the points of the cards you have taken.

Given the integer array cardPoints and the integer k, return the maximum score you can obtain.
## Example
Input: cardPoints = [1,2,3,4,5,6,1], k = 3

Output: 12

Explanation: After the first step, your score will always be 1. However, choosing the rightmost card first will maximize your total score. The optimal strategy is to take the three cards on the right, giving a final score of 1 + 6 + 5 = 12.
## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int maxScore(vector<int>& cardPoints, int k) 
    {
        int n=cardPoints.size();
        int l_sum=0,r_sum=0,max_sum=0;
        for(int i=0;i<k;i++)
        {
            l_sum=l_sum+cardPoints[i];
        }
        max_sum=l_sum;
        int r_ind=n-1;
        for(int i=k-1;i>=0;i--)
        {
            l_sum=l_sum-cardPoints[i];
            r_sum=r_sum+cardPoints[r_ind];
            r_ind--;
            max_sum=max(max_sum,l_sum + r_sum);
        }
        return max_sum;
    }
};
```
## Complexity
- Time complexity : O(K)

- Space complexity : O(1)
