

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


.. method:: math53.logseries_pmf(k, mu)


    Returns `\text{pmf}(x)`, the value of the probability mass function (:ref:`Pmf <Dist_Pmf>`) of the log-series distribution with mean `mu` and the support interval `(0,+\infty)`, and `0 \le q \le 1`.

    See also  Wikipedia :cite:p:`WikipediaDis97`, MathWorld :cite:p:`WolframDis97`, :cite:t:`Johnson2005`, :cite:t:`Ehrhardt2018` (3.9.17).





    .. math:: \text{pmf}(x) = \frac{-1}{\ln(1-p)} \frac{p^k}{k}.

    The following example shows both forms of the syntax: 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> a = 0; b = 1; t = 0.3; x = 0.6;
        >>> print ("LogseriesPdf(x, a, b): ", LogseriesPdf(x, a, b))
        >>> print ("dist_logseries(a, b).pdf(x): ", dist_logseries(a, b).pdf(x))
        6.3563523462564525615615615614561356E+00





.. _Ctx_LogseriesCdf:

Log-series distribution, cdf
-------------------------------------------------------------------------------


.. method:: math53.logseries_cdf(k, mu)

    Returns `\text{cdf}(x)`, the value of the cumulative distribution function (:ref:`Cdf <Dist_Cdf>`) of the log-series distribution with mean `mu` and the support interval `(0,+\infty)`, and `0 \le q \le 1`.

    See also  Wikipedia :cite:p:`WikipediaDis97`, MathWorld :cite:p:`WolframDis97`, :cite:t:`Johnson2005`, :cite:t:`Ehrhardt2018` (3.9.17).

    .. math::  \text{cdf}(x) = 1 + \frac{B(p; k+1, 0)}{\ln(1-p)}.

    The following example shows both forms of the syntax:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> a = 0; b = 1; t = 0.3; x = 0.6;
        >>> print ("LogseriesCdf(x, a, b): ", LogseriesCdf(x, a, b))
        >>> print ("dist_logseries(a, b).cdf(x): ", dist_logseries(a, b).cdf(x))
        6.3563523462564525615615615614561356E+00





.. _Ctx_ZetaPmf:

Zeta distribution, pmf
-------------------------------------------------------------------------------


.. method:: math53.zeta_pmf(k, r)


    Returns `\text{pmf}(x)`, the value of the probability mass function (:ref:`Pmf <Dist_Pmf>`) of the zeta distribution with parameter `r`, and `0 \le q \le 1`.


    See also  Wikipedia :cite:p:`WikipediaDis103`, :cite:t:`Rinne2008`, :cite:t:`Johnson2005` page 527, :cite:t:`Ehrhardt2018` (3.9.34).


    .. math:: \text{pmf}_X(k) = \frac{k^{-(r+1)}}{\zeta(r+1)}.

    The following example shows both forms of the syntax: 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> a = 0; b = 1; t = 0.3; x = 0.6;
        >>> print ("ZetaPdf(x, a, b): ", ZetaPdf(x, a, b))
        >>> print ("dist_zeta(a, b).pdf(x): ", dist_zeta(a, b).pdf(x))
        6.3563523462564525615615615614561356E+00




.. _Ctx_ZetaCdf:

Zeta distribution, cdf
-------------------------------------------------------------------------------


.. method:: math53.zeta_cdf(k, r)


    Returns `\text{cdf}(x)`, the value of the cumulative distribution function (:ref:`Cdf <Dist_Cdf>`) of the zeta distribution:

    .. math:: \text{cdf}(x) = \frac{H_k^{r+1}}{\zeta(r+1)} = 1 - \frac{\zeta(r+1, k+1)}{\zeta(r+1)}.

    The following example shows both forms of the syntax:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> a = 0; b = 1; t = 0.3; x = 0.6;
        >>> print ("ZetaCdf(x, a, b): ", ZetaCdf(x, a, b))
        >>> print ("dist_zeta(a, b).cdf(x): ", dist_zeta(a, b).cdf(x))
        6.3563523462564525615615615614561356E+00





