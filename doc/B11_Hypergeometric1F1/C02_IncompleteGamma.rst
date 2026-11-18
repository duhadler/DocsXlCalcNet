

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Incomplete gamma functions
===============================================================================


.. _rst_mpm_gamma_p: 

Lower normalized incomplete gamma function, `P(a,x)`
---------------------------------------------------------------------------------------------------

.. method:: ctx.gamma_p(a, x)

    where ``ctx`` is ``math53``, ``ctxboost``, ``ctxflint``.

    Note: ctx.incGammaP(a, x)

    Returns the lower normalized incomplete gamma function `\displaystyle P(a,x)=\frac{1}{\Gamma(a)} \int_0^x t^{a-1} e^{-t} \, \mathrm{d}t, \,` for `a \geq 0` and `x \geq 0`.

    See also  Wikipedia :cite:p:`WikipediaFun01`, MathWorld :cite:p:`WolframFun01b`, NIST :cite:p:`DLMFun01`,  BoostMath :cite:p:`BoostFun01`, :cite:t:`Ehrhardt2018` (3.5.2.1), Flint :cite:p:`FlintFun01`, Flint :cite:p:`FlintFun02`, Mpmath :cite:p:`MpmathFun01`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_p(a, x)))
        fpm:  0.126316105337314
        mpm:  0.126316105337313741137600132735985572024812275186916466464681861576313968609551245555422737
        dpm:  0.126316105337313741137600132735985572024812275186916466464681861576313968609551245555422737
        gpm:  0.12631610533731374113760013273598557202481227518691646646468186157631396860955124555542273701
        apm: [0.1263161053373137411376001327359855720248122751869164664646818615763139686095512455554227 +/- 6.19e-89]
     math53:  0.126316105337314
      sreal:  0.1263161
      dreal:  0.126316105337314
      ereal:  0.12631610533731374111
      qreal:  0.126316105337313741137600132735986
      oreal:  0.12631610533731374113760013273598557202481227518691646646468186157631396
      mreal:  0.12631610533731374113760013273598557202481227518691646646468186157631396860955124555542275
     sflint:  0.1263161
     dflint:  0.126316105337314
     eflint:  0.12631610533731374115
     qflint:  0.126316105337313741137600132735986
     oflint:  0.12631610533731374113760013273598557202481227518691646646468186157631397
     mflint:  0.126316105337313741137600132735985572024812275186916466464681861576313968609551245555422734
     aflint: [0.126316105337313741137600132735985572024812275186916466464681861576313968609551245555423 +/- 3.68e-88]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_p(a, x)))
        fpm:  (0.99983587955112, -0.000161017588835076)
        mpm:  (0.9998358795511197936096176833895849330915, -0.0001610175888350764324777252607106789147347)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.gamma_p(a, x))))
        fpm:  0.99983587955112
        mpm:  0.999835879551119793609617683389584933091518789932676095098595408413038157744915994864106565
        dpm:  0.999835879551119793609617683389584933091518789932676095098595408413038157744915994864106565
        gpm:  0.99983587955111979360961768338958493309151878993267609509859540841303815774491599486410656505
        apm: [0.999835879551119793609617683389584933091518789932676095098595408413038157744915994864107 +/- 5.63e-88]
    cmath53:  NaN
    sflintc:  0.9998359
    dflintc:  0.99983587955112
    eflintc:  0.99983587955111979359
    qflintc:  0.999835879551119793609617683389585
    oflintc:  0.99983587955111979360961768338958493309151878993267609509859540841303816
    mflintc:  0.999835879551119793609617683389584933091518789932676095098595408413038157744915994864106565
    aflintc: [0.999835879551119793609617683389584933091518789932676095098595408413038157744915994864107 +/- 8.37e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hyperg_1f1(a, b, x))))
        fpm:  -0.000161017588835076
        mpm:  -0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534636873741
        dpm:  -0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534636873741
        gpm:  -0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534636873741
        apm: [-0.0001610175888350764324777252607106789147347814525259859287468932782622753335876785346369 +/- 6.40e-89]
    cmath53:  NaN
    sflintc:  -0.0001610173
    dflintc:  -0.000161017588835076
    eflintc:  -0.00016101758883507643234
    qflintc:  -0.000161017588835076432477725260710678
    oflintc:  -0.00016101758883507643247772526071067891473478145252598592874689327826227531
    mflintc:  -0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534636867321
    aflintc: [-0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534637 +/- 2.36e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D01a_GammaPReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D01b_GammaPCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C02_IncompleteGamma/D01_GammaP.cs>`__. 







|newpage|


.. _rst_mpm_gamma_q: 

Upper normalized incomplete gamma functions , `Q(a,x)`
---------------------------------------------------------------------------------------------------

.. method:: ctx.gamma_q(a, x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Note: ctx.incGammaQ(a, x)

    Returns the upper normalized incomplete gamma function `\displaystyle Q(a,x)=\frac{1}{\Gamma(a)} \int_x^{\infty} t^{a-1} e^{-t} \, \mathrm{d}t, \,` for `a \geq 0` and `x \geq 0`.

    See also  Wikipedia :cite:p:`WikipediaFun01`, MathWorld :cite:p:`WolframFun01b`, NIST :cite:p:`DLMFun01`,  BoostMath :cite:p:`BoostFun01`, :cite:t:`Ehrhardt2018` (3.5.2.1), Flint :cite:p:`FlintFun01`, Flint :cite:p:`FlintFun02`, Mpmath :cite:p:`MpmathFun01`.



    If *regularized* is 0, computes the upper incomplete gamma function
    `\Gamma(s,z)`.

    If *regularized* is 1, computes the regularized upper incomplete
    gamma function `Q(s,z) = \Gamma(s,z) / \Gamma(s)`.

    If *regularized* is 2, computes the generalized exponential integral
    `z^{-s} \Gamma(s,z) = E_{1-s}(z)` .

    The different methods respectively implement the formulas

    .. math ::

        \Gamma(s,z) = e^{-z} U(1-s,1-s,z)

    .. math ::

        \Gamma(s,z) = \Gamma(s) - \frac{z^s}{s} {}_1F_1(s, s+1, -z)

    .. math ::

        \Gamma(s,z) = \Gamma(s) - \frac{z^s e^{-z}}{s} {}_1F_1(1, s+1, z)

    .. math ::

        \Gamma(s,z) = \frac{(-1)^n}{n!} (\psi(n+1) - \log(z))
                    + \frac{(-1)^n}{(n+1)!} z \, {}_2F_2(1,1,2,2+n,-z)
                    - z^{-n} \sum_{k=0}^{n-1} \frac{(-z)^k}{(k-n) k!},
                    \quad n = -s \in \mathbb{Z}_{\ge 0}

    and an automatic algorithm choice. The automatic version also handles
    other special input such as `z = 0` and `s = 1, 2, 3`.
    The *singular* version evaluates the finite sum directly and therefore
    assumes that *s* is not too large.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_q(a, x)))
        fpm:  0.873683894662686
        mpm:  0.873683894662686258862399867264014427975187724813083533535318138423686031390448754444577263
        dpm:  0.873683894662686258862399867264014427975187724813083533535318138423686031390448754444577263
        gpm:  0.87368389466268625886239986726401442797518772481308353353531813842368603139044875444457726299
        apm: [0.8736838946626862588623998672640144279751877248130835335353181384236860313904487544445773 +/- 4.50e-89]
     math53:  0.873683894662686
      sreal:  0.8736839
      dreal:  0.873683894662686
      ereal:  0.87368389466268625896
      qreal:  0.873683894662686258862399867264015
      oreal:  0.87368389466268625886239986726401442797518772481308353353531813842368603
      mreal:  0.87368389466268625886239986726401442797518772481308353353531813842368603139044875444457725
     sflint:  0.8736839
     dflint:  0.873683894662686
     eflint:  0.87368389466268625885
     qflint:  0.873683894662686258862399867264014
     oflint:  0.87368389466268625886239986726401442797518772481308353353531813842368603
     mflint:  0.873683894662686258862399867264014427975187724813083533535318138423686031390448754444577264
     aflint: [0.8736838946626862588623998672640144279751877248130835335353181384236860313904487544445773 +/- 6.74e-89]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_q(a, x)))
        fpm:  (0.000164120448880206, 0.000161017588835076)
        mpm:  (0.0001641204488802063903823166104150669084812, 0.0001610175888350764324777252607106789147348)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.gamma_q(a, x))))
        fpm:  0.000164120448880206
        mpm:  0.000164120448880206390382316610415066908481210067323904901404591586961842255084005135893434601
        dpm:  0.000164120448880206390382316610415066908481210067323904901404591586961842255084005135893434601
        gpm:  0.00016412044888020639038231661041506690848121006732390490140459158696184225508400513589343460099
        apm: [0.000164120448880206390382316610415066908481210067323904901404591586961842255084005135893 +/- 5.44e-88]
    cmath53:  NaN
    sflintc:  0.0001641203
    dflintc:  0.000164120448880206
    eflintc:  0.00016412044888020639021
    qflintc:  0.000164120448880206390382316610415066
    oflintc:  0.0001641204488802063903823166104150669084812100673239049014045915869618422
    mflintc:  0.000164120448880206390382316610415066908481210067323904901404591586961842255084005135893432499
    aflintc: [0.000164120448880206390382316610415066908481210067323904901404591586961842255084005135893 +/- 7.72e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.gamma_q(a, x))))
        fpm:  0.000161017588835076
        mpm:  0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534636873741
        dpm:  0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534636873741
        gpm:  0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534636873741
        apm: [0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534637 +/- 2.09e-88]
    cmath53:  NaN
    sflintc:  0.0001610173
    dflintc:  0.000161017588835076
    eflintc:  0.00016101758883507643234
    qflintc:  0.000161017588835076432477725260710678
    oflintc:  0.00016101758883507643247772526071067891473478145252598592874689327826227531
    mflintc:  0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534636867917
    aflintc: [0.000161017588835076432477725260710678914734781452525985928746893278262275333587678534637 +/- 4.12e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D02a_GammaQReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D02b_GammaQCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C02_IncompleteGamma/D02_GammaQ.cs>`__. 








|newpage|

Lower non-normalized incomplete gamma function, `\gamma(a,x)`
-------------------------------------------------------------------------------

.. method:: ctx.gamma_lower(a, x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Note: ctx.incgammaL(a, x), ctxboost.TgammaLower(a, x)

    Returns the real lower non-normalized incomplete gamma function `\displaystyle \gamma(a,x)= \int_0^x t^{a-1} e^{-t} \, \mathrm{d}t, \,` for `a \geq 0` and `x \geq 0`.

    See also  Wikipedia :cite:p:`WikipediaFun01`, MathWorld :cite:p:`WolframFun01a`, NIST :cite:p:`DLMFun01`,  BoostMath :cite:p:`BoostFun01`, :cite:t:`Ehrhardt2018` (3.5.2.2), Flint :cite:p:`FlintFun01`, Flint :cite:p:`FlintFun02`, Mpmath :cite:p:`MpmathFun01`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_lower(a, x)))
        fpm:  3.52823034747165
        mpm:  3.52823034747164759103759227567090606951766415829297094886796390601360342416288602756406282
        dpm:  3.52823034747164759103759227567090606951766415829297094886796390601360342416288602756406282
        gpm:  3.5282303474716475910375922756709060695176641582929709488679639060136034241628860275640628198
        apm: [3.528230347471647591037592275670906069517664158292970948867963906013603424162886027564063 +/- 8.91e-88]
     math53:  3.52823034747165
      sreal:  3.52823
      dreal:  3.52823034747165
      ereal:  3.5282303474716475912
      qreal:  3.52823034747164759103759227567091
      oreal:  3.5282303474716475910375922756709060695176641582929709488679639060136033
      mreal:  3.52823034747164759103759227567090606951766415829297094886796390601360342416288602756406281
     sflint:  3.52823
     dflint:  3.52823034747165
     eflint:  3.528230347471647591
     qflint:  3.52823034747164759103759227567091
     oflint:  3.5282303474716475910375922756709060695176641582929709488679639060136034
     mflint:  3.52823034747164759103759227567090606951766415829297094886796390601360342416288602756406274
     aflint: [3.52823034747164759103759227567090606951766415829297094886796390601360342416288602756406 +/- 5.57e-87]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_lower(a, x)))
        fpm:  (0.0713555644042352, -1.14913869019126E-05)
        mpm:  (0.07135556440423523026166251190220581561841, -0.00001149138690191256193538790661890712840025)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.gamma_lower(a, x))))
        fpm:  0.0713555644042352
        mpm:  0.0713555644042352302616625119022058156183928760551006185443234481085582896666652108674293049
        dpm:  0.0713555644042352302616625119022058156183928760551006185443234481085582896666652108674293049
        gpm:  0.071355564404235230261662511902205815618392876055100618544323448108558289666665210867429304906
        apm: [0.0713555644042352302616625119022058156183928760551006185443234481085582896666652108674293 +/- 1.39e-89]
    cmath53:  NaN
    sflintc:  0.07135564
    dflintc:  0.0713555644042355
    eflintc:  0.071355564404235230332
    qflintc:  0.0713555644042352302616625119022061
    oflintc:  0.071355564404235230261662511902205815618392876055100618544323448108558301
    mflintc:  0.0713555644042352302616625119022058156183928760551006185443234481085582896666652108674293057
    aflintc: [0.0713555644042352302616625119022058156183928760551006185443234481085582896666652108674293 +/- 3.37e-89]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.gamma_lower(a, x))))
        fpm:  -1.14913869019126E-05
        mpm:  -0.0000114913869019125619353879066189071284002494206758154078717384595026182665707928982176663703
        dpm:  -0.0000114913869019125619353879066189071284002494206758154078717384595026182665707928982176663703
        gpm:  -1.1491386901912561935387906618907128400249420675815407871738459502618266570792898217666370299e-05
        apm: [-1.149138690191256193538790661890712840024942067581540787173845950261826657079289821767e-5 +/- 6.12e-90]
    cmath53:  NaN
    sflintc:  -1.149138E-05
    dflintc:  -1.14913869019126E-05
    eflintc:  -1.1491386901912561936e-05
    qflintc:  -1.14913869019125619353879066189071e-05
    oflintc:  -1.1491386901912561935387906618907128400249420675815407871738459502618267e-05
    mflintc:  -1.14913869019125619353879066189071284002494206758154078717384595026182665707928982176659119E-05
    aflintc: [-1.14913869019125619353879066189071284002494206758154078717384595026182665707928982177e-5 +/- 4.13e-89]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D03a_GammaLowerReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D03b_GammaLowerCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C02_IncompleteGamma/D03_GammaLower.cs>`__. 










|newpage|

Upper non-normalized incomplete gamma function, `\Gamma(a,x)`
-------------------------------------------------------------------------------

.. method:: ctx.gamma_upper(a, x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Note: ctx.incGammaU(a, x)

    Returns the real upper non-normalized incomplete gamma function `\displaystyle \Gamma(a,x) = \int_x^{\infty} t^{a-1} e^{-t} \, \mathrm{d}t, \,` for `a \geq 0` and `x \geq 0`.

    See also  Wikipedia :cite:p:`WikipediaFun01`, MathWorld :cite:p:`WolframFun01a`, NIST :cite:p:`DLMFun01`,  BoostMath :cite:p:`BoostFun01`, :cite:t:`Ehrhardt2018` (3.5.2.2), Flint :cite:p:`FlintFun01`, Flint :cite:p:`FlintFun02`, Mpmath :cite:p:`MpmathFun01`. 





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_upper(a, x)))
        fpm:  24.4035233908967
        mpm:  24.4035233908967357676355130016520874218327601936887658141002688559891040839267496905191655
        dpm:  24.4035233908967357676355130016520874218327601936887658141002688559891040839267496905191655
        gpm:  24.403523390896735767635513001652087421832760193688765814100268855989104083926749690519165501
        apm: [24.403523390896735767635513001652087421832760193688765814100268855989104083926749690519165 +/- 6.92e-88]
     math53:  24.4035233908967
      sreal:  24.40352
      dreal:  24.4035233908967
      ereal:  24.40352339089673577
      qreal:  24.4035233908967357676355130016521
      oreal:  24.403523390896735767635513001652087421832760193688765814100268855989101
      mreal:  24.4035233908967357676355130016520874218327601936887658141002688559891040839267496905191639
     sflint:  24.40352
     dflint:  24.4035233908967
     eflint:  24.403523390896735765
     qflint:  24.4035233908967357676355130016521
     oflint:  24.403523390896735767635513001652087421832760193688765814100268855989103
     mflint:  24.4035233908967357676355130016520874218327601936887658141002688559891040839267496905191655
     aflint: [24.40352339089673576763551300165208742183276019368876581410026885598910408392674969051917 +/- 5.49e-87]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_upper(a, x)))
        fpm:  (1.17128295749711E-05, 1.14913869019126E-05)
        mpm:  (0.00001171282957497106447400187753172322032046, 0.00001149138690191256193538790661890712840025)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.gamma_upper(a, x))))
        fpm:  1.17128295749711E-05
        mpm:  0.0000117128295749710644740018775317232203204601286379485592754459742256737785524963515867132228
        dpm:  0.0000117128295749710644740018775317232203204601286379485592754459742256737785524963515867132228
        gpm:  1.17128295749710644740018775317232203204601286379485592754459742256737785524963515867132228e-05
        apm: [1.17128295749710644740018775317232203204601286379485592754459742256737785524963515867e-5 +/- 2.10e-89]
    cmath53:  NaN
    sflintc:  1.171283E-05
    dflintc:  1.17128295749711E-05
    eflintc:  1.1712829574971064473e-05
    qflintc:  1.17128295749710644740018775317232e-05
    oflintc:  1.171282957497106447400187753172322032046012863794855927544597422567378e-05
    mflintc:  1.17128295749710644740018775317232203204601286379485592754459742256737785524963515867129974E-05
    aflintc: [1.17128295749710644740018775317232203204601286379485592754459742256737785524963515867e-5 +/- 3.73e-89]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.gamma_upper(a, x))))
        fpm:  1.14913869019126E-05
        mpm:  0.0000114913869019125619353879066189071284002494206758154078717384595026182665707928982176663703
        dpm:  0.0000114913869019125619353879066189071284002494206758154078717384595026182665707928982176663703
        gpm:  1.1491386901912561935387906618907128400249420675815407871738459502618266570792898217666370299e-05
        apm: [1.149138690191256193538790661890712840024942067581540787173845950261826657079289821767e-5 +/- 9.52e-90]
    cmath53:  NaN
    sflintc:  1.149138E-05
    dflintc:  1.14913869019126E-05
    eflintc:  1.1491386901912561936e-05
    qflintc:  1.14913869019125619353879066189071e-05
    oflintc:  1.1491386901912561935387906618907128400249420675815407871738459502618267e-05
    mflintc:  1.14913869019125619353879066189071284002494206758154078717384595026182665707928982176659548E-05
    aflintc: [1.14913869019125619353879066189071284002494206758154078717384595026182665707928982177e-5 +/- 5.40e-89]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D04a_GammaUpperReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D04b_GammaUpperCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C02_IncompleteGamma/D04_GammaUpper.cs>`__. 









