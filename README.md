# wril_cubic_fields

This repository uses **SageMath** and **Mathematica** to carry out computations related to WR ideal lattices in cyclic cubic fields, and contains the results of all heavy symbolic computations described in the paper.

Authors: Nam H. Le, Dat T. Tran, David Karpuk, and Ha T. N. Tran.

## Structure

```text
notebooks/
├── sagemath/    # SageMath notebooks (*.ipynb)
│   ├── algebraic_elements.ipynb
│   ├── all_fund_units_are_totally_positive.ipynb
│   ├── compute_disc.ipynb
│   ├── compute_gram_matrix_of_good_bases.ipynb
    └── shank_twist_example_n39.ipynb
└── wolfram/     # Mathematica notebooks (*.nb)
    ├── cal_norm_df'p.nb
    ├── solve_ineqs_same_sign_conditions.nb
    └── solve_ineqs_wr_conditions.nb

output/
└── wolfram/     # PDF exports of Mathematica notebooks
    ├── cal_norm_df'p.pdf
    ├── solve_ineqs_same_sign_conditions.pdf
    └── solve_ineqs_wr_conditions.pdf
```
Here are brief descriptions of the files:
- `algebraic_elements.ipynb`: Computes the minimal polynomials of several elements in the corresponding family of cyclic cubic fields to verify that these elements are algebraic integers and therefore belong to the ring of integers of the field.
- `all_fund_units_are_totally_positive.ipynb`: Contains examples in which every unit in the fundamental unit group is either totally positive or totally negative.
- `compute_disc.ipynb`: Computes the discriminant of each set, verifying that it coincides with the discriminant of the corresponding number field and thus confirming that these sets form integral bases.
- `compute_gram_matrix_of_good_bases.ipynb`: In this notebook, we will apply **Algorithm 1** to verify that the bases of the form $B = \{x, y, z\}$ 
  for families of cyclic cubic fields are good.
- `shanks_twist_example_n39.ipynb`: Contains an example of Shanks cyclic cubic field with $n= 39$.
- `cal_norm_df'p.pdf`: Computes the norm of $df'(\rho)$.
- `solve_ineqs_same_sign_conditions.pdf`: Solves inequalities under the same sign conditions ($e_1,e_2,e_3$ have the same sign).
- `solve_ineqs_wr_conditions.pdf`: Solves inequalities for the WR conditions.


## Requirements

- [SageMath version 10.6](https://www.sagemath.org/)
- [Wolfram Mathematica 14.2](https://www.wolfram.com/mathematica/)

