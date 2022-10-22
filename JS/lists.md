# Linked List
``` js
 class LinkedList{
  constructor(node){
    this.node = node;
    this.next = null;
  }
}

createLinkedList(arr){
  let node, temp;
  for(let decrement = arr.length-1; decrement >= 0; decrement--){
    if(!node){
      node = new LinkedList(arr[decrement]);
    }
    else{
      temp = new LinkedList(arr[decrement]);
      temp.next = node;
      node = temp;
    }
  }
  return node;
}
```