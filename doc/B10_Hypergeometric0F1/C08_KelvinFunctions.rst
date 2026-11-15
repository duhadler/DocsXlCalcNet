

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Kelvin functions
===============================================================================


.. _rst_mpm_ber: 

Kelvin function `\mathrm{ber}(\nu, x)`
-------------------------------------------------------------------------------

.. method:: ctx.kelvin_ber(nu, z, scaled=False)


    Returns the Kelvin function `\mathrm{ber}(\nu, x)`. 

    If *scaled* is *True*, then `\mathrm{ber}(\nu, x) \cdot \exp(-|x| / \sqrt{2})` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun1040`, MathWorld :cite:p:`WolframFun1040`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1040`.

    Here `\nu` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `n, x \in \mathbb{C}` is accepted. 


    This function is traditionally defined for `\nu \in \mathbb{R}` and real `x \ge 0` as the real part of the Bessel `J` function of a rotated argument:

    .. math :: \mathrm{ber}(\nu, x) = \Re \Big( J_{\nu}\big( x e^{3\pi i/4} \bigr) \Bigr).

    In XlCalcNet this is generalized to complex `\nu` and `x` following the definition given in Maple :cite:p:`Maplesoft104` as

    .. math::  \mathrm{ber}(\nu, x) = \frac{ J_{\nu}(x(-a + i a)) + J_{\nu}(x(-a - i a)) }{2}, \quad \text{where } a = \tfrac{1}{2} \sqrt{2},

    which is equivalent to the traditional definition for `\nu \in \mathbb{R}` and real `x \ge 0`.



    Note that this differs from Mpmath, which uses the conventions of Mathematica.

    The Kelvin functions are all real valued for real `x` and positive `\nu`.



