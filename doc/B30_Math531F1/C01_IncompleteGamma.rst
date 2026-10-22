

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Incomplete gamma functions
===============================================================================



.. _rst_mpm_gamma_tricomi: 

Tricomi's entire incomplete gamma function: `\gamma^*(a,x)`
-------------------------------------------------------------------------------

.. method:: ctx.gamma_tricomi(a, z, len)


Returns Tricomi's entire incomplete gamma function `\gamma^*(a,x)`.

See also: Flint :cite:p:`FlintFun01`, Flint :cite:p:`FlintFun02`.

This routine returns Tricomi's incomplete gamma function `\gamma^*`, defined as

.. math :: \gamma^*(a,x)=e^{-x} \frac{M(1,a+1,x)}{\Gamma(a+1)}

Special cases are `\gamma^*(0,x)=1, \gamma^*(a,0)=1/\Gamma(a+1)`, and `\gamma^*(-n,x)=x^n`, if `-n` is a negative integer. Otherwise there are the following relations to the other incomplete functions:

.. math :: \gamma^*(a,x)=\frac{x^{-a}}{\Gamma(a)}\gamma(a,x)=x^{-a} P(a,x).




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import dec, mpm, gmp, fpm, apm
    >>> mpm.dps = 40; a= 10; x = 30
    >>> \mathrm{d}x = dec.gamma_tricomi(a, x); mx = mpm.gamma_tricomi(a, x); gx = gmp.gamma_tricomi(a, x)
    >>> fx = fpm.gamma_tricomi(a, x); ax = apm.gamma_tricomi(a, x)
    >>> mpm.show([\mathrm{d}x, mx, gx, fx, ax])
    dec:  1.693496720095407516508168391232985587748E-15
    mpm:  1.693496720095407516508168391232985587748e-15
    gmp:  1.693496720095407516508168391232985587748E-15
    fpm:  1.69349672009541E-15
    apm:  1.693496720095407516508168391232985587748e-15 (4.214e-39%)


An example with complex input:

.. code-block:: pycon

    >>> from xlcalcnet import dec, mpm, gmp, fpm, apm
    >>> mpm.dps = 20; a= '10 + 3j'; z = '3 + 2j'
    >>> \mathrm{d}z = dec.gamma_tricomi(a, z); mz = mpm.gamma_tricomi(a, z); gz = gmp.gamma_tricomi(a, z)
    >>> fz = fpm.gamma_tricomi(a, z); az = apm.gamma_tricomi(a, z)
    >>> mpm.show([\mathrm{d}z, mz, gz, fz, az],  aligned=True)
    dec: -2.6190844813399921279E-8               - 1.3081710985777839884E-8j
    mpm: -2.6190844813399921279e-8               - 1.3081710985777839884e-8j
    gmp: -2.6190844813399921279E-08              - 1.3081710985777839884E-08j
    fpm: -2.61908448133999E-08                   - 1.30817109857778E-08j
    apm: -2.6190844813399921279e-8 (-1.446e-18%) - 1.3081710985777839884e-8 (-2.75e-18%)j





|newpage|



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









