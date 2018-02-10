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

# A graph is valid tree?
ValidTree.java
```
public boolean validTree(int n, int[][] edges){
  if(n==0){return false;}
  if(edges.length!=n-1){return false;}
  Map<Integer, Set<Integer>> graph = initializeGraph(n,edges);
  Queue<Integer> queue = new LinkedList<>();
  Set<Integer> hash = new HashSet<>();
  queue.offer(0);
  hash.add(0);
  while(!queue.isEmpty()){
    int node=queue.poll();
    for(Integer neighbour: graph.get(node)){
      if(hash.contains(neighbour)){
        continue;
      }
      hash.add(neighbour);
      queue.offer(neighbour);
    }
  }
  return (hash.size()==n);
}
```
