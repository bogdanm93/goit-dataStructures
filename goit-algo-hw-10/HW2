import numpy as np
import matplotlib.pyplot as plt
import scipy.integrate as integrate

# Function to integrate
def quadratic_function(x):
    return x ** 2

# Integration boundaries
lower_bound = 0
upper_bound = 2

# Monte Carlo simulation setup
num_samples = 10000
random_x = np.random.uniform(lower_bound, upper_bound, num_samples)
random_y = np.random.uniform(0, quadratic_function(upper_bound), num_samples)

# Determine points under the curve
points_under_curve = random_y < quadratic_function(random_x)
monte_carlo_integral = (upper_bound - lower_bound) * quadratic_function(upper_bound) * np.sum(points_under_curve) / num_samples

# Comparison using SciPy quad function
quad_result, quad_error = integrate.quad(quadratic_function, lower_bound, upper_bound)

# Plotting the function and Monte Carlo points
x_vals = np.linspace(lower_bound, upper_bound, 400)
y_vals = quadratic_function(x_vals)

plt.plot(x_vals, y_vals, 'r', linewidth=2)
plt.fill_between(x_vals, y_vals, color='gray', alpha=0.3)
plt.scatter(random_x, random_y, c=points_under_curve, s=1, cmap='bwr', alpha=0.5)
plt.title(f"Monte Carlo Integration: {monte_carlo_integral}\nSciPy Quad Integration: {quad_result}")
plt.xlabel('x')
plt.ylabel('f(x)')
plt.grid()
plt.show()

# Print the results
print(f"Monte Carlo Integration result: {monte_carlo_integral}")
print(f"SciPy Quad Integration result: {quad_result}")
print(f"Difference between results: {abs(monte_carlo_integral - quad_result)}")