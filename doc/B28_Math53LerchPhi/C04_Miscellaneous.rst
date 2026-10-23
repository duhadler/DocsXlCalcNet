

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Miscellaneous functions
===============================================================================



.. _Ctx_LogseriesPdf:

Log-series distribution, pmf
-------------------------------------------------------------------------------


.. method:: math53.logseries_pmf(p, k)


    Returns `\text{pmf}(x)`, the value of the probability mass function (:ref:`Pmf <Dist_Pmf>`) of the log-series distribution with shape parameters `p, 0 \le p \le 1`, `k>1`. and the support interval `(0,+\infty)`.

    See also  Wikipedia :cite:p:`WikipediaDis97`, MathWorld :cite:p:`WolframDis97`, :cite:t:`Johnson2005`, :cite:t:`Ehrhardt2018` (3.9.17).


    .. math:: \text{pmf}(x) = \frac{-1}{\log(1-p)} \frac{p^k}{k}.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logseries_pmf(0.01, 1)
        0.9949916247342216
        >>> math53.logseries_pmf(0.5, 2)
        0.18033688011112042
        >>> math53.logseries_pmf(0.9333, 3)
        0.10008431129451109





.. _Ctx_LogseriesCdf:

Log-series distribution, cdf
-------------------------------------------------------------------------------


.. method:: math53.logseries_cdf(p, k)

    Returns `\text{cdf}(x)`, the value of the cumulative distribution function (:ref:`Cdf <Dist_Cdf>`) of the log-series distribution with shape parameters `p, 0 \le p \le 1`, `k>1`. and the support interval `(0,+\infty)`.

    See also  Wikipedia :cite:p:`WikipediaDis97`, MathWorld :cite:p:`WolframDis97`, :cite:t:`Johnson2005`, :cite:t:`Ehrhardt2018` (3.9.17).

    .. math::  \text{cdf}(x) = 1 + \frac{B(p; k+1, 0)}{\log(1-p)} = 1 + \frac{a^k (\Phi(p,1,k)-1/k)}{\log(1-p)}, 

    where `B(\cdot)` is the incomplete beta function, and `\Phi(\cdot)` is Lerch's transcendent.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logseries_cdf(0.01, 1)
        0.9949916247342216
        >>> math53.logseries_cdf(0.5, 2)
        0.9016844005556022
        >>> math53.logseries_cdf(0.9333, 3)
        0.6056425762046286





.. _Ctx_ZetaPmf:

Zeta distribution, pmf
-------------------------------------------------------------------------------


.. method:: math53.zeta_pmf(r, k)


    Returns `\text{pmf}(x)`, the value of the probability mass function (:ref:`Pmf <Dist_Pmf>`) of the zeta distribution with parameter `r`, and `0 \le q \le 1`.


    See also  Wikipedia :cite:p:`WikipediaDis103`, :cite:t:`Rinne2008`, :cite:t:`Johnson2005` page 527, :cite:t:`Ehrhardt2018` (3.9.34).


    .. math:: \text{pmf}_X(k) = \frac{k^{-(r+1)}}{\zeta(r+1)}.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.zeta_pmf(0.01, 1)
        0.009942537765307869
        >>> math53.zeta_pmf(0.5, 2)
        0.1353378988096703
        >>> math53.zeta_pmf(0.9333, 3)
        0.0698271086340029




.. _Ctx_ZetaCdf:

Zeta distribution, cdf
-------------------------------------------------------------------------------


.. method:: math53.zeta_cdf(r, k)


    Returns `\text{cdf}(x)`, the value of the cumulative distribution function (:ref:`Cdf <Dist_Cdf>`) of the zeta distribution:

    .. math:: \text{cdf}(x) = \frac{H_k^{r+1}}{\zeta(r+1)} = 1 - \frac{\zeta(r+1, k+1)}{\zeta(r+1)}.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.zeta_cdf(0.01, 1)
        0.009942537765308734
        >>> math53.zeta_cdf(0.5, 2)
        0.5181312828090969
        >>> math53.zeta_cdf(0.9333, 3)
        0.806786037677741





