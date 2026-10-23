

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Hyperbolic functions
=======================================================================




Cardinal hyperbolic sine, `\mathrm{sinhc}(x) = \sinh(x)/x`
-------------------------------------------------------------------------------

.. method:: math53.sinhc (x)

    Returns `\mathrm{sinhc}(x) = \sinh(x)/x`, accurate also for `x` near 0.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.sinhc(-4.333)
        8.788291416587565
        >>> math53.sinhc(0.0)
        1.0
        >>> math53.sinhc(4.333)
        8.788291416587565





Auxiliary function,  `\mathrm{sinhmx}(x) = \sinh(x)-x`
-------------------------------------------------------------------------------

.. method:: math53.sinhmx (x)

    Returns sinh(x)-x, accurate also for `x` near 0.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.sinhmx(-4.333)
        -33.746666708073924
        >>> math53.sinhmx(0.0)
        0.0
        >>> math53.sinhmx(4.333)
        33.746666708073924







Auxiliary function,  `\mathrm{coshm1}(x) = \cosh(x)-1`
-------------------------------------------------------------------------------

.. method:: math53.coshm1(x)

    Returns `\cosh(x)-1`, accurate also for `x` near 0.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.coshm1(-4.333)
        37.09279481211629
        >>> math53.coshm1(0.0)
        0.0
        >>> math53.coshm1(4.333)
        37.09279481211629





Auxiliary function `\mathrm{acosh}(1+x)`
-------------------------------------------------------------------------------

.. method:: math53.acosh1p(z)

    Returns `\mathrm{acosh}(1+x), x \ge 0`, accurate also for `x` near 0.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.acosh1p(-4.333)
        nan
        >>> math53.acosh1p(0.0)
        0.0
        >>> math53.acosh1p(4.333)
        2.3581527329799776









Auxiliary function `\log(\cosh(x))`
-------------------------------------------------------------------------------

.. method:: math53.logcosh(x)

    Returns ln(cosh(x)), accurate for x ~ 0 and without overflow for large x


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logcosh(-4.333)
        3.640025151705744
        >>> math53.logcosh(0.0)
        0.0
        >>> math53.logcosh(4.333)
        3.640025151705744






Auxiliary function `\log(\sinh(x))`
-------------------------------------------------------------------------------

.. method:: math53.logsinh(x)

    Returns ln(sinh(x)), x > 0, accurate for x ~ 0 and without overflow for large x


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logsinh(-4.333)
        nan
        >>> math53.logsinh(0.0)
        -inf
        >>> math53.logsinh(4.333)
        3.639680457470837












Gudermannian function `\mathrm{gd}(x) = \mathrm{asin}(\mathrm{tanh}(x))`
-------------------------------------------------------------------------------

.. method:: math53.gd(x)

    Returns the Gudermannian function `\mathrm{gd}(x) = \mathrm{asin}(\mathrm{tanh}(x))`. See also  Wikipedia :cite:p:`WikipediaFun304`,  MathWorld :cite:p:`WolframFun304`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.gd(-4.333)
        -1.5445416269481194
        >>> math53.gd(0.0)
        0.0
        >>> math53.gd(4.333)
        1.5445416269481194





Inverse Gudermannian function `\mathrm{arcgd}(x) = \mathrm{atanh}(\sin(x))`
-------------------------------------------------------------------------------

.. method:: math53.arcgd(z)


    Returns the inverse Gudermannian function `\mathrm{arcgd}(x) = \mathrm{atanh}(\sin(x)), |x| < \pi/2.`

    See also  Wikipedia :cite:p:`WikipediaFun305`,  MathWorld :cite:p:`WolframFun305`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.arcgd(-0.733)
        -0.8091157114590968
        >>> math53.arcgd(0.0)
        0.0
        >>> math53.arcgd(0.733)
        0.8091157114590968








Langevin function, `L(x)`
-------------------------------------------------------------------------------

.. method:: math53.langevinl(x)

    Returns the Langevin function `L(x)`, defined as `L(x) = \coth(x) - 1/x` for `x \ne 0`, and  `L(0) = 0` for `x = 0`.

    See also :cite:t:`Ehrhardt2018` (3.10.16).

    https://en.wikipedia.org/wiki/Brillouin_and_Langevin_functions

    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.langevinl(-0.733)
        -0.23600650435321588
        >>> math53.langevinl(0.0)
        0.0
        >>> math53.langevinl(0.733)
        0.23600650435321588






Inverse Langevin function, `L^{-1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.langevinlinv(x)

    Returns the functional inverse `L^{-1}` of the Langevin function, i.e. `L(L^{-1}(x))= x`, `|x| < 1`.

    See also :cite:t:`Ehrhardt2018` (3.10.17).

    https://en.wikipedia.org/wiki/Brillouin_and_Langevin_functions

    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.langevinlinv(-0.733)
        -3.7292029668920454
        >>> math53.langevinlinv(0.0)
        0.0
        >>> math53.langevinlinv(0.733)
        3.7292029668920454







Solutions of Kepler’s equation, `\mathrm{kepler}(M,e)`
-------------------------------------------------------------------------------

.. method:: math53.kepler(M,e)

    Returns the solutions (eccentric anomaly `x`) of Kepler’s equation from the mean anomaly `M` and the eccentricity `e`, more precisely the solutions `x` of

    .. math:: 

        M =\begin{cases}
        x - e \sin(x), & e<1,\\
        x+x^3/3, &  e=1 \text{ (Barker's equation)},\\
        e \sinh(x)-x, & e>1.
        \end{cases}

    See also :cite:t:`Ehrhardt2018` (3.10.23).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.kepler(1.2, 0.333)
        1.5327591321519451
        >>> math53.kepler(2.4, 0.333)
        2.577919997073644
        >>> math53.kepler(4.8, 4.333)
        1.1179306170995853





