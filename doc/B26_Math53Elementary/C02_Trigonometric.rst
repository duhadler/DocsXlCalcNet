

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Trigonometric functions
=======================================================================





Sine, `x` in degrees, `\mathrm{sind}(x)`
-------------------------------------------------------------------------------

.. method:: math53.sind(x)

    Returns the sine of `x`, with `x` in degrees, `\mathrm{sind}(x)`.  See also  Wikipedia :cite:p:`WikipediaFun31`,  MathWorld :cite:p:`WolframFun31`,  NIST :cite:p:`DLMFun30`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.sind(-4.333)
        -0.07555305176474306
        >>> math53.sind(0.0)
        0.0
        >>> math53.sind(4.333)
        0.07555305176474306






Inverse sine, input in degrees, `\mathrm{asind}(x)`
-------------------------------------------------------------------------------

.. method:: math53.asind(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp``, ``ctxflint``.

    Returns the inverse sine of `x`, `\mathrm{asin}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun51`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.13), Mpmath :cite:p:`MpmathFun51`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.asind(-0.333)
        -19.45096478286684
        >>> math53.asind(0.0)
        0.0
        >>> math53.asind(0.333)
        19.45096478286684



Cosine, `x` in degrees, `\mathrm{cosd}(x)`
-------------------------------------------------------------------------------

.. method:: math53.cosd(x)

    Returns the cosine of `x`, with `x` in degrees, `\mathrm{cosd}(x)`.   See also  Wikipedia :cite:p:`WikipediaFun30`,  MathWorld :cite:p:`WolframFun32`,  NIST :cite:p:`DLMFun30`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.cosd(-4.333)
        0.99714178348369
        >>> math53.cosd(0.0)
        1.0
        >>> math53.cosd(4.333)
        0.99714178348369





Inverse cosine, input in degrees, `\mathrm{acosd}(x)`
-------------------------------------------------------------------------------

.. method:: math53.acosd(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp``, ``ctxflint``.

    Returns the inverse cosine of `x`, `\mathrm{acos}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun52`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.3), Flint :cite:p:`FlintFun50`, Flint :cite:p:`FlintFun51`, Mpmath :cite:p:`MpmathFun52`.

    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.acosd(-0.333)
        109.45096478286685
        >>> math53.acosd(0.0)
        90.0
        >>> math53.acosd(0.333)
        70.54903521713317





Tangent, with `x` in degrees, `\mathrm{tand}(x)`
-------------------------------------------------------------------------------

.. method:: math53.tand(x)

    Returns the tangent of `x`, with `x` in degrees, `\mathrm{tand}tan(x)`.  See also  Wikipedia :cite:p:`WikipediaFun30`,  MathWorld :cite:p:`WolframFun33`,  NIST :cite:p:`DLMFun30`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.tand(-4.333)
        -0.07576961773759515
        >>> math53.tand(0.0)
        0.0
        >>> math53.tand(4.333)
        0.07576961773759515





Inverse tangent, input in degrees, `\mathrm{atand}(x)`
-------------------------------------------------------------------------------

.. method:: math53.atand(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns the inverse tangent of `x`, `\mathrm{atan}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun53`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.15), Flint :cite:p:`FlintFun50`, Flint :cite:p:`FlintFun51`, Mpmath :cite:p:`MpmathFun53`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.atand(-4.333)
        -77.00441747834749
        >>> math53.atand(0.0)
        0.0
        >>> math53.atand(4.333)
        77.00441747834749









Cotangent, with `x` in degrees, `\mathrm{cotd}(x)`
-------------------------------------------------------------------------------

.. method:: math53.cotd(x)

    Returns the cotangent of `x`, with `x` in degrees, `\mathrm{cotd}(x)`. See also  Wikipedia :cite:p:`WikipediaFun30`,  MathWorld :cite:p:`WolframFun36`,  NIST :cite:p:`DLMFun30`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.cotd(-4.333)
        -13.197902138865127
        >>> math53.cotd(0.0)
        inf
        >>> math53.cotd(4.333)
        13.197902138865127







Inverse cotangent, input in degrees, `\mathrm{acotd}(x)`
-------------------------------------------------------------------------------

.. method:: math53.acotd(x)


    Returns the inverse cotangent of `x`, `\mathrm{acot}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun56`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.5).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.acotd(-4.333)
        -12.995582521652512
        >>> math53.acotd(0.0)
        90.0
        >>> math53.acotd(4.333)
        12.995582521652512







