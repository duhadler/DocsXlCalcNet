

.. |newpage| raw:: latex

   \newpage


.. |newline| raw:: latex

   \newline



.. |br| raw:: html

   <br />





|newpage|

Weierstrass elliptic functions, in terms of (real) lattice invariants `g_2, g_3`
=====================================================================================

The Weierstrass functions take real values on the real axis iff the lattice is fixed under complex conjugation, or, equivalently, when `g_2, g_3 \in \mathbb{R}`.



.. _rst_mpm_wpg: 

Weierstrass function `\wp_g(z, g_2, g_3)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_pg(z, g2, g3)

    where ``ctx`` is ``math53``, or ``cmathc53``.

    Returns the Weierstrass function `\wp_g(x, g_2, g_3)` based on the lattice invariants `g_2`, `g_3`.

    See also Wikipedia :cite:p:`WikipediaFun195a`, MathWorld :cite:p:`WolframFun190`, :cite:t:`Ehrhardt2018` (3.2.17.5).


    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_pg(-4.333, 10, 1.333)
        13.66531644861815
        >>> math53.weierstrass_pg(0.1, 20.0, 2.0)
        100.01000747639043
        >>> math53.weierstrass_pg(4.333, 34.0, 4.333)
        23.029224134567052




    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.weierstrass_pg(-4.333 + 2j, 10 + 2j, 1.333 + 2j))
        (-0.773959377143707, -2.75887336080179)
        >>> print(cmath53.weierstrass_pg(0.1 + 2j, 20.0 + 2j, 2.0 + 2j))
        (-14.0272474577254, -12.142040527299)
        >>> print(cmath53.weierstrass_pg(4.333 + 2j, 34.0 + 2j, 4.333 + 2j))
        (-2.53556102759659, 1.72556229967144)





|11a_TestWeierstrassP_re| `\quad` |11b_TestWeierstrassP_im| `\quad` |11c_TestWeierstrassP_abs|

.. |11a_TestWeierstrassP_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/11a_TestWeierstrassP_re.3D.xml.jpg
   :width: 30 %

.. |11b_TestWeierstrassP_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/11b_TestWeierstrassP_im.3D.xml.jpg
   :width: 30 %

.. |11c_TestWeierstrassP_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/11c_TestWeierstrassP_abs.3D.xml.jpg
   :width: 30 %



**Left figure**: real part of the Weierstrass function `\wp_g(z, g_2, g_3)`. 


**Middle figure**: imaginary part of the Weierstrass function `\wp_g(z, g_2, g_3)`. 


**Right figure**:  absolute value of the Weierstrass function `\wp_g(z, g_2, g_3)`, with color-coded phase. 







|newpage|


.. _rst_mpm_wpg_prime: 

Weierstrass function, first derivative: `\wp_g'(z, g_2, g_3)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_pg_prime(z, g2, g3)

    where ``ctx`` is ``math53``, or ``cmathc53``.

    Returns the first derivative (with respect to z) of Weierstrass function `\wp_g(x, g_2, g_3)` based on the lattice invariants `g_2`, `g_3`.

    See also: MathWorld :cite:p:`WolframFun191`, :cite:t:`Ehrhardt2018` (3.2.17.6).


    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_pg_prime(-4.333, 10, 1.333)
        100.34693001925689
        >>> math53.weierstrass_pg_prime(0.1, 20.0, 2.0)
        -1999.799694269612
        >>> math53.weierstrass_pg_prime(4.333, 34.0, 4.333)
        219.24056194806474




    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.weierstrass_pg_prime(-4.333 + 2j, 10 + 2j, 1.333 + 2j))
        (-9.60742727506246, -4.7515735665036)
        >>> print(cmath53.weierstrass_pg_prime(0.1 + 2j, 20.0 + 2j, 2.0 + 2j))
        (140.509864195873, -75.5822080332633)
        >>> print(cmath53.weierstrass_pg_prime(4.333 + 2j, 34.0 + 2j, 4.333 + 2j))
        (-10.8452449282067, -2.62673784448917)






|12a_TestWeierstrassPPrime_re| `\quad` |12b_TestWeierstrassPPrime_im| `\quad` |12c_TestWeierstrassPPrime_abs|

.. |12a_TestWeierstrassPPrime_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/12a_TestWeierstrassPPrime_re.3D.xml.jpg
   :width: 30 %

.. |12b_TestWeierstrassPPrime_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/12b_TestWeierstrassPPrime_im.3D.xml.jpg
   :width: 30 %

.. |12c_TestWeierstrassPPrime_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/12c_TestWeierstrassPPrime_abs.3D.xml.jpg
   :width: 30 %



**Left figure**: real part of the Weierstrass function, first derivative: `\wp_g'(z, g_2, g_3)`. 


**Middle figure**: imaginary part of the Weierstrass function, first derivative: `\wp_g'(z, g_2, g_3)`. 


**Right figure**:  absolute value of the Weierstrass function, first derivative: `\wp_g'(z, g_2, g_3)`, with color-coded phase. 







|newpage|



.. _rst_mpm_weierstrass_zeta: 

