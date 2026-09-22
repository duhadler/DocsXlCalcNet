

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

        >>> from xlcalcnet import ereal
        >>> ereal.Erfce(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Erfce('0.51')
        ereal('5.3518479027559984754E-1')








Difference of error functions, `\mathrm{erfh}(x,h) = \mathrm{erf}(x+h)-\mathrm{erf}(x-h)`
---------------------------------------------------------------------------------------------

.. method:: math53.erfh(x, h)

    Returns the difference of error functions `\displaystyle \mathrm{erfh}(x,h) = \mathrm{erf}(x+h)-\mathrm{erf}(x-h) = \mathrm{erfc}(x-h)-\mathrm{erfc}(x+h)`.

    See also :cite:t:`Ehrhardt2018` (3.3.9).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Erfh(0.5, 0.6)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Erfh('0.51', 0.61)
        ereal('5.3518479027559984754E-1')







Difference of error functions, `\mathrm{erf2}(x_1,x_2) = \mathrm{erf}(x_2)-\mathrm{erf}(x_1)`
---------------------------------------------------------------------------------------------------

.. method:: math53.erf2(x1, x2)

    Returns the difference of error functions `\displaystyle \mathrm{erf2}(x_1,x_2) = \mathrm{erf}(x_2)-\mathrm{erf}(x_1) = \mathrm{erfh}\left(  \tfrac{1}{2}(x_2+x_1), \tfrac{1}{2}(x_2-x_1) \right)`.

    See also :cite:t:`Ehrhardt2018` (3.3.10).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Erf2(0.5, 0.6)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Erf2('0.51', 0.61)
        ereal('5.3518479027559984754E-1')









Probability function `Q(x) = \Phi(-x)`
-------------------------------------------------------------------------------

.. method:: math53.erfq(x)

    Returns the integral `\displaystyle Q(x) = \Phi(-x) = \frac{1}{\sqrt 2\pi} \int_x^{\infty} \exp(-t^2)\, \mathrm{d}t = P(-x)`. 

    See also: :cite:t:`Ehrhardt2018` (3.3.12.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.ErfQ(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.ErfQ('0.51')
        ereal('5.3518479027559984754E-1')






Inverse of the exponentially scaled complementary error function, `\mathrm{erfcx}^{-1}(x)`
-----------------------------------------------------------------------------------------------

.. method:: math53.erfcx_inv(x)

    Returns `\mathrm{erfcx}^{-1}(x)`, the functional inverse of `\mathrm{erfcx}`, satisfying `\mathrm{erfcx}(\mathrm{erfcx}^{-1}(x)) = x`, for `0 \le x \le \infty`.

    See also :cite:t:`Ehrhardt2018` (3.3.11.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.ErfceInv(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.ErfceInv('0.51')
        ereal('5.3518479027559984754E-1')








Inverse of the imaginary error function, `\mathrm{erfi}^{-1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.erfi_inv(x)

    Returns `\mathrm{erfi}^{-1}(x)`, the functional inverse of `\mathrm{erfi}`, satisfying `\mathrm{erfi}(\mathrm{erfi}^{-1}(x)) = x`.

    See also :cite:t:`Ehrhardt2018` (3.3.11.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.ErfiInv(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.ErfiInv('0.51')
        ereal('5.3518479027559984754E-1')









Generalized Dawson integral, `F(p, x)`
-------------------------------------------------------------------------------

.. method:: math53.dawson2(p, x)

    Returns the generalized Dawson integral `\displaystyle F(p, x) = e^{-x^p} \int_0^x e^{t^p} \mathrm{d}t, p \ge 0, x \ge 0`. See also :cite:t:`Ehrhardt2018` (3.3.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Dawson2(1.5, 0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Dawson2(1.5, '0.51')
        ereal('5.3518479027559984754E-1')



        



Generalized error function, `\mathrm{erfg}(p, x)`
-------------------------------------------------------------------------------

.. method:: math53.erfg(p,x)

    Returns the generalized error function `\displaystyle \mathrm{erfg}(p, x) = \int_0^x e^{-t^p} \mathrm{d}t = \frac{1}{p}\gamma\left(\frac{1}{p}, x^p \right)`, where `\gamma(\cdot)` denotes the non-normalised lower incomplete gamma function. See also :cite:t:`Ehrhardt2018` (3.3.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Erfg(1.5, 0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Erfg(1.5, '0.51')
        ereal('5.3518479027559984754E-1')





Expint3, `\mathrm{erfg}(3, x)`
-------------------------------------------------------------------------------

.. method:: math53.expint3(x)

    Returns `\displaystyle \mathrm{expint3}(p, x) = \mathrm{erfg}(3, x) = \int_0^x e^{-t^3} \mathrm{d}t = \frac{1}{3}\gamma\left(\frac{1}{3}, x^3 \right)`, where `\gamma(\cdot)` denotes the non-normalised lower incomplete gamma function. See also :cite:t:`Ehrhardt2018` (3.3.13).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Expint3(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Expint3('0.51')
        ereal('5.3518479027559984754E-1')










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

        >>> from xlcalcnet import ereal
        >>> ereal.InErfc(3, 0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.InErfc(3, '0.51')
        ereal('5.3518479027559984754E-1')




    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import dec, mpm, gmp, fpm, apm
        >>> mpm.dps = 40; n = '4'; x = '5.0'
        >>> \mathrm{d}x = dec.inerfc(n, x); mx = mpm.inerfc(n, x); gx = gmp.inerfc(n, x)
        >>> fx = fpm.inerfc(n, x); ax = apm.inerfc(n, x)
        >>> mpm.show([\mathrm{d}x, mx, gx, fx, ax])
        dec:  8.631401306269731883125812071651943647995E-6
        mpm:  8.631401306269731883125812071651943647995e-6
        gmp:  8.631401306269731883125812071651943647995E-06
        fpm:  8.63140130626973E-06
        apm:  8.631401306269731883125812071651943657349e-6 (1.945e-32%)


    An example with complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import dec, mpm, gmp, fpm, apm
        >>> mpm.dps = 20; n = '4'; z = '5.0 + 3.0j'
        >>> \mathrm{d}z = dec.inerfc(n, z); mz = mpm.inerfc(n, z); gz = gmp.inerfc(n, z)
        >>> fz = fpm.inerfc(n, z); az = apm.inerfc(n, z)
        >>> mpm.show([\mathrm{d}z, mz, gz, fz, az], aligned=True)
        dec: -3.8136067248438755019E-6               - 2.7044284620493310438E-6j
        mpm: -3.8136067248438755019e-6               - 2.7044284620493310438e-6j
        gmp: -3.8136067248438755019E-06              - 2.7044284620493310438E-06j
        fpm: -3.81360672484388E-06                   - 2.70442846204933E-06j
        apm: -3.8136067248438754005e-6 (-2.848e-13%) - 2.7044284620493310996e-6 (-3.025e-13%)j



        

Fresnel auxiliary function `\mathrm{f}(x)`
-------------------------------------------------------------------------------

.. method:: math53.fresnel_f(x) 

    Returns the Fresnel auxiliary function `\displaystyle \mathrm{f}\left(x\right)=\left(\tfrac{1}{2}-S\left(x\right)\right)\cos\left(\tfrac{1}{2}\pi x^{2}\right)-\left(\tfrac{1}{2}-C\left(x\right)\right)\sin\left(\tfrac{1}{2}\pi x^{2}\right)`.

    See also  Wikipedia :cite:p:`WikipediaFun182`, MathWorld :cite:p:`WolframFun182b`, NIST :cite:p:`DLMFun182`, :cite:t:`Ehrhardt2018` (3.3.15).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.FresnelF(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.FresnelF('0.51')
        ereal('5.3518479027559984754E-1')







Fresnel auxiliary function `\mathrm{g}(x)`
-------------------------------------------------------------------------------

.. method:: math53.fresnel_g(x)

    Returns the Fresnel auxiliary function `\displaystyle \mathrm{g}\left(x\right)=\left(\tfrac{1}{2}-C\left(x\right)\right)\cos\left(\tfrac{1}{2}\pi x^{2}\right)+\left(\tfrac{1}{2}-S\left(x\right)\right)\sin\left(\tfrac{1}{2}\pi x^{2}\right)`.

    See also  Wikipedia :cite:p:`WikipediaFun182`, MathWorld :cite:p:`WolframFun182b`, NIST :cite:p:`DLMFun182`, :cite:t:`Ehrhardt2018` (3.3.15).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.FresnelG(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.FresnelG('0.51')
        ereal('5.3518479027559984754E-1')







Goodwin-Staton integral, `G(x)`
-------------------------------------------------------------------------------

.. method:: math53.goodwin_staton(x)

    Returns the Goodwin-Staton integral  `\displaystyle G(x) = \int_0^{\infty} \frac{e^{-t^2}}{t+x} \, \mathrm{d}t = \sqrt{\pi} F(x) - \tfrac{1}{2} e^{-x^2} \mathrm{Ei}(x^2), \quad x \ne 0`.

    See also Wikipedia :cite:p:`WikipediaFun183`, NIST :cite:p:`DLMFun183`, :cite:t:`Ehrhardt2018` (3.3.16).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.GoodwinStaton(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.GoodwinStaton('0.51')
        ereal('5.3518479027559984754E-1')






Voigt function U
-------------------------------------------------------------------------------

.. method:: math53.voigt_u(z)

    Returns the Voigt function U. See also  Wikipedia :cite:p:`WikipediaFun185`, NIST :cite:p:`DLMFun185`.

    The Voigt functions[1] U, V, and H (sometimes called the line broadening function) are defined by

    .. math :: U(x,t)+iV(x,t)={\sqrt {\frac {\pi }{4t}}}e^{z^{2}}\operatorname {erfc} (z)={\sqrt {\frac {\pi }{4t}}}w(iz),

    .. math :: H(a,u)={\frac {U(u/a,1/4a^{2})}{a{\sqrt {\pi }}}},

    where

    .. math :: z=(1-ix)/2{\sqrt {t}},

    erfc is the complementary error function, and w(z) is the Faddeeva function.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ecplx
        >>> ecplx.VoigtU(0.5)
        ecplx('5.2359877559829887307E-1')
        >>> ecplx.VoigtU('0.1')
        ecplx('5.3518479027559984754E-1')







Voigt function V
-------------------------------------------------------------------------------

.. method:: math53.voigt_v(x, t)

    Returns the Voigt function V. See also Wikipedia :cite:p:`WikipediaFun185`, NIST :cite:p:`DLMFun185`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ecplx
        >>> ecplx.VoigtV(0.5)
        ecplx('5.2359877559829887307E-1')
        >>> ecplx.VoigtV('0.1')
        ecplx('5.3518479027559984754E-1')






Voigt function H
-------------------------------------------------------------------------------

.. method:: math53.voigt_h(x, t)

    Returns the Voigt function H. See also Wikipedia :cite:p:`WikipediaFun185`, NIST :cite:p:`DLMFun185`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ecplx
        >>> ecplx.VoigtH(0.5)
        ecplx('5.2359877559829887307E-1')
        >>> ecplx.VoigtH('0.1')
        ecplx('5.3518479027559984754E-1')






Voigt Profile distribution, pdf
-------------------------------------------------------------------------------

.. method:: math53.voigt_profile_pdf(q, a, b)


    Returns `\text{pdf}(x)`, the probability density function of a random variable `X`, following a Voigt Profile distribution with shape `a > 0`, scale `b > 0`, and the support interval `(0, +\infty)`.
    See also  Wikipedia :cite:p:`WikipediaDis56`.


    .. math:: \text{pdf}(x) = V(x; \sigma, \gamma) = \frac{\Re[w(z)]}{\sigma \sqrt{2 \pi}}, \quad \text{where } z = \frac{x + i\gamma}{\sigma \sqrt{\pi}}.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ecplx
        >>> ecplx.VoigtProfilePdf(0.5)
        ecplx('5.2359877559829887307E-1')
        >>> ecplx.VoigtProfilePdf('0.1')
        ecplx('5.3518479027559984754E-1')





