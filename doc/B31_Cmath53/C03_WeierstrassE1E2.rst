

.. |newpage| raw:: latex

   \newpage


.. |newline| raw:: latex

   \newline



.. |br| raw:: html

   <br />





|newpage|

Weierstrass elliptic functions, in terms of (real) lattice roots `e_1, e_2`
=====================================================================================

The Weierstrass functions take real values on the real axis iff the lattice is fixed under complex conjugation, or, equivalently, when `g_2, g_3 \in \mathbb{R}`.






Weierstrass function `\wp_e(x,e_1,e_2)`
-------------------------------------------------------------------------------

.. method:: ctx.weierstrass_pe(x,e1,e2)  

    where ``ctx`` is ``math53``, or ``cmathc53``.

    Returns the Weierstrass function `\wp_e(x,e_1,e_2)`, using the lattice roots.


    See also  Wikipedia :cite:p:`WikipediaFun195a`, MathWorld :cite:p:`WolframFun190`, :cite:t:`Ehrhardt2018` (3.2.17.2).

    .. math:: \wp_e(x,e_1,e_2) = e_3 + \frac{e_1-e_3}{\mathrm{sn}^2(u,k)}  = e_2 + (e_1-e_3) \frac{\mathrm{dn}^2(u,k)}{\mathrm{sn}^2(u,k)}  = e_1 + (e_1-e_3) \frac{\mathrm{cn}^2(u,k)}{\mathrm{sn}^2(u,k)}, \quad k = \sqrt{\frac{e_2-e_3}{e_1-e_3}}, \quad u = x \sqrt{e_1-e_3}.




    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_pe(-4.333, 10, 1.333)
        62.77933900177221
        >>> math53.weierstrass_pe(0.1, 20.0, 2.0)
        100.87803026305971
        >>> math53.weierstrass_pe(4.333, 34.0, 4.333)
        34.006941639647195




    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.weierstrass_pe(-4.333 + 2j, 10 + 2j, 1.333 + 2j))
        (5.59040619306163, 0.0542886723540591)
        >>> print(cmath53.weierstrass_pe(0.1 + 2j, 20.0 + 2j, 2.0 + 2j))
        (-13.69274135737, -14.9209564362749)
        >>> print(cmath53.weierstrass_pe(4.333 + 2j, 34.0 + 2j, 4.333 + 2j))
        (72.65404480432, -5.52157466207592)










Weierstrass function `\wp'_e(x,e_1,e_2)`
-------------------------------------------------------------------------------

.. method:: ctx.weierstrass_pe_prime(x,e1,e2)

    where ``ctx`` is ``math53``, or ``cmathc53``.

    Returns the derivative of the Weierstrass function `\wp'_e(x,e_1,e_2)`, using the lattice roots.


    See also Wikipedia :cite:p:`WikipediaFun195a`, MathWorld :cite:p:`WolframFun190`, :cite:t:`Ehrhardt2018` (3.2.17.3).



    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_pe_prime(-4.333, 10, 1.333)
        980.5172428571691
        >>> math53.weierstrass_pe_prime(0.1, 20.0, 2.0)
        -1982.5872192708089
        >>> math53.weierstrass_pe_prime(4.333, 34.0, 4.333)
        7.720363063395518




    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.weierstrass_pe_prime(-4.333 + 2j, 10 + 2j, 1.333 + 2j))
        (-4.38999824494254, 39.3851479574405)
        >>> print(cmath53.weierstrass_pe_prime(0.1 + 2j, 20.0 + 2j, 2.0 + 2j))
        (-214.843672001201, -39.9786384235354)
        >>> print(cmath53.weierstrass_pe_prime(4.333 + 2j, 34.0 + 2j, 4.333 + 2j))
        (-1082.62138709268, 172.238870179954)










Weierstrass Zeta function `\zeta_e(z, e_1, e_2)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_zeta_e(z, e_1, e_2)

    where ``ctx`` is ``math53``, or ``cmathc53``.


    Computes the Weierstrass zeta function `\zeta_e(z; e_1, e_2)`, using the lattice roots.


    See also MathWorld :cite:p:`WolframFun194`, Flint :cite:p:`FlintFun190`.



    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_zeta_e(-4.333, 10, 1.333)
        -25.9488086106238
        >>> math53.weierstrass_zeta_e(0.1, 20.0, 2.0)
        9.970614183821874
        >>> math53.weierstrass_zeta_e(4.333, 34.0, 4.333)
        63.38036787983493




    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.weierstrass_zeta_e(-4.333 + 2j, 10 + 2j, 1.333 + 2j))
        (-18.0157055351652, -10.4828149424189)
        >>> print(cmath53.weierstrass_zeta_e(0.1 + 2j, 20.0 + 2j, 2.0 + 2j))
        (-0.151095298216553, -19.2822083793587)
        >>> print(cmath53.weierstrass_zeta_e(4.333 + 2j, 34.0 + 2j, 4.333 + 2j))
        (70.6503283547739, -38.2130366771291)








Weierstrass Sigma function `\sigma_e(z, e_1, e_2)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_sigma_e(z, e_1, e_2)

    where ``ctx`` is ``math53``, or ``cmathc53``.


    Computes the Weierstrass sigma function, `\sigma_g(z; g_2, g_3)`, using the lattice roots.



    See also MathWorld :cite:p:`WolframFun193`, Flint :cite:p:`FlintFun190`.

    See also: https://dlmf.nist.gov/23.2



    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_sigma_e(-4.333, 10, 1.333)
        3.935093358056559e+16
        >>> math53.weierstrass_sigma_e(0.1, 20.0, 2.0)
        0.09992639951939603
        >>> math53.weierstrass_sigma_e(4.333, 34.0, 4.333)
        -7.654411553804196e+58




    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.weierstrass_sigma_e(-4.333 + 2j, 10 + 2j, 1.333 + 2j))
        (-1.39944090147892E+21, 7.70690014562852E+20)
        >>> print(cmath53.weierstrass_sigma_e(0.1 + 2j, 20.0 + 2j, 2.0 + 2j))
        (277453554.514112, 70902365.1072344)
        >>> print(cmath53.weierstrass_sigma_e(4.333 + 2j, 34.0 + 2j, 4.333 + 2j))
        (7.40240693393652E+75, 4.73199376169483E+75)





Inverse Weierstrass function `\wp^{-1}_e(y,e_1,e_2)`
-------------------------------------------------------------------------------

.. method:: math53.weierstrass_pe_inv(y,e1,e2) 

    Returns the functional inverse `\wp^{-1}_e` of the Weierstrass function for `y \ge e_1`, i.e. the smallest positive `x` with `\wp_e(x,e_1,e_2) = y`. The result is computed with the symmetric Carlson integral,

    .. math:: \wp^{-1}_e(y,e_1,e_2) = \frac{1}{2} \int_y^{\infty} \frac{\mathrm{d}t}{\sqrt{(t-e_1)(t-e_2)(t-e_3)}} = R_F(y-e_1, y-e_2, y-e_3)

    See also: MathWorld :cite:p:`WolframFun192`, :cite:t:`Ehrhardt2018` (3.2.17.8).




    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.weierstrass_pe_inv(50.1, 10, 1.333)
        0.14192809248211186
        >>> math53.weierstrass_pe_inv(44.333, 20.0, 2.0)
        0.1538126930316279
        >>> math53.weierstrass_pe_inv(144.333, 34.0, 4.333)
        0.083768035526265





