###### 45:00
why dummy node.
Use dummy.next to refer header if head node changes


ReverseNodesinKGroup.java
```
public ListNode reverseKGroup(ListNode head, int k){
  ListNode dummy = new ListNode(0);
  dummy.next = head;
  ListNode prev = dummy;
  while(prev!=null){
    prev = reverseNextKNode(prev,k);
  }
  return dummy.next;
}
private ListNode reverseNextKNode(ListNode head,int k){
  ListNode curr = head;
  ListNode n1 = head.next;
  
  for(int i=0;i<k;i++){
    curr = curr.next;
    if(curr==null) return null;
  }
  
  ListNode nk = curr;
  ListNode nkplus = curr.next;
  
  //reverse
  ListNode prev = null;
  curr=head.next;
  while(curr!=nkplus){
    ListNode temp = curr.next;
    curr.next = prev;
    prev=curr;
    curr=temp;
  }
  head.next=nk;
  n1.next = nkplus;
  return n1;
}
```
