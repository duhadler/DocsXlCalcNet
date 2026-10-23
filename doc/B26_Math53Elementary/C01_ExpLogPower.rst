

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Root, exponential, logarithmic and power functions
===============================================================================




Auxiliary function `\mathrm{sqrt1pmx}(x) = \sqrt{1+x^2}-x`
-------------------------------------------------------------------------------

.. method:: math53.sqrt1pmx (x)

    Returns `\sqrt{1+x^2}-x`, accurate also for `x` near 0. 


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.sqrt1pmx(-4.333)
        8.779896558275222
        >>> math53.sqrt1pmx(0.0)
        1.0
        >>> math53.sqrt1pmx(4.333)
        0.1138965582752203







Bring radical
-------------------------------------------------------------------------------

.. method:: math53.bring(x)

    Returns the Bring radical `b = \text{BR}(x)` of `x`, i.e. the unique real `b` with `b^5 + b + x = 0`. The function can be used (together with standard radicals) to solve a class of quintic equations in closed form.

    See also: https://en.wikipedia.org/wiki/Bring_radical, :cite:t:`Ehrhardt2018` (3.10.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bring(-4.333)
        1.252357338752218
        >>> math53.bring(0.0)
        0.0
        >>> math53.bring(4.333)
        -1.252357338752218




        

Auxiliary function `\mathrm{expmx2h}(x) = \exp(-x^2 / 2)`
-------------------------------------------------------------------------------

.. method:: math53.expmx2h(x)

    Returns `\exp(-x^2 / 2)` with damped error amplification.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.expmx2h(-4.333)
        8.376925527113537e-05
        >>> math53.expmx2h(0.0)
        1.0
        >>> math53.expmx2h(4.333)
        8.376925527113537e-05









Relative error exponential  `\mathrm{exprel}(x) = (\exp(x) - 1)/x`
-------------------------------------------------------------------------------

.. method:: math53.exprel(x)

    where ``ctx`` is ``math53``, ``ctxcpp`` or ``ctxflint``.

    Returns exprel(x) = `(\exp(x) - 1)/x`,  1 for `x=0`.

    .. math ::

        \mathrm{exprel}(x) = \begin{cases}
            (\exp(x) - 1)/x = \mathrm{expm1}(x)/x, & \mbox{if } x \ne 0 \\
            1,                                    & \mbox{if } x = 0.
        \end{cases}



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.exprel(-4.333)
        0.22775718808161466
        >>> math53.exprel(0.0)
        1.0
        >>> math53.exprel(4.333)
        17.348825645093516







Auxiliary function   `\mathrm{expx2}(x) = \exp(x \cdot |x|)`
-------------------------------------------------------------------------------

.. method:: math53.expx2(x)

    Returns `\exp(x \cdot |x|)` with damped error amplification.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.expx2(-4.333)
        7.01728812868064e-09
        >>> math53.expx2(0.0)
        1.0
        >>> math53.expx2(4.333)
        142505193.1262249




Auxiliary function `\mathrm{logistic}(x) = 1/(1+\exp(-x))`
-------------------------------------------------------------------------------

.. method:: math53.logistic  (x)

    Returns `\mathrm{logistic}(x) = 1/(1+\exp(-x))`. See also Wikipedia :cite:p:`WikipediaFun320`, MathWorld :cite:p:`WolframFun320`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logistic(-4.333)
        0.012957990198853193
        >>> math53.logistic(0.0)
        0.5
        >>> math53.logistic(4.333)
        0.9870420098011469







Einstein functions
-------------------------------------------------------------------------------

.. method:: math53.einstein(n,x)

    Returns the Einstein function `E_n` for  `n=1,2,3,4`, with `\displaystyle E_1(x) =  \frac{x^2 e^x}{(e^x-1)^2}`, `\displaystyle E_2(x) =  \frac{x}{e^x-1}`, `E_3(x) = \log(1-e^{-x}), x>0`, `\displaystyle E_4(x) =  \frac{x}{e^x-1} - \log(1-e^{-x}), x>0`.


    See also https://mathworld.wolfram.com/EinsteinFunctions.html

    See also: :cite:t:`Abramowitz1970` table 27.3, :cite:t:`Ehrhardt2018` (3.10.7).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.einstein(1,4.333)
        0.253079999702088
        >>> math53.einstein(2,4.333)
        0.05764078909184343
        >>> math53.einstein(3,4.333)
        -0.013215039301928083
        >>> math53.einstein(4,4.333)
        0.07085582839377151






Auxiliary function `\mathrm{log1mexp}(x) = \log(1-\exp(x))`
-------------------------------------------------------------------------------

.. method:: math53.log1mexp(x)

    Returns `\log(1-\exp(x)), x<0`, calculated in an accurate and efficient way.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.log1mexp(-4.333)
        -0.013215039301928083
        >>> math53.log1mexp(0.0)
        -inf
        >>> math53.log1mexp(4.333)
        nan