An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_ber(nu, x, scaled=False)))
        fpm:  0.031615032153568
        mpm:  0.0316150321535679926927457132525527749283905198919160147702225471663741145657445031103275263
        dpm:  0.0316150321535679926927457132525527749283905198919160147702225471663741145657445031103275263
        gpm:  0.031615032153567992692745713252552774928390519891916014770222547166374114565744503110327526302
        apm: [0.03161503215356799269274571325255277492839051989191601477022254716637411456574450311032753 +/- 5.39e-90]
     math53:  0.031615032153568
     sflint:  0.03161504
     dflint:  0.031615032153568
     eflint:  0.031615032153567992698
     qflint:  0.0316150321535679926927457132525528
     oflint:  0.031615032153567992692745713252552774928390519891916014770222547166374115
     mflint:  0.0316150321535679926927457132525527749283905198919160147702225471663741145657445031103275264
     aflint: [0.0316150321535679926927457132525527749283905198919160147702225471663741145657445031103275 +/- 3.24e-89]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_ber(nu, x, scaled=False)))
        fpm:  (0.319757896582837, 0.0444238160821789)
        mpm:  (0.3197578965828370623690466444032041468447, 0.04442381608217885269645776712410464115333)
    cmath53:  (0.319757896582836, 0.044423816082179)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.kelvin_ber(nu, x, scaled=False))))
        fpm:  0.319757896582837
        mpm:  0.319757896582837062369046644403204146844717196575279663371010544852092096743246380822615907
        dpm:  0.319757896582837062369046644403204146844717196575279663371010544852092096743246380822615907
        gpm:  0.31975789658283706236904664440320414684471719657527966337101054485209209674324638082261590703
        apm: [0.3197578965828370623690466444032041468447171965752796633710105448520920967432463808226159 +/- 3.50e-89]
    cmath53:  0.319757896582836
    sflintc:  0.3197576
    dflintc:  0.319757896582837
    eflintc:  0.31975789658283706215
    qflintc:  0.319757896582837062369046644403203
    oflintc:  0.3197578965828370623690466444032041468447171965752796633710105448520921
    mflintc:  0.319757896582837062369046644403204146844717196575279663371010544852092096743246380822615904
    aflintc: [0.3197578965828370623690466444032041468447171965752796633710105448520920967432463808226159 +/- 9.11e-89]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.kelvin_ber(nu, x, scaled=False))))
        fpm:  0.0444238160821789
        mpm:  0.0444238160821788526964577671241046411533228775026270282796727677636335881143934957139348468
        dpm:  0.0444238160821788526964577671241046411533228775026270282796727677636335881143934957139348468
        gpm:  0.044423816082178852696457767124104641153322877502627028279672767763633588114393495713934846804
        apm: [0.0444238160821788526964577671241046411533228775026270282796727677636335881143934957139348 +/- 7.39e-89]
    cmath53:  0.044423816082179
    sflintc:  0.04442386
    dflintc:  0.0444238160821789
    eflintc:  0.044423816082178852739
    qflintc:  0.0444238160821788526964577671241048
    oflintc:  0.044423816082178852696457767124104641153322877502627028279672767763633588
    mflintc:  0.0444238160821788526964577671241046411533228775026270282796727677636335881143934957139348473
    aflintc: [0.044423816082178852696457767124104641153322877502627028279672767763633588114393495713935 +/- 2.28e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D01a_KelvinBerReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D01b_KelvinBerCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C08_KelvinFunctions/D01_KelvinBer.cs>`__. 







|newpage|


.. _rst_mpm_bei: 

Kelvin function `\mathrm{bei}(\nu, x)`
-------------------------------------------------------------------------------

.. method:: ctx.kelvin_bei(nu, z, scaled=False)


    Returns the Kelvin function `\mathrm{bei}(\nu, x)`.  

    If *scaled* is *True*, then `\mathrm{bei}(\nu, x) \cdot \exp(-|x| / \sqrt{2})` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun1041`, MathWorld :cite:p:`WolframFun1041`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1041`.

    Here `\nu` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `n, x \in \mathbb{C}` is accepted. 


    This function is traditionally defined for `\nu \in \mathbb{R}` and real `x \ge 0` as the imaginary part of the Bessel `J` function of a rotated argument:

    .. math :: \mathrm{bei}(\nu, x) = \Im \Big( J_{\nu}\big( x e^{3\pi i/4} \bigr) \Bigr).

    In XlCalcNet this is generalized to complex `\nu` and `x` following the definition given in Maple :cite:p:`Maplesoft104` as

    .. math::  \mathrm{bei}(\nu, x) = \frac{ J_{\nu}(x(-a + i a)) - J_{\nu}(x(-a - i a)) }{2}, \quad \text{where } a = \tfrac{1}{2 i} \sqrt{2},


    which is equivalent to the traditional definition for `\nu \in \mathbb{R}` and real `x \ge 0`.



    Note that this differs from Mpmath, which uses the conventions of Mathematica.

    The Kelvin functions are all real valued for real `x` and positive `\nu`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_bei(nu, x, scaled=False)))
        fpm:  -0.00811697598295039
        mpm:  -0.00811697598295038833297919104359082947628353361355425692297600379754787807809473606843148294
        dpm:  -0.00811697598295038833297919104359082947628353361355425692297600379754787807809473606843148294
        gpm:  -0.0081169759829503883329791910435908294762835336135542569229760037975478780780947360684314829391
        apm: [-0.00811697598295038833297919104359082947628353361355425692297600379754787807809473606843148 +/- 4.52e-90]
     math53:  -0.00811697598295043
     sflint:  -0.008116985
     dflint:  -0.00811697598295039
     eflint:  -0.0081169759829503883411
     qflint:  -0.00811697598295038833297919104359086
     oflint:  -0.0081169759829503883329791910435908294762835336135542569229760037975478781
     mflint:  -0.00811697598295038833297919104359082947628353361355425692297600379754787807809473606843148303
     aflint: [-0.00811697598295038833297919104359082947628353361355425692297600379754787807809473606843148 +/- 8.67e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_bei(nu, x, scaled=False)))
        fpm:  (-0.0199186554987316, -0.125254399400867)
        mpm:  (-0.01991865549873161513814163203432292202879, -0.1252543994008674866147239349904282448012)
    cmath53:  (-0.0199186554987318, -0.125254399400867)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.kelvin_bei(nu, x, scaled=False))))
        fpm:  -0.0199186554987316
        mpm:  -0.019918655498731615138141632034322922028792768691096064635740615479376278125820430897788473
        dpm:  -0.019918655498731615138141632034322922028792768691096064635740615479376278125820430897788473
        gpm:  -0.019918655498731615138141632034322922028792768691096064635740615479376278125820430897788472999
        apm: [-0.0199186554987316151381416320343229220287927686910960646357406154793762781258204308977885 +/- 5.43e-89]
    cmath53:  -0.0199186554987318
    sflintc:  -0.01991866
    dflintc:  -0.0199186554987316
    eflintc:  -0.019918655498731615139
    qflintc:  -0.0199186554987316151381416320343229
    oflintc:  -0.019918655498731615138141632034322922028792768691096064635740615479376278
    mflintc:  -0.019918655498731615138141632034322922028792768691096064635740615479376278125820430897788473
    aflintc: [-0.019918655498731615138141632034322922028792768691096064635740615479376278125820430897788 +/- 5.45e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.kelvin_bei(nu, x, scaled=False))))
        fpm:  -0.125254399400867
        mpm:  -0.1252543994008674866147239349904282448012737812030312350407391662688851433825159024043687
        dpm:  -0.1252543994008674866147239349904282448012737812030312350407391662688851433825159024043687
        gpm:  -0.12525439940086748661472393499042824480127378120303123504073916626888514338251590240436870001
        apm: [-0.1252543994008674866147239349904282448012737812030312350407391662688851433825159024043687 +/- 3.23e-89]
    cmath53:  -0.125254399400867
    sflintc:  -0.1252542
    dflintc:  -0.125254399400867
    eflintc:  -0.12525439940086748645
    qflintc:  -0.125254399400867486614723934990428
    oflintc:  -0.12525439940086748661472393499042824480127378120303123504073916626888514
    mflintc:  -0.125254399400867486614723934990428244801273781203031235040739166268885143382515902404368698
    aflintc: [-0.1252543994008674866147239349904282448012737812030312350407391662688851433825159024043687 +/- 8.86e-89]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D02a_KelvinBeiReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D02b_KelvinBeiCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C08_KelvinFunctions/D02_KelvinBei.cs>`__. 









|newpage|


.. _rst_mpm_ker: 

Kelvin function `\mathrm{ker}(\nu, x)`
-------------------------------------------------------------------------------

.. method:: ctx.kelvin_ker(nu, z, scaled=False)


    Returns the Kelvin function `\mathrm{ker}(\nu, x)`.  

    If *scaled* is *True*, then `\mathrm{bei}(\nu, x) \cdot \exp(|x| / \sqrt{2})` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun1042`, MathWorld :cite:p:`WolframFun1042`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1042`.


    Here `\nu` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `n, x \in \mathbb{C}` is accepted. 


    This function is traditionally defined for `\nu \in \mathbb{R}` and real `x \ge 0` as the real part of the Bessel `K` function of a rotated argument:

    .. math :: \mathrm{ker}(\nu, x) = \Re \Big( e^{-\pi i/2} K_n\big(x e^{3\pi i/4} \bigr) \Bigr).

    In XlCalcNet this is generalized to complex `\nu` and `x` following the definition given in Maple :cite:p:`Maplesoft104` as

    .. math::  \mathrm{ker}(\nu, x) = \frac{ e^{-i \nu \pi/2} K_{\nu}(x(a + i a)) + e^{i \nu \pi/2} K_{\nu}(x(a - i a)) }{2}, \quad \text{where } a = \tfrac{1}{2} \sqrt{2},


    which is equivalent to the traditional definition for `\nu \in \mathbb{R}` and real `x \ge 0`.



    Note that this differs from Mpmath, which uses the conventions of Mathematica.

    The Kelvin functions are all real valued for real `x` and positive `\nu`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_ker(nu, x, scaled=False)))
        fpm:  2.91800433823935
        mpm:  2.91800433823935050772694782314833770270133541159771861738881134371945562230231056636293714
        dpm:  2.91800433823935050772694782314833770270133541159771861738881134371945562230231056636293714
        gpm:  2.91800433823935050772694782314833770270133541159771861738881134371945562230231056636293714
        apm: [2.918004338239350507726947823148337702701335411597718617388811343719455622302310566362937 +/- 4.27e-88]
     math53:  2.91800433823935
     sflint:  2.918004
     dflint:  2.91800433823935
     eflint:  2.9180043382393505071
     qflint:  2.91800433823935050772694782314834
     oflint:  2.9180043382393505077269478231483377027013354115977186173888113437194556
     mflint:  2.91800433823935050772694782314833770270133541159771861738881134371945562230231056636293713
     aflint: [2.91800433823935050772694782314833770270133541159771861738881134371945562230231056636294 +/- 3.72e-87]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_ker(nu, x, scaled=False)))
        fpm:  (1.09124617244099, 0.261526566911288)
        mpm:  (1.09124617244099007011656227051090104683, 0.2615265669112884230044970870819124982905)
    cmath53:  (1.091246172441, 0.261526566911283)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.kelvin_ker(nu, x, scaled=False))))
        fpm:  1.09124617244099
        mpm:  1.09124617244099007011656227051090104682968784020145006766946353535927783943456715078424786
        dpm:  1.09124617244099007011656227051090104682968784020145006766946353535927783943456715078424786
        gpm:  1.09124617244099007011656227051090104682968784020145006766946353535927783943456715078424786
        apm: [1.091246172440990070116562270510901046829687840201450067669463535359277839434567150784248 +/- 3.60e-88]
    cmath53:  1.091246172441
    sflintc:  1.091246
    dflintc:  1.09124617244099
    eflintc:  1.09124617244099007
    qflintc:  1.0912461724409900701165622705109
    oflintc:  1.0912461724409900701165622705109010468296878402014500676694635353592778
    mflintc:  1.09124617244099007011656227051090104682968784020145006766946353535927783943456715078424786
    aflintc: [1.091246172440990070116562270510901046829687840201450067669463535359277839434567150784248 +/- 7.44e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.kelvin_ker(nu, x, scaled=False))))
        fpm:  0.261526566911288
        mpm:  0.261526566911288423004497087081912498290457614519179130044931715512763439048157997749599387
        dpm:  0.261526566911288423004497087081912498290457614519179130044931715512763439048157997749599387
        gpm:  0.26152656691128842300449708708191249829045761451917913004493171551276343904815799774959938702
        apm: [0.261526566911288423004497087081912498290457614519179130044931715512763439048157997749599 +/- 5.76e-88]
    cmath53:  0.261526566911283
    sflintc:  0.2615266
    dflintc:  0.261526566911288
    eflintc:  0.261526566911288423
    qflintc:  0.261526566911288423004497087081913
    oflintc:  0.26152656691128842300449708708191249829045761451917913004493171551276344
    mflintc:  0.261526566911288423004497087081912498290457614519179130044931715512763439048157997749599387
    aflintc: [0.261526566911288423004497087081912498290457614519179130044931715512763439048157997749599 +/- 9.51e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D03a_KelvinKerReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D03b_KelvinKerCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C08_KelvinFunctions/D03_KelvinKer.cs>`__. 












|newpage|


.. _rst_mpm_kei: 

Kelvin function `\mathrm{kei}(\nu, x)`
-------------------------------------------------------------------------------

.. method:: ctx.kelvin_kei(nu, z, scaled=False)


    Returns the Kelvin function `\mathrm{kei}(\nu, x)`. 

    If *scaled* is *True*, then `\mathrm{kei}(\nu, x) \cdot \exp(|x| / \sqrt{2})` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun1043`, MathWorld :cite:p:`WolframFun1043`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1043`.


    Here `\nu` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `n, x \in \mathbb{C}` is accepted. 


    This function is traditionally defined for `\nu \in \mathbb{R}` and real `x \ge 0` as the imaginary part of the Bessel `K` function of a rotated argument:

    .. math :: \mathrm{kei}(\nu, x) = \Im \Big( e^{-\pi i/2} K_n\big(x e^{3\pi i/4} \bigr) \Bigr).

    In XlCalcNet this is generalized to complex `\nu` and `x` following the definition given in Maple :cite:p:`Maplesoft104` as

    .. math::  \mathrm{kei}(\nu, x) = \frac{ e^{-i \nu \pi/2} K_{\nu}(x(a + i a)) - e^{i \nu \pi/2} K_{\nu}(x(a - i a)) }{2 i}, \quad \text{where } a = \tfrac{1}{2} \sqrt{2}.


    which is equivalent to the traditional definition for `\nu \in \mathbb{R}` and real `x \ge 0`.



    Note that this differs from Mpmath, which uses the conventions of Mathematica.

    The Kelvin functions are all real valued for real `x` and positive `\nu`.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_kei(nu, x, scaled=False)))
        fpm:  0.328177462330288
        mpm:  0.328177462330288135774333729239761518316421214229704341864354983901983656235721065189236011
        dpm:  0.328177462330288135774333729239761518316421214229704341864354983901983656235721065189236011
        gpm:  0.32817746233028813577433372923976151831642121422970434186435498390198365623572106518923601101
        apm: [0.328177462330288135774333729239761518316421214229704341864354983901983656235721065189236 +/- 3.09e-88]
     math53:  0.328177462330313
     sflint:  0.328178
     dflint:  0.328177462330288
     eflint:  0.32817746233028813625
     qflint:  0.328177462330288135774333729239763
     oflint:  0.32817746233028813577433372923976151831642121422970434186435498390198366
     mflint:  0.328177462330288135774333729239761518316421214229704341864354983901983656235721065189236016
     aflint: [0.328177462330288135774333729239761518316421214229704341864354983901983656235721065189236 +/- 8.63e-88]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_kei(nu, x, scaled=False)))
        fpm:  (0.64885760448229, -0.716615639631133)
        mpm:  (0.6488576044822901684808952352364377785889, -0.7166156396311331323256141997713375799249)
    cmath53:  (0.648857604482281, -0.716615639631135)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.kelvin_kei(nu, x, scaled=False))))
        fpm:  0.64885760448229
        mpm:  0.648857604482290168480895235236437778588918707656791726783704668374515267105287193019653098
        dpm:  0.648857604482290168480895235236437778588918707656791726783704668374515267105287193019653098
        gpm:  0.64885760448229016848089523523643777858891870765679172678370466837451526710528719301965309798
        apm: [0.648857604482290168480895235236437778588918707656791726783704668374515267105287193019653 +/- 2.87e-88]
    cmath53:  0.648857604482281
    sflintc:  0.6488575
    dflintc:  0.64885760448229
    eflintc:  0.64885760448229016833
    qflintc:  0.648857604482290168480895235236437
    oflintc:  0.64885760448229016848089523523643777858891870765679172678370466837451527
    mflintc:  0.648857604482290168480895235236437778588918707656791726783704668374515267105287193019653097
    aflintc: [0.648857604482290168480895235236437778588918707656791726783704668374515267105287193019653 +/- 6.61e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.kelvin_kei(nu, x, scaled=False))))
        fpm:  -0.716615639631133
        mpm:  -0.716615639631133132325614199771337579924974919046220632478604574843549417086155082414979429
        dpm:  -0.716615639631133132325614199771337579924974919046220632478604574843549417086155082414979429
        gpm:  -0.71661563963113313232561419977133757992497491904622063247860457484354941708615508241497942894
        apm: [-0.716615639631133132325614199771337579924974919046220632478604574843549417086155082414979 +/- 6.51e-88]
    cmath53:  -0.716615639631135
    sflintc:  -0.7166155
    dflintc:  -0.716615639631133
    eflintc:  -0.71661563963113313221
    qflintc:  -0.716615639631133132325614199771337
    oflintc:  -0.71661563963113313232561419977133757992497491904622063247860457484354942
    mflintc:  -0.716615639631133132325614199771337579924974919046220632478604574843549417086155082414979428
    aflintc: [-0.71661563963113313232561419977133757992497491904622063247860457484354941708615508241498 +/- 1.19e-87]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D04a_KelvinKeiReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D04b_KelvinKeiCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C08_KelvinFunctions/D04_KelvinKei.cs>`__. 










|newpage|


First derivative of the Kelvin function `\mathrm{ber}(\nu, x)`, `\mathrm{ber}'(\nu, x)`
---------------------------------------------------------------------------------------------

.. method:: ctx.kelvin_ber_prime(nu, z, scaled=False)


    Returns `\mathrm{ber}'(\nu, x)`, the first derivative (with respect to `x`) of the Kelvin function `\mathrm{ber}(\nu, x)`. 

    If *scaled* is *True*, then `\mathrm{ber}(\nu, x) \cdot \exp(-|x| / \sqrt{2})` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun1040`, MathWorld :cite:p:`WolframFun1040`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1040`.

    Here `\nu` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `n, x \in \mathbb{C}` is accepted. 

    The function is calculated as

    .. math::  \mathrm{ber}'(\nu, x) = \frac{a_1 J'_{\nu}(x \cdot a_1) + a_2 J'_{\nu}(x \cdot a_2) }{2},

    where `a = \tfrac{1}{2} \sqrt{2}`, `a_1 = -a + i a`, `a_2 = -a - i a`, and `J'_{\nu}(x)` is the first derivative (with respect to `x`) of the Bessel function `J_{\nu}(x)`.

    The Kelvin functions are all real valued for real `x` and positive `\nu`.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_ber_prime(nu, x, scaled=False)))
        fpm:  0.0618007359036927
        mpm:  0.061800735903692737991769833097649565833080468853259443450850323011054719277027156245589082
        dpm:  0.061800735903692737991769833097649565833080468853259443450850323011054719277027156245589082
        gpm:  0.061800735903692737991769833097649565833080468853259443450850323011054719277027156245589081996
        apm: [0.06180073590369273799176983309764956583308046885325944345085032301105471927702715624558908 +/- 5.70e-90]
     math53:  0.0618007359036927
     sflint:  0.06180074
     dflint:  0.0618007359036927
     eflint:  0.061800735903692738001
     qflint:  0.0618007359036927379917698330976496
     oflint:  0.061800735903692737991769833097649565833080468853259443450850323011054719
     mflint:  0.0618007359036927379917698330976495658330804688532594434508503230110547192770271562455890821
     aflint: [0.0618007359036927379917698330976495658330804688532594434508503230110547192770271562455891 +/- 3.32e-89]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_ber_prime(nu, x, scaled=False)))
        fpm:  (-0.103326116062683, 0.135303021707742)
        mpm:  (-0.1033261160626825606818893811458590708554, 0.1353030217077416051302214739604969923916)
    cmath53:  (-0.103326116062681, 0.135303021707741)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.kelvin_ber_prime(nu, x, scaled=False))))
        fpm:  -0.103326116062683
        mpm:  -0.103326116062682560681889381145859070855399098248734028749264280310369745439630176111964273
        dpm:  -0.103326116062682560681889381145859070855399098248734028749264280310369745439630176111964273
        gpm:  -0.103326116062682560681889381145859070855399098248734028749264280310369745439630176111964273
        apm: [-0.1033261160626825606818893811458590708553990982487340287492642803103697454396301761119643 +/- 9.53e-89]
    cmath53:  -0.103326116062681
    sflintc:  -0.1033258
    dflintc:  -0.103326116062683
    eflintc:  -0.10332611606268256042
    qflintc:  -0.103326116062682560681889381145858
    oflintc:  -0.10332611606268256068188938114585907085539909824873402874926428031036975
    mflintc:  -0.10332611606268256068188938114585907085539909824873402874926428031036974543963017611196427
    aflintc: [-0.103326116062682560681889381145859070855399098248734028749264280310369745439630176111964 +/- 4.59e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.kelvin_ber_prime(nu, x, scaled=False))))
        fpm:  0.135303021707742
        mpm:  0.135303021707741605130221473960496992391643790199202653299437806174885182139899977224010081
        dpm:  0.135303021707741605130221473960496992391643790199202653299437806174885182139899977224010081
        gpm:  0.135303021707741605130221473960496992391643790199202653299437806174885182139899977224010081
        apm: [0.1353030217077416051302214739604969923916437901992026532994378061748851821398999772240101 +/- 8.77e-89]
    cmath53:  0.135303021707741
    sflintc:  0.1353028
    dflintc:  0.135303021707742
    eflintc:  0.13530302170774160489
    qflintc:  0.135303021707741605130221473960496
    oflintc:  0.13530302170774160513022147396049699239164379019920265329943780617488518
    mflintc:  0.135303021707741605130221473960496992391643790199202653299437806174885182139899977224010078
    aflintc: [0.135303021707741605130221473960496992391643790199202653299437806174885182139899977224010 +/- 2.60e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D05a_KelvinBerRealPrime.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D05b_KelvinBerCplxPrime.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C08_KelvinFunctions/D05_KelvinBerPrime.cs>`__. 









|newpage|



First derivative of the Kelvin function `\mathrm{bei}(\nu, x)`, `\mathrm{bei}'(\nu, x)`
------------------------------------------------------------------------------------------------

.. method:: ctx.kelvin_bei_prime(nu, z, scaled=False)


    Returns `\mathrm{bei}'(\nu, x)`, the first derivative (with respect to `x`) of the Kelvin function `\mathrm{bei}(\nu, x)`. 

    If *scaled* is *True*, then `\mathrm{bei}(\nu, x) \cdot \exp(-|x| / \sqrt{2})` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun1040`, MathWorld :cite:p:`WolframFun1040`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1040`.

    Here `\nu` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `n, x \in \mathbb{C}` is accepted. 

    The function is calculated as

    .. math::  \mathrm{bei}'(\nu, x) = \frac{a_1 J'_{\nu}(x \cdot a_1) - a_2 J'_{\nu}(x \cdot a_2) }{2 i},

    where `a = \tfrac{1}{2} \sqrt{2}`, `a_1 = -a + i a`, `a_2 = -a - i a`, and `J'_{\nu}(x)` is the first derivative (with respect to `x`) of the Bessel function `J_{\nu}(x)`.

    The Kelvin functions are all real valued for real `x` and positive `\nu`.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_bei_prime(nu, x, scaled=False)))
        fpm:  -0.00843198057420073
        mpm:  -0.00843198057420072886548227199417631993600060781051212891341704758682393655700192197280483433
        dpm:  -0.00843198057420072886548227199417631993600060781051212891341704758682393655700192197280483433
        gpm:  -0.0084319805742007288654822719941763199360006078105121289134170475868239365570019219728048343309
        apm: [-0.00843198057420072886548227199417631993600060781051212891341704758682393655700192197280483 +/- 8.36e-90]
     math53:  -0.0084319805742008
     sflint:  -0.008431994
     dflint:  -0.00843198057420073
     eflint:  -0.0084319805742007288785
     qflint:  -0.00843198057420072886548227199417636
     oflint:  -0.0084319805742007288654822719941763199360006078105121289134170475868239365
     mflint:  -0.00843198057420072886548227199417631993600060781051212891341704758682393655700192197280483447
     aflint: [-0.0084319805742007288654822719941763199360006078105121289134170475868239365570019219728048 +/- 4.96e-89]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_bei_prime(nu, x, scaled=False)))
        fpm:  (-0.0916036321472191, 0.292658675742027)
        mpm:  (-0.09160363214721909073472933190060139633141, 0.2926586757420265480677882116119412427319)
    cmath53:  (-0.091603632147219, 0.292658675742026)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.kelvin_bei_prime(nu, x, scaled=False))))
        fpm:  -0.0916036321472191
        mpm:  -0.0916036321472190907347293319006013963314051668809393439635423404569148867606664548023760022
        dpm:  -0.0916036321472190907347293319006013963314051668809393439635423404569148867606664548023760022
        gpm:  -0.0916036321472190907347293319006013963314051668809393439635423404569148867606664548023760022
        apm: [-0.0916036321472190907347293319006013963314051668809393439635423404569148867606664548023760 +/- 6.83e-89]
    cmath53:  -0.091603632147219
    sflintc:  -0.09160365
    dflintc:  -0.0916036321472191
    eflintc:  -0.091603632147219090753
    qflintc:  -0.0916036321472190907347293319006015
    oflintc:  -0.091603632147219090734729331900601396331405166880939343963542340456914887
    mflintc:  -0.0916036321472190907347293319006013963314051668809393439635423404569148867606664548023760024
    aflintc: [-0.091603632147219090734729331900601396331405166880939343963542340456914886760666454802376 +/- 1.92e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.kelvin_bei_prime(nu, x, scaled=False))))
        fpm:  0.292658675742027
        mpm:  0.29265867574202654806778821161194124273195242211445073930543362756503390139477106658867728
        dpm:  0.29265867574202654806778821161194124273195242211445073930543362756503390139477106658867728
        gpm:  0.29265867574202654806778821161194124273195242211445073930543362756503390139477106658867727997
        apm: [0.2926586757420265480677882116119412427319524221144507393054336275650339013947710665886773 +/- 8.76e-89]
    cmath53:  0.292658675742026
    sflintc:  0.2926585
    dflintc:  0.292658675742027
    eflintc:  0.29265867574202654794
    qflintc:  0.292658675742026548067788211611941
    oflintc:  0.2926586757420265480677882116119412427319524221144507393054336275650339
    mflintc:  0.292658675742026548067788211611941242731952422114450739305433627565033901394771066588677278
    aflintc: [0.292658675742026548067788211611941242731952422114450739305433627565033901394771066588677 +/- 4.67e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D06a_KelvinBeiRealPrime.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D06b_KelvinBeiCplxPrime.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C08_KelvinFunctions/D06_KelvinBeiPrime.cs>`__. 








|newpage|



First derivative of the Kelvin function `\mathrm{ker}(\nu, x)`, `\mathrm{ker}'(\nu, x)`
----------------------------------------------------------------------------------------------

.. method:: ctx.kelvin_ker_prime(nu, z, scaled=False)


    Returns `\mathrm{ker}'(\nu, x)`, the first derivative (with respect to `x`) of the Kelvin function `\mathrm{ker}(\nu, x)`. 

    If *scaled* is *True*, then `\mathrm{ber}(\nu, x) \cdot \exp(|x| / \sqrt{2})` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun1042`, MathWorld :cite:p:`WolframFun1042`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1042`.

    Here `\nu` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `n, x \in \mathbb{C}` is accepted. 

    The function is calculated as

    .. math::  \mathrm{ker}'(\nu, x) = \frac{e^{-\nu\pi i/2} a_1 K'_{\nu}(x \cdot a_1) + e^{\nu\pi i/2} a_2 K'_{\nu}(x \cdot a_2) }{2},

    where `a = \tfrac{1}{2} \sqrt{2}, \: a_1 = -a + i a, \:a_2 = -a - i a`, and `K'_{\nu}(x)` is the first derivative (with respect to `x`) of the Bessel function `K_{\nu}(x)`.

    The Kelvin functions are all real valued for real `x` and positive `\nu`.






An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_ker_prime(nu, x, scaled=False)))
        fpm:  -5.52415129389176
        mpm:  -5.52415129389176397989393553861058179569921990930715950173239583122269252522975898129437501
        dpm:  -5.52415129389176397989393553861058179569921990930715950173239583122269252522975898129437501
        gpm:  -5.52415129389176397989393553861058179569921990930715950173239583122269252522975898129437501
        apm: [-5.524151293891763979893935538610581795699219909307159501732395831222692525229758981294375 +/- 5.49e-88]
     math53:  -5.52415129389175
     sflint:  -5.524149
     dflint:  -5.52415129389176
     eflint:  -5.5241512938917639785
     qflint:  -5.52415129389176397989393553861058
     oflint:  -5.5241512938917639798939355386105817956992199093071595017323958312226925
     mflint:  -5.52415129389176397989393553861058179569921990930715950173239583122269252522975898129437499
     aflint: [-5.52415129389176397989393553861058179569921990930715950173239583122269252522975898129437 +/- 6.57e-87]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_ker_prime(nu, x, scaled=False)))
        fpm:  (-1.16220602546931, 0.443562774086013)
        mpm:  (-1.1622060254693133384966631726156228215, 0.44356277408601313115948683903190514947)
    cmath53:  (-1.16220602546932, 0.443562774086021)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.kelvin_ker_prime(nu, x, scaled=False))))
        fpm:  -1.16220602546931
        mpm:  -1.1622060254693133384966631726156228214998889128546367928090940294667208138535355792835881
        dpm:  -1.1622060254693133384966631726156228214998889128546367928090940294667208138535355792835881
        gpm:  -1.1622060254693133384966631726156228214998889128546367928090940294667208138535355792835880999
        apm: [-1.162206025469313338496663172615622821499888912854636792809094029466720813853535579283588 +/- 5.22e-88]
    cmath53:  -1.16220602546932
    sflintc:  -1.162206
    dflintc:  -1.16220602546931
    eflintc:  -1.1622060254693133384
    qflintc:  -1.16220602546931333849666317261562
    oflintc:  -1.1622060254693133384966631726156228214998889128546367928090940294667208
    mflintc:  -1.1622060254693133384966631726156228214998889128546367928090940294667208138535355792835881
    aflintc: [-1.16220602546931333849666317261562282149988891285463679280909402946672081385353557928359 +/- 3.07e-87]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.kelvin_ker_prime(nu, x, scaled=False))))
        fpm:  0.443562774086013
        mpm:  0.443562774086013131159486839031905149470009236507593595459636172292848306867664490393074631
        dpm:  0.443562774086013131159486839031905149470009236507593595459636172292848306867664490393074631
        gpm:  0.44356277408601313115948683903190514947000923650759359545963617229284830686766449039307463097
        apm: [0.443562774086013131159486839031905149470009236507593595459636172292848306867664490393075 +/- 7.87e-88]
    cmath53:  0.443562774086021
    sflintc:  0.4435626
    dflintc:  0.443562774086013
    eflintc:  0.44356277408601313105
    qflintc:  0.443562774086013131159486839031905
    oflintc:  0.44356277408601313115948683903190514947000923650759359545963617229284831
    mflintc:  0.443562774086013131159486839031905149470009236507593595459636172292848306867664490393074629
    aflintc: [0.44356277408601313115948683903190514947000923650759359545963617229284830686766449039307 +/- 5.78e-87]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D07a_KelvinKerRealPrime.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D07b_KelvinKerCplxPrime.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C08_KelvinFunctions/D07_KelvinKerPrime.cs>`__. 









|newpage|



First derivative of the Kelvin function `\mathrm{kei}(\nu, x)`, `\mathrm{kei}'(\nu, x)`
------------------------------------------------------------------------------------------

