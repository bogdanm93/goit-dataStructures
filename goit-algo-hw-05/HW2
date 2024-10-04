def binary_search_algorithm(array, target):
    left = 0
    right = len(array) - 1
    count_iterations = 0
    upper_limit = None

    while left <= right:
        count_iterations += 1
        middle = (left + right) // 2

        if array[middle] < target:
            left = middle + 1
        elif array[middle] > target:
            right = middle - 1
        else:
            return (count_iterations, array[middle])

    # Determine the smallest element greater than or equal to the target
    if left < len(array):
        upper_limit = array[left]
    else:
        upper_limit = None  # No such element exists

    return (count_iterations, upper_limit)

# Demonstration:
sorted_list = [1.3, 1.7, 3.2, 4.5, 5.6]
search_value = 2.7

outcome = binary_search_algorithm(sorted_list, search_value)
print(f"Number of iterations: {outcome[0]}, Upper limit: {outcome[1]}")