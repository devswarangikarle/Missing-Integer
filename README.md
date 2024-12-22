# Missing-Integer

In a kingdom of scattered treasures, the king has a list of randomly placed treasure chests, each labeled with a number. However, one treasure chest is missing, and the king needs to find the smallest missing chest number quickly. Your task is to help the king locate the smallest missing chest number using the least time and space possible.
Input
First line of the input contains n number of integers
Second line of the input contains n space-separated integers, representing an array arr (list of integers in unsorted manner.)

Constraints
1 ≤ n ≤ 500000
-2^31 ≤ arr[i] ≤ 2^31 - 1

def smallest_missing_integer(arr):

    n = len(arr)
    for i in range(n):
        while 1 <= arr[i] <= n and arr[i] != arr[arr[i] - 1]:
            # Swap arr[i] to its correct position
            arr[arr[i] - 1], arr[i] = arr[i], arr[arr[i] - 1]
    
    # Find the first missing number
    for i in range(n):
        if arr[i] != i + 1:
            return i + 1
    
    return n + 1

# Input
n = int(input())
arr = list(map(int, input().split()))
print(smallest_missing_integer(arr))
