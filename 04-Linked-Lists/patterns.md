# Linked Lists

Lists are a fundamental ADT; interview questions often become pointer-invariant exercises.

## Fast & Slow Pointers

Recognize middle-node, cycle, and meeting-point problems.

~~~cpp
ListNode* slow = head;
ListNode* fast = head;

while (fast && fast->next) {
    slow = slow->next;
    fast = fast->next->next;
}
~~~

## Reversal

Invariant: prev is the reversed prefix; cur is the first unprocessed node.

~~~cpp
ListNode* prev = nullptr;
ListNode* cur = head;

while (cur) {
    ListNode* next = cur->next;
    cur->next = prev;
    prev = cur;
    cur = next;
}

return prev;
~~~

## Dummy node

Use a dummy node when head insertion/deletion creates repeated special cases.

**Common mistake:** save cur->next before changing the link.
