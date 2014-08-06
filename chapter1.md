#Chapter 1

###KeyPoint1: 代码应当易于理解.

####Yes
> for (Node* ndoe = list->head; node != NULL; node = node->next)  
> &nbsp;&nbsp;&nbsp;&nbsp;Print(node->data);

####No
> Node* node = list->head;   
> if (node == NULL) return;  
> while (node->next != NULL){  
> &nbsp;&nbsp;&nbsp;&nbsp;Print(node->data);    
> &nbsp;&nbsp;&nbsp;&nbsp;node = node->next;  
> }  
> if (node != NULL) Print(node->data);

####note
相比于第一种list遍历方法， 第二种可读性差且代码冗长  
  
  
###KeyPoint2: 代码的写法应当使别人理解他的时间最小化
####Yes
> bucket = FindBucket(key);
> (if bucket!= NULL) assert(!bucket.IsOccupied());

####No
> assert((!(bucket = FindBucket(key))) || !bucket->IsOccupied()); 

####Note
代码并不总是短越好, 可读性并不总是由长度决定
例如:  
> //Fast version of "hash = (65599 * hash) + c"  
> hash = (hash << 6) + (hash << 16) + c;  
上面的因为注释增加了代码长度, 但是会比没有注释的版本更加容易阅读
