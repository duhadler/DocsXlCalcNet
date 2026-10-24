

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Error function, and related functions
===============================================================================




Exponentially scaled complementary error function, `\mathrm{erfcx}(x)`
-------------------------------------------------------------------------------

.. method:: math53.erfcx(x)


    Returns the exponentially scaled complementary error function `\displaystyle \mathrm{erfcx}(z) = \exp(z^2) \cdot \mathrm{erfc}(z) = w(iz)`. See also :cite:t:`Ehrhardt2018` (3.3.6).



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.erfcx(-4.333)
        285010386.1254641
        >>> math53.erfcx(0.0)
        1.0
        >>> math53.erfcx(4.333)
        0.12698575347883756








Difference of error functions, `\mathrm{erfh}(x,h) = \mathrm{erf}(x+h)-\mathrm{erf}(x-h)`
---------------------------------------------------------------------------------------------

.. method:: math53.erfh(x, h)

    Returns the difference of error functions `\displaystyle \mathrm{erfh}(x,h) = \mathrm{erf}(x+h)-\mathrm{erf}(x-h) = \mathrm{erfc}(x-h)-\mathrm{erfc}(x+h)`.

    See also :cite:t:`Ehrhardt2018` (3.3.9).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.erfh(-4.333, -4.3)
        -0.9627769999250788
        >>> math53.erfh(0.0, 0.1)
        0.2249258320365698
        >>> math53.erfh(4.333, 4.3)
        0.9627769999250788







Difference of error functions, `\mathrm{erf2}(x_1,x_2) = \mathrm{erf}(x_2)-\mathrm{erf}(x_1)`
---------------------------------------------------------------------------------------------------

.. method:: math53.erf2(x1, x2)

    Returns the difference of error functions `\displaystyle \mathrm{erf2}(x_1,x_2) = \mathrm{erf}(x_2)-\mathrm{erf}(x_1) = \mathrm{erfh}\left(  \tfrac{1}{2}(x_2+x_1), \tfrac{1}{2}(x_2-x_1) \right)`.

    See also :cite:t:`Ehrhardt2018` (3.3.10).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.erf2(-4.333, -4.3)
        3.023761733234312e-10
        >>> math53.erf2(0.0, 0.1)
        0.1124629160182849
        >>> math53.erf2(4.333, 4.3)
        -3.023761733234312e-10









Probability function `Q(x) = \Phi(-x)`
-------------------------------------------------------------------------------