Auxiliary function,  `\mathrm{acos}(1-x)`
-------------------------------------------------------------------------------

.. method:: math53.acos1m(x)

    Returns `\mathrm{acos}(1-x)`, `0 \le x \le 2`, accurate also for `x` near 0.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.acos1m(-0.333)
        nan
        >>> math53.acos1m(0.0)
        0.0
        >>> math53.acos1m(0.333)
        0.8406213674789956









Haversine function `\mathrm{hav}(x) = (1 - \cos(x))/2`
-------------------------------------------------------------------------------

.. method:: math53.hav(x)

    Returns the haversine function `\mathrm{hav}(x) = (1 - \cos(x))/2 = \sin^2(x/2)`. See also  MathWorld :cite:p:`WolframFun302`,  Wikipedia :cite:p:`WikipediaFun302`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.hav(-4.333)
        0.6851764839496324
        >>> math53.hav(0.0)
        0.0
        >>> math53.hav(4.333)
        0.6851764839496324






Inverse haversine function `\mathrm{archav}(x) = \mathrm{acos}(1-2x)`
-------------------------------------------------------------------------------

.. method:: math53.archav(z)

    Returns the inverse haversine function `\mathrm{archav}(x) = \mathrm{acos}(1-2x) =2 \mathrm{asin}(\sqrt{x})`, `0 \le x \le 1`. See also  MathWorld :cite:p:`WolframFun303`,  Wikipedia :cite:p:`WikipediaFun303`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.archav(-0.333)
        nan
        >>> math53.archav(0.0)
        0.0
        >>> math53.archav(0.333)
        1.2302522220901777







Versine function `\mathrm{vers}(x) = 1 - \cos(x)`
-------------------------------------------------------------------------------

.. method:: math53.vers(x)

    Returns the versine function `\mathrm{vers}(x) = 1 - \cos(x)`.

    See also:   https://en.wikipedia.org/wiki/Versine#Haversine


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.vers(-4.333)
        1.3703529678992648
        >>> math53.vers(0.0)
        0.0
        >>> math53.vers(4.333)
        1.3703529678992648





Coversine, `\mathrm{covers}(x) = 1 - \sin(x)`
-------------------------------------------------------------------------------

.. method:: math53.covers(x)

    Returns the `\mathrm{covers}(x) = 1 - \sin(x)`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.covers(-4.333)
        0.07110889811119075
        >>> math53.covers(0.0)
        1.0
        >>> math53.covers(4.333)
        1.928891101888809







Versint function `\mathrm{versint}(x) = x - \sin(x)`
-------------------------------------------------------------------------------

.. method:: math53.versint (x)

    Returns `\displaystyle \mathrm{versint}(x) = \int_0^x \mathrm{vers}(t) \mathrm{d}t = x - \sin(x)`, accurate also near 0.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.versint(-4.333)
        -5.26189110188881
        >>> math53.versint(0.0)
        0.0
        >>> math53.versint(4.333)
        5.26189110188881










Integral of cos powers, `\mathrm{cosint}(n,x)`
-------------------------------------------------------------------------------

.. method:: math53.cosint(n,x)

    Returns `\displaystyle \mathrm{IC}_n(x) = \int_0^x \cos^n(t) \, \mathrm{d}t`, the integral of the nth cos power, for `n \ge 0`.

    See also  :cite:t:`Ehrhardt2018` (3.10.13).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.cosint(2, 4.333)
        2.33850878821987
        >>> math53.cosint(3, 0.0)
        0.0
        >>> math53.cosint(4, -4.333)
        -1.7656780674583596







Integral of sin powers, `\mathrm{sinint}(n,x)`
-------------------------------------------------------------------------------

.. method:: math53.sinint(n,x)

    Returns sinint(n,x) = integral(sin(t)^n, t=0..x), n >= 0

    Returns `\displaystyle \mathrm{IS}_n(x) = \int_0^x \sin^n(t) \, \mathrm{d}t`, the integral of the nth sin power, for `n \ge 0`.

    See also  :cite:t:`Ehrhardt2018` (3.10.14).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.sinint(2, 4.333)
        1.9944912117801308
        >>> math53.sinint(3, 0.0)
        0.0
        >>> math53.sinint(4, -4.333)
        -1.421660491018621













