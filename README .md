# Data Type Memory & Performance Benchmark Lab

**Author:** Mohit Sharma\
**Environment:** Google Colab\
**Language:** Python\
**Core Library:** NumPy

## Overview

The **Data Type Memory & Performance Benchmark Lab** is a small
data-management and numerical-computing project built in Python using
NumPy. It explores how NumPy data types affect array memory usage and
compares a standard Python loop with a NumPy vectorized operation.

The notebook generates a reproducible dataset of 200,000 random
integers, examines basic statistics, compares memory requirements,
demonstrates floating-point precision, benchmarks two calculation
approaches, and visualizes the results with Matplotlib.

## Objectives

-   Create and inspect a NumPy array containing 200,000 random integers.
-   Compare memory usage for 1-byte integer, `int32`, `float32`, and
    `float64` arrays.
-   Observe how `float32` and `float64` represent the value `1 / 3`.
-   Compare the execution time of a Python loop and a NumPy vectorized
    calculation.
-   Plot memory usage and execution-time comparisons.
-   Summarize observations from the experiment.

## Technologies Used

-   **Python 3** --- programming language.
-   **NumPy** --- array creation, data types, numerical calculations,
    and vectorized operations.
-   **Matplotlib** --- bar charts for memory and execution-time
    comparisons.
-   **`time` module** --- elapsed-time measurement with
    `time.perf_counter()`.
-   **Google Colab / Jupyter Notebook** --- interactive environment for
    running code and viewing outputs.

## Features

### 1. Dataset generation and summary statistics

The notebook sets a random seed of `42` and creates an array of
**200,000 integers** in the range 1--100. It displays the first ten
values, mean, minimum, and maximum.

### 2. Data type memory comparison

The notebook compares the memory occupied by four arrays using each
array's `nbytes` and `itemsize` properties.

  -----------------------------------------------------------------------
  Displayed data type         Bytes per element  Total memory for 200,000
                                                                 elements
  ------------------- ------------------------- -------------------------
  `uint8` label                               1                 195.31 KB
  (1-byte integer                               
  array)                                        

  `int32`                                     4                 781.25 KB

  `float32`                                   4                 781.25 KB

  `float64`                                   8               1,562.50 KB
  -----------------------------------------------------------------------

These values are based on the notebook's recorded output. They describe
the array element storage and do not include Python object overhead.

### 3. Floating-point precision

The notebook converts `1 / 3` to `float32` and `float64` and prints both
representations. The recorded output is:

-   Original value: `0.3333333333333333`
-   `float32`: `0.33333334`
-   `float64`: `0.3333333333333333`

This illustrates that floating-point formats can represent the same
decimal value with different precision.

### 4. Python loop vs. NumPy vectorization

Both methods calculate the sum of the squares of the dataset's values.
The notebook checks that both methods return the same result, then
measures each method over five runs and reports the median elapsed time.

Recorded output:

  Measurement                               Result
  --------------------------- --------------------
  Python loop result                   `676645304`
  NumPy result                         `676645304`
  Results match                             `True`
  Python loop time (median)     `0.034037 seconds`
  NumPy time (median)           `0.000553 seconds`
  Reported speedup                        `61.52×`

**Note:** Timing results depend on the runtime environment and may
differ when the notebook is run again. The speedup above is the result
recorded in this notebook, not a guarantee for every machine or
workload.

### 5. Visualizations

The notebook uses Matplotlib to create two bar charts:

-   **Memory Usage by NumPy Data Type** --- compares array storage in
    KB.
-   **Execution Time Comparison** --- compares the measured Python-loop
    and NumPy execution times.

## How to Run

### Option A: Run in Google Colab

1.  Open [Google Colab](https://colab.research.google.com/).
2.  Select **File → Upload notebook**.
3.  Upload `Data_Management.ipynb`.
4.  Select **Runtime → Run all** to execute the cells in order.
5.  Review the printed statistics, memory comparison, benchmark output,
    and charts.

### Option B: Run locally

1.  Install Python 3.

2.  Install the required libraries:

    ``` bash
    pip install numpy matplotlib jupyter
    ```

3.  Start Jupyter:

    ``` bash
    jupyter notebook
    ```

4.  Open `Data_Management.ipynb` and run the cells from top to bottom.

## Project Structure

``` text
.
├── Data_Management.ipynb
└── README.md
```

Keep the notebook and this README in the same GitHub repository.

## Conclusion

This experiment demonstrates two important aspects of numerical
computing with NumPy: **array data types affect memory consumption**,
and **vectorized operations can be faster than explicit Python loops**
for suitable numerical workloads. The notebook also shows how
floating-point precision differs between `float32` and `float64`, and
how charts can make the results easier to interpret.

The benchmark is an educational comparison rather than a universal
performance guarantee. Results should be measured in the target runtime
before drawing conclusions about other workloads.

## Author

**Mohit Sharma**
