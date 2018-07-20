## Problem
Find the sum of all left leaves in a given binary tree.

Example:

    3
   / \
  9  20
    /  \
   15   7

There are two left leaves in the binary tree, with values 9 and 15 respectively. Return 24.
## 解题思路
用递归来做，是左子叶就加到sum中，不是就加0
## 代码实现
```C++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    int sumOfLeftLeaves(TreeNode* root) {
        int sum=0;
        dfs(root,sum);
        return sum;
    }
    int dfs(TreeNode* root,int &sum){
        if(!root)return 0;
        if(root->left) sum+=dfs(root->left,sum);
        if(root->right) dfs(root->right,sum);
        if(!(root->left) && !(root->right))
            return root->val;
        return 0;
    }
};
```