.. method:: math53.erfq(x)

    Returns the integral `\displaystyle Q(x) = \Phi(-x) = \frac{1}{\sqrt 2\pi} \int_x^{\infty} \exp(-t^2)\, \mathrm{d}t = P(-x)`. 

    See also: :cite:t:`Ehrhardt2018` (3.3.12.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.erfq(-4.333)
        0.999992645444505
        >>> math53.erfq(0.0)
        0.5
        >>> math53.erfq(4.333)
        7.3545554950826356e-06






Inverse of the exponentially scaled complementary error function, `\mathrm{erfcx}^{-1}(x)`
-----------------------------------------------------------------------------------------------

.. method:: math53.erfcx_inv(x)

    Returns `\mathrm{erfcx}^{-1}(x)`, the functional inverse of `\mathrm{erfcx}`, satisfying `\mathrm{erfcx}(\mathrm{erfcx}^{-1}(x)) = x`, for `0 \le x \le \infty`.

    See also :cite:t:`Ehrhardt2018` (3.3.11.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.erfcx_inv(0.133)
        4.12712473131774
        >>> math53.erfcx_inv(0.210)
        2.51088550998549
        >>> math53.erfcx_inv(4.333)
        -0.9333744710363929








Inverse of the imaginary error function, `\mathrm{erfi}^{-1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.erfi_inv(x)

    Returns `\mathrm{erfi}^{-1}(x)`, the functional inverse of `\mathrm{erfi}`, satisfying `\mathrm{erfi}(\mathrm{erfi}^{-1}(x)) = x`.

    See also :cite:t:`Ehrhardt2018` (3.3.11.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.erfi_inv(0.133)
        0.11732758262007195
        >>> math53.erfi_inv(0.210)
        0.18400956197700832
        >>> math53.erfi_inv(4.333)
        1.475620575243282









Generalized Dawson integral, `F(p, x)`
-------------------------------------------------------------------------------

.. method:: math53.dawson2(p, x)

    Returns the generalized Dawson integral `\displaystyle F(p, x) = e^{-x^p} \int_0^x e^{t^p} \mathrm{d}t, p \ge 0, x \ge 0`. See also :cite:t:`Ehrhardt2018` (3.3.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.dawson2(0.133, 0.2)
        0.18253875263386812
        >>> math53.dawson2(0.20, 1.2)
        1.0197368694644748
        >>> math53.dawson2(4.333, 4.3)
        0.0017883958128242687







Generalized error function, `\mathrm{erfg}(p, x)`
-------------------------------------------------------------------------------

.. method:: math53.erfg(p,x)

    Returns the generalized error function `\displaystyle \mathrm{erfg}(p, x) = \int_0^x e^{-t^p} \mathrm{d}t = \frac{1}{p}\gamma\left(\frac{1}{p}, x^p \right)`, where `\gamma(\cdot)` denotes the non-normalised lower incomplete gamma function. See also :cite:t:`Ehrhardt2018` (3.3.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.erfg(0.133, 0.2)
        0.0984423713670484
        >>> math53.erfg(0.20, 1.2)
        0.5113754785616778
        >>> math53.erfg(4.333, 4.3)
        0.9105748355517699





Expint3, `\mathrm{erfg}(3, x)`
-------------------------------------------------------------------------------

.. method:: math53.expint3(x)

    Returns `\displaystyle \mathrm{expint3}(p, x) = \mathrm{erfg}(3, x) = \int_0^x e^{-t^3} \mathrm{d}t = \frac{1}{3}\gamma\left(\frac{1}{3}, x^3 \right)`, where `\gamma(\cdot)` denotes the non-normalised lower incomplete gamma function. See also :cite:t:`Ehrhardt2018` (3.3.13).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.expint3(0.333)
        0.32995806253817933
        >>> math53.expint3(2.1)
        0.8929727701083042
        >>> math53.expint3(4.333)
        0.8929795115692493










Scaled repeated integrals of  the complementary error function, `i^n \mathrm{erfc}(x)`
--------------------------------------------------------------------------------------------

.. method:: math53.inerfc(n, x)

    Returns the scaled repeated integrals of the complementary error function, defined for `n \ge -1` using the awkward but standard notation

    .. math::  i^n \mathrm{erfc}(x) = \int_x^{\infty} \mathrm{erfc}(t) \, \mathrm{d}t = \frac{2}{\sqrt{\pi}} \int_x^{\infty} \frac{(t-x)^n}{n!} e^{-t^2} \, \mathrm{d}t, \quad (n = 0,1,2,...).

    See also :cite:t:`Ehrhardt2018` (3.3.7),  NIST :cite:p:`DLMFun187` (eq. 7.18.10), MathWorld :cite:p:`WolframFun187`.


    These functions compute the scaled repeated integrals of complementary error function, defined for `n \geq -1` using the awkward but standard notation

    .. math :: i^n \text{erfc}(x) = \int_x^\infty i^{n-1} \text{erfc}(t)\mathrm{d}t = \frac{2}{\sqrt{\pi}} \int_x^\infty \frac{(t-x)^n}{n!} e^{-t^2} \mathrm{d}t, \quad (n=0,1,2,\ldots)


    .. math :: i^{-1} \text{erfc}(x) =  \frac{2}{\sqrt{\pi}} e^{-x^2}, \quad i^{0} \text{erfc}(x) =  \text{erfc}(x).


    .. math :: i^{n} \text{erfc}(x) =  -\frac{z}{n} i^{n-1} \text{erfc}(x) + \frac{1}{2n} i^{n-2} \text{erfc}(x.


    We also have

    .. math :: i^{n} \text{erfc}(x) =  \frac{e^{-z^2}}{2^n \sqrt{\pi}}  U \left(\tfrac{1}{2}n+\tfrac{1}{2},\tfrac{1}{2},z^2  \right)  




    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.inerfc(2, -4.3)
        18.98999999998569
        >>> math53.inerfc(3, 0.01)
        0.09156879696249248
        >>> math53.inerfc(4, 4.3)
        1.6897530115750235e-05







Fresnel auxiliary function `\mathrm{f}(x)`
-------------------------------------------------------------------------------

.. method:: math53.fresnel_f(x) 

    Returns the Fresnel auxiliary function `\displaystyle \mathrm{f}\left(x\right)=\left(\tfrac{1}{2}-S\left(x\right)\right)\cos\left(\tfrac{1}{2}\pi x^{2}\right)-\left(\tfrac{1}{2}-C\left(x\right)\right)\sin\left(\tfrac{1}{2}\pi x^{2}\right)`.

    See also  Wikipedia :cite:p:`WikipediaFun182`, MathWorld :cite:p:`WolframFun182b`, NIST :cite:p:`DLMFun182`, :cite:t:`Ehrhardt2018` (3.3.15).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.fresnel_f(-4.333)
        0.5184512886301054
        >>> math53.fresnel_f(0.0)
        0.5
        >>> math53.fresnel_f(4.333)
        0.0733990512696557







Fresnel auxiliary function `\mathrm{g}(x)`
-------------------------------------------------------------------------------

.. method:: math53.fresnel_g(x)

    Returns the Fresnel auxiliary function `\displaystyle \mathrm{g}\left(x\right)=\left(\tfrac{1}{2}-C\left(x\right)\right)\cos\left(\tfrac{1}{2}\pi x^{2}\right)+\left(\tfrac{1}{2}-S\left(x\right)\right)\sin\left(\tfrac{1}{2}\pi x^{2}\right)`.

    See also  Wikipedia :cite:p:`WikipediaFun182`, MathWorld :cite:p:`WolframFun182b`, NIST :cite:p:`DLMFun182`, :cite:t:`Ehrhardt2018` (3.3.15).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.fresnel_g(-4.333)
        -1.2856518027760035
        >>> math53.fresnel_g(0.0)
        0.5
        >>> math53.fresnel_g(4.333)
        0.0012401961792171978







Goodwin-Staton integral, `G(x)`
-------------------------------------------------------------------------------

.. method:: math53.goodwin_staton(x)

    Returns the Goodwin-Staton integral  `\displaystyle G(x) = \int_0^{\infty} \frac{e^{-t^2}}{t+x} \, \mathrm{d}t = \sqrt{\pi} F(x) - \tfrac{1}{2} e^{-x^2} \mathrm{Ei}(x^2), \quad x \ne 0`.

    See also Wikipedia :cite:p:`WikipediaFun183`, NIST :cite:p:`DLMFun183`, :cite:t:`Ehrhardt2018` (3.3.16).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.goodwin_staton(-4.333)
        -0.2387165659508476
        >>> math53.goodwin_staton(0.1)
        2.1650436618898743
        >>> math53.goodwin_staton(4.333)
        0.18225199823760455






Voigt function U
-------------------------------------------------------------------------------

.. method:: math53.voigt_u(x, t)

    Returns the Voigt function U. See also  Wikipedia :cite:p:`WikipediaFun185`, NIST :cite:p:`DLMFun185`.

    The Voigt functions[1] U, V, and H (sometimes called the line broadening function) are defined by

    .. math :: U(x,t)+iV(x,t)={\sqrt {\frac {\pi }{4t}}}e^{z^{2}}\operatorname {erfc} (z)={\sqrt {\frac {\pi }{4t}}}w(iz),

    .. math :: H(a,u)={\frac {U(u/a,1/4a^{2})}{a{\sqrt {\pi }}}},

    where

    .. math :: z=(1-ix)/2{\sqrt {t}},

    erfc is the complementary error function, and w(z) is the Faddeeva function.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.voigt_u(-4.333, 0.13)
        0.05254336595640464
        >>> math53.voigt_u(0.0, 0.21)
        0.7811438005184261
        >>> math53.voigt_u(4.333, 4.3)
        0.1490998347762494







Voigt function V
-------------------------------------------------------------------------------

.. method:: math53.voigt_v(x, t)

    Returns the Voigt function V. See also Wikipedia :cite:p:`WikipediaFun185`, NIST :cite:p:`DLMFun185`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.voigt_v(-4.333, 0.13)
        -0.22146326272595282
        >>> math53.voigt_v(0.0, 0.21)
        0.0
        >>> math53.voigt_v(4.333, 4.3)
        0.19560699319119224






Voigt function H
-------------------------------------------------------------------------------

.. method:: math53.voigt_h(a, u)

    Returns the Voigt function H. See also Wikipedia :cite:p:`WikipediaFun185`, NIST :cite:p:`DLMFun185`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.voigt_h(-4.333, 0.13)
        -0.1268843321935899
        >>> math53.voigt_h(0.1, 0.21)
        0.861821897691752
        >>> math53.voigt_h(4.333, 4.3)
        0.06643025352849169






Voigt Profile distribution, pdf
-------------------------------------------------------------------------------

.. method:: math53.voigt_profile_pdf(x, sigma, gamma)


    Returns `\text{pdf}(x)`, the probability density function of a random variable `X`, following a Voigt Profile distribution with shape `sigma > 0`, scale `gamma > 0`, and the support interval `(0, +\infty)`.
    See also  Wikipedia :cite:p:`WikipediaDis56`.


    .. math:: \text{pdf}(x) = V(x; \sigma, \gamma) = \frac{\Re[w(z)]}{\sigma \sqrt{2 \pi}}, \quad \text{where } z = \frac{x + i\gamma}{\sigma \sqrt{\pi}}.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.voigt_profile_pdf(-4.333, 0.13, 1.13)
        0.022564184036184317
        >>> math53.voigt_profile_pdf(0.0, 0.21, 1.21)
        0.31591913104142727
        >>> math53.voigt_profile_pdf(4.333, 4.3, 14.3)
        0.023604268551340794





