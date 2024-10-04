For small datasets (Size: 100), both Insertion Sort and Merge Sort perform relatively well, but Timsort is the quickest due to its optimized implementation in Python's sorted function. As the dataset size grows, Insertion Sort becomes much slower compared to Merge Sort and Timsort. Merge Sort maintains steady performance with increasing array sizes, while Insertion Sort's efficiency drops significantly. Timsort consistently surpasses both Merge Sort and Insertion Sort across all sizes, particularly with larger arrays, showcasing its superior efficiency and effectiveness in sorting. These findings validate the expected performance of these sorting algorithms, with Timsort excelling, especially with larger datasets.

Evaluating performance for array size: 100 Merge Sort Execution Time: 0.000187 seconds Insertion Sort Execution Time: 0.000247 seconds Timsort (Python's sorted) Execution Time: 0.000010 seconds

Evaluating performance for array size: 1000 Merge Sort Execution Time: 0.002379 seconds Insertion Sort Execution Time: 0.027072 seconds Timsort (Python's sorted) Execution Time: 0.000109 seconds

Evaluating performance for array size: 10000 Merge Sort Execution Time: 0.033295 seconds Insertion Sort Execution Time: 2.777143 seconds Timsort (Python's sorted) Execution Time: 0.001199 seconds
