# Predicting Prime Counting Function using ML techniques
This project aims to predict the prime counting function π(x), which gives the number of prime numbers less than or equal to a given number x. For example, π(10) = 4 because there are 4 prime numbers (2, 3, 5, 7) less than or equal to 10.

## Theoretical Background

The manual method to find the exact output of prime counting function is to use Sieve of Eratosthenes algorithm. This algorithm sieves out all the prime numbers and a simple for loop can be used to find total number of primes below each number. However, this manual approach is slow for large values as time complexity of this algorithm is O(n log log n).

There are also mathematical approximations to estimate number of primes below a given number but it will not give exact number like the manual approach. Some mathematical approximations include:

- **Prime Number Theorem (PNT)**: π(x) ~ x/ln(x)
- **Logarithmic Integral**: π(x) ~ Li(x) = ∫₂ˣ dt/ln(t)
- **Legendre's Formula**: π(x) ~ x/(ln(x) - 1.08366)

## Project Objective

In this project, I do not intend to replace the traditional techniques such as Sieve of Eratosthenes and mathematical approximations of prime counting function with a ML model. I merely intend to explore whether ML has the potential in approximating prime counting function. The reason I am doing this is that Machine learning and number theory are usually seen as unrelated fields, and I am just curious to see what insights might emerge when they intersect. If the model do work, it could possibly offer faster performance than the sieve and have higher accuracy than the mathematical approximations. Also, I'm personally interested in both ML and number theory.

## Project Structure

The project consists of the following components:

1. **CreatingDataset.ipynb**: Generates the dataset using the Sieve of Eratosthenes algorithm and saves it to "π(x).csv"
2. **Regression_Techniques.ipynb**: Simple linear regression + multiple linear regression
3. **RandomForest_approach.ipynb**: Random forest regression
4. **NeuralNetwork_approach.ipynb**: Neural network model

## Usage

1. Run `CreatingDataset.ipynb` to generate the dataset (or use the existing "π(x).csv" file)
2. Run the prediction notebooks in order of increasing complexity:
   - `Regression_Techniques.ipynb`
   - `RandomForest_approach.ipynb`
   - `NeuralNetwork_approach.ipynb`

## Project Results

### Model Performance on Test Set

| Model | MAPE on Test Set |
|-------|------------------|
| Simple Linear Regression | 9.50% |
| Multiple Linear Regression | 0.12% |
| Random Forest Regression | 0.01% |
| Neural Network Model | 2.69% |

### Results on Large Values Beyond Dataset

| Model | APE on 10^6 | APE on 10^7 | APE on 10^8 |
|-------|-------------|-------------|-------------|
| Simple Linear Regression | 19.83% | 41.05% | 62.64% |
| Multiple Linear Regression | 0.98% | 11.11% | 126.55% |
| Random Forest Regression | 87.78% | 98.56% | 99.83% |
| Neural Network Model | 56.89% | 1198.08% | 14386.10% |

## Conclusion

Within the range of values in the training dataset, **Random Forest Regression** proved to be the most accurate model. All models, except for Simple Linear Regression (SLR), achieved high accuracy with a **Mean Absolute Percentage Error (MAPE) of under 3%**.

However, when evaluating **Absolute Percentage Error (APE) on values beyond the training range**, MLR outperformed the others. The remaining models (Random Forest and Neural Network) showed significantly lower accuracy, likely because they are not well-suited for **extrapolation**.

Overall, **MLR is the best-performing model** in this study, as it generalises well and is capable of **extrapolating to values 10x and even 100x larger than the maximum value in the training data**.

## Dependencies

- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn
- tensorflow (for neural network model)
- scipy

## References

1. Prime Number Theorem: https://en.wikipedia.org/wiki/Prime_number_theorem
2. Logarithmic Integral: https://en.wikipedia.org/wiki/Logarithmic_integral_function
3. Legendre's Formula: https://en.wikipedia.org/wiki/Legendre%27s_constant
