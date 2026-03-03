# PABL_PythonProgrammingCourse

Q1. You are given an array of integers arr[]. You have to reverse the given array.

**Note:** Modify the array in place.
```python
def reverse_array(arr):
    left,right=0,len(arr)-1
    while left<right:
        arr[left],arr[right]=arr[right],arr[left]
        left+=1
        right-=1
# Example
arr = [1, 4, 3, 2, 6, 5]
reverse_array(arr)
print(arr)
```
<img width="1920" height="895" alt="Screenshot (428)" src="https://github.com/user-attachments/assets/a8ad6f3b-9009-4e4c-b135-d75cf9f458f7" />
Q2. Given an array arr[]. Your task is to find the minimum and maximum elements in the array.

```python
def find_min_max(arr):
    if not arr:
        return None
    min=arr[0]
    max=arr[0]
    for i in range(1,len(arr)):
        if arr[i] < min:
            min = arr[i]
        if arr[i] > max:
            max = arr[i]
    return [min,max]
# Example
arr = [1, 4, 3, 2, 6, 5]
print(find_min_max(arr))
```
<img width="1920" height="901" alt="Screenshot (430)" src="https://github.com/user-attachments/assets/b2db32e1-3871-4c7a-abce-84515be45761" />
Q3. Given an integer array arr[] and an integer k, your task is to find and return the kth smallest element in the given array.

**Note:** The kth smallest element is determined based on the sorted order of the array.
```python
def kth_smallest(arr,k):
    arr.sort()
    return arr[k-1]
# Example
arr= [10, 5, 4, 3, 48, 6, 2, 33, 53, 10]
print(kth_smallest(arr, 4))
```
<img width="1920" height="914" alt="Screenshot (431)" src="https://github.com/user-attachments/assets/af37af96-7893-4208-9444-daf971bb116e" />
Q4. You are given two arrays a[] and b[], return the Union of both the arrays in any order.

The Union of two arrays is a collection of all distinct elements present in either of the arrays. If an element appears more than once in one or both arrays, it should be included only once in the result.

**Note:** Elements of a[] and b[] are not necessarily distinct. Note that, You can return the Union in any order but the driver code will print the result in sorted order only.
```python
def find_union(a, b):
    return list(set(a)|set(b))
# Example
a = [1, 2, 3, 4, 5]
b = [1, 2, 3, 6, 7]
print(sorted(find_union(a, b)))
```
<img width="1920" height="901" alt="Screenshot (432)" src="https://github.com/user-attachments/assets/e8158ec6-2c4a-4849-8c33-62c26d6c4ebe" />
Q5. Given an array arr[]. The task is to find the largest element and return it.

```python
def largest(arr):
    max=arr[0]
    for i in range(1,len(arr)):
        if arr[i]>max:
            max=arr[i]
    return max
# Example
arr= [10, 5, 4, 3, 48, 6, 2, 33, 53, 10]
print(largest(arr))
```
<img width="1920" height="893" alt="Screenshot (433)" src="https://github.com/user-attachments/assets/953f5d37-438b-4b08-9273-e0893e39b41c" />
Q6. Given an array arr, rotate the array by one position in clockwise direction.

```python
def rotate(arr):
    if len(arr)==0:
        return arr
    last=arr[-1]
    for i in range(len(arr)-1,0,-1):
        arr[i]=arr[i - 1]
    arr[0]=last
    return arr
# Example
arr = [1, 2, 3, 4, 5]
print(rotate(arr))
```
<img width="1920" height="907" alt="Screenshot (434)" src="https://github.com/user-attachments/assets/9092a800-9d6e-4e25-b5da-89b4a0e18da4" />
Q7. You are given an integer array arr[]. You need to find the maximum sum of a subarray (containing at least one element) in the array arr[].

