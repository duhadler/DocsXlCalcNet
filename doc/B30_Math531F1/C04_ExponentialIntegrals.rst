

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Exponential integrals, and related functions
===============================================================================




Entire cosine integral `\mathrm{Cin}(x)`
-------------------------------------------------------------------------------

.. method:: math53.cin(z)

    Returns the entire cosine integral of  `\displaystyle \mathrm{Cin}(x) = \int_0^{x} \frac{1-\cos(t)}{t} \, \mathrm{d}t`.

    See also   Wikipedia :cite:p:`WikipediaFun178`, MathWorld :cite:p:`WolframFun178`, NIST :cite:p:`DLMFun178`, :cite:t:`Ehrhardt2018` (3.4.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.cin(-4.333)
        2.2259335713533317
        >>> math53.cin(0.0)
        0.0
        >>> math53.cin(4.333)
        2.2259335713533317







Entire hyperbolic cosine integral `\mathrm{Cinh}(x)`
-------------------------------------------------------------------------------

.. method:: math53.cinh(z)

    Returns the entire hyperbolic cosine integral `\displaystyle \mathrm{Cinh}(x) = \int_0^{x} \frac{\cosh(t)-1}{t} \, \mathrm{d}t`.

    See also   Wikipedia :cite:p:`WikipediaFun180`, MathWorld :cite:p:`WolframFun180`, NIST :cite:p:`DLMFun180`, :cite:t:`Ehrhardt2018` (3.4.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.cinh(-4.333)
        10.3553644776616
        >>> math53.cinh(0.0)
        0.0
        >>> math53.cinh(4.333)
        10.3553644776616







Entire exponential integral `\displaystyle \mathrm{Ein}(x)`
-------------------------------------------------------------------------------

.. method:: math53.ein(x) 

    Returns the entire exponential integral `\displaystyle \mathrm{Ein}(x) = -\int_0^{x} \frac{1-e^{-t}}{t} \, \mathrm{d}t`.

    See also   Wikipedia :cite:p:`WikipediaFun180`, MathWorld :cite:p:`WolframFun180`, NIST :cite:p:`DLMFun180`, :cite:t:`Ehrhardt2018` (3.4.11).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.ein(-4.333)
        -22.756735632456937
        >>> math53.ein(0.0)
        0.0
        >>> math53.ein(4.333)
        2.046006677133737







Scaled exponential integral `\mathrm{e1s}(x)`
-------------------------------------------------------------------------------

.. method:: math53.exp_integral_e1_scaled(z)

    Returns the scaled exponential integral `\mathrm{e1s}(x) = e ^{-x} E_1(x)` for `x \ne 0`.

    See also   Wikipedia :cite:p:`WikipediaFun175`, MathWorld :cite:p:`WolframFun175`, NIST :cite:p:`DLMFun175`,  BoostMath :cite:p:`BoostFun175`, :cite:t:`Ehrhardt2018` (3.4.6).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.exp_integral_e1_scaled(-4.333)
        -24.800211440116243
        >>> math53.exp_integral_e1_scaled(0.1)
        1.8229239584193906
        >>> math53.exp_integral_e1_scaled(4.333)
        0.002530869474431569








Scaled exponential integral `\mathrm{eis}(x)`
-------------------------------------------------------------------------------

.. method:: math53.exp_integral_ei_scaled(x)

    Returns the scaled exponential integral `\mathrm{eis}(x) = e ^{-x} \mathrm{Ei}(x)` for `x \ne 0`.

    See also   Wikipedia :cite:p:`WikipediaFun175`, MathWorld :cite:p:`WolframFun175`, NIST :cite:p:`DLMFun175`,  BoostMath :cite:p:`BoostFun175`, :cite:t:`Ehrhardt2018` (3.4.8).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.exp_integral_ei_scaled(-4.333)
        -0.19278255765376273
        >>> math53.exp_integral_ei_scaled(0.1)
        -1.46838175654763
        >>> math53.exp_integral_ei_scaled(4.333)
        0.3255797560584637








Scaled exponential integral `\mathrm{eisx2}(x)`
-------------------------------------------------------------------------------

.. method:: math53.eisx2(x)

    Returns the scaled exponential integral `\mathrm{eisx2}(x) = e ^{-x^2} \mathrm{Ei}(x^2)` for `x \ne 0`.

    See also   Wikipedia :cite:p:`WikipediaFun175`, MathWorld :cite:p:`WolframFun175`, NIST :cite:p:`DLMFun175`,  BoostMath :cite:p:`BoostFun175`, :cite:t:`Ehrhardt2018` (3.4.9).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.eisx2(-4.333)
        0.056464567713243055
        >>> math53.eisx2(0.1)
        -3.977950399261558
        >>> math53.eisx2(4.333)
        0.056464567713243055









Inverse of the exponential integral, `\mathrm{Ei}^{-1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.ei_inv(x) 

    Returns `\mathrm{Ei}^{-1}(x) = \log(\mathrm{li}^{-1}(x))`, the functional inverse of the exponential integral, i.e. `\mathrm{Ei}(\mathrm{Ei}^{-1}(x)) = x`.

    See also   Wikipedia :cite:p:`WikipediaFun175`, MathWorld :cite:p:`WolframFun175`, NIST :cite:p:`DLMFun175`,  BoostMath :cite:p:`BoostFun175`, :cite:t:`Ehrhardt2018` (3.4.10).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.ei_inv(-4.333)
        0.056464567713243055
        >>> math53.ei_inv(0.1)
        0.39872353634725033
        >>> math53.ei_inv(4.333)
        1.8245993296832108







Generalized exponential integral `E_p(p,x)`
-------------------------------------------------------------------------------

.. method:: math53.gei(p,x) 

    Returns the generalized exponential integral of real order `\displaystyle E_p(x) = \int_{1}^{\infty} \frac{e^{-xt}}{t^p} \, \mathrm{d}t = x^{p-1} \Gamma(1-p, x) = x^{p-1} Q(1-p, x) \Gamma(1-p)`.

    See also   Wikipedia :cite:p:`WikipediaFun175`, MathWorld :cite:p:`WolframFun176`, NIST :cite:p:`DLMFun176`,  BoostMath :cite:p:`BoostFun176`, :cite:t:`Ehrhardt2018` (3.4.13).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.gei(-4.333, 0.333)
        14126.353468990947
        >>> math53.gei(0.1, 2.1)
        0.05633928555021888
        >>> math53.gei(4.333, 4.333)
        0.0015971422905912734








Exponential integral `\displaystyle \beta_n(x)`
-------------------------------------------------------------------------------

.. method:: math53.eibeta(n,x)

    Returns the exponential integral  `\displaystyle \beta_n(x) = \int_{1}^{1} t^n e^{-xt} \, \mathrm{d}t = x^{-n-1}\left(\Gamma(n+1,-x)-\Gamma(n+1,x)\right), n \ge 0`. 

    See also  :cite:t:`Abramowitz1970` (5.1.6) and (5.1.47), and :cite:t:`Ehrhardt2018` (3.4.14).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.eibeta(2, 0.333)
        0.6889912735534381
        >>> math53.eibeta(3, 2.1)
        -1.3634776730533458
        >>> math53.eibeta(4, 4.333)
        8.588862944132174







Inverse of the logarithmic integral, `\mathrm{li}^{-1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.log_integral_inv(x)

    Returns `\mathrm{li}^{-1}(x)`, the functional inverse of the logarithmic integral, i.e. `\mathrm{li}(\mathrm{li}^{-1}(x)) = x`.

    See also   Wikipedia :cite:p:`WikipediaFun177`, MathWorld :cite:p:`WolframFun177`, NIST :cite:p:`DLMFun177`, :cite:t:`Ehrhardt2018` (3.4.16).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.log_integral_inv(-4.333)
        1.0073438990424428
        >>> math53.log_integral_inv(0.1)
        1.4899216524808407
        >>> math53.log_integral_inv(4.333)
        6.2003102410812225





Shifted sine integral `\mathrm{si}(x) =  \mathrm{Si}(x) - \pi/2`
-------------------------------------------------------------------------------

.. method:: math53.shifted_sin_integral(x)

    Returns the shifted sine integral, `\mathrm{si}(x) =  \mathrm{Si}(x) - \pi/2`.

    See also   Wikipedia :cite:p:`WikipediaFun179`, MathWorld :cite:p:`WolframFun179`, NIST :cite:p:`DLMFun178`, :cite:t:`Ehrhardt2018` (3.4.19).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.shifted_sin_integral(-4.333)
        -3.2610627580571516
        >>> math53.shifted_sin_integral(0.1)
        -1.4708518656866196
        >>> math53.shifted_sin_integral(4.333)
        0.11947010446735848






