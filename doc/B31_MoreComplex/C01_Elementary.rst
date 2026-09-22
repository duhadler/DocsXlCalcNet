

.. |newline| raw:: latex

   \newline



.. |newpage| raw:: latex

   \newpage


.. |cr| raw:: latex

   \hspace{0.0mm}




|newpage|

Additional elementary complex functions
===============================================================================




Auxiliary function `\sqrt{1-z^2}`
--------------------------------------------------------------------------------------------------------

.. method:: math53.sqrt1mz2(z)

    Returns the square root of `1-z^2`. For very large `z` (when `z^2` would overflow) we have `\sqrt{1-z^2} = \pm iz`, where the sign is chosen to make `\Re \sqrt{1-z^2} \ge 0`; otherwise the result is computed from the definition.

    See also Wikipedia :cite:p:`WikipediaFun24`, MathWorld :cite:p:`WolframFun24`, BoostMath :cite:p:`BoostFun24`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ecplx
        >>> ecplx.Cuberoot(0.5)
        ecplx('5.2359877559829887307E-1')
        >>> ecplx.Cuberoot('0.1')
        ecplx('5.3518479027559984754E-1')



Cube root, `\mathrm{cuberoot}(x) = \sqrt[3]{x} = y`, with `\mathrm{arg}(y)` closest to `\mathrm{arg}(x)`
--------------------------------------------------------------------------------------------------------

.. method:: math53.cuberoot(z)

    Returns the cube root of `x`, `x^{1/3}` in a way which gives a negative number for negative input.  See also Wikipedia :cite:p:`WikipediaFun24`, MathWorld :cite:p:`WolframFun24`, BoostMath :cite:p:`BoostFun24`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ecplx
        >>> ecplx.Cuberoot(0.5)
        ecplx('5.2359877559829887307E-1')
        >>> ecplx.Cuberoot('0.1')
        ecplx('5.3518479027559984754E-1')





Nth root, `\mathrm{surd}(x, n) = \sqrt[n]{x} = y`, with `\mathrm{arg}(y)` closest to `\mathrm{arg}(x)`
------------------------------------------------------------------------------------------------------

.. method:: mathc53.surd(x, n)

    Returns the complex nth root `w = z^{1/n}` with arg(`w`) closest to arg(`z`), e.g. surd(-8, 3) = -2 or surd(`i`, 5) = `i`, compared to the cnroot results `\sqrt[3]{-8} = 1+i \sqrt{3}` and `\sqrt[5]{i} = \cos(\pi/10) +  i\sin(\pi/10)`. See  :cite:t:`Ehrhardt2018` (4.2.60).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ecplx
        >>> ecplx.Surd(0.5)
        ecplx('5.2359877559829887307E-1')
        >>> ecplx.Surd('0.1')
        ecplx('5.3518479027559984754E-1')






Continuous inverse cotangent, `\mathrm{acotc}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.acotc(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns the continuous inverse cotangent of `x`, `\mathrm{acotc}(x) = \pi/2 - \mathrm{atan}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun56`,  NIST :cite:p:`DLMFun50`, Mpmath :cite:p:`MpmathFun56`.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Acotc(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Acotc('0.51')
        ereal('5.3518479027559984754E-1')




Continuous inverse hyperbolic cotangent, `\mathrm{acothc}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.acothc(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns the continuous inverse hyperbolic cotangent of `x`, `\mathrm{acothc}(x) = \pi/2 - \mathrm{atan}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun56`,  NIST :cite:p:`DLMFun50`, Mpmath :cite:p:`MpmathFun56`.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Acotc(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Acotc('0.51')
        ereal('5.3518479027559984754E-1')


