

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

        >>> from xlcalcnet import math53
        >>> math53.signgamma(-4.333)
        -1.0
        >>> math53.signgamma(0.0)
        1.0
        >>> math53.signgamma(4.333)
        1.0








Logarithm and sign of the gamma function
-------------------------------------------------------------------------------

.. method:: math53.lgamma_s(x,s)

    Returns (as a tuple) the logarithm and sign of the gamma function. 

    See also  Wikipedia :cite:p:`WikipediaFun75`, MathWorld :cite:p:`WolframFun75`, NIST :cite:p:`DLMFun75`,  BoostMath :cite:p:`BoostFun75`, :cite:t:`Ehrhardt2018` (3.5.1.10).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> print(math53.lgamma_s(-4.333))
        (-2.40239615347222, -1)
        >>> print(math53.lgamma_s(0.0))
        (NaN, 1)
        >>> print(math53.lgamma_s(4.333))
        (2.22531226395457, 1)






Logarithm of `\Gamma(1 + x)`
-------------------------------------------------------------------------------

.. method:: math53.lgamma1p(x)

    Returns `\log|\Gamma(1+x)|` with increased accuracy for `x` near `0`.

    See also  Wikipedia :cite:p:`WikipediaFun77`, MathWorld :cite:p:`WolframFun77`,  BoostMath :cite:p:`BoostFun77`, :cite:t:`Ehrhardt2018` (3.5.1.7).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.lgamma1p(-4.333)
        -0.9361360107144484
        >>> math53.lgamma1p(0.0)
        0.0
        >>> math53.lgamma1p(4.333)
        3.691572406712339





Logarithm of factorials: `\log(x!)`
-------------------------------------------------------------------------------