**Note :** A subarray is a continuous part of an array.
```python
def max_subarray_sum(arr):
    max_sum=arr[0]
    current_sum=arr[0]
    for i in range(1,len(arr)):
        current_sum=max(arr[i],current_sum+arr[i])
        max_sum=max(max_sum,current_sum)
    return max_sum
# Example
arr = [-2, 1, -3, 4, -1, 2, 1, -5, 4]
print(max_subarray_sum(arr))
```
<img width="1920" height="905" alt="Screenshot (435)" src="https://github.com/user-attachments/assets/423f6fdc-d93b-4edb-a1a4-401cba5e1dbe" />
Q8. Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with O(log n) runtime complexity.
```python
def search_insert(nums, target):
    left,right=0,len(nums)-1
    while left<=right:
        mid=(left+right)//2
        if nums[mid]==target:
            return mid
        elif nums[mid]<target:
            left = mid + 1
        else:
            right = mid - 1
    return left
# Examples
print(search_insert([1, 3, 5, 6], 5))
```
<img width="1920" height="896" alt="Screenshot (436)" src="https://github.com/user-attachments/assets/abef5e13-abe9-476e-bcf4-0a52c39219ec" />
Q9. Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.
```python
def two_sum(nums,target):
    for i in range(len(nums)):
        for j in range(i+1,len(nums)):
            if nums[i]+nums[j]==target:
                return [i,j]
    return []
# Example
print(two_sum([2, 7, 11, 15],9))
```
<img width="1920" height="898" alt="Screenshot (437)" src="https://github.com/user-attachments/assets/8af9568a-c81d-4ee2-b017-b337dd46ec89" />
Q10. You are given an array arr[] of non-negative numbers. Each number tells you the maximum number of steps you can jump forward from that position.

For example:
  • If arr[i] = 3, you can jump to index i + 1, i + 2, or i + 3 from position i.
  • If arr[i] = 0, you cannot jump forward from that position.
  
Your task is to find the minimum number of jumps needed to move from the first position in the array to the last position.

**Note:** Return -1 if you can't reach the end of the array.
```python
def min_jumps(arr):
    n=len(arr)
    if n<=1:
        return 0
    if arr[0]==0:
        return -1
    jumps=0           # Total jumps taken
    current_end=0     # End of current jump range
    farthest=0        # Farthest index reachable
    for i in range(n-1):
        farthest=max(farthest,i+arr[i])
        if i==current_end:
            jumps+=1
            current_end=farthest
            if current_end>=n-1:
                return jumps
    return -1
# Examples
print(min_jumps([1, 3, 5, 8, 9, 2, 6, 7, 6, 8, 9]))
```
<img width="1920" height="902" alt="Screenshot (438)" src="https://github.com/user-attachments/assets/ed45cf15-547c-4801-b5d6-5a2e9f8840e8" />
Q11. Given an integer array arr[] and an integer k, your task is to find and return the kth smallest element in the given array.

**Note:** The kth smallest element is determined based on the sorted order of the array.
```python
def kthSmallest(arr,k):
        arr.sort()
        return arr[k-1]
# Examples
print(kthSmallest([10, 5, 4, 3, 48, 6, 2, 33, 53, 10],4))
```
<img width="1920" height="912" alt="Screenshot (439)" src="https://github.com/user-attachments/assets/0cb1110d-3c49-4c01-8872-6295f957c9cc" />
Q12. Given an array arr[] denoting heights of n towers and a positive integer k.

For each tower, you must perform exactly one of the following operations exactly once.

Increase the height of the tower by k

Decrease the height of the tower by k

Find out the minimum possible difference between the height of the shortest and tallest towers after you have modified each tower.

You can find a slight modification of the problem here.

**Note:** It is compulsory to increase or decrease the height by k for each tower. After the operation, the resultant array should not contain any negative integers.
```python
def getMinDiff(arr,k):
    n=len(arr)
    if n==1:
        return 0
    arr.sort()
    result=arr[-1]-arr[0]
    for i in range(1, n):
        min_h=min(arr[0]+k,arr[i]-k)
        max_h=max(arr[-1]-k,arr[i-1]+k)
        if min_h<0:
            continue
        result = min(result, max_h - min_h)
    return result
# Examples
print(getMinDiff([1, 5, 8, 10], 2))
```
<img width="1920" height="908" alt="Screenshot (440)" src="https://github.com/user-attachments/assets/29eed8e2-0122-4dd5-8a0a-b96f1b42f8b6" />
Q13. You are given an array arr[] of non-negative numbers. Each number tells you the maximum number of steps you can jump forward from that position.

For example:

   If arr[i] = 3, you can jump to index i + 1, i + 2, or i + 3 from position i.
   
   If arr[i] = 0, you cannot jump forward from that position.

