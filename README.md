# Statistics

## Document: Bootstrapping with Dynamic Visualization

### Objective:
To dynamically visualize the distribution of means from bootstrapped samples. The aim is to understand how the distribution changes as the size of the initial random sample (from which the bootstrapping is done) varies.

### Methodology:

1. **Data Generation**:
    - A set of `100,000` random numbers, named `samples`, was generated from a uniform distribution between `0` and `10`.

2. **Random Sample Extraction**:
    - From the above `samples`, a random subset, named `random_samples`, was extracted. The size of this subset was determined by a widget (a slider) that allowed for dynamic size selection.

3. **Bootstrapping**:
    - Bootstrapping is a resampling technique where random samples are drawn with replacement from an existing sample. 
    - For each value of the `random_samples` size (determined by the widget), bootstrapping was performed `10,000` times. 
    - From each bootstrapped sample, a mean value was computed, resulting in `10,000` mean values for each size of `random_samples`.

4. **Visualization**:
    - The `10,000` bootstrapped means were plotted as a histogram. 
    - The dynamic widget allowed the user to change the size of `random_samples` and immediately observe the corresponding histogram of bootstrapped means.

### Tools Used:
- **Python Programming Language**: The primary language used for coding and data manipulation.
- **NumPy**: A Python library used for numerical computations and random data generation.
- **Matplotlib**: A plotting library in Python used to create the histogram.
- **ipywidgets**: A library to create interactive widgets in Jupyter Notebook. In this project, it was used to create a slider that can adjust the size of `random_samples`.

### Implementation:
1. The `samples` dataset was created using `np.random.uniform(0, 10, size=100000)`.
2. A function, `plot_histogram`, was defined to handle the drawing of random samples, bootstrapping, and plotting.
3. Inside `plot_histogram`:
    - `random_samples` was drawn from `samples` based on the user-defined size from the widget.
    - Bootstrapping was done for `10,000` iterations, each time drawing samples of the same size as `random_samples` with replacement.
    - The mean of each bootstrapped sample was stored in a list, `bootstrap_means`.
    - A histogram of the `bootstrap_means` was plotted.
4. `ipywidgets` was used to create an interactive slider to adjust the size of `random_samples` dynamically. This was done using `widgets.IntSlider` and `widgets.interactive`.

### Conclusion:
The project enabled a dynamic visualization of how the distribution of means from bootstrapped samples changes based on the size of the initial random sample. The use of interactive widgets made the exploration more intuitive and user-friendly.