.. method:: math53.logfactorial(n) 

    Returns `\log(x!) = \log(\Gamma(x+1))`. See also  Wikipedia :cite:p:`WikipediaFun70`, MathWorld :cite:p:`WolframFun70`,  BoostMath :cite:p:`BoostFun70`, :cite:t:`Ehrhardt2018` (3.5.4.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logfactorial(2)
        0.6931471805599453
        >>> math53.logfactorial(5)
        4.787491742782046
        >>> math53.logfactorial(15)
        27.89927138384089




Logarithm of the binomial coefficient
-------------------------------------------------------------------------------

.. method:: math53.logbinomial(n,k)

    Returns the logarithm of the binomial coefficient, `\displaystyle \log{n \choose k} = \log\left(\frac{n!}{k!(n-k)!}\right)\,`, for `n\ge k \ge 0`.

    See also  Wikipedia :cite:p:`WikipediaFun72`, MathWorld :cite:p:`WolframFun72`, NIST :cite:p:`DLMFun72`,  BoostMath :cite:p:`BoostFun72`, :cite:t:`Ehrhardt2018` (3.5.4.5).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logbinomial(13, 3)
        5.655991810819852
        >>> math53.logbinomial(24, 8)
        13.508266389286396
        >>> math53.logbinomial(37, 12)
        21.33979273614502





.. _rst_log_beta: 

Log-Beta function
-------------------------------------------------------------------------------

.. method:: math53.logbeta(a, b)

    where ``ctx`` is ``math53``, ``ctxcpp``, ``ctxboost`` or ``ctxflint``.

    Returns the logarithm of `B(a,b)`

    See also  Wikipedia :cite:p:`WikipediaFun78`, MathWorld :cite:p:`WolframFun78`, NIST :cite:p:`DLMFun78`,  BoostMath :cite:p:`BoostFun78`, :cite:t:`Ehrhardt2018` (3.5.3.2), Mpmath :cite:p:`MpmathFun78`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logbeta(1.2, -4.333)
        -2.573142285269107
        >>> math53.logbeta(3.7, 0.1)
        2.134462769230688
        >>> math53.logbeta(4.8, 4.333)
        -5.783706647804463





Inverse of the gamma function, `\Gamma^{-1}(y)`
-------------------------------------------------------------------------------

.. method:: math53.gamma_inv(y)

    Returns `\Gamma^{-1}(y)`, the functional inverse of the gamma function, i.e. it returns `x` with `\Gamma(x)=y, \, y \ge 0.8857421875`.

    See also  Wikipedia :cite:p:`WikipediaFun75`, MathWorld :cite:p:`WolframFun75`, NIST :cite:p:`DLMFun75`,  BoostMath :cite:p:`BoostFun75`, :cite:t:`Ehrhardt2018` (3.5.1.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.gamma_inv(0.9)
        1.6492265028621345
        >>> math53.gamma_inv(1.5)
        2.662766345320147
        >>> math53.gamma_inv(4.333)
        3.7325782628811806







Inverse of the logarithm of the gamma function, `\log\Gamma^{-1}(y)`
-------------------------------------------------------------------------------

.. method:: math53.lgamma_inv(y)

    Returns the functional inverse of `\log\Gamma(x)`, i.e. it returns `x = \log\Gamma^{-1}(y)`
    with `\log\Gamma(x) = y` for `y \ge -0.12142 > y_m` (the minimum of `\log\Gamma(x)` for positive arguments).
    The result is greater than `x_m = 1.46163\ldots` (the positive zero of the `\psi` function).

    See also  Wikipedia :cite:p:`WikipediaFun77`, MathWorld :cite:p:`WolframFun77`,  BoostMath :cite:p:`BoostFun77`, :cite:t:`Ehrhardt2018` (3.5.1.6).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.lgamma_inv(0.9)
        3.214573262668465
        >>> math53.lgamma_inv(1.5)
        3.7611332794709584
        >>> math53.lgamma_inv(4.333)
        5.729662140740046







Temme's regulated gamma function, `\Gamma^{*}(x)`
-------------------------------------------------------------------------------

.. method:: math53.gammastar(x)

    Returns Temme's `\Gamma^{*}(x)`, defined by `\Gamma(x) = \sqrt{2\pi} e^{-x} x^{x-1/2} \Gamma^{*}(x)`.

    See also  Wikipedia :cite:p:`WikipediaFun75`, MathWorld :cite:p:`WolframFun75`, NIST :cite:p:`DLMFun75`,  BoostMath :cite:p:`BoostFun75`, :cite:t:`Ehrhardt2018` (3.5.1.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.gammastar(0.9)
        1.093716919051002
        >>> math53.gammastar(1.5)
        1.05634424426856
        >>> math53.gammastar(4.333)
        1.0193840818217619








Relative Pochhammer symbol, `((a)_x - 1)/x`
-------------------------------------------------------------------------------

.. method:: math53.poch1(a,x)

    Returns `\displaystyle \frac{(a)_x - 1}{x}`, accurate also for small `|x|`. For `x=0` the value `\psi(a)` is returned.

    See also :cite:t:`Ehrhardt2018` (3.5.4.7).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.poch1(1.2, -4.333)
        -0.04297013038959621
        >>> math53.poch1(2.4, 0)
        0.6529011697005977
        >>> math53.poch1(4.8, 4.333)
        693.9682866581799







.. _rst_mpm_catalan: 

Catalan function `C(x)`
-------------------------------------------------------------------------------

.. method:: math53.catalan_c(x)

    where ``ctx`` is ``math53``, ``ctxcpp``, ``ctxboost`` or ``ctxflint``.

    Returns the Catalan function `\displaystyle C(x) = \frac{1}{x+1} \binom{2x}{x} = \frac{\Gamma(2x+1)}{(x+1)\Gamma(x+1)^2}`.

    See also:  MathWorld :cite:p:`WolframFun301`,  Wikipedia :cite:p:`WikipediaFun301`, :cite:t:`Ehrhardt2018` (3.10.5).


        >>> from xlcalcnet import math53
        >>> math53.catalan_c(0.9)
        0.9539132521406414
        >>> math53.catalan_c(1.5)
        1.3581221810508415
        >>> math53.catalan_c(4.333)
        20.057821670219337




Bessel Lambda function, `\Lambda(\nu,x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_lambda(v,x)

    Returns the Bessel `\Lambda_{\nu}(x)` function, defined for `x, \nu \ge 0` as

    .. math:: \Lambda(\nu,x) = \Gamma(\nu+1) \frac{J_{\nu}(x)}{(x/2)^{\nu}}

    See also: :cite:t:`Ehrhardt2018` (3.1.3.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_lambda(1.2, 1.333)
        0.8116122406406188
        >>> math53.bessel_lambda(2.4, 0)
        1.0
        >>> math53.bessel_lambda(4.8, 4.333)
        0.4208160109325211