Weierstrass Zeta function `\zeta_g(z, g_2, g_3)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_zeta_g(z, g2, g3)

    where ``ctx`` is ``math53``, or ``cmathc53``.

    Computes the Weierstrass zeta function `\zeta_g(z; g_2, g_3)`. 


    The function is related to `\wp(z; g_2, g_3)` by `\displaystyle \frac{d \zeta(z; g_2, g_3)}{\mathrm{d}z} = -\wp(z; g_2, g_3)` and `\displaystyle \zeta(z; g_2, g_3) - z^{-1} = \int_0^z \left(\wp(z; g_2, g_3) - z^{-2} \right)`.


    See also MathWorld :cite:p:`WolframFun194`, Flint :cite:p:`FlintFun190`.



    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_zeta_g(-4.333, 10, 1.333)
        -6.828148914468967
        >>> math53.weierstrass_zeta_g(0.1, 20.0, 2.0)
        9.999666519045453
        >>> math53.weierstrass_zeta_g(4.333, 34.0, 4.333)
        1.491047024531138




    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.weierstrass_zeta_g(-4.333 + 2j, 10 + 2j, 1.333 + 2j))
        (-4.3288407986234, -0.33662296937503)
        >>> print(cmath53.weierstrass_zeta_g(0.1 + 2j, 20.0 + 2j, 2.0 + 2j))
        (1.51475775412759, -5.77385329910738)
        >>> print(cmath53.weierstrass_zeta_g(4.333 + 2j, 34.0 + 2j, 4.333 + 2j))
        (5.53116697709506, -3.43549361319103)





|13a_TestWeierstrassZeta_re| `\quad` |13b_TestWeierstrassZeta_im| `\quad` |13c_TestWeierstrassZeta_abs|

.. |13a_TestWeierstrassZeta_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/13a_TestWeierstrassZeta_re.3D.xml.jpg
   :width: 30 %

.. |13b_TestWeierstrassZeta_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/13b_TestWeierstrassZeta_im.3D.xml.jpg
   :width: 30 %

.. |13c_TestWeierstrassZeta_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/13c_TestWeierstrassZeta_abs.3D.xml.jpg
   :width: 30 %



**Left figure**: real part of the Weierstrass Zeta function `\zeta_g(z, g_2, g_3)`. 


**Middle figure**: imaginary part of the Weierstrass Zeta function `\zeta_g(z, g_2, g_3)`. 


**Right figure**:  absolute value of the Weierstrass Zeta function `\zeta_g(z, g_2, g_3)`, with color-coded phase. 








|newpage|


.. _rst_mpm_weierstrass_sigma: 

Weierstrass Sigma function `\sigma_g(z, g_2, g_3`)
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_sigma_g(z, g2, g3)

    where ``ctx`` is ``math53``, or ``cmathc53``.


    Computes the Weierstrass sigma function, `\sigma_g(z; g_2, g_3)`. We have `\sigma_g(tz; t^{-4} g_2, t^{-6} g_3) = t \sigma_g(z; g_2, g_3)`.  |newline|

    The function is related to `\zeta(z; g_2, g_3)` by `\displaystyle \frac{d}{\mathrm{d}z} \log \sigma(z; g_2, g_3) = \zeta(z; g_2, g_3)`.


    See also MathWorld :cite:p:`WolframFun193`, Flint :cite:p:`FlintFun190`.

    See also: https://dlmf.nist.gov/23.2




    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_sigma_g(-4.333, 10, 1.333)
        -372.92427325514853
        >>> math53.weierstrass_sigma_g(0.1, 20.0, 2.0)
        0.09999916642609118
        >>> math53.weierstrass_sigma_g(4.333, 34.0, 4.333)
        87291.86806897493




    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.weierstrass_sigma_g(-4.333 + 2j, 10 + 2j, 1.333 + 2j))
        (-3115.98477265303, 2832.39246145056)
        >>> print(cmath53.weierstrass_sigma_g(0.1 + 2j, 20.0 + 2j, 2.0 + 2j))
        (-0.789295547618554, -1.39808798175058)
        >>> print(cmath53.weierstrass_sigma_g(4.333 + 2j, 34.0 + 2j, 4.333 + 2j))
        (-2463045.45917973, 482034.324963562)




|14a_TestWeierstrassSigma_re| `\quad` |14b_TestWeierstrassSigma_im| `\quad` |14c_TestWeierstrassSigma_abs|

.. |14a_TestWeierstrassSigma_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/14a_TestWeierstrassSigma_re.3D.xml.jpg
   :width: 30 %

.. |14b_TestWeierstrassSigma_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/14b_TestWeierstrassSigma_im.3D.xml.jpg
   :width: 30 %

.. |14c_TestWeierstrassSigma_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/14c_TestWeierstrassSigma_abs.3D.xml.jpg
   :width: 30 %



**Left figure**: real part of the Weierstrass Sigma function `\sigma_g(z, g_2, g_3`). 


**Middle figure**: imaginary part of the Weierstrass Sigma function `\sigma_g(z, g_2, g_3`). 


**Right figure**:  absolute value of the Weierstrass Sigma function `\sigma_g(z, g_2, g_3`), with color-coded phase. 






|newpage|

.. _rst_mpm_wpg_inv: 

Inverse Weierstrass function `\wp_g^{-1}(z, g_2, g_3)`
-------------------------------------------------------------------------------


.. method:: math53.weierstrass_pg_inv(z, g2, g3)


    Returns the functional inverse `\wp^{-1}_g` of the Weierstrass function for `y \ge e_1`, i.e. the smallest positive `x` with `\wp^{-1}_g(y,g_2,g_3) = y`, if it exists. See also: MathWorld :cite:p:`WolframFun192`, :cite:t:`Ehrhardt2018` (3.2.17.9).

    See also MathWorld :cite:p:`WolframFun192`, Flint :cite:p:`FlintFun190`.


    .. math :: \wp_g^{-1}(z; g_2, g_3) = \wp^{-1}(z| \tau = \omega_2/\omega_1, \omega = \omega_1)



    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_pg_inv(4.333, 10, 1.333)
        0.4873459128502748
        >>> math53.weierstrass_pg_inv(10.1, 20.0, 2.0)
        0.3162445425781658
        >>> math53.weierstrass_pg_inv(14.333, 34.0, 4.333)
        0.26525776346953506








