```cpp
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
    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
        return build(preorder, 0, preorder.size() - 1,
        inorder, 0, inorder.size() - 1);

    }

    TreeNode* build(vector<int>& preorder, int PreStart, int PreEnd, vector<int>& inorder, int inStart, int inEnd){
        if(PreStart > PreEnd){
            return nullptr;
        }

        int rootVal = preorder[PreStart];

        int index = 0;
        for( int i = inStart; i<=inEnd; i++){
            if(inorder[i] == rootVal){
                index = i;
                break;
            }
        }

        int leftSize = index - inStart;

        TreeNode* root = new TreeNode(rootVal);
        
        root->left = build(preorder, PreStart + 1, PreStart + leftSize,
        inorder, inStart, index - 1);

        root->right = build(preorder, PreStart + leftSize + 1, PreEnd,
        inorder, index + 1, inEnd);

        return root;
    }
};
```
