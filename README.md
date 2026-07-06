# Perceptron-Play-Alpha-CyLabAcademy-WRITEUP

## 1. Challenge Description
This challenge requires us to find the correct weights ($w_1, w_2$) and bias ($b$) for a 2D Perceptron model. The model's objective is to achieve linear separation between two distinct classes of coordinate points (Class 0 and Class 1) on a 2D Cartesian plane.

---

## 2. Data Analysis
By executing the `POINTS` command in the challenge instance, we are provided with 6 labeled coordinate points:

| Coordinate (x, y) | Target Label | Expected Activation |
|-------------------|--------------|---------------------|
| `(-3, -2)`        | 0            | Negative ($< 0$)    |
| `(-1, -1)`        | 0            | Negative ($< 0$)    |
| `(-4, -2)`        | 0            | Negative ($< 0$)    |
| `(+3, +1)`        | 1            | Positive ($\ge 0$)  |
| `(+2, +2)`        | 1            | Positive ($\ge 0$)  |
| `(+1, +3)`        | 1            | Positive ($\ge 0$)  |

The Perceptron activation formula is defined as:
$$\text{Activation} = (w_1 \cdot x) + (w_2 \cdot y) + b$$

---

## 3. Methodology & Solution
To cleanly separate these two regions, we need a decision boundary line that cuts through the empty space between the two clusters.

1. **Initial Attempt (Finding the Slope):** We initially attempted a standard diagonal slope using `SET 1 -1 0`. However, this line passed directly through edge boundary points like `(-1, -1)`, resulting in misclassifications (indicated by `x` marks on the ASCII graph).
   
2. **Fine-Tuning & Optimization:** By analyzing the parallel distribution of the data points, the most optimal decision boundary is achieved by using a positive diagonal slope and shifting it slightly downwards using a negative bias.

The final parameters that successfully classify all points with 100% accuracy are:
* $w_1 = 1$
* $w_2 = 1$
* $b = -1$

```bash
> SET 1 1 -1