.. method:: ctx.kelvin_kei_prime(nu, z, scaled=False)


    Returns `\mathrm{kei}'(\nu, x)`, the first derivative (with respect to `x`) of the Kelvin function `\mathrm{kei}(\nu, x)`. 

    If *scaled* is *True*, then `\mathrm{kei}(\nu, x) \cdot \exp(|x| / \sqrt{2})` is returned.


    See also  Wikipedia :cite:p:`WikipediaFun1043`, MathWorld :cite:p:`WolframFun1043`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1043`.


    Here `\nu` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `n, x \in \mathbb{C}` is accepted. 

    The function is calculated as

    .. math::  \mathrm{ker}'(\nu, x) = \frac{e^{-\nu\pi i/2} a_1 K'_{\nu}(x \cdot a_1) - e^{\nu\pi i/2} a_2 K'_{\nu}(x \cdot a_2) }{2 i},

    where `a = \tfrac{1}{2} \sqrt{2}, \: a_1 = -a + i a, \:a_2 = -a - i a`, and `K'_{\nu}(x)` is the first derivative (with respect to `x`) of the Bessel function `K_{\nu}(x)`.

    The Kelvin functions are all real valued for real `x` and positive `\nu`.



    


An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_kei_prime(nu, x, scaled=False)))
        fpm:  -1.55503085862289
        mpm:  -1.55503085862289307341137877952276394035665127179031000302499895417143598410299919225498339
        dpm:  -1.55503085862289307341137877952276394035665127179031000302499895417143598410299919225498339
        gpm:  -1.5550308586228930734113787795227639403566512717903100030249989541714359841029991922549833899
        apm: [-1.55503085862289307341137877952276394035665127179031000302499895417143598410299919225498 +/- 3.91e-87]
     math53:  -1.55503085862294
     sflint:  -1.555032
     dflint:  -1.55503085862289
     eflint:  -1.5550308586228930741
     qflint:  -1.55503085862289307341137877952277
     oflint:  -1.555030858622893073411378779522763940356651271790310003024998954171436
     mflint:  -1.55503085862289307341137877952276394035665127179031000302499895417143598410299919225498339
     aflint: [-1.55503085862289307341137877952276394035665127179031000302499895417143598410299919225498 +/- 4.89e-87]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.kelvin_kei_prime(nu, x, scaled=False)))
        fpm:  (-0.554609419706092, 1.0793947812899)
        mpm:  (-0.5546094197060921071757789012022791105959, 1.079394781289898168623544321095979517641)
    cmath53:  (-0.554609419706082, 1.07939478128989)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.kelvin_kei_prime(nu, x, scaled=False))))
        fpm:  -0.554609419706092
        mpm:  -0.554609419706092107175778901202279110595856575964294374864134616051540028816791893652514083
        dpm:  -0.554609419706092107175778901202279110595856575964294374864134616051540028816791893652514083
        gpm:  -0.55460941970609210717577890120227911059585657596429437486413461605154002881679189365251408305
        apm: [-0.554609419706092107175778901202279110595856575964294374864134616051540028816791893652514 +/- 5.00e-88]
    cmath53:  -0.554609419706082
    sflintc:  -0.5546094
    dflintc:  -0.554609419706092
    eflintc:  -0.55460941970609210712
    qflintc:  -0.554609419706092107175778901202279
    oflintc:  -0.55460941970609210717577890120227911059585657596429437486413461605154003
    mflintc:  -0.554609419706092107175778901202279110595856575964294374864134616051540028816791893652514083
    aflintc: [-0.55460941970609210717577890120227911059585657596429437486413461605154002881679189365251 +/- 5.25e-87]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.kelvin_kei_prime(nu, x, scaled=False))))
        fpm:  1.0793947812899
        mpm:  1.07939478128989816862354432109597951764077131983590939510667069825499402410730512917929774
        dpm:  1.07939478128989816862354432109597951764077131983590939510667069825499402410730512917929774
        gpm:  1.0793947812898981686235443210959795176407713198359093951066706982549940241073051291792977399
        apm: [1.079394781289898168623544321095979517640771319835909395106670698254994024107305129179298 +/- 6.81e-88]
    cmath53:  1.07939478128989
    sflintc:  1.079394
    dflintc:  1.0793947812899
    eflintc:  1.0793947812898981684
    qflintc:  1.07939478128989816862354432109598
    oflintc:  1.079394781289898168623544321095979517640771319835909395106670698254994
    mflintc:  1.07939478128989816862354432109597951764077131983590939510667069825499402410730512917929774
    aflintc: [1.07939478128989816862354432109597951764077131983590939510667069825499402410730512917930 +/- 3.42e-87]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D08a_KelvinKeiRealPrime.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C08_KelvinFunctions/D08b_KelvinKeiCplxPrime.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C08_KelvinFunctions/D08_KelvinKeiPrime.cs>`__. 












