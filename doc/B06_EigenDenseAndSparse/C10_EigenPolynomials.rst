

.. |spacingstart| raw:: latex

   \begin{spacing}{1.5}



.. |spacingend| raw:: latex

   \end{spacing}



.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />







Eigen: Polynomials
===============================================================================



Building a polynomial from its roots
------------------------------------------------------------------------------------------------------------

.. method:: ctx.roots_to_monic_poly(results, matB)

    Calculates the monic polynomial from its roots.

    See also: Eigen :cite:p:`EigenMat170`.



Polynomial evaluation
------------------------------------------------------------------------------------------------------------

.. method:: ctx.poly_eval(roots)

    Evaluates a polynomial

    See also: Eigen :cite:p:`EigenMat170`.







Polynomial roots
------------------------------------------------------------------------------------------------------------

.. method:: ctx.poly_roots()


    Computes all roots (real or complex) of a given polynomial.

    See also: Eigen :cite:p:`EigenMat171`.






