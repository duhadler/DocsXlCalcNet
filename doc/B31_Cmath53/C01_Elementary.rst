

.. |newline| raw:: latex

   \newline



.. |newpage| raw:: latex

   \newpage


.. |cr| raw:: latex

   \hspace{0.0mm}




Additional elementary complex functions
===============================================================================




Auxiliary function `\sqrt{1-z^2}`
--------------------------------------------------------------------------------------------------------

.. method:: cmath53.sqrt1mz2(z)

    Returns the square root of `1-z^2`. For very large `z` (when `z^2` would overflow) we have `\sqrt{1-z^2} = \pm iz`, where the sign is chosen to make `\Re \sqrt{1-z^2} \ge 0`; otherwise the result is computed from the definition.

    See also Wikipedia :cite:p:`WikipediaFun24`, MathWorld :cite:p:`WolframFun24`, BoostMath :cite:p:`BoostFun24`.


    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.sqrt1mz2(-4.333))
        (0, 4.21602763273677)
        >>> print(cmath53.sqrt1mz2(0.0))
        (1, 0)
        >>> print(cmath53.sqrt1mz2(4.333))
        (0, 4.21602763273677)


    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.sqrt1mz2(-4.333 + 2j))
        (2.04503636378806, 4.23757745996643)
        >>> print(cmath53.sqrt1mz2(0.0 + 2j))
        0.0
        >>> print(cmath53.sqrt1mz2(4.333 + 2j))
        (2.04503636378806, -4.23757745996643)






Cube root, `\mathrm{cuberoot}(x) = \sqrt[3]{x} = y`, with `\mathrm{arg}(y)` closest to `\mathrm{arg}(x)`
--------------------------------------------------------------------------------------------------------

.. method:: cmath53.cuberoot(z)

    Returns the cube root of `x`, `x^{1/3}` in a way which gives a negative number for negative input.  See also Wikipedia :cite:p:`WikipediaFun24`, MathWorld :cite:p:`WolframFun24`, BoostMath :cite:p:`BoostFun24`.



    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.cuberoot(-4.333))
        (-1.63028261124085, 0)
        >>> print(cmath53.cuberoot(0.0))
        (0, 0)
        >>> print(cmath53.cuberoot(4.333))
        (1.63028261124085, 0)


    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.cuberoot(-4.333 + 2j))
        (-1.66615392003231, 0.24184624308246)
        >>> print(cmath53.cuberoot(0.0 + 2j))
        (1.09112363597172, 0.629960524947436)
        >>> print(cmath53.cuberoot(4.333 + 2j))
        (1.66615392003231, 0.24184624308246)





Nth root, `\mathrm{surd}(x, n) = \sqrt[n]{x} = y`, with `\mathrm{arg}(y)` closest to `\mathrm{arg}(x)`
------------------------------------------------------------------------------------------------------

.. method:: cmathc53.surd(x, n)

    Returns the complex nth root `w = z^{1/n}` with arg(`w`) closest to arg(`z`), e.g. surd(-8, 3) = -2 or surd(`i`, 5) = `i`, compared to the cnroot results `\sqrt[3]{-8} = 1+i \sqrt{3}` and `\sqrt[5]{i} = \cos(\pi/10) +  i\sin(\pi/10)`. See  :cite:t:`Ehrhardt2018` (4.2.60).



    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.surd(-4.333, 2))
        (0, 2.08158593384948)
        >>> print(cmath53.surd(0.0, 3))
        (0, 0)
        >>> print(cmath53.surd(4.333, 4))
        (1.44277022905571, 0)


    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.surd(-4.333 + 2j, 2))
        (0.468670657289459, 2.13369449195618)
        >>> print(cmath53.surd(0.0 + 2j, 3))
        (1.09112363597172, 0.629960524947436)
        >>> print(cmath53.surd(4.333 + 2j, 4))
        (1.46939697568672, 0.159477209033463)






Continuous inverse cotangent, `\mathrm{acotc}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.acotc(x)

    where ``ctx`` is ``math53``, or ``cmathc53``.

    Returns the continuous inverse cotangent of `x`, `\mathrm{acotc}(x) = \pi/2 - \mathrm{atan}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun56`,  NIST :cite:p:`DLMFun50`, Mpmath :cite:p:`MpmathFun56`.



    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.acotc(-4.333)
        2.9147769503723295
        >>> math53.acotc(0.0)
        1.5707963267948966
        >>> math53.acotc(4.333)
        0.2268157032174636


    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.acotc(-4.333 + 2j))
        (2.95221017246, -0.0849298596570046)
        >>> print(cmath53.acotc(0.0 + 2j))
        (0, -0.549306144334055)
        >>> print(cmath53.acotc(4.333 + 2j))
        (0.189382481129794, -0.0849298596570046)




Continuous inverse hyperbolic cotangent, `\mathrm{acothc}(x)`
-------------------------------------------------------------------------------

.. method:: cmathc53.acothc(x)

    Returns the continuous inverse hyperbolic cotangent of `x`, `\mathrm{acothc}(x) = \pi/2 - \mathrm{atanh}(x) + i \cdot \pi/2`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun56`,  NIST :cite:p:`DLMFun50`, Mpmath :cite:p:`MpmathFun56`.



    An example in Python, real input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.acothc(-4.333))
        (-0.235020566146431, 3.14159265358979)
        >>> print(cmath53.acothc(0.0))
        (0, 1.5707963267949)
        >>> print(cmath53.acothc(4.333))
        (0.235020566146431, 0)


    An example in Python, complex input:

    .. code-block:: pycon

        >>> from xlcalcnet import cmath53
        >>> print(cmath53.acothc(-4.333 + 2j))
        (-0.191034096798641, 3.05075645267977)
        >>> print(cmath53.acothc(0.0 + 2j))
        (0, 2.67794504458899)
        >>> print(cmath53.acothc(4.333 + 2j))
        (0.191034096798641, 3.05075645267977)


