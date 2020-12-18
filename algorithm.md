# 算法

## 二分查找

需要排序

最多需要log~2~n步

```javascript
var birnatySeacher=function(arr,item){
    let low=0,
        high=arr.length-1;  
    let mid,element;
    while(low<=high){//控制范围，不是只包含一个元素
        mid=Math.floor((low+high)/2);//向下取整
        element=arr[mid];
        if(element<item){
            low=mid+1;
        }else if(element>item){
            high=mid-1;
        }else{
            return mid;
        }
    }
    return -1;
};
```

## 选择排序

O(n^2^)

大致的思路是找到数据结构中的最小值并将其放置在第一位，接着找到第二小的值并将其放在第二位，以此类推。

```javascript
var selectionSort=function(arr){
    let min;
    for(let i=0;i<arr.length-1;i++){//外循环迭代数组
        min=i;//令第一个值为最小值
       for(let j=i;j<arr.length;j++){
           if(arr[min]>arr[j]){//比较当前位置数值小于min位置数值
               min=j;//改变最小值
           }
       }
       if(i!=min){//当前最小值和原有的不同，则交换
           swap(i,min);
       }
    }
};
```

![image-20201201134738369](算法.assets/image-20201201134738369.png)

### 反转链表

1. 双指针迭代

   申请两个指针，第一个指针叫pre,最初指向null

   第二个指针cur指向head，然后不断遍历cur

   每次迭代到cur，都将cur的next指向pre,然后pre和cur都前进一位，当迭代完了（cur变为null）,pre就是最后一个节点了

   ![迭代.gif](算法.assets/7d8712af4fbb870537607b1dd95d66c248eb178db4319919c32d9304ee85b602-迭代.gif)

   ```java
   public ListNode reverseList(ListNode head){
       ListNode pre=null;
       ListNode cur=head;
       while(cur!=null){
           ListNode tmp=cur.next;//临时变量保存cur的下一个节点
           cur.next=pre;
           pre=cur;
           cur=tmp;
       }
       return pre;
   }
   ```

   

2. 