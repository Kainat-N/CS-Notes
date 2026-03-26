# Bubble Sort


## Code
```python
def bubble_sort(self, arr): 
    n = len(arr)
    swapped = False    # A bool to check if any swapping has happened

    for i in range(0, n): 
        swapped = False
        for j in range(0, n-i-1): 
            if arr[j] > arr[j+1]: 
                arr[j], arr[j+1] = arr[j+1], arr[j]
                swapped = True
        if not swapped: 
            break
```
**Time Complexity**: O(n²) --> O(n) best case  
**Space Complexity**: O(1)

---

# Insertion Sort
## Code
```python
def insertion_sort(arr): 
    n = len(arr)
    for i in range(n):
        for j in range(i, 0, -1): 
            if arr[j] < arr[j-1]: 
                arr[j], arr[j-1] = arr[j-1], arr[j]
            else: 
                break
    
    return arr

arr =[5, 4, 3, 2, 1]
print(insertion_sort(arr))
```
**Time Complexity**: O(n²) for all cases  
**Space Complexity**: O(n)

---  

# Selection Sort
## Code
```python
def selection_sort(arr): 
    '''You start from index 0, find the minimum character in the array and swap it with 0'''
    min_index = 0       # This will store the index where we found the min_value

    for i in range(len(arr)): 
        min_index = i
        for  j in range(i, len(arr)): 
            if arr[j] < min_index: 
                min_index = j
            
        arr[i], arr[min_index] = arr[min_index], arr[i]
    return arr
```
**Time Complexity**: O(n²)  
**Space Complexity**: O(1)  

---

# Merge Sort (Divide and Conquer)
## Code
```python
def merge_sorted_array(right, left):
    i = j = 0
    result = []

    while i < len(right) and j < len(left): 
        if right[i] >= left[j]: 
            result.append(left[j])
            j += 1
        else: 
            result.append(right[i])
            i += 1
    
    result.extend(right[i:])
    result.extend(left[j:])
    
    return result

def merge_sort(arr): 
    if len(arr) == 1: 
        return arr
    
    # General Case: 
    middle = len(arr)//2
    sorted_right = merge_sort(arr[:middle])
    sorted_left = merge_sort(arr[middle:])
    return merge_sorted_array(sorted_right, sorted_left)


arr =[5, 4, 3, 2, 1]
print(merge_sort(arr))
```
**Time Complexity**: O(nlogn)  
**Space Complexity**: O(n)

