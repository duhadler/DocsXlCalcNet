

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Integrals of zero-order Bessel functions
===============================================================================





Integral of `J_0`
-------------------------------------------------------------------------------

.. method:: math53.bessel_j0_int(x)

    Returns the integral `\displaystyle \int_0^x J_0(t) \mathrm{d}t.`  See also  Wikipedia :cite:p:`WikipediaFun84`, MathWorld :cite:p:`WolframFun84`, NIST :cite:p:`DLMFun84`, BoostMath :cite:p:`BoostFun84`, :cite:t:`Ehrhardt2018` (3.1.5.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_j0_int(0.01)
        0.009999916666979166
        >>> math53.bessel_j0_int(10.5)
        0.9438066255262282
        >>> math53.bessel_j0_int(20.9333)
        1.1661904476467662




Integral of `Y_0`
-------------------------------------------------------------------------------

.. method:: math53.bessel_y0_int(x)

    Returns the integral `\displaystyle \int_0^x Y_0(t) \mathrm{d}t, \quad x \ge 0.`  See also  Wikipedia :cite:p:`WikipediaFun85`, MathWorld :cite:p:`WolframFun85`, NIST :cite:p:`DLMFun85`, BoostMath :cite:p:`BoostFun84`, :cite:t:`Ehrhardt2018` (3.1.5.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_y0_int(0.01)
        -0.03642134343346274
        >>> math53.bessel_y0_int(10.5)
        0.23800420896642513
        >>> math53.bessel_y0_int(20.9333)
        -0.0517899620038398




Integral of `I_0`
-------------------------------------------------------------------------------

.. method:: math53.bessel_i0_int(x)

    Returns the integral `\displaystyle \int_0^x I_0(t) \mathrm{d}t.`  See also Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun86`, NIST :cite:p:`DLMFun86`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.5.1).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_i0_int(0.01)
        0.010000083333645833
        >>> math53.bessel_i0_int(10.5)
        4794.898946365337
        >>> math53.bessel_i0_int(20.9333)
        111070471.99595156







Integral of `K_0`
-------------------------------------------------------------------------------

.. method:: math53.bessel_k0_int(x)

    Returns the integral `\displaystyle \int_0^x K_0(t) \mathrm{d}t, \quad x \ge 0.`  See also  Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun87`, NIST :cite:p:`DLMFun87`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.5.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_k0_int(0.01)
        0.057211521554724545
        >>> math53.bessel_k0_int(10.5)
        1.5707862309450589
        >>> math53.bessel_k0_int(20.9333)
        1.5707963265790326










