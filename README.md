# LEETCODE-Trees-1261
**Code Breakdown:**

1. **`bfs(TreeNode root, int x)`:**
   - Performs a Breadth-First Search (BFS) traversal of the tree.
   - Resets the value of the root node to `x` (which is initially 0 in the constructor).
   - During the traversal:
     - Adds the current node's value to the `HashSet s`.
     - Calculates the values of the left and right children as `2 * parent.val + 1` and `2 * parent.val + 2`, respectively.
     - Updates the values of the left and right children in the tree.

2. **`FindElements(TreeNode root)`:**
   - The constructor.
   - Clears the `HashSet s`.
   - Calls `bfs(root, 0)` to initialize the tree and populate the `HashSet s`.

3. **`find(int target)`:**
   - Checks if the `HashSet s` contains the `target` value.

**Dry Run Example:**

Let's say we have the following initial tree:

```
    -1
   /  \
  -1   -1
```

And we perform the following operations:

1. `FindElements obj = new FindElements(root);`

   - `s` is cleared.
   - `bfs(root, 0)` is called.

     - **Root:**
       - `root.val` becomes 0.
       - 0 is added to `s`.

     - **Left Child:**
       - `root.left.val` becomes `2 * 0 + 1 = 1`.
       - 1 is added to `s`.

     - **Right Child:**
       - `root.right.val` becomes `2 * 0 + 2 = 2`.
       - 2 is added to `s`.

   - The tree now looks like this:

     ```
         0
        /  \
       1    2
     ```

   - `s` contains {0, 1, 2}.

2. `obj.find(1);`

   - `s.contains(1)` returns `true`.

3. `obj.find(3);`

   - `s.contains(3)` returns `false`.

4. `obj.find(2);`

   - `s.contains(2)` returns `true`.

**Summary:**

The code effectively reconstructs the tree according to the specified rule (left child = 2 * parent + 1, right child = 2 * parent + 2) and stores the values in a `HashSet`. The `find()` method then efficiently checks for the presence of a target value in the `HashSet`. The BFS traversal ensures that all possible values are generated and stored in the set.
