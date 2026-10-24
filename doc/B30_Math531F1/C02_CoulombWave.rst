

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />






|newpage|

Coulomb wave functions
==============================================================================================



.. _rst_mpm_coulombc: 

Normalizing Gamow constant for Coulomb wave functions
-------------------------------------------------------------------------------

.. method:: math53.coulomb_cl(l, eta)

    Returns the normalizing Gamow constant for Coulomb wave functions. See also  Wikipedia :cite:p:`WikipediaFun1052`, MathWorld :cite:p:`WolframFun1052`, NIST :cite:p:`DLMFun1052`, :cite:t:`Thompson1986`, :cite:t:`Michel2007`, :cite:t:`Ehrhardt2018` (3.1.10.1), Mpmath :cite:p:`MpmathFun1052`. 


    Gives the normalizing Gamow constant for Coulomb wave functions,

    .. math ::  C_l(\eta) = 2^l \exp\left(-\pi \eta/2 + [\log \Gamma(1+l+i\eta) + \log \Gamma(1+l-i\eta)]/2 - \log \Gamma(2l+2)\right),

    where the log gamma function with continuous imaginary part away from the negative half axis is implied.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.coulomb_cl(2, -4.333)
        3.69103518943773
        >>> math53.coulomb_cl(3, 0.0)
        0.009523809523809523
        >>> math53.coulomb_cl(4, 4.333)
        1.8588429181136979e-07







Coulomb phase shift `\sigma_L(\eta)`
-------------------------------------------------------------------------------

.. method:: math53.coulomb_sl(L, eta)

    Returns the Coulomb phase shift for Coulomb wave functions.

    See also: :cite:t:`Ehrhardt2018` (3.1.10.2). 



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.coulomb_sl(2, -4.333)
        -5.268776330468265
        >>> math53.coulomb_sl(3, 0.0)
        0.0
        >>> math53.coulomb_sl(4, 4.333)
        7.059330502056313






.. _rst_mpm_coulombf: 

Regular Coulomb wave functions `F_l(\eta, x), F'_l(\eta, x)`
-------------------------------------------------------------------------------------------

.. method:: math53.coulomb_f_fprime(L, eta, x)


    Returns simultaneously the regular Coulomb wave function `F_l(\eta, x)`, and its first derivative, `F'_l(\eta, x)`.
    
    See also  Wikipedia :cite:p:`WikipediaFun1052`, MathWorld :cite:p:`WolframFun1052`, NIST :cite:p:`DLMFun1052`, :cite:t:`Ehrhardt2018` (3.1.10.3), Flint :cite:p:`FlintFun1052`, Flint :cite:p:`FlintFun1053`, Mpmath :cite:p:`MpmathFun1053`.




    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> print(math53.coulomb_f_fprime(2, -4.333, 4.333))
        (0.682089111804269, 0.645302191673521)
        >>> print(math53.coulomb_f_fprime(3, 0.0, 4.333))
        (1.04051906190237, 0.316468713579997)
        >>> print(math53.coulomb_f_fprime(4, 4.333, -4.333))
        (0, 0)









Irregular Coulomb wave functions `G_l(\eta,x), G'_l(\eta,x)`
-------------------------------------------------------------------------------

.. method:: math53.coulomb_g_gprime(L, eta, x)

    Returns simultaneously the irregular Coulomb wave function `G_l(\eta, x)`, and its first derivative, `G'_l(\eta, x)`.

    See also  Wikipedia :cite:p:`WikipediaFun1052`, MathWorld :cite:p:`WolframFun1052`, NIST :cite:p:`DLMFun1052`, :cite:t:`Ehrhardt2018` (3.1.10.5), Mpmath :cite:p:`MpmathFun1054`.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> print(math53.coulomb_g_gprime(2, -4.333, 4.333))
        (0.38242285077798, -1.10428635087651)
        >>> print(math53.coulomb_g_gprime(3, 0.0, 4.333))
        (0.631311726911029, -0.769048467457657)
        >>> print(math53.coulomb_g_gprime(4, 4.333, -4.333))
        (0, 0)




