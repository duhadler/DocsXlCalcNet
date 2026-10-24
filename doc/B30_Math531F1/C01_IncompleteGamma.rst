

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





Incomplete gamma functions
===============================================================================



.. _rst_mpm_gamma_tricomi: 

Tricomi's entire incomplete gamma function: `\gamma^*(a,x)`
-------------------------------------------------------------------------------

.. method:: math53.gamma_tricomi(a, z)


    Returns Tricomi's entire incomplete gamma function `\gamma^*(a,x)`.

    See also: Flint :cite:p:`FlintFun01`, Flint :cite:p:`FlintFun02`.

    This routine returns Tricomi's incomplete gamma function `\gamma^*`, defined as

    .. math :: \gamma^*(a,x)=e^{-x} \frac{M(1,a+1,x)}{\Gamma(a+1)}

    Special cases are `\gamma^*(0,x)=1, \gamma^*(a,0)=1/\Gamma(a+1)`, and `\gamma^*(-n,x)=x^n`, if `-n` is a negative integer. Otherwise there are the following relations to the other incomplete functions:

    .. math :: \gamma^*(a,x)=\frac{x^{-a}}{\Gamma(a)}\gamma(a,x)=x^{-a} P(a,x).




    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.gamma_tricomi(1.2, -4.333)
        17.84105392965348
        >>> math53.gamma_tricomi(2.4, 0.0)
        0.33543467201965116
        >>> math53.gamma_tricomi(4.8, 4.333)
        0.00041567540877246445




Truncated exponential function, `e_n(x)` 
-------------------------------------------------------------------------------

.. method:: math53.expn(n,x)

    Returns `\displaystyle e_n(x) = \sum_{k=0}^n \frac{x^k}{k!} = \frac{\Gamma(n+1, x)}{\Gamma(n+1)} e^x`, the truncated exponential sum function, for `n>0`.

    See also: :cite:t:`Ehrhardt2018` (3.10.25).

    https://mathworld.wolfram.com/ExponentialSumFunction.html


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.expn(2, -4.333)
        6.054444500000001
        >>> math53.expn(3, 0.0)
        1.0
        >>> math53.expn(4, 4.333)
        42.9663958795967





Relative exponential, `\mathrm{exprel}_n(x)`
-------------------------------------------------------------------------------

.. method:: math53.expreln(n,x) 

    Returns  `\displaystyle \mathrm{exprel}_n(x) = \frac{n!}{x^n} \left(e^x - \sum_{k=0}^{n-1} \frac{x^k}{k!} \right) = e^x x^{-n} \left(\Gamma(1+n) - n \Gamma(n,x) \right)  = {}_1F_1(1, 1+n, x)`.

    See also  :cite:t:`Ehrhardt2018` (3.10.10).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.expreln(2, -4.333)
        0.35644717836066736
        >>> math53.expreln(3, 0.0)
        1.0
        >>> math53.expreln(4, 4.333)
        3.2608612360022433









