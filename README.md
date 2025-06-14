# Predicting Prime Counting Function using ML techniques
This project aims to predict the prime counting function π(x), which gives the number of prime numbers less than or equal to a given number x. For example, π(10) = 4 because there are 4 prime numbers (2, 3, 5, 7) less than or equal to 10.

## Theoretical Background

The manual method to find the exact output of prime counting function is to use Sieve of Eratosthenes algorithm. This algorithm sieves out all the prime numbers and a simple for loop can be used to find total number of primes below each number. However, this manual approach is slow for large values as time complexity of this algorithm is O(n log log n).

There are also mathematical approximations to estimate number of primes below a given number but it will not give exact number like the manual approach. Some mathematical approximations include:

- **Prime Number Theorem (PNT)**: π(x) ~ x/ln(x)
- **Logarithmic Integral**: π(x) ~ Li(x) = ∫₂ˣ dt/ln(t)
- **Legendre's Formula**: π(x) ~ x/(ln(x) - 1.08366)

## Project Objective

In this project, I do not intend to replace the traditional techniques such as Sieve of Eratosthenes and mathematical approximations of prime counting function with a ML model. I merely intend to explore whether ML has the potential in approximating prime counting function. The reason I am doing this is because Machine learning and number theory are usually seen as unrelated fields, and I am just curious to see what insights might emerge when they intersect. If the model turns out to be effective, it could possibly offer faster performance than the sieve and have higher accuracy than the mathematical approximations. Also, I'm personally interested in both ML and number theory.

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
