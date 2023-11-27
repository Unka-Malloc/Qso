# Linked List

#### Easy

* [反转链表](linked-list.md#206.-fan-zhuan-lian-biao)
* [环形链表](linked-list.md#141.-huan-xing-lian-biao)
* [相交链表](linked-list.md#160.-xiang-jiao-lie-biao)

#### Medium

* [反转链表II](linked-list.md#92.-fan-zhuan-lian-biao-ii)
* [环形链表II](linked-list.md#142.-huan-xing-lian-biao-ii)
* 旋转链表
* 排序链表
* 分隔链表
* [两数相加](linked-list.md#2.-liang-shu-xiang-jia)
* 两数相加II

#### Hard

* [合并K个升序链表](linked-list.md#23.-he-bingkge-sheng-xu-lian-biao)
* [K个一组翻转链表](linked-list.md#25.kge-yi-zu-fan-zhuan-lian-biao)

### Answers

#### [206. 反转链表](https://leetcode.cn/problems/reverse-linked-list/description/)

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
      ListNode* prev = nullptr;
      ListNode* curr = head;

      while (curr) {
        ListNode* next = curr -> next;
        curr -> next = prev;
        prev = curr;
        curr = next;
      }

      return prev;
    }
};
```
{% endtab %}

{% tab title="Python" %}
```python
class Solution:
  def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
    prev = None
    curr = head

    while curr:
      temp = currr.next
      curr.next = prev
      prev = curr
      curr = temp
    
    return prev
```
{% endtab %}
{% endtabs %}

#### [141. 环形链表](https://leetcode.cn/problems/linked-list-cycle/description/)

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
  bool hasCycle(ListNode *head) {
    ListNode* slow = head;
    ListNode* fast = head;
    
    while (fast && fast->next) {
      slow = slow->next;
      fast = fast->next->next;
      if (slow == fast) {
        return true;
      }
    }
    
    return false;
  }
};
```
{% endtab %}
{% endtabs %}

#### [160. 相交列表](https://leetcode.cn/problems/intersection-of-two-linked-lists/)

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode* A = headA;
        ListNode* B = headB;
        while (A != B) {
            A = (A != nullptr) ? A->next : headB;
            B = (B != nullptr) ? B->next : headA;
        }
        return A;
    }
};
```
{% endtab %}

{% tab title="Python" %}
```python
class Solution:
  def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> Optional[ListNode]:
    A, B = headA, headB
    while A != B:
      A = A.next if A else headB
      B = B.next if B else headA
    return A
```
{% endtab %}
{% endtabs %}

#### [92. 反转链表II](https://leetcode.cn/problems/reverse-linked-list-ii/description/)

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
  ListNode* reverseBetween(ListNode* head, int left, int right) {
    ListNode* dummy = new ListNode(0, head);

    ListNode* before_left = dummy;

    ListNode* end_of_reversed = nullptr;

    ListNode* prev = nullptr;
    ListNode* curr = dummy;
    ListNode* temp = dummy->next;

    int count = 0;

    while (count <= right) {
      if (count == left - 1) {
        before_left = curr;
        end_of_reversed = curr->next;
      }

      if (count >= left) {
        temp = curr->next;
        curr->next = prev;
        prev = curr;
        curr = temp;
      }
      else {
        curr = curr->next;
      }

      if (count == right) {
        before_left->next = prev;
        end_of_reversed->next = curr;
      }

      count += 1;
    }

    return dummy->next;
  }
};
```
{% endtab %}
{% endtabs %}

#### [142. 环形链表II](https://leetcode.cn/problems/linked-list-cycle-ii/)

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
  ListNode *detectCycle(ListNode *head) {
    ListNode* slow = head;
    ListNode* fast = head;

    do{
      if (fast == nullptr) return nullptr;
      if (fast->next == nullptr) return nullptr;
      
      slow = slow->next;
      fast = fast->next->next;
    } while(slow != fast);
    
    slow = head;
    while(slow != fast){
      slow = slow->next;
      fast = fast->next;
    }

    return slow;
  }
};
```
{% endtab %}
{% endtabs %}

#### [2. 两数相加](https://leetcode.cn/problems/add-two-numbers/description/)

{% tabs %}
{% tab title="Python" %}
```python
class Solution:
  def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
    if not l1 or l1.val == 0:
      return l2
    
    if not l2 or l2.val == 0:
      return l1
    
    buf1 = []
    buf2 = []

    m = 0
    n = 0

    while l1:
      buf1.append(l1.val)
      l1 = l1.next
      m += 1

    while l2:
      buf2.append(l2.val)
      l2 = l2.next
      n += 1

    if m < n:
      buf1 = [0] * (n - m) + buf1
    elif m > n:
      buf2 = [0] * (m - n) + buf2

    tmp = buf1.pop() + buf2.pop()
    one = False
    if tmp >= 10:
      head = ListNode(val=tmp%10)
      one = True
    else:
      head = ListNode(val=tmp)

    for i in range(max(m, n)-1):
      tmp = buf1.pop() + buf2.pop()

      if one:
        tmp += 1
        one = False
      
      if tmp >= 10:
        head = ListNode(tmp%10, head)
        one = True
      else:
        head = ListNode(tmp, head)

    if one:
      head = ListNode(1, head)
    
    return head
```
{% endtab %}

{% tab title="Java" %}
```java
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        int carry = 0;
        ListNode head = null;
        ListNode tail = null;
        
        while (l1 != null || l2 != null) {
            int n1 = (l1 != null) ? l1.val : 0;
            int n2 = (l2 != null) ? l2.val : 0;
            int sum = n1 + n2 + carry;

            if (head == null) {
                head = tail = new ListNode(sum % 10);
            }
            else {
                tail.next = new ListNode(sum % 10);
                tail = tail.next;
            }

            carry = sum / 10;
            if (l1 != null) {
                l1 = l1.next;
            }
            if (l2 != null) {
                l2 = l2.next;
            }
        }
        
        if (carry > 0) {
            tail.next = new ListNode(carry);
        }
        
        return head;
    }
}
```
{% endtab %}
{% endtabs %}

#### [23. 合并K个升序链表](https://leetcode.cn/problems/merge-k-sorted-lists/description/)

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
    ListNode* mergeKLists(vector<ListNode*>& lists) {
      auto cmp = [](const ListNode *a, const ListNode *b) {
        return a->val > b->val;
      };

      priority_queue<ListNode*, vector<ListNode*>, decltype(cmp)> pq;

      for (auto head: lists) {
        if (head) {
          pq.push(head);
        }
      }

      ListNode* dummy = new ListNode();
      ListNode* curr = dummy;
      while (!pq.empty()) {
        auto node = pq.top();

        pq.pop();

        if (node->next) {
          pq.push(node->next);
        }

        curr->next = node;
        curr = curr->next;
      }

      return dummy->next;
    }
};
```
{% endtab %}

{% tab title="Python" %}
```python
class Solution:
  def mergeKLists(self, lists: List[Optional[ListNode]]) -> Optional[ListNode]:
    import heapq

    dummy = ListNode()
    tail = dummy

    priority_queue = []

    for i in range(len(lists)):
      if lists[i]:
        heapq.heappush(priority_queue, (lists[i].val, i))
        lists[i] = lists[i].next # replace the node with next one

    while priority_queue:
      value, index = heapq.heappop(priority_queue)

      tail.next = ListNode(value)  # re-create node
      tail = tail.next

      if lists[index]:
        heapq.heappush(priority_queue, (lists[index].val, index))
        lists[index] = lists[index].next # replace the node with next one

    return dummy.next
```
{% endtab %}
{% endtabs %}

#### [25. K个一组翻转链表](https://leetcode.cn/problems/reverse-nodes-in-k-group/description/)

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
  ListNode* reverseKGroup(ListNode* head, int k) {
    ListNode* dummy = new ListNode(0, head);
    ListNode* before_left = dummy;

    ListNode* left = head;
    ListNode* right = head;

    ListNode* prev = nullptr;
    ListNode* curr = nullptr;
    ListNode* temp = nullptr;

    while (left != nullptr && right != nullptr) {
      for (int i = 1; i < k; i += 1) {
        if (right && right->next) {
          right = right->next;
        } else {
          return dummy->next;
        }
      }

      prev = nullptr;
      curr = left;
      for (int j = 0; j < k; j += 1) {
        temp = curr->next;
        curr->next = prev;
        prev = curr;
        curr = temp;
      }

      before_left->next = prev;
      
      left->next = curr;

      before_left = left;
      
      left = curr;
      right = curr;
    }

    return dummy->next;
  }
};
```
{% endtab %}

{% tab title="Python" %}
```python
class Solution:
  def reverseKGroup(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
    dummy = ListNode(0, head)
    before_left = dummy

    left, right = head, head

    while (left and right):
      count = 1

      while right and count < k:
        count += 1
        if right.next:
          right = right.next
        else:
          return dummy.next

      # simply reverse

      prev, curr = None, left

      for i in range(k):
        tmp = curr.next
        curr.next = prev
        prev = curr
        curr = tmp

      before_left.next = prev

      left.next = curr

      before_left = left
      
      left, right = curr, curr
    
    return dummy.next
```
{% endtab %}
{% endtabs %}
