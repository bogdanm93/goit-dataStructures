import random
import timeit

def perform_merge_sort(arr):
    if len(arr) <= 1:
        return

    mid_point = len(arr) // 2
    left_part = arr[:mid_point]
    right_part = arr[mid_point:]

    perform_merge_sort(left_part)
    perform_merge_sort(right_part)

    i = j = k = 0
    while i < len(left_part) and j < len(right_part):
        if left_part[i] < right_part[j]:
            arr[k] = left_part[i]
            i += 1
        else:
            arr[k] = right_part[j]
            j += 1
        k += 1

    while i < len(left_part):
        arr[k] = left_part[i]
        i += 1
        k += 1

    while j < len(right_part):
        arr[k] = right_part[j]
        j += 1
        k += 1

def perform_insertion_sort(arr):
    for i in range(1, len(arr)):
        key_item = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key_item:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key_item

def evaluate_time(sort_function, array):
    return timeit.timeit(lambda: sort_function(array.copy()), number=1)

def generate_random_array(size):
    return [random.randint(0, 100000) for _ in range(size)]

def execute_tests():
    array_sizes = [100, 1000, 10000]
    for size in array_sizes:
        print(f"\nEvaluating performance for array size: {size}")
        array = generate_random_array(size)

        merge_sort_time = evaluate_time(perform_merge_sort, array)
        insertion_sort_time = evaluate_time(perform_insertion_sort, array)
        timsort_time = evaluate_time(sorted, array)

        print(f"Merge Sort Execution Time: {merge_sort_time:.6f} seconds")
        print(f"Insertion Sort Execution Time: {insertion_sort_time:.6f} seconds")
        print(f"Timsort (Python's sorted) Execution Time: {timsort_time:.6f} seconds")

if __name__ == "__main__":
    execute_tests()