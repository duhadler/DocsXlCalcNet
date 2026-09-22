
.. |spacingstart| raw:: latex

   \begin{spacing}{1.5}


.. |spacingend| raw:: latex

   \end{spacing}


.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />




|newpage|

Descriptive Statistics
===============================================================================


Partial Sum
-------------------------------------------------------------------------------

.. method:: ctx.mat_sum(mat, partialmode)

    Calculates the PartialSum.  Writing ``matA.sum(partialmode)`` has the same effect.


    Here partialmode is set as follows: 1 for full matrix calculation, 2 for rowwise calculation, 3 for columnwise calculation.


    See also: Eigen :cite:p:`EigenMat101`.




Partial Product
-------------------------------------------------------------------------------

.. method:: ctx.mat_prod(matA, partialmode)

    Calculates the PartialProd.   Writing ``matA.prod(partialmode)`` has the same effect.

    Here partialmode is set as follows: 1 for full matrix calculation, 2 for rowwise calculation, 3 for columnwise calculation.


    See also: Eigen :cite:p:`EigenMat101`.




Partial Arithmetic Mean
-------------------------------------------------------------------------------

.. method:: ctx.mat_mean(matA, partialmode)

    Calculates the PartialMean.   Writing ``matA.mean(partialmode)`` has the same effect.

    Here partialmode is set as follows: 1 for full matrix calculation, 2 for rowwise calculation, 3 for columnwise calculation.



    See also: Eigen :cite:p:`EigenMat101`.





Partial Minimal Coefficient
-------------------------------------------------------------------------------

.. method:: ctx.mat_min_coeff(matA, partialmode)

    Calculates the PartialMinCoeff.   Writing ``matA.min_coeff(partialmode)`` has the same effect.

    Here partialmode is set as follows: 1 for full matrix calculation, 2 for rowwise calculation, 3 for columnwise calculation.



    See also: Eigen :cite:p:`EigenMat101`.





Partial Maximal Coefficient
-------------------------------------------------------------------------------

.. method:: ctx.mat_max_coeff(matA, partialmode)

    Calculates the PartialMaxCoeff.  Writing ``matA.max_coeff(partialmode)`` has the same effect.

    Here partialmode is set as follows: 1 for full matrix calculation, 2 for rowwise calculation, 3 for columnwise calculation.



    See also: Eigen :cite:p:`EigenMat101`.





Trace
-------------------------------------------------------------------------------

.. method:: ctx.mat_trace(matA)

    Returns the trace of the matrix `A`.  Writing ``matA.Trace()`` has the same effect.



    See also: Eigen :cite:p:`EigenMat101`,  Wikipedia :cite:p:`WikipediaMat10`.







Partial Squared Norm
-------------------------------------------------------------------------------

.. method:: ctx.mat_squared_norm(matA, partialmode)

    Calculates the PartialSquaredNorm.  Writing ``matA.PartialSquaredNorm(partialmode)`` has the same effect.

    Here partialmode is set as follows: 1 for full matrix calculation, 2 for rowwise calculation, 3 for columnwise calculation.


    See also: Eigen :cite:p:`EigenMat101`.




Partial Norm
-------------------------------------------------------------------------------

.. method:: ctx.mat_norm(matA, partialmode)

    Calculates the PartialNorm.  Writing ``matA.PartialNorm(partialmode)`` has the same effect.

    Here partialmode is set as follows: 1 for full matrix calculation, 2 for rowwise calculation, 3 for columnwise calculation.



    See also: Eigen :cite:p:`EigenMat101`.





Partial Stable Norm
-------------------------------------------------------------------------------

.. method:: ctx.mat_stable_norm(matA, partialmode)

    Calculates the PartialStableNorm.  Writing ``matA.PartialStableNorm(partialmode)`` has the same effect.

    Here partialmode is set as follows: 1 for full matrix calculation, 2 for rowwise calculation, 3 for columnwise calculation.



    See also: Eigen :cite:p:`EigenMat101`.





Covariance matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_covariance(matA)

    Calculates the covariance matrix.  Writing ``matA.Covariance()`` has the same effect.

    See also:  Wikipedia :cite:p:`WikipediaMat11`,  Wikipedia :cite:p:`WikipediaMat12`.





Correlation matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_correlation(matA)

    Calculates the correlation matrix.  Writing ``matA.Correlation_mat()`` has the same effect.

    See also:  Wikipedia :cite:p:`WikipediaMat13`.








