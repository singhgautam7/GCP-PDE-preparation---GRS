## Windowing
- Windowing is the process of taking a small subset of a larger dataset, for processing and analysis. 
- A naive approach, the rectangular window, involves simply truncating the dataset before and after the window, while not modifying the contents of the window at all.
- Types:
    1. **Fixed Window**:
        - Windows of fixed interval duration, uniform across all the keys, no overlaps between two consecutive widows.
        - Also Known as Tumbling Window
        - Use cases — any aggregation use cases, any batch analysis of data, relatively simple use cases.
    2. **Sliding Window**:
        - Windows of fixed interval duration, uniform across all the keys, overlap between two windows (same element can be present in multiple windows)
        - Also Known as Hopping Window
        - Use cases — Moving averages of data
    3. **Session Window**:
        - Windows of dynamically set intervals, non-uniform across keys (different windows for different keys, different window sizes for each key), no overlap between two windows
        - Use cases — user session data, click data, real time gaming data analysis

![Different types of windows](https://www.oreilly.com/radar/wp-content/uploads/sites/3/2020/02/Figure-03-Windowing.jpg)

## Window functions or Analytic functions
- Analytic functions are those which compute values over groups of rows, returning a single result for each of the rows.
- This is like the annotate function in django.