Your task is to find the minimum number of jumps needed to move from the first position in the array to the last position.
```python
def min_jumps(arr):
    n=len(arr)
    if n<=1:
        return 0
    if arr[0]==0:
        return -1
    jumps=0           # Total jumps taken
    current_end=0     # End of current jump range
    farthest=0        # Farthest index reachable
    for i in range(n-1):
        farthest=max(farthest,i+arr[i])
        if i==current_end:
            jumps+=1
            current_end=farthest
            if current_end>=n-1:
                return jumps
    return -1
# Examples
print(min_jumps([1, 3, 5, 8, 9, 2, 6, 7, 6, 8, 9]))
```
<img width="1920" height="905" alt="Screenshot (441)" src="https://github.com/user-attachments/assets/34fd48f1-6ca2-487c-8d9f-7a18e731fd32" />
Q14. Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive.

There is only one repeated number in nums, return this repeated number.

You must solve the problem without modifying the array nums and using only constant extra space.
```python
def find_duplicate(nums):
    slow=nums[0]
    fast=nums[0]
    while True:
        slow=nums[slow]           # Move 1 step
        fast=nums[nums[fast]]     # Move 2 steps
        if slow==fast:
            break
    slow=nums[0]
    while slow!=fast:
        slow=nums[slow]
        fast=nums[fast]
    return slow
# Examples
print(find_duplicate([1, 3, 4, 2, 2]))
```
<img width="1920" height="904" alt="Screenshot (442)" src="https://github.com/user-attachments/assets/44422a7d-79a2-49e8-8381-76d2ca578134" />
Q15. Given two sorted arrays a[] and b[] of size n and m respectively, the task is to merge them in sorted order without using any extra space. Modify a[] so that it contains the first n elements and modify b[] so that it contains the last m elements.

```python
def merge_arrays(a, b):
    n,m=len(a),len(b)
    i=n-1
    j=0
    while i>=0 and j<m:
        if a[i] > b[j]:
            a[i],b[j] = b[j],a[i]
            i-=1
            j+=1
        else:
            break
    a.sort()
    b.sort()
    return a, b
# Example
a=[2, 4, 7, 10]
b=[2, 3]
print(merge_arrays(a, b))
```
<img width="1920" height="907" alt="Screenshot (443)" src="https://github.com/user-attachments/assets/517e6c7b-48e9-47ee-8ac4-a440291d0ccc" />
Q16. Given an array of intervals where intervals[i] = [starti, endi], merge all overlapping intervals, and return an array of the non-overlapping intervals that cover all the intervals in the input.

```python
def merge(intervals):
    if not intervals:
        return []
    # Sort by start time
    intervals.sort(key=lambda x: x[0])
    merged=[intervals[0]]
    for start,end in intervals[1:]:
        last_end=merged[-1][1]
        if start<=last_end:              # Overlapping intervals
            merged[-1][1]=max(last_end,end)  # Extend the interval
        else:
            merged.append([start,end])   # Non-overlapping, add new
    return merged
# Examples
print(merge([[1,4],[4,5]]))
```
<img width="1920" height="901" alt="Screenshot (444)" src="https://github.com/user-attachments/assets/282caf22-c9e8-4472-a5e5-505bb9ec81d4" />
Q17. Given three sorted arrays in non-decreasing order, print all common elements in non-decreasing order across these arrays. If there are no such elements return an empty array. In this case, the output will be -1.

**Note:** can you handle the duplicates without using any additional Data Structure?
```python
def common_elements(a, b, c):
    i,j,k=0,0,0
    result=[]
    while i<len(a) and j<len(b) and k<len(c):
        if a[i]==b[j]==c[k]:
            result.append(a[i])
            i+=1
            j+=1
            k+=1
            # Skip duplicates in all three arrays
            while i<len(a) and a[i]==a[i-1]: i+=1
            while j<len(b) and b[j]==b[j-1]: j+=1
            while k<len(c) and c[k]==c[k-1]: k+=1
        # Advance the pointer with the smallest value
        elif a[i]<=b[j] and a[i]<=c[k]:
            i+=1
        elif b[j]<=a[i] and b[j]<=c[k]:
            j+=1
        else:
            k+=1
    return result if result else [-1]
# Examples
print(common_elements([1,5,10,20,40,80],
                      [6,7,20,80,100],
                      [3,4,15,20,30,70,80,120]))
```
<img width="1920" height="902" alt="Screenshot (445)" src="https://github.com/user-attachments/assets/a55405ab-0e61-4079-a5bf-4d1fe770f2df" />
Q18. Given an integer n, find its factorial. Return a list of integers denoting the digits that make up the factorial of n.

