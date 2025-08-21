# wril_cubic_fields

This repository uses **SageMath** and **Mathematica** to carry out computations related to WR ideal lattices in cyclic cubic fields, and contains the results of all heavy symbolic computations described in the paper.

Authors: 

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
- `compute_gram_matrix_of_good_bases.ipynb`: In this notebook, we verify that the bases of the form $B = \{x, y, z\}$ 
  for families of cyclic cubic fields are good, following these steps:

  - **Step 1.** Verify that these sets are indeed integral bases.  
    This is done by computing transition matrices (via the function `to_transition_matrix`) 
    and confirming the unimodularity of the transition matrices.

  - **Step 2.** In the function `compute_gram_matrix`, we proceed as follows:

    + Embed the basis elements $x,y,z$ of $B$ into $\mathbb{R}^3$ using the permutations  
      `shank_permutation`, `washington_permutation`, `kishi_permutation`. Denote by  
      $$
      x = (x_1, x_2, x_3), 
      y = (y_1, y_2, y_3), 
      z = (z_1, z_2, z_3).
      $$

    + Compute
      $$
      \alpha_0 =
      \begin{vmatrix} 
        x_2^2 - y_2^2 & x_3^2 - y_3^2 \\
        y_2^2 - z_2^2 & y_3^2 - z_3^2
      \end{vmatrix},
      \quad
      \beta_0 =
      \begin{vmatrix}
        x_3^2 - y_3^2 & x_1^2 - y_1^2 \\
        y_3^2 - z_3^2 & y_1^2 - z_1^2
      \end{vmatrix},
      \quad
      \gamma_0 =
      \begin{vmatrix}
        x_1^2 - y_1^2 & x_2^2 - y_2^2 \\
        y_1^2 - z_1^2 & y_2^2 - z_2^2
      \end{vmatrix}.
      $$

    + Then compute
      $$
      s = \alpha_0 x_1^2 + \beta_0 x_2^2 + \gamma_0 x_3^2
      \quad \# \; \|Tx\|^2 = \|Ty\|^2 = \|Tz\|^2,
      $$
      $$
      u = \alpha_0 x_1 y_1 + \beta_0 x_2 y_2 + \gamma_0 x_3 y_3
      \quad \# \; \langle Tx, Ty \rangle,
      $$
      $$
      v = \alpha_0 z_1 x_1 + \beta_0 z_2 x_2 + \gamma_0 z_3 x_3
      \quad \# \; \langle Tz, Tx \rangle,
      $$
      $$
      w = \alpha_0 y_1 z_1 + \beta_0 y_2 z_2 + \gamma_0 y_3 z_3
      \quad \# \; \langle Ty, Tz \rangle.
      $$

    + Finally, define
      $$
      e_1 = \alpha_0 + \beta_0 + \gamma_0, \quad
      e_2 = \alpha_0\beta_0 + \beta_0\gamma_0 + \gamma_0\alpha_0, \quad
      e_3 = \alpha_0 \beta_0 \gamma_0.
      $$

      We need the values $e_1, e_2, e_3$ in order to pass them to **Mathematica** and check 
      whether $\alpha_0, \beta_0, \gamma_0$ have the same sign.

  - For each good basis, we use the function `rewrite_alpha0_and_compute_norm_psi` to express  
    $$
    \alpha^2 = k \, \psi
    $$  
    and compute the norm of $\psi$ in order to check whether $\mathrm{Norm}(\psi)$ divides 
    the discriminant of the number field.

- `shanks_twist_example_n39.ipynb`: Contains an example of Shanks cyclic cubic field with $n= 39$.
- `cal_norm_df'p.pdf`: Computes the norm of $df'(\rho)$.
- `solve_ineqs_same_sign_conditions.pdf`: Solves inequalities under the same sign conditions ($e_1,e_2,e_3$ have the same sign).
- `solve_ineqs_wr_conditions.pdf`: Solves inequalities for the WR conditions.


## Requirements

- [SageMath version 10.6](https://www.sagemath.org/)
- [Wolfram Mathematica 14.2](https://www.wolfram.com/mathematica/)

