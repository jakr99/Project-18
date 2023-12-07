# Lab 12: \LaTeX

## Directions
Your lab assignment today is to write the code to produce this document (yes this one, the whole thing) as well as a ”README.md” which mimics this. You should end up with a second copy of this document at the end, but one that you compiled using \LaTeX{} via the `pdflatex` command.

1. First, write some ”code” (hint: \LaTeX{} is popular on stack overflow).
2. Then, compile it with `pdflatex`.
3. Check the pdf to see if it looks right.
4. Rinse, repeat.
5. When you’re done, submit your `.tex` file and ”README.md”.

## Text Formatting
Sometimes, you may want to emphasize some text.

## Problem 0: Latent Dirichlet Allocation
Hey, can you help me with my homework? In Latent Dirichlet Allocation, we might need to use the equation for collapsed Gibbs sampling with equal document lengths $N$. (hint: math symbols can’t be emphasized like text)

According to our model, the total probability is given as follows:
\begin{equation}
    P(W, Z, \theta, \phi, \alpha, \beta) = \prod_{i=1}^{K} P(\phi_i ; \beta) \prod_{j=1}^{M} P(\theta_j ; \alpha) \prod_{t=1}^{N} P(Z_{j,t}| \theta_j)P(W_{j, t}| \phi_{Z_{j,t}})
\end{equation}

After some fancy math on (1), integrating $\phi$ and $\theta$ out gives us
\begin{equation}
    P(Z,W; \alpha, \beta) = \prod_{j=1}^{M} \Gamma\left(\sum_{i=1}^{K} \alpha_i\right) \prod_{i=1}^{K} \Gamma\left(n_i^{(j,\cdot)} + \alpha_i\right) \Gamma\left(\alpha_i\right) \Gamma\left(\sum_{i=1}^{K} n_i^{(j,\cdot)} + \alpha_i\right) \times \prod_{r=1}^{K} \Gamma\left(\sum_{i=1}^{V} \beta_r\right) \prod_{i=1}^{V} \Gamma\left(n_i^{(\cdot,r)} + \beta_r\right) \Gamma\left(\beta_r\right) \Gamma\left(\sum_{i=1}^{V} n_i^{(\cdot,r)} + \beta_r\right)
\end{equation}

Now we can work with that!

## Problem 1: Let’s Learn Markdown!
Make your git page’s `README.md` to mimic this paper. HINT: you can embed latex equations into your markdown. You could use Pandoc, but don’t because that’s cheating. To keep it simple, I’d recommend turning your equations into images.