```python
def factorial(n):
    fact = 1
    for i in range(2, n + 1):
        fact *= i
    return [int(digit) for digit in str(fact)]
# Examples
print(factorial(5))
```
<img width="1920" height="906" alt="Screenshot (446)" src="https://github.com/user-attachments/assets/2d505f75-3781-4f7e-b8a4-12d4162cb3de" />
Q19. Given two arrays a[] and b[], your task is to determine whether b[] is a subset of a[].

```python
from collections import Counter
def is_subset(a, b):
    freq_a = Counter(a)
    for num in b:
        if freq_a[num]<=0:
            return False
        freq_a[num]-=1
    return True
# Examples
a= [11, 7, 1, 13, 21, 3, 7, 3]
b= [11, 3, 7, 1, 7]
print(is_subset(a, b))
```
<img width="1920" height="908" alt="Screenshot (447)" src="https://github.com/user-attachments/assets/ada5b63b-c6da-4202-b09f-34bedbd417ba" />
Q20. Given an array arr[] and an integer target, determine if there exists a triplet in the array whose sum equals the given target.

Return true if such a triplet exists, otherwise, return false.
```python
def has_triplet_sum(arr, target):
    arr.sort()
    n=len(arr)
    for i in range(n-2):
        left=i+1
        right=n-1
        while left<right:
            current_sum=arr[i]+arr[left]+arr[right]
            if current_sum==target:
                return True
            elif current_sum<target:
                left+=1
            else:
                right-=1
    return False
    # Examples
    print(has_triplet_sum([1, 4, 45, 6, 10, 8], 13))
```
<img width="1920" height="908" alt="Screenshot (448)" src="https://github.com/user-attachments/assets/ce08f237-87ea-40d1-8ceb-87236c83140b" />
Q21. Given an array arr[] with non-negative integers representing the height of blocks. 

If the width of each block is 1, compute how much water can be trapped between the blocks during the rainy season.
```python
def max_water(arr):
    n=len(arr)
    if n<3:
        return 0
    left=0
    right=n-1
    left_max=0
    right_max=0
    water=0
    while left<right:
        if arr[left]<arr[right]:
            if arr[left]>=left_max:
                left_max=arr[left]
            else:
                water+=left_max-arr[left]
            left+=1
        else:
            if arr[right]>=right_max:
                right_max=arr[right]
            else:
                water+=right_max-arr[right]
            right-=1
    return water
# Examples
arr = [3, 0, 1, 0, 4, 0, 2]
print(max_water(arr))
```
<img width="1920" height="904" alt="Screenshot (449)" src="https://github.com/user-attachments/assets/95fbf98b-abc8-4e96-bdce-67cce142e228" />
Q22. Given an array arr[] of positive integers, where each value represents the number of chocolates in a packet. Each packet can have a variable number of chocolates. There are m students, the task is to distribute chocolate packets among m students such that - 

  i. Each student gets exactly one packet. 
  
  ii. The difference between maximum number of chocolates given to a student and minimum number of chocolates given to a student is minimum and return that minimum possible difference.
```python
def findMinDiff(arr, m):
    n=len(arr)
    if m==0 or n==0 or m>n:
        return 0
    arr.sort()
    min_diff=float('inf')
    for i in range(n-m+1):
        diff=arr[i+m-1]-arr[i]
        min_diff=min(min_diff,diff)
    return min_diff
# Examples
arr = [3, 4, 1, 9, 56, 7, 9, 12]
m = 5
print(findMinDiff(arr, m))
```
<img width="1920" height="900" alt="Screenshot (450)" src="https://github.com/user-attachments/assets/cde8f25b-25ff-4ced-a43d-80bf32fb2468" />
Q23. Given a number x and an array of integers arr, find the smallest subarray with sum greater than the given value. If such a subarray do not exist return 0 in that case.

