11111
import random
import time

# Deterministic Quick Sort
def deterministic_quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[0]
    less = [x for x in arr[1:] if x <= pivot]
    greater = [x for x in arr[1:] if x > pivot]
    return deterministic_quick_sort(less) + [pivot] + deterministic_quick_sort(greater)

def deterministic_quick_sort1(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[-1]  # Choose the last element as the pivot
    less = [x for x in arr[:-1] if x <= pivot]
    greater = [x for x in arr[:-1] if x > pivot]
    return deterministic_quick_sort1(less) + [pivot] + deterministic_quick_sort1(greater)

# Randomized Quick Sort
def randomized_quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = random.choice(arr)
    less = [x for x in arr if x < pivot]
    equal = [x for x in arr if x == pivot]
    greater = [x for x in arr if x > pivot]
    return randomized_quick_sort(less) + equal + randomized_quick_sort(greater)

# Measure execution time
def measure_execution_time(sort_function, arr):
    start_time = time.time()
    sorted_array = sort_function(arr)
    end_time = time.time()
    execution_time = end_time - start_time
    return execution_time, sorted_array

if __name__ == "__main__":
    random.seed(42)  # For consistent results with randomized Quick Sort
    arr = [random.randint(1, 1000) for _ in range(1000)]
    det_time, det_sorted = measure_execution_time(deterministic_quick_sort, arr.copy())
    det_time1, det_sorted1 = measure_execution_time(deterministic_quick_sort1, arr.copy())
    rand_time, rand_sorted = measure_execution_time(randomized_quick_sort, arr.copy())

    print("Deterministic Quick Sort (low pivot)")
    print("Execution Time:", det_time, "seconds")
    # Uncomment the next line to print the sorted array:
    # print("Sorted Array:", det_sorted)

    print("Deterministic Quick Sort (high pivot)")
    print("Execution Time:", det_time1, "seconds")
    # Uncomment the next line to print the sorted array:
    # print("Sorted Array:", det_sorted1)

    print("\nRandomized Quick Sort:")
    print("Execution Time:", rand_time, "seconds")
    # Uncomment the next line to print the sorted array:
    # print("Sorted Array:", rand_sorted)



2222
import random

def quicksort(arr, start, stop):
    if start < stop:
        # pivotindex is the index where the pivot lies in the array
        pivotindex = partitionrandom(arr, start, stop)
        # At this stage, the array is partially sorted around the pivot.
        # Separately sorting the left half of the array and the right half of the array.
        quicksort(arr, start, pivotindex - 1)
        quicksort(arr, pivotindex + 1, stop)

def partitionrandom(arr, start, stop):
    # Generating a random number between the starting index of the array and the ending index of the array.
    randpivot = random.randrange(start, stop)
    # Swapping the starting element of the array and the pivot
    arr[start], arr[randpivot] = arr[randpivot], arr[start]
    return partition(arr, start, stop)

def partition(arr, start, stop):
    pivot = start  # pivot
    i = start + 1  # a variable to memorize where the partition in the array starts from.
    for j in range(start + 1, stop + 1):
        # If the current element is smaller or equal to the pivot, shift it to the left side of the partition.
        if arr[j] <= arr[pivot]:
            arr[i], arr[j] = arr[j], arr[i]
            i = i + 1
    arr[pivot], arr[i - 1] = arr[i - 1], arr[pivot]
    pivot = i - 1
    return pivot

if __name__ == "__main__":
    array = [11, 7, 8, 9, 1, 5]
    print("Unsorted array: ")
    print(array)
    print("The length is:", len(array))  # Length is 6
    quicksort(array, 0, len(array) - 1)
    print("The sorted array is: ")
    print(array)



3333
import random
import time

# Deterministic Quick Sort
def deterministic_quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[0]
    less = [x for x in arr[1:] if x <= pivot]
    greater = [x for x in arr[1:] if x > pivot]
    return deterministic_quick_sort(less) + [pivot] + deterministic_quick_sort(greater)

def deterministic_quick_sort1(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[-1]  # Choose the last element as the pivot
    less = [x for x in arr[:-1] if x <= pivot]
    greater = [x for x in arr[:-1] if x > pivot]
    return deterministic_quick_sort1(less) + [pivot] + deterministic_quick_sort1(greater)

# Randomized Quick Sort
def randomized_quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = random.choice(arr)
    less = [x for x in arr if x < pivot]
    equal = [x for x in arr if x == pivot]
    greater = [x for x in arr if x > pivot]
    return randomized_quick_sort(less) + equal + randomized_quick_sort(greater)

# Measure execution time
def measure_execution_time(sort_function, arr):
    start_time = time.time()
    sorted_array = sort_function(arr)
    end_time = time.time()
    execution_time = end_time - start_time
    return execution_time, sorted_array

if __name__ == "__main__":
    random.seed(42)  # For consistent results with randomized Quick Sort
    arr = [random.randint(1, 1000) for _ in range(1000)]
    det_time, det_sorted = measure_execution_time(deterministic_quick_sort, arr.copy())
    det_time1, det_sorted1 = measure_execution_time(deterministic_quick_sort1, arr.copy())
    rand_time, rand_sorted = measure_execution_time(randomized_quick_sort, arr.copy())

    print("Deterministic Quick Sort (low pivot)")
    print("Execution Time:", det_time, "seconds")
    # Uncomment the next line to print the sorted array:
    # print("Sorted Array:", det_sorted)

    print("Deterministic Quick Sort (high pivot)")
    print("Execution Time:", det_time1, "seconds")
    # Uncomment the next line to print the sorted array:
    # print("Sorted Array:", det_sorted1)

    print("\nRandomized Quick Sort:")
    print("Execution Time:", rand_time, "seconds")
    # Uncomment the next line to print the sorted array:
    # print("Sorted Array:", rand_sorted)
