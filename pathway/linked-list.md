# Linked List

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

      auto dummy = new ListNode();
      auto cur = dummy;
      while (!pq.empty()) {
        auto node = pq.top();

        pq.pop();

        if (node->next) {
          pq.push(node->next);
        }

        cur->next = node;
        cur = cur->next;
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