```python
def smallest_subarray_with_sum(arr, x):
    n=len(arr)
    min_length=float('inf')
    current_sum=0
    left=0
    for right in range(n):
        current_sum+=arr[right]
        while current_sum>x:
            min_length=min(min_length,right-left+1)
            current_sum-=arr[left]
            left+=1
    return 0 if min_length==float('inf') else min_length
# Examples
arr = [1, 4, 45, 6, 10, 19]
x = 51
print(smallest_subarray_with_sum(arr, x))
```
<img width="1920" height="907" alt="Screenshot (451)" src="https://github.com/user-attachments/assets/330c76b5-e2da-4252-9928-4ba6dbe5d2d2" />
Q24.Given an array and a range a, b. The task is to partition the array around the range such that the array is divided into three parts. 

1) All elements smaller than a come first.

2) All elements in range a to b come next.

3) All elements greater than b appear in the end.

The individual elements of three sets can appear in any order. You are required to return the modified array.

**Note:** The generated output is true if you modify the given array successfully. Otherwise false.

**Geeky Challenge:** Solve this problem in O(n) time complexity.
```python
def threeWayPartition(arr, a, b):
  try:
    low=0
    mid=0
    high=len(arr)-1
    while mid<=high:
        if arr[mid]<a:
            # Element belongs to left partition
            arr[low],arr[mid]=arr[mid],arr[low]
            low+=1
            mid+=1
        elif arr[mid]>b:
            # Element belongs to right partition
            arr[mid],arr[high]=arr[high],arr[mid]
            high-=1
        else:
            mid+=1
    for i in range(len(arr)):
            if i < low and arr[i] >= a:
                return False
            if i >= low and i < mid and (arr[i] < a or arr[i] > b):
                return False
            if i >= mid and arr[i] <= b:
                return False
    return True

  except:
    return False
# Examples
print(threeWayPartition([1, 2, 3, 3, 4], 1, 2))
```
<img width="1920" height="904" alt="Screenshot (452)" src="https://github.com/user-attachments/assets/39613c83-f0f1-4ce3-9a5d-8bac4f18fabd" />
Q25. Given an array arr and a number k. One can apply a swap operation on the array any number of times, i.e choose any two index i and j (i < j) and swap arr[i] , arr[j] . Find the minimum number of swaps required to bring all the numbers less than or equal to k together, i.e. make them a contiguous subarray.

```python
def min_swaps(arr, k):
    n=len(arr)
    # Step 1: Count total elements <= k
    count=sum(1 for x in arr if x<=k)
    if count==0 or count==n:
        return 0
    # Step 2: Count elements > k in first window of size count
    bad=sum(1 for i in range(count) if arr[i]>k)
    # Step 3: Slide the window
    min_bad=bad
    for i in range(1,n-count+1):
        # Remove outgoing element (left of window)
        if arr[i-1]>k:
            bad-=1
        # Add incoming element (right of window)
        if arr[i+count-1]>k:
            bad+=1
        min_bad=min(min_bad,bad)
    return min_bad
# Examples
print(min_swaps([2, 1, 5, 6, 3], 3))
```
<img width="1920" height="902" alt="Screenshot (453)" src="https://github.com/user-attachments/assets/19fa74ba-af3f-425c-9f88-1e1fcffcf0be" />
Q26. Given an array arr[] of positive integers. Return true if all the array elements are palindrome otherwise, return false.

```python
def is_palindrome(num):
    s = str(num)
    return s == s[::-1]
def all_palindromes(arr):
    for num in arr:
        if not is_palindrome(num):
            return False
    return True
# Examples
print(all_palindromes([111, 222, 333, 444, 555]))
```
<img width="1920" height="909" alt="Screenshot (454)" src="https://github.com/user-attachments/assets/8111c69b-c568-4255-99d4-6fc54060279e" />
Q27. Given an array arr[] of integers, calculate the median.

```python
def find_median(arr):
    arr.sort()
    n=len(arr)
    if n%2!=0:
        return arr[n//2]
    else:
        return (arr[n//2-1]+arr[n//2])/2
# Examples
print(find_median([90, 100, 78, 89, 67]))
```
<img width="1920" height="904" alt="Screenshot (455)" src="https://github.com/user-attachments/assets/b1c0dd18-805f-4261-aba6-af4bc473733f" />
Q28. You are given a rectangular matrix mat[][] of size n x m, and your task is to return an array while traversing the matrix in spiral form.