Auxiliary function `\mathrm{log1pexp}(x) = \log(1+\exp(x))`
-------------------------------------------------------------------------------

.. method:: math53.log1pexp(x)

    Returns `\mathrm{ln1pexp}(x)) = \log(1+\exp(x)) = \mathrm{log1p}(\exp(x))`. See also  :ref:`log1p() <rst_xreal_log1p>`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.log1pexp(-4.333)
        0.013042677332710145
        >>> math53.log1pexp(0.0)
        0.6931471805599453
        >>> math53.log1pexp(4.333)
        4.3460426773327105







Auxiliary function `\mathrm{log1pmx}(x) = \log(1+x)-x`
-------------------------------------------------------------------------------

.. method:: math53.log1pmx(x)

    Returns `\mathrm{ln1pmx}(x)) = \log(1+x)-x = \mathrm{log1p}(x)-x`, accurate also for `-0.5 \le x \le 0.5`. See also  :ref:`log1p() <rst_xreal_log1p>`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.log1pmx(-4.333)
        nan
        >>> math53.log1pmx(0.0)
        0.0
        >>> math53.log1pmx(4.333)
        -2.659086068381535







Auxiliary function `\mathrm{logaddexp}(x, y) = \log[\exp(x) + \exp(y)]`
-------------------------------------------------------------------------------

.. method:: math53.logaddexp(x, y)

    Accurately compute ln[exp(x) + exp(y)].

    See also: https://www.boost.org/doc/libs/latest/libs/math/doc/html/math_toolkit/powers/logaddexp.html

    See also: https://nhigham.com/2021/01/05/what-is-the-log-sum-exp-function/


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logaddexp(1.2, -4.333)
        1.203946312008691
        >>> math53.logaddexp(3.7, 0)
        3.724422845933779
        >>> math53.logaddexp(4.8, 4.333)
        5.2866641257129325





Auxiliary function `\mathrm{logsubexp}(x, y) = \log[\exp(x) - \exp(y)]`
-------------------------------------------------------------------------------

.. method:: math53.logsubexp(x, y)

    Accurately compute `\log[\exp(x) - \exp(y)], x > y`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logsubexp(1.2, -4.333)
        1.1960380528914856
        >>> math53.logsubexp(3.7, 0)
        3.6749657144139602
        >>> math53.logsubexp(4.8, 4.333)
        3.8141445624254304







Auxiliary function `\mathrm{logit}(x) = \log(x/(1.0-x))`
-------------------------------------------------------------------------------

.. method:: math53.logit(x)

    Returns `\mathrm{logit}(x) = \log(x/(1.0-x))`, accurate also near `x=0.5`. See also  Wikipedia :cite:p:`WikipediaFun321`,  MathWorld :cite:p:`WolframFun321`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.logit(-0.333)
        nan
        >>> math53.logit(0.0)
        -inf
        >>> math53.logit(0.333)
        -0.6946475559351799









Wright `\omega` function
-------------------------------------------------------------------------------

.. method:: math53.wright_omega(x)

    Returns the Wright `\omega(x)` function, which is defined as the unique solution of `\omega(x) + \log(\omega(x)) = x`. For real `x` it can be written in terms of the Lambert W function as `\omega(x) = W(e^x)`

    See also: :cite:t:`Ehrhardt2018` (3.10.26).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.wright_omega(-0.333)
        0.4548304865283553
        >>> math53.wright_omega(0.0)
        0.5671432904097838
        >>> math53.wright_omega(0.333)
        0.695756104553223






Auxiliary function `\mathrm{compound}(x,n) = (1+x)^n`
-------------------------------------------------------------------------------

.. method:: ctx.compound_si(x, n)

    Returns `(1+x)^n`, computed accurately also when `x` is very close to 0. 


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.compound_si(-4.333, 3)
        -37.02592703700001
        >>> math53.compound_si(0.0, 2)
        1.0
        >>> math53.compound_si(4.333, 3)
        151.675261037







Auxiliary function `\mathrm{comprel}(x,n) = (1+x)^n - 1`
-------------------------------------------------------------------------------

.. method:: ctx.comprel(x, n)

    Returns `(1+x)^n - 1`, computed accurately also when `x` is very close to 0. 


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.comprel(-4.333, 3)
        8.775889000000001
        >>> math53.comprel(0.0, 2)
        2.0
        >>> math53.comprel(4.333, 3)
        34.773889000000004






Auxiliary function `\mathrm{hypot3}(x,y,z) = \sqrt{x^2 + y^2 + z^2}`
-------------------------------------------------------------------------------

