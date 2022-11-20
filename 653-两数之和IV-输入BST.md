### 爷的做法！

```java
class Solution {
    public boolean findTarget(TreeNode root, int k) {
        Set<Integer> l=new HashSet<Integer>();
        preorder(root,l);
        for(Integer i:l){
            if(l.contains(k-i)){
                return true;
            }
        }
        return false;
    }
    public void preorder(TreeNode n, Set<Integer> l){
        if(n==null){
            return;
        }
        l.add(n.val);
        preorder(n.left,l);
        preorder(n.right,l);
    }
}
```

### 很好，很有精神！但是没考虑[1]和k=2的情况（

### 前方，题解会很有用：

```java
class Solution {
    Set<Integer> set = new HashSet<Integer>();

    public boolean findTarget(TreeNode root, int k) {
        if (root == null) {
            return false;
        }
        if (set.contains(k - root.val)) {
            return true;
        }
        set.add(root.val);
        return findTarget(root.left, k) || findTarget(root.right, k);
    }
}
```

### 直接按顺序找而不是全放在Set里再找，这样就不会出现重复（k为set中元素两倍）的情况了。

### 不愧是题解，轻易就做到了我做不到的事情呢（哭
