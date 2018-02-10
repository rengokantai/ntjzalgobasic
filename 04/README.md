TreeLevelTraversal.java
```
public List<List<Integer>> getResult(TreeNode root){
  List<List<Integer>> result = new ArrayList<>();
  if(root==null)
    return result;

  Queue<TreeNode> queue = new LinkedList<TreeNode>();
  queue.offer(root);
  
  while(!queue.isEmpty()){
    List<Integer> temp = new ArrayList<>()
    int size = queue.size()
    for(int i=0;i<size;i++){
      TreeNode i = queue.poll();
      temp.add(i.val);
      if(i.left!=null) queue.offer(i.left);
      if(i.left!=null) queue.offer(i.right);
    }
    result.add(temp);
  }
  return result;
}
```
