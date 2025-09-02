## Fruit Into Baskets (java)

You are visiting a farm that has a single row of fruit trees arranged from left to right. The trees are represented by an integer array fruits where fruits[i] is the type of fruit the ith tree produces.

You want to collect as much fruit as possible. However, the owner has some strict rules that you must follow:

- You only have two baskets, and each basket can only hold a single type of fruit. There is no limit on the amount of fruit each basket can hold.
- Starting from any tree of your choice, you must pick exactly one fruit from every tree (including the start tree) while moving to the right. The picked fruits must fit in one of your baskets.
- Once you reach a tree with fruit that cannot fit in your baskets, you must stop.

Given the integer array fruits, return the maximum number of fruits you can pick.

## Example
Input: fruits = [0,1,2,2]

Output: 3

Explanation: We can pick from trees [1,2,2].
If we had started at the first tree, we would only pick from trees [0,1].
## PROGRAM:(Main.cpp)
```
class Solution {
    public int totalFruit(int[] fruits) 
    {
        int left=0,right=0,len=0;
        int n=fruits.length;
        HashMap<Integer,Integer> mpp= new HashMap<>();

        while(right < n)
        {
            mpp.put(fruits[right],mpp.getOrDefault(fruits[right],0)+1);

            if(mpp.size() >2)
            {
                mpp.put(fruits[left],mpp.get(fruits[left])-1);
                if(mpp.get(fruits[left])==0)
                {
                    mpp.remove(fruits[left]);
                }
                left++;
            }
            len=Math.max(len,right-left+1);
            right++;
        }
        return len;
    }
}
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1) (practically constant due to at most two fruit types).