|newpage|

.. _rst_mpm_gamma_derivative: 

Derivative of the incomplete gamma function
-------------------------------------------------------------------------------

.. method:: ctx.gamma_p_prime(a, z)



Returns the partial derivative with respect to `x` of the incomplete gamma function `P(a,x)`:

The partial derivative with respect to `x` of the incomplete gamma function `P(a,x)` is defined as:

.. math :: \frac{\partial}{\partial x}P(a,x) = \frac{e^{-x} x^{a-1}}{\Gamma(a)}.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_p_prime(a, x)))
        fpm:  0.141220624442451
        mpm:  0.141220624442451056699432708292515800932353431506110625630540482051998608578142224905084469
        dpm:  0.141220624442451056699432708292515800932353431506110625630540482051998608578142224905084469
        gpm:  0.141220624442451056699432708292515800932353431506110625630540482051998608578142224905084469
        apm: [0.14122062444245105669943270829251580093235343150611062563054048205199860857814222490508447 +/- 2.46e-90]
     math53:  0.141220624442451
      sreal:  0.1412206
      dreal:  0.141220624442451
      ereal:  0.14122062444245105667
      qreal:  0.141220624442451056699432708292516
      oreal:  0.1412206244424510566994327082925158009323534315061106256305404820519986
      mreal:  0.141220624442451056699432708292515800932353431506110625630540482051998608578142224905084483
     sflint:  0.1412206
     dflint:  0.141220624442451
     eflint:  0.14122062444245105671
     qflint:  0.141220624442451056699432708292516
     oflint:  0.14122062444245105669943270829251580093235343150611062563054048205199861
     mflint:  0.141220624442451056699432708292515800932353431506110625630540482051998608578142224905084468
     aflint: [0.14122062444245105669943270829251580093235343150611062563054048205199860857814222490508447 +/- 3.74e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_p_prime(a, x)))
        fpm:  (0.000535235960277627, 0.000222604605139011)
        mpm:  (0.0005352359602776265748193352494796072327281, 0.0002226046051390106128166609701948109758652)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.gamma_p_prime(a, x))))
        fpm:  0.000535235960277627
        mpm:  0.000535235960277626574819335249479607232728234991889475247106352349147989713609156831946778776
        dpm:  0.000535235960277626574819335249479607232728234991889475247106352349147989713609156831946778776
        gpm:  0.00053523596027762657481933524947960723272823499188947524710635234914798971360915683194677877604
        apm: [0.0005352359602776265748193352494796072327282349918894752471063523491479897136091568319467788 +/- 4.13e-92]
    cmath53:  NaN
    sflintc:  0.0005352353
    dflintc:  0.000535235960277624
    eflintc:  0.00053523596027762657429
    qflintc:  0.000535235960277626574819335249479605
    oflintc:  0.00053523596027762657481933524947960723272823499188947524710635234914798962
    mflintc:  0.000535235960277626574819335249479607232728234991889475247106352349147989713609156831946778772
    aflintc: [0.0005352359602776265748193352494796072327282349918894752471063523491479897136091568319467788 +/- 4.76e-92]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.gamma_p_prime(a, x))))
        fpm:  0.000222604605139011
        mpm:  0.000222604605139010612816660970194810975865224422136844224988195981096783185659244112796236837
        dpm:  0.000222604605139010612816660970194810975865224422136844224988195981096783185659244112796236837
        gpm:  0.00022260460513901061281666097019481097586522442213684422498819598109678318565924411279623683699
        apm: [0.0002226046051390106128166609701948109758652244221368442249881959810967831856592441127962368 +/- 4.38e-92]
    cmath53:  NaN
    sflintc:  0.0002226044
    dflintc:  0.00022260460513901
    eflintc:  0.00022260460513901061265
    qflintc:  0.00022260460513901061281666097019481
    oflintc:  0.00022260460513901061281666097019481097586522442213684422498819598109678316
    mflintc:  0.00022260460513901061281666097019481097586522442213684422498819598109678318565924411279623684
    aflintc: [0.0002226046051390106128166609701948109758652244221368442249881959810967831856592441127962368 +/- 5.61e-92]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D05a_GammaPPrimeReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D05b_GammaPPrimeCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C02_IncompleteGamma/D05_GammaPPrime.cs>`__. 









|newpage|


.. _rst_mpm_real_gamma_p_inv: 

Inverse of the real lower normalised incomplete gamma function, `P^{-1}(a, q)`
----------------------------------------------------------------------------------------

.. method:: ctx.gamma_p_inv(a, q)

    where ``ctx`` is ``math53``, ``ctxcpp``, ``ctxboost`` or ``ctxflint``.


    Note: ctx.incGammaPInv(a, p)

    Returns `P^{-1}(a,p)`, the functional inverse of the real lower normalized incomplete gamma function, i.e. the function calculates `x` with `P(a,x) = p` where `a>0` and  `0<p<1`.

    See also   BoostMath :cite:p:`BoostFun02`,  Wikipedia :cite:p:`WikipediaFun01`, MathWorld :cite:p:`WolframFun02`, NIST :cite:p:`DLMFun01`, :cite:t:`Ehrhardt2018` (3.5.2.4).




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; p = 0.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_boost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_p_inv(a, p)))
        fpm:  6.00239619014205
        mpm:  6.00239619014205174380605049597150170816628931856817372783313436324346359920598833433283577
        dpm:  6.00239619014205174380605049597150170816628931856817372783313436324346359920598833433283577
        gpm:  6.0023961901420517438060504959715017081662893185681737278331343632434635992059883343328357695
        apm: [6.00239619014205174380605049597150170816628931856817372783313436324346359920598833433283577 +/- 1.46e-90]
     math53:  6.00239619014205
      sreal:  6.002396
      dreal:  6.00239619014205
      ereal:  6.0023961901420517435
      qreal:  6.0023961901420517438060504959715
      oreal:  6.0023961901420517438060504959715017081662893185681737278331343632434634
      mreal:  6.00239619014205174380605049597150170816628931856817372783313436324346359920598833433283573




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D06a_GammaPInverse.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C02_IncompleteGamma/D06_GammaPInverse.cs>`__. 








