# Read-once formulas and a question of Han on the Fourier entropy-influence conjecture

Yitzchak Shmalo

For a Boolean function f and a coordinate k let

    Q_k(f) = sum over S not containing k of |f^(S) f^(S + k)|, divided by the influence I_k(f).

Han (arXiv:2312.08271, Question 3.1) asked whether every Boolean function has a coordinate k with Q_k(f) <= c for
a universal constant c, and observed that this would imply the Fourier entropy-influence conjecture. The answer is
negative.

For balanced alternating read-once AND-OR formulas with fan-ins s_1, ..., s_L, Q_k is the same at every coordinate
and equals

    Q_k = 2L - 1 - 4 (p_1 + ... + p_{L-1}) - 2 p_L + |1 - 2 p_L|,   p_0 = 1/2,  p_l = (1 - p_{l-1})^{s_l}.

Choosing each fan-in as the least one with p_l <= 1/4 gives monotone read-once formulas of depth L with fan-ins at
most 7 on at most 2 * 7^(L-1) variables and Q_k >= L at every coordinate. Depth two gives the tribes functions, for
which min_k Q_k approaches 4 and stays below it. The Fourier entropy-influence conjecture is known for these
formulas (O'Donnell and Tan), so the inequality fails on a class where the conjecture holds.

## Contents

- `paper/han_question_read_once_trees.tex`, `paper/han_question_read_once_trees.pdf` - the paper.
- `code/q31_check.py` - computes Q_k from truth tables by the integer Walsh-Hadamard transform and compares it, as
  exact rationals, with the closed forms for AND (n <= 8), tribes (sw <= 20) and 22 read-once formulas (n <= 20).
  `python q31_check.py` prints `TOTAL MISMATCHES 0` (a few minutes). Requires Python 3 and NumPy.
- `code/q31_check_output.txt` - its output.
- `code/deep_trees.py`, `code/deep_trees_output.txt` - the closed form along the family of the main theorem to
  depth 80.

## License

The paper is released under CC BY 4.0 and the code under the MIT License.
