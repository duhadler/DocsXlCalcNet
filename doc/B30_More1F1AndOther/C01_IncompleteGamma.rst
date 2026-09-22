

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Incomplete gamma functions
===============================================================================





Truncated exponential function, `e_n(x)` 
-------------------------------------------------------------------------------

.. method:: math53.expn(n,x)

    Returns `\displaystyle e_n(x) = \sum_{k=0}^n \frac{x^k}{k!} = \frac{\Gamma(n+1, x)}{\Gamma(n+1)} e^x`, the truncated exponential sum function, for `n>0`.

    See also: :cite:t:`Ehrhardt2018` (3.10.25).

    https://mathworld.wolfram.com/ExponentialSumFunction.html


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Expn(2,3)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Expn(4,13)
        ereal('5.3518479027559984754E-1')





Relative exponential, `\mathrm{exprel}_n(x)`
-------------------------------------------------------------------------------

.. method:: math53.expreln(n,x) 

    Returns  `\displaystyle \mathrm{exprel}_n(x) = \frac{n!}{x^n} \left(e^x - \sum_{k=0}^{n-1} \frac{x^k}{k!} \right) = e^x x^{-n} \left(\Gamma(1+n) - n \Gamma(n,x) \right)  = {}_1F_1(1, 1+n, x)`.

    See also  :cite:t:`Ehrhardt2018` (3.10.10).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Expreln(3, 4)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Expreln(3, 12)
        ereal('5.3518479027559984754E-1')









