

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Gamma functions
===============================================================================



Sign of the gamma function
-------------------------------------------------------------------------------

.. method:: math53.signgamma(x)

    Returns the sign of `\Gamma(x)`, which is `+1` if `x > 0` or if `\lfloor x \rfloor` is even, `-1` otherwise, and meaningless for `0` or negative integers.

    See also  Wikipedia :cite:p:`WikipediaFun75`, MathWorld :cite:p:`WolframFun75`, NIST :cite:p:`DLMFun75`,  BoostMath :cite:p:`BoostFun75`, :cite:t:`Ehrhardt2018` (3.5.1.9).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.SignGamma(1.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.SignGamma('1.51')
        ereal('5.3518479027559984754E-1')








Logarithm and sign of the gamma function
-------------------------------------------------------------------------------

.. method:: math53.lgamma_s(x,s)

    Returns (as a tuple) the logarithm and sign of the gamma function. 

    See also  Wikipedia :cite:p:`WikipediaFun75`, MathWorld :cite:p:`WolframFun75`, NIST :cite:p:`DLMFun75`,  BoostMath :cite:p:`BoostFun75`, :cite:t:`Ehrhardt2018` (3.5.1.10).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.LogGammaS(1.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.LogGammaS('1.51')
        ereal('5.3518479027559984754E-1')






Logarithm of `\Gamma(1 + x)`
-------------------------------------------------------------------------------

.. method:: math53.lgamma1p(x)

    Returns `\log|\Gamma(1+x)|` with increased accuracy for `x` near `0`.

    See also  Wikipedia :cite:p:`WikipediaFun77`, MathWorld :cite:p:`WolframFun77`,  BoostMath :cite:p:`BoostFun77`, :cite:t:`Ehrhardt2018` (3.5.1.7).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.LogGamma1p(1.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.LogGamma1p('1.51')
        ereal('5.3518479027559984754E-1')





Logarithm of factorials: `\log(x!)`
-------------------------------------------------------------------------------

.. method:: math53.logfactorial(n) 

    Returns `\log(x!) = \log(\Gamma(x+1))`. See also  Wikipedia :cite:p:`WikipediaFun70`, MathWorld :cite:p:`WolframFun70`,  BoostMath :cite:p:`BoostFun70`, :cite:t:`Ehrhardt2018` (3.5.4.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.LogFactorial(3)
        ereal('5.2359877559829887307E-1')
        >>> ereal.LogFactorial('0.51')
        ereal('5.3518479027559984754E-1')




Logarithm of the binomial coefficient
-------------------------------------------------------------------------------

.. method:: math53.logbinomial(n,k)

    Returns the logarithm of the binomial coefficient, `\displaystyle \log{n \choose k} = \log\left(\frac{n!}{k!(n-k)!}\right)\,`, for `n\ge k \ge 0`.

    See also  Wikipedia :cite:p:`WikipediaFun72`, MathWorld :cite:p:`WolframFun72`, NIST :cite:p:`DLMFun72`,  BoostMath :cite:p:`BoostFun72`, :cite:t:`Ehrhardt2018` (3.5.4.5).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.LogBinomial(13, 7)
        ereal('5.2359877559829887307E-1')
        >>> ereal.LogBinomial(12.6, '4.51')
        ereal('5.3518479027559984754E-1')





.. _rst_log_beta: 

Log-Beta function
-------------------------------------------------------------------------------

.. method:: math53.logbeta(a, b)

    where ``ctx`` is ``math53``, ``ctxcpp``, ``ctxboost`` or ``ctxflint``.

    Returns the logarithm of `B(a,b)`

    See also  Wikipedia :cite:p:`WikipediaFun78`, MathWorld :cite:p:`WolframFun78`, NIST :cite:p:`DLMFun78`,  BoostMath :cite:p:`BoostFun78`, :cite:t:`Ehrhardt2018` (3.5.3.2), Mpmath :cite:p:`MpmathFun78`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.LogBeta(3.1, 0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.LogBeta(3.4, '0.51')
        ereal('5.3518479027559984754E-1')





Inverse of the gamma function, `\Gamma^{-1}(y)`
-------------------------------------------------------------------------------

.. method:: math53.gamma_inv(y)

    Returns `\Gamma^{-1}(y)`, the functional inverse of the gamma function, i.e. it returns `x` with `\Gamma(x)=y, \, y \ge 0.8857421875`.

    See also  Wikipedia :cite:p:`WikipediaFun75`, MathWorld :cite:p:`WolframFun75`, NIST :cite:p:`DLMFun75`,  BoostMath :cite:p:`BoostFun75`, :cite:t:`Ehrhardt2018` (3.5.1.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.GammaInv(1.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.GammaInv('1.51')
        ereal('5.3518479027559984754E-1')







Inverse of the logarithm of the gamma function, `\log\Gamma^{-1}(y)`
-------------------------------------------------------------------------------

.. method:: math53.lgamma_inv(y)

    Returns the functional inverse of `\log\Gamma(x)`, i.e. it returns `x = \log\Gamma^{-1}(y)`
    with `\log\Gamma(x) = y` for `y \ge -0.12142 > y_m` (the minimum of `\log\Gamma(x)` for positive arguments).
    The result is greater than `x_m = 1.46163\ldots` (the positive zero of the `\psi` function).

    See also  Wikipedia :cite:p:`WikipediaFun77`, MathWorld :cite:p:`WolframFun77`,  BoostMath :cite:p:`BoostFun77`, :cite:t:`Ehrhardt2018` (3.5.1.6).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.LogGammaInv(1.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.LogGammaInv('1.51')
        ereal('5.3518479027559984754E-1')







Temme's regulated gamma function, `\Gamma^{*}(x)`
-------------------------------------------------------------------------------

.. method:: math53.gammastar(x)

    Returns Temme's `\Gamma^{*}(x)`, defined by `\Gamma(x) = \sqrt{2\pi} e^{-x} x^{x-1/2} \Gamma^{*}(x)`.

    See also  Wikipedia :cite:p:`WikipediaFun75`, MathWorld :cite:p:`WolframFun75`, NIST :cite:p:`DLMFun75`,  BoostMath :cite:p:`BoostFun75`, :cite:t:`Ehrhardt2018` (3.5.1.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.GammaStar(1.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.GammaStar('1.51')
        ereal('5.3518479027559984754E-1')








Relative Pochhammer symbol, `((a)_x - 1)/x`
-------------------------------------------------------------------------------

.. method:: math53.poch1(a,x)

    Returns `\displaystyle \frac{(a)_x - 1}{x}`, accurate also for small `|x|`. For `x=0` the value `\psi(a)` is returned.

    See also :cite:t:`Ehrhardt2018` (3.5.4.7).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Poch1(13, 7)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Poch1(12.6, '4.51')
        ereal('5.3518479027559984754E-1')







.. _rst_mpm_catalan: 

Catalan function `C(x)`
-------------------------------------------------------------------------------

.. method:: math53.catalan_c(x)

    where ``ctx`` is ``math53``, ``ctxcpp``, ``ctxboost`` or ``ctxflint``.

    Returns the Catalan function `\displaystyle C(x) = \frac{1}{x+1} \binom{2x}{x} = \frac{\Gamma(2x+1)}{(x+1)\Gamma(x+1)^2}`.

    See also:  MathWorld :cite:p:`WolframFun301`,  Wikipedia :cite:p:`WikipediaFun301`, :cite:t:`Ehrhardt2018` (3.10.5).



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import dec, mpm, ipm
        >>> mpm.dps = 40; x = '10.5'
        >>> \mathrm{d}x = dec.catalan(x); mx = mpm.catalan(x); ix = ipm.catalan(x)
        >>> mpm.show([\mathrm{d}x, mx, ix])
        dec:  3.137576033650317681318411712507890972194E+4
        mpm:  3.137576033650317681318411712507890972194e+4
        ipm:  3.137576033650317681318411712507890972194e+4 (3.597e-39%)

        >>> from xlcalcnet import mpm, fpm, gmp, apm
        >>> mpm.dps = 40; x = '10.5'
        >>> fx = fpm.catalan(x); gx = gmp.catalan(x); ax = apm.catalan(x)
        >>> mpm.show([fx, gx, ax])
        fpm:  3.13757603365032E+04
        gmp:  3.137576033650317681318411712507890972194E+04
        apm:  3.137576033650317681318411712507890972194e+4 (3.597e-39%)