|newpage|


.. _rst_mpm_real_gamma_q_inv: 

Inverse of the real upper normalised incomplete gamma function, `Q^{-1}(a, q)`
-----------------------------------------------------------------------------------------

.. method:: ctx.gamma_q_inv(a, q)

    where ``ctx`` is ``math53``, ``ctxcpp``, ``ctxboost`` or ``ctxflint``.


    Note: ctx.incGammaQInv(a, q)


    Returns `Q^{-1}(a,q)`, the functional inverse of the real upper normalized incomplete gamma function, i.e. the function calculates `x` with `Q(a,x) = q` where `a>0` and  `0<q<1`.

    See also   BoostMath :cite:p:`BoostFun02`,  Wikipedia :cite:p:`WikipediaFun01`, MathWorld :cite:p:`WolframFun02`, NIST :cite:p:`DLMFun01`, :cite:t:`Ehrhardt2018` (3.5.2.4).



An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; q = 0.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_boost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.gamma_q_inv(a, q)))
        fpm:  3.72142207565333
        mpm:  3.72142207565332620157316204041578706438830950976695140364151337106975742720125247031762521
        dpm:  3.72142207565332620157316204041578706438830950976695140364151337106975742720125247031762521
        gpm:  3.72142207565332620157316204041578706438830950976695140364151337106975742720125247031762521
        apm: [3.72142207565332620157316204041578706438830950976695140364151337106975742720125247031762521 +/- 9.75e-91]
     math53:  3.72142207565333
      sreal:  3.721422
      dreal:  3.72142207565333
      ereal:  3.7214220756533262018
      qreal:  3.72142207565332620157316204041579
      oreal:  3.7214220756533262015731620404157870643883095097669514036415133710697576
      mreal:  3.72142207565332620157316204041578706438830950976695140364151337106975742720125247031762514




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C02_IncompleteGamma/D07a_GammaQInverse.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C02_IncompleteGamma/D07_GammaQInverse.cs>`__. 






