remove duplicate elements from an array
Remove duplicate elements in Python
Here, in this section we will discuss the program to remove duplicate elements in python programming language. We will discuss two approaches to solve this program, by using extra space and without using extra space.

Here, we will discuss the following two methods, for removing the duplicate elements from the given array.

Method 1 : Using Auxiliary space.
Method 2 : Without using extra space
Now, let’s discuss the above two methods in brief,

Method 1 :
Declare an array say temp[], as an auxiliary array.
Traverse input array and one by one copy unique elements of arr[] to temp[]. Also keep track of count of unique elements. Let this count be j
Copy j elements from temp[] to arr[] and return j.
Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(n)
Method 1 : Code in Python
Run
# This function returns new size of modified array.
def removeDuplicates(arr, n):
# Return, if array is empty or contains a single element
    if n == 0 or n == 1:
        return n

    temp = list(range(n))

    # Start traversing elements
    j = 0;
    for i in range(0, n-1):
        # If current element is not equal to next element then store that current element
        if arr[i] != arr[i+1]:
            temp[j] = arr[i]
            j += 1

    temp[j] = arr[n-1]
    j += 1

    # Modify original array
    for i in range(0, j):
        arr[i] = temp[i]

    return j

# Driver code
arr = [10, 20, 20, 30, 40, 40, 40, 50, 50]
n = len(arr)

n = removeDuplicates(arr, n)

# Print updated array
for i in range(n):
    print ("%d"%(arr[i]), end = " ")
Output
10 20 30 40 50
Related Pages
Finding the Longest Palindrome in an Array

Counting Distinct Elements in an Array

Finding Non Repeating elements in an Array

Removing Duplicate elements from an array

Finding Minimum scalar product of two vectors

Method 2 (Efficient Approach) :
In this method we will maintain a separate index for same array as maintained for different array in Method 1

Method 2 : Code in Python
Run
# This function returns new size of modified array.
def removeDuplicates(arr, n):

    # Return, if array is empty or contains a single element
    if n == 0 or n == 1:
        return n

    # Start traversing elements
    j = 0;
    for i in range(0, n-1):

        # If current element is not equal to next element then store that current element
        if arr[i] != arr[i+1]:
            arr[j] = arr[i]
            j += 1

    arr[j] = arr[n-1]
    j += 1

    return j

# Driver code
arr = [10, 20, 20, 30, 40, 40, 40, 50, 50]
n = len(arr)

n = removeDuplicates(arr, n)

# Print updated array
for i in range(n):
    print ("%d"%(arr[i]), end = " ")
Output
10 20 30 40 50