.. method:: math53.hypot3(x, y, z)

    Returns `\mathrm{hypot3}(x, y, z) = \sqrt { x^2 + y^2  + z^2 }` in a way which avoids undue underflow and overflow. See also  BoostMath :cite:p:`BoostFun117`,  Wikipedia :cite:p:`WikipediaFun117`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.hypot3(1.2, -4.333, -1.333)
        4.689539209773174
        >>> math53.hypot3(2.4, 0, 0)
        2.4
        >>> math53.hypot3(4.8, -4.333, -1.333)
        6.602406985334969







.. _rst_mpm_fibpoly: 

Fibonacci polynomials, `\mathrm{fibpoly}(n, x)`
-------------------------------------------------------------------------------

.. method:: math53.fibpoly(n, x)

    where ``ctx`` is ``math53``, ``ctxcpp`` or ``ctxflint``.


    Returns `F_n(x)`, the Fibonacci polynomial of index `n \in \mathbb{Z}`. See also  Wikipedia :cite:p:`WikipediaFun310`,  Wikipedia :cite:p:`WikipediaFun311`, :cite:t:`Jin2018`, MathWorld :cite:p:`WolframFun310`, MathWorld :cite:p:`WolframFun311`, :cite:t:`Ehrhardt2018` (3.10.11).

    https://en.wikipedia.org/wiki/Fibonacci_polynomials#Properties

    https://functions.wolfram.com/HypergeometricFunctions/Fibonacci2General/26/03/01/0002/


    For any non-negative integer n, the Fibonacci polynomials `\{F_n(x)\}` are defined by the second order linear recursive formula  `F_{n+2}(x)=xF_{n+1}(x)+F_{n}(x)` with `F_{0}(x)=0`, `F_{1}(x)=1`,  `L_{0}(x)=2`, and  `L_{1}(x)=x`. The general terms of `F_{n}(x)` are given by


    .. math :: F_{n}(x)=\frac{1}{\sqrt{x^{2}+4}} \biggl[ \biggl( \frac{x+ \sqrt{x^{2}+4}}{2} \biggr) ^{n}- \biggl( \frac{x-\sqrt{x^{2}+4}}{2} \biggr) ^{n} \biggr]



    An example in Python

    .. code-block:: pycon

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.fibpoly(2, -4.333)
        -4.333
        >>> math53.fibpoly(3, -4.333)
        19.774889
        >>> math53.fibpoly(4, 4.333)
        90.01759403700001







.. _rst_mpm_lucaspoly: 

Lucas polynomials, `\mathrm{lucpoly}(n, x)`
-------------------------------------------------------------------------------

.. method:: math53.lucpoly(n, x)

    where ``ctx`` is ``math53``, ``ctxcpp`` or ``ctxflint``.


    Returns `L_n(x)`, the Lucas polynomial of index `n \in \mathbb{Z}`. See also  :cite:t:`Ehrhardt2018` (3.10.18),  Wikipedia :cite:p:`WikipediaFun312`,  Wikipedia :cite:p:`WikipediaFun313`, :cite:t:`Jin2018`, MathWorld :cite:p:`WolframFun312`, MathWorld :cite:p:`WolframFun313`.


    For any non-negative integer n, Lucas polynomials  `\{L_n(x)\}` are defined by the second order linear recursive formulas  `L_{n+2}(x)=xL_{n+1}(x)+L_{n}(x)`,  `L_{0}(x)=2`, and  `L_{1}(x)=x`. For negative indices we have `L_{-n}(x)= (-1)^n L_{n}(x)`.  The general terms of `L_{n}(x)` are given by

    .. math :: L_{n}(x)= \biggl( \frac{x+\sqrt{x^{2}+4}}{2} \biggr) ^{n}+ \biggl( \frac{x-\sqrt{x ^{2}+4}}{2} \biggr) ^{n}.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.lucpoly(2, -4.333)
        20.774889
        >>> math53.lucpoly(3, -4.333)
        -94.35059403700001
        >>> math53.lucpoly(4, 4.333)
        429.5960129623211






Fibonacci function, `F_{\nu}(x)`,  of real index `\nu`
-------------------------------------------------------------------------------

.. method:: math53.fibfun(v,x)

    Returns `\displaystyle F_{\nu}(x) = \frac{2^{-\nu}(x+\sqrt{x^2+4})^{\nu} - \cos(\pi\nu) \cdot 2^{\nu} (x+\sqrt{x^2+4})^{-\nu} }{\sqrt{x^2+4}}`, the general Fibonacci function of real index `\nu`.

    See also  :cite:t:`Ehrhardt2018` (3.10.12) , https://en.wikipedia.org/wiki/Fibonacci_polynomials.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.fibfun(1.2, -4.333)
        1.0790638603231733
        >>> math53.fibfun(3.7, -4.333)
        -33.57833497912526
        >>> math53.fibfun(4.8, 4.333)
        302.6505730178296