```python
def spirallyTraverse(mat):
    result=[]
    if not mat:
        return result
    top=0
    bottom=len(mat)-1
    left=0
    right=len(mat[0])-1
    while top<=bottom and left<=right:
        # Move Right → along top row
        for i in range(left,right+1):
            result.append(mat[top][i])
        top+=1
        # Move Down ↓ along right column
        for i in range(top,bottom+1):
            result.append(mat[i][right])
        right-=1
        # Move Left ← along bottom row
        if top<=bottom:
            for i in range(right,left-1,-1):
                result.append(mat[bottom][i])
            bottom-=1
        # Move Up ↑ along left column
        if left<=right:
            for i in range(bottom,top-1,-1):
                result.append(mat[i][left])
            left+=1
    return result
# Examples
mat1 = [[1,  2,  3,  4],
        [5,  6,  7,  8],
        [9,  10, 11, 12],
        [13, 14, 15, 16]]
print(spirallyTraverse(mat1))
```
<img width="1920" height="900" alt="Screenshot (456)" src="https://github.com/user-attachments/assets/7c7c2055-4e9a-4a85-bdcc-cae2daaca138" />
Q29.  You are given an m x n integer matrix matrix with the following two properties:

   • Each row is sorted in non-decreasing order.

   • The first integer of each row is greater than the last integer of the previous row.

Given an integer target, return true if target is in matrix or false otherwise.

You must write a solution in O(log(m * n)) time complexity.
```python
def search_matrix(matrix,target):
    m=len(matrix)
    n=len(matrix[0])
    left=0
    right=m*n-1
    while left<=right:
        mid=(left+right)//2
        # Convert 1D mid index → 2D row, col
        row=mid//n
        col=mid%n
        val=matrix[row][col]
        if val==target:
            return True
        elif val<target:
            left=mid+1
        else:
            right=mid-1
    return False
# Examples
matrix1 = [[1,  3,  5,  7],
           [10, 11, 16, 20],
           [23, 30, 34, 60]]
print(search_matrix(matrix1, 3))
```
<img width="1920" height="891" alt="Screenshot (457)" src="https://github.com/user-attachments/assets/f23f0fca-368c-450e-8c37-5c441a21fad2" />
Q30. Given a row-wise sorted matrix mat[][] of size n*m, where the number of rows and columns is always odd. Return the median of the matrix.

```python
def median(mat):
    n=len(mat)
    m=len(mat[0])
    total=n*m
    required=total//2+1
    low =min(row[0]  for row in mat)
    high=max(row[-1] for row in mat)
    def count_less_equal(mid):
        """Count elements <= mid using binary search on each row"""
        count=0
        for row in mat:
            # Binary search in each sorted row
            lo,hi=0,m
            while lo<hi:
                pivot=(lo+hi)//2
                if row[pivot]<=mid:
                    lo=pivot+1
                else:
                    hi=pivot
            count+=lo
        return count
    # Binary search on answer
    while low<=high:
        mid=(low+high)//2
        if count_less_equal(mid)<required:
            low=mid+1
        else:
            high=mid-1
    return low
# Examples
print(median([[1, 3, 5],
              [2, 6, 9],
              [3, 6, 9]]))
```
<img width="1920" height="912" alt="Screenshot (458)" src="https://github.com/user-attachments/assets/caeb66b4-fd90-47c3-9c29-f22d4d71c5f8" />
Q31. You are given a 2D binary array arr[][] consisting of only 1s and 0s. Each row of the array is sorted in non-decreasing order. Your task is to find and return the index of the first row that contains the maximum number of 1s. If no such row exists, return -1.

Note:   • The array follows 0-based indexing.
        • The number of rows and columns in the array are denoted by n and m respectively.
```python
def row_with_max_ones(arr):
    n=len(arr)
    m=len(arr[0])
    max_ones=0
    result=-1
    for i in range(n):
        lo,hi=0,m-1
        first_one=m
        while lo<=hi:
            mid=(lo+hi)//2
            if arr[i][mid]==1:
                first_one=mid
                hi=mid-1
            else:
                lo=mid+1
        ones_count=m-first_one
        if ones_count>max_ones:
            max_ones=ones_count
            result=i
    return result
# Examples
print(row_with_max_ones([[0,1,1,1],
                          [0,0,1,1],
                          [1,1,1,1],
                          [0,0,0,0]]))
```
<img width="1920" height="897" alt="Screenshot (459)" src="https://github.com/user-attachments/assets/bc8e42b1-6526-4ea6-b5d2-5f5b1ff47c34" />













