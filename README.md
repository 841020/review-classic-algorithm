# review-classic-algorithm

# in-place reverse array

```python
# Time complexity O(N)
# Space complexity O(1)
def reverse_array(array):
    length = len(array)
    for index in range(length//2):
        array[index], array[length-index-1] = array[length-index-1], array[index]
```

# in-place reverse linked list

```python
# Time complexity O(N)
# Space complexity O(1)
def reverse_linked_list(head):
    ref_head = None
    while head:
        node = head.next
        head.next = ref_head
        ref_head = head
        head = node
    return ref_head

# recursion solution
# Time complexity O(N)
# Space complexity O(N)
def reverse_linked_list(head):
    def parser(head):
        if not head:
            return None
        elif head.next is None:
            ref_head['output'] = head
            return head
        result = parser(head.next)
        if result is not None:
            head.next = None
            result.next = head
        return head
    ref_head = {'output': None}
    parser(head)
    return ref_head['output']
```

# greatest common divisor

```python
# Space complexity O(1)
def gcd(num1, num2):
    while num2:
        num1, num2 = num2, num1 % num2
    return num1

# recursion solution
# Space complexity O(N)
def gcd(num1, num2):
    if not num2:
        return num1
    return gcd(num2, num1 % num2)
```

# binary search

```python
# Time complexity O(logN)
# Space complexity O(1)
def binary_search(lt, target_num):
    low = 0
    high = len(lt)-1
    while low <= high:
        mid = (low+high)//2
        guess = lt[mid]
        if guess == target_num:
            return True
        if guess > target_num:
            high = mid-1
        else:
            low = mid+1
    return False

# recursion solution
# Time complexity O(logN)
# Space complexity O(N)
def binary_search(low, high):
    if low > high:
        return False
    mid = (low+high)//2
    guess = lt[mid]
    if guess == target_num:
        return True
    if guess > target_num:
        return binary_search(low, mid-1)
    return binary_search(mid+1, high)
```

# in-place merge sort

# in-place quick sort (random pivot)

# breadth-first search (queue)

# depth-first search

```python
# recursion solution
# Time complexity O(N)
# Space complexity O(N)
def dfs(root):
    if root is None:
        return False
    if root.val == target_value:
        return True
    return dfs(root.left) or dfs(root.right)

# stack solution
# Time complexity O(N)
# Space complexity O(N)
def dfs(root):
    stack = [root]
    while stack:
        root = stack.pop()
        if root is None:
            continue
        if root.val == target_value:
            return True
        stack.append(root.left)
        stack.append(root.right)
    return False
```

# primality test
