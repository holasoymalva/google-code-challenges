# Remove Duplicates from Sorted List

Given the head of a sorted linked list, delete all duplicates such that each element appears only once. Return the linked list sorted as well.

Example 1:
<br/>
<img width="302" height="242" alt="image" src="https://github.com/user-attachments/assets/4c1c0d40-30a9-4817-88ad-77a98563a07d" />

Input: head = [1,1,2]
Output: [1,2]

Example 2:
<br/>
<img width="542" height="222" alt="image" src="https://github.com/user-attachments/assets/5bbd52cc-810a-46fa-a948-a5684503b5bc" />

Input: head = [1,1,2,3,3]
Output: [1,2,3]
 

Constraints:

The number of nodes in the list is in the range [0, 300].
-100 <= Node.val <= 100
The list is guaranteed to be sorted in ascending order.

## Solution

``` javascript

var deleteDuplicates = function(head) {
    if(head == null || head.next == null){
        return head;
    }

    let curr = head;

    while (curr != null && curr.next != null){
        if(curr.val == curr.next.val){
            curr.next = curr.next.next
        }
        else {
            curr= curr.next;
        }
    }
    return head;
};

```

``` typescript

function deleteDuplicates(head: ListNode | null): ListNode | null {
    let res: ListNode = head;

    while (head && head.next){
        if(head.val === head.next.val){
            head.next = head.next.next;
        } else {
            head = head.next;
        }
    }

    return res;
};

```
