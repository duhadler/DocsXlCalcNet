

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

        >>> from xlcalcnet import ereal
        >>> ereal.Sinhc(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Sinhc('0.51')
        ereal('5.3518479027559984754E-1')






Auxiliary function,  `\mathrm{sinhmx}(x) = \sinh(x)-x`
-------------------------------------------------------------------------------

.. method:: math53.sinhmx (x)

    Returns sinh(x)-x, accurate also for `x` near 0.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Sinhmx(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Sinhmx('0.51')
        ereal('5.3518479027559984754E-1')







Auxiliary function,  `\mathrm{coshm1}(x) = \cosh(x)-1`
-------------------------------------------------------------------------------

.. method:: math53.coshm1(x)

    Returns `\cosh(x)-1`, accurate also for `x` near 0.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Coshm1(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Coshm1('0.51')
        ereal('5.3518479027559984754E-1')





Auxiliary function `\mathrm{acosh}(1+x)`
-------------------------------------------------------------------------------

.. method:: math53.acosh1p(z)

    Returns `\mathrm{acosh}(1+x), x \ge 0`, accurate also for `x` near 0.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Acosh1p(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Acosh1p('0.51')
        ereal('5.3518479027559984754E-1')









Auxiliary function `\log(\cosh(x))`
-------------------------------------------------------------------------------

.. method:: math53.logcosh(x)

    Returns ln(cosh(x)), accurate for x ~ 0 and without overflow for large x


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Logcosh(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Logcosh('0.51')
        ereal('5.3518479027559984754E-1')






Auxiliary function `\log(\sinh(x))`
-------------------------------------------------------------------------------

.. method:: math53.logsinh(x)

    Returns ln(sinh(x)), x > 0, accurate for x ~ 0 and without overflow for large x


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Logsinh(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Logsinh('0.51')
        ereal('5.3518479027559984754E-1')












Gudermannian function `\mathrm{gd}(x) = \mathrm{asin}(\mathrm{tanh}(x))`
-------------------------------------------------------------------------------

.. method:: math53.gd(x)

    Returns the Gudermannian function `\mathrm{gd}(x) = \mathrm{asin}(\mathrm{tanh}(x))`. See also  Wikipedia :cite:p:`WikipediaFun304`,  MathWorld :cite:p:`WolframFun304`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.Gudermann(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Gudermann('0.51')
        ereal('5.3518479027559984754E-1')





Inverse Gudermannian function `\mathrm{arcgd}(x) = \mathrm{atanh}(\sin(x))`
-------------------------------------------------------------------------------

.. method:: math53.arcgd(z)


    Returns the inverse Gudermannian function `\mathrm{arcgd}(x) = \mathrm{atanh}(\sin(x)), |x| < \pi/2.`

    See also  Wikipedia :cite:p:`WikipediaFun305`,  MathWorld :cite:p:`WolframFun305`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.ArcGd(0.5)
        ereal('5.2359877559829887307E-1')
        >>> ereal.ArcGd('0.51')
        ereal('5.3518479027559984754E-1')








Langevin function, `L(x)`
-------------------------------------------------------------------------------

.. method:: math53.langevin_l(x)

    Returns the Langevin function `L(x)`, defined as `L(x) = \coth(x) - 1/x` for `x \ne 0`, and  `L(0) = 0` for `x = 0`.

    See also :cite:t:`Ehrhardt2018` (3.10.16).

    https://en.wikipedia.org/wiki/Brillouin_and_Langevin_functions

    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.LangevinL(0.2)
        ereal('5.2359877559829887307E-1')
        >>> ereal.LangevinL(0.21)
        ereal('5.3518479027559984754E-1')






Inverse Langevin function, `L^{-1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.langevin_l_inv(x)

    Returns the functional inverse `L^{-1}` of the Langevin function, i.e. `L(L^{-1}(x))= x`, `|x| < 1`.

    See also :cite:t:`Ehrhardt2018` (3.10.17).

    https://en.wikipedia.org/wiki/Brillouin_and_Langevin_functions

    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import ereal
        >>> ereal.LangevinLInv(0.2)
        ereal('5.2359877559829887307E-1')
        >>> ereal.LangevinLInv(0.21)
        ereal('5.3518479027559984754E-1')







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

        >>> from xlcalcnet import ereal
        >>> ereal.Kepler(3, 0.44)
        ereal('5.2359877559829887307E-1')
        >>> ereal.Kepler(3, 0.14404)
        ereal('5.3518479027559984754E-1')





