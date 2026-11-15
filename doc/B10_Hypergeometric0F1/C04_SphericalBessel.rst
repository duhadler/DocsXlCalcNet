

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Spherical Bessel functions
===============================================================================



.. _rst_mpm_bessel_jn: 

Spherical Bessel function of the first kind, `j_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_jn(n, x, scaled=False)

    Returns `j_n(x)`, the spherical Bessel function of the first kind. 

    If *scaled* is *True*, then `j_{\nu}(x) \cdot \exp(-|\Im(x)|)` is returned, which means that for purely  real `x` just `j_{\nu}(x)` is returned.  

    See also  Wikipedia :cite:p:`WikipediaFun143`, MathWorld :cite:p:`WolframFun143a`, NIST :cite:p:`DLMFun143`, BoostMath :cite:p:`BoostFun143`, :cite:t:`Ehrhardt2018` (3.1.6.1).

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 



    This function is traditionally defined as `\displaystyle j_n(x) = \sqrt{\tfrac{1}{2}\pi/x} J_{n+\tfrac{1}{2}}(x)`, where `J_n(x)` is a Bessel function of the first kind. 

    In XlCalcNet, the definition `\displaystyle j_n(x) = \sqrt{\tfrac{1}{2}\pi} \frac{1}{\sqrt{x}} J_{n+\tfrac{1}{2}}(x)` is used instead, which gives identical results for `\Re(x) \ge 0`, but differs from the "traditional version" along the branch cut of the square root function. This ensures that the general definition for complex `n` and complex `x` agrees with the results from  Rayleigh's formula `\displaystyle j_n(x) = (-x)^n \left(\frac{1}{x}\frac{d}{dx}\right)^n \frac{\sin x}{x}` for integer `n \ge 0` and real or complex `x \ne 0`. Given `j_0(x)` and `j_1(x)`, Rayleigh's formula can also be computed recursively as `\displaystyle j_n(x) = \frac{2n-1}{x} j_{n-1}(x) -  j_{n-2}(x)` for `n \ge 2`.

    We extend this to negative integer indices using `j_{-n}(x) = (-1)^n y_{n+1}(x)` for `n > 0`, where `y_n(x)` is the spherical Bessel function of the second kind. We also have `j_n(-x) = (-1)^n j_{n+1}(x)` for `x > 0`. 


    For `n \in \mathbb{Z}` and `x \in \mathbb{R}` the function is real-valued. With `j_0(0) = 1`, `j_n(0) = 0` for `n>0` and `n \ne 0`, `j_n(0) = -\infty` for even `n<0`, `j_n(0) =` NaN for odd `n<0`, `j_n(-\infty) = j_n(\infty) = 0`, we have the following explicit versions of Rayleigh's formula for `x \ne 0` and `n = 0,1,2,3`:

    .. math:: j_0(x) = \frac{\sin x}{x}.

    .. math:: j_1(x) = \frac{\sin x}{x^2} - \frac{\cos x}{x}.

    .. math:: j_2(x) = y_{-1}(x) = \left(\frac{3}{x^2} - 1\right) \frac{\sin x}{x} - \frac{3\cos x}{x^2}.

    .. math:: j_3(x) = y_{-2}(x)  = \left(\frac{15}{x^3} - \frac{6}{x}\right) \frac{\sin x}{x} - \left(\frac{15}{x^2} - 1\right) \frac{\cos x}{x}.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = -2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_jn(n, x, scaled=False)))
        fpm:  -0.0103715220821118
        mpm:  -0.0103715220821117511655575969569040964760294390274729128966641434836505083193967299348680215
        dpm:  -0.0103715220821117511655575969569040964760294390274729128966641434836505083193967299348680215
        gpm:  -0.010371522082111751165557596956904096476029439027472912896664143483650508319396729934868021501
        apm: [-0.0103715220821117511655575969569040964760294390274729128966641434836505083193967299348680215 +/- 7.47e-92]
     math53:  -0.0103715220821118
      sreal:  -0.01037152
      dreal:  -0.0103715220821117
      ereal:  -0.010371522082111751166
      qreal:  -0.0103715220821117511655575969569041
      oreal:  -0.010371522082111751165557596956904096476029439027472912896664143483650511
      mreal:  -0.0103715220821117511655575969569040964760294390274729128966641434836505083193967299348680215
     sflint:  -0.01037152
     dflint:  -0.0103715220821118
     eflint:  -0.010371522082111751166
     qflint:  -0.0103715220821117511655575969569041
     oflint:  -0.010371522082111751165557596956904096476029439027472912896664143483650508
     mflint:  -0.0103715220821117511655575969569040964760294390274729128966641434836505083193967299348680215
     aflint: [-0.010371522082111751165557596956904096476029439027472912896664143483650508319396729934868021 +/- 5.39e-91]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_jn(n, x, scaled=False)))
        fpm:  (-0.125768109998084, -0.150716430194426)
        mpm:  (-0.1257681099980838494826881489858193830171, -0.1507164301944257054076586858082813167879)
    cmath53:  (-0.125768109998084, -0.150716430194426)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_bessel_jn(n, x, scaled=False))))
        fpm:  -0.125768109998084
        mpm:  -0.125768109998083849482688148985819383017095423190238628362848687732597835014944241114922991
        dpm:  -0.125768109998083849482688148985819383017095423190238628362848687732597835014944241114922991
        gpm:  -0.12576810999808384948268814898581938301709542319023862836284868773259783501494424111492299101
        apm: [-0.1257681099980838494826881489858193830170954231902386283628486877325978350149442411149230 +/- 2.59e-89]
    cmath53:  -0.125768109998084
    sflintc:  -0.1257681
    dflintc:  -0.125768109998084
    eflintc:  -0.12576810999808384944
    qflintc:  -0.125768109998083849482688148985819
    oflintc:  -0.12576810999808384948268814898581938301709542319023862836284868773259783
    mflintc:  -0.125768109998083849482688148985819383017095423190238628362848687732597835014944241114922991
    aflintc: [-0.1257681099980838494826881489858193830170954231902386283628486877325978350149442411149230 +/- 5.79e-89]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_bessel_jn(n, x, scaled=False))))
        fpm:  -0.150716430194426
        mpm:  -0.150716430194425705407658685808281316787867120205746521676084902811808659863227147771750148
        dpm:  -0.150716430194425705407658685808281316787867120205746521676084902811808659863227147771750148
        gpm:  -0.15071643019442570540765868580828131678786712020574652167608490281180865986322714777175014801
        apm: [-0.1507164301944257054076586858082813167878671202057465216760849028118086598632271477717501 +/- 6.51e-89]
    cmath53:  -0.150716430194426
    sflintc:  -0.1507164
    dflintc:  -0.150716430194426
    eflintc:  -0.15071643019442570541
    qflintc:  -0.150716430194425705407658685808281
    oflintc:  -0.15071643019442570540765868580828131678786712020574652167608490281180866
    mflintc:  -0.150716430194425705407658685808281316787867120205746521676084902811808659863227147771750148
    aflintc: [-0.150716430194425705407658685808281316787867120205746521676084902811808659863227147771750 +/- 2.00e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D01a_SphBesselJnReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D01b_SphBesselJnCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C04_SphericalBessel/D01_SphBesselJn.cs>`__. 










|newpage|


.. _rst_mpm_bessel_yn: 

Spherical Bessel function of the second kind, `y_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_yn(n, x, scaled=False)

    Returns `y_n(x)`, the Spherical Bessel function of the second kind. 

    If *scaled* is *True*, then `y_{\nu}(x) \cdot \exp(-|\Im(x)|)` is returned, which means that for purely  real `x` just `y_{\nu}(x)` is returned. 

    See also  Wikipedia :cite:p:`WikipediaFun143`, MathWorld :cite:p:`WolframFun143b`, NIST :cite:p:`DLMFun143`, BoostMath :cite:p:`BoostFun143`, :cite:t:`Ehrhardt2018` (3.1.6.2).

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 



    This function is traditionally defined as `\displaystyle y_n(x) = \sqrt{\tfrac{1}{2}\pi/x} Y_{n+\tfrac{1}{2}}(x)`, where `Y_n(x)` is a Bessel function of the second kind and, in general, `n` and `x` are complex numbers. 

    In XlCalcNet, the definition `\displaystyle y_n(x) = \sqrt{\tfrac{1}{2}\pi} \frac{1}{\sqrt{x}} Y_{n+\tfrac{1}{2}}(x)` is used instead, which gives identical results for `\Re(x) \ge 0`, but differs from the "traditional version" along the branch cut of the square root function. This ensures that results for real input and complex input with zero imaginary part are the same. It also ensures that the general definition for complex `n` and complex `x` agrees with the results from  Rayleigh's formula `\displaystyle y_n(x) = -(-x)^n \left(\frac{1}{x}\frac{d}{dx}\right)^n \frac{\cos x}{x}` for integer `n \ge 0` and real or complex `x \ne 0`. Given `y_0(x)` and `y_1(x)`, Rayleigh's formula can also be computed recursively as `\displaystyle y_n(x) = \frac{2n+1}{x} y_{n-1}(x) -  y_{n-2}(x)` for `n \ge 2`.


    With `y_n(0) =` NaN for even `n`, `y_n(0) = -\infty` for odd `n`, `y_n(-\infty) = y_n(\infty) = 0`, we have the following explicit versions of Rayleigh's formula for `x \ne 0` and `n = 0,1,2,3`:


    .. math:: y_0(x) = -j_{-1}(x) = -\frac{\cos x}{x},

    .. math:: y_1(x) = j_{-2}(x)  = -\frac{\cos x}{x^2} - \frac{\sin x}{x},

    .. math:: y_2(x) = -j_{-3}(x) = \left(-\frac{3}{x^2} + 1\right) \frac{\cos x}{x} - \frac{3\sin x}{x^2},

    .. math:: y_3(x) = j_{-4}(x)  = \left(-\frac{15}{x^3} + \frac{6}{x}\right) \frac{\cos x}{x} - \left(\frac{15}{x^2} - 1\right) \frac{\sin x}{x}.


    We extend this to negative integer indices using `y_{-n}(x) = (-1)^{n+1} j_{n+1}(x)` for `n > 0`, where `j_n(x)` is the spherical Bessel function of the first kind. We also have `y_n(-x) = (-1)^{n+1} y_{n}(x)` for `x > 0`. Therefore we can calculate `y_n(x)` for any `n \in \mathbb{Z}` and `x \in \mathbb{R}` without resorting to complex functions, using the general definition with `n \ge 0, x \ge 0`, always obtaining a real result.






An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = -2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_yn(n, x, scaled=False)))
        fpm:  -3.77254209230478
        mpm:  -3.77254209230478368531331197597234814520669101593274908655450446763883251904386705739763553
        dpm:  -3.77254209230478368531331197597234814520669101593274908655450446763883251904386705739763553
        gpm:  -3.7725420923047836853133119759723481452066910159327490865545044676388325190438670573976355301
        apm: [-3.7725420923047836853133119759723481452066910159327490865545044676388325190438670573976355 +/- 4.08e-89]
     math53:  -3.77254209230478
      sreal:  -3.772542
      dreal:  -3.77254209230478
      ereal:  -3.772542092304783685
      qreal:  -3.77254209230478368531331197597235
      oreal:  -3.7725420923047836853133119759723481452066910159327490865545044676388325
      mreal:  -3.77254209230478368531331197597234814520669101593274908655450446763883251904386705739763553
     sflint:  -3.772542
     dflint:  -3.77254209230478
     eflint:  -3.772542092304783685
     qflint:  -3.77254209230478368531331197597235
     oflint:  -3.7725420923047836853133119759723481452066910159327490865545044676388325
     mflint:  -3.77254209230478368531331197597234814520669101593274908655450446763883251904386705739763553
     aflint: [-3.7725420923047836853133119759723481452066910159327490865545044676388325190438670573976355 +/- 5.11e-89]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_yn(n, x, scaled=False)))
        fpm:  (-0.0993284385361067, 0.0460599186199454)
        mpm:  (-0.0993284385361067288670599566581893262604, 0.04605991861994540026749817463792266772967)
    cmath53:  (-0.0993284385361066, 0.0460599186199458)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_bessel_yn(n, x, scaled=False))))
        fpm:  -0.0993284385361067
        mpm:  -0.0993284385361067288670599566581893262604145989965203006159548699764146635083987794360373668
        dpm:  -0.0993284385361067288670599566581893262604145989965203006159548699764146635083987794360373668
        gpm:  -0.099328438536106728867059956658189326260414598996520300615954869976414663508398779436037366804
        apm: [-0.0993284385361067288670599566581893262604145989965203006159548699764146635083987794360374 +/- 4.60e-89]
    cmath53:  -0.0993284385361066
    sflintc:  -0.09932838
    dflintc:  -0.0993284385361067
    eflintc:  -0.09932843853610672881
    qflintc:  -0.0993284385361067288670599566581891
    oflintc:  -0.099328438536106728867059956658189326260414598996520300615954869976414664
    mflintc:  -0.0993284385361067288670599566581893262604145989965203006159548699764146635083987794360373662
    aflintc: [-0.0993284385361067288670599566581893262604145989965203006159548699764146635083987794360374 +/- 7.52e-89]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_bessel_yn(n, x, scaled=False))))
        fpm:  0.0460599186199454
        mpm:  0.0460599186199454002674981746379226677296567485088254801476905757888544458876337705649057335
        dpm:  0.0460599186199454002674981746379226677296567485088254801476905757888544458876337705649057335
        gpm:  0.046059918619945400267498174637922667729656748508825480147690575788854445887633770564905733501
        apm: [0.0460599186199454002674981746379226677296567485088254801476905757888544458876337705649057 +/- 4.53e-89]
    cmath53:  0.0460599186199458
    sflintc:  0.04605998
    dflintc:  0.0460599186199454
    eflintc:  0.046059918619945400323
    qflintc:  0.0460599186199454002674981746379229
    oflintc:  0.046059918619945400267498174637922667729656748508825480147690575788854446
    mflintc:  0.0460599186199454002674981746379226677296567485088254801476905757888544458876337705649057341
    aflintc: [0.0460599186199454002674981746379226677296567485088254801476905757888544458876337705649057 +/- 7.12e-89]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D02a_SphBesselYnReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D02b_SphBesselYnCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C04_SphericalBessel/D02_SphBesselYn.cs>`__. 








|newpage|


First derivative of the spherical Bessel function of the first kind, `j'_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_jn_prime(n, x, scaled=False)

    Returns `j'_n(x)`, the first derivative (with respect to `x`) of `j_n(x)`, the spherical Bessel function of the first kind. 

    If *scaled* is *True*, then `j'_{\nu}(x) \cdot \exp(-|\Im(x)|)` is returned, which means that for purely  real `x` just `j'_{\nu}(x)` is returned.  

    See also  Wikipedia :cite:p:`WikipediaFun143`, MathWorld :cite:p:`WolframFun143a`, NIST :cite:p:`DLMFun143`, BoostMath :cite:p:`BoostFun143`, :cite:t:`Ehrhardt2018` (3.1.6.1).

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 


    In all cases, the function is calculated as 

    `\displaystyle j'_n(x) = \frac{n j_{n-1}(x) - (n+1)j_{n+1}(x)}{2n+1}` for `|2n+1|>0.1` and `\displaystyle j'_n(x) = j_{n-1}(x) - \frac{n+1}{x} j_{n}(x)` otherwise.


    For `n \in \mathbb{Z}` and `x \in \mathbb{R}` the function is real-valued with  `j'_1(0) = 1/3`, `j'_n(0) = 0` for `n \ge 0` and `n \ne 1`, `j'_{-n}(0) = -\infty` for odd `n>0` and `j'_{-n}(0) =` NaN for even `n>0`. We also have `j_n(-\infty) = 0` and `y_n(\infty) = 0`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_jn_prime(n, x, scaled=False)))
        fpm:  0.0169661571818249
        mpm:  0.0169661571818248841340548279736114854080475011855977252298890041156098092317927073305077205
        dpm:  0.0169661571818248841340548279736114854080475011855977252298890041156098092317927073305077205
        gpm:  0.016966157181824884134054827973611485408047501185597725229889004115609809231792707330507720498
        apm: [0.016966157181824884134054827973611485408047501185597725229889004115609809231792707330507720 +/- 5.20e-91]
     math53:  0.0169661571818249
      sreal:  0.01696616
      dreal:  0.0169661571818249
      ereal:  0.016966157181824884136
      qreal:  0.0169661571818248841340548279736115
      oreal:  0.016966157181824884134054827973611485408047501185597725229889004115609814
      mreal:  0.0169661571818248841340548279736114854080475011855977252298890041156098092317927073305077205
     sflint:  0.01696616
     dflint:  0.0169661571818249
     eflint:  0.016966157181824884136
     qflint:  0.0169661571818248841340548279736115
     oflint:  0.016966157181824884134054827973611485408047501185597725229889004115609809
     mflint:  0.0169661571818248841340548279736114854080475011855977252298890041156098092317927073305077205
     aflint: [0.016966157181824884134054827973611485408047501185597725229889004115609809231792707330507720 +/- 6.38e-91]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_jn_prime(n, x, scaled=False)))
        fpm:  (0.534125965584427, -0.1975094894105)
        mpm:  (0.534125965584427293020268156480038936793, -0.1975094894105004482150031678003154354556)
    cmath53:  (0.534125965584427, -0.1975094894105)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_bessel_jn_prime(n, x, scaled=False))))
        fpm:  0.534125965584427
        mpm:  0.534125965584427293020268156480038936793005103523059888764147520723329235871234948726149669
        dpm:  0.534125965584427293020268156480038936793005103523059888764147520723329235871234948726149669
        gpm:  0.53412596558442729302026815648003893679300510352305988876414752072332923587123494872614966896
        apm: [0.5341259655844272930202681564800389367930051035230598887641475207233292358712349487261497 +/- 7.93e-89]
    cmath53:  0.534125965584427
    sflintc:  0.534126
    dflintc:  0.534125965584427
    eflintc:  0.53412596558442729304
    qflintc:  0.534125965584427293020268156480039
    oflintc:  0.53412596558442729302026815648003893679300510352305988876414752072332924
    mflintc:  0.534125965584427293020268156480038936793005103523059888764147520723329235871234948726149669
    aflintc: [0.534125965584427293020268156480038936793005103523059888764147520723329235871234948726150 +/- 4.83e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_bessel_jn_prime(n, x, scaled=False))))
        fpm:  -0.1975094894105
        mpm:  -0.197509489410500448215003167800315435455566167479783814533126144859972605258055690987267085
        dpm:  -0.197509489410500448215003167800315435455566167479783814533126144859972605258055690987267085
        gpm:  -0.197509489410500448215003167800315435455566167479783814533126144859972605258055690987267085
        apm: [-0.1975094894105004482150031678003154354555661674797838145331261448599726052580556909872671 +/- 5.97e-89]
    cmath53:  -0.1975094894105
    sflintc:  -0.1975094
    dflintc:  -0.1975094894105
    eflintc:  -0.19750948941050044815
    qflintc:  -0.197509489410500448215003167800315
    oflintc:  -0.19750948941050044821500316780031543545556616747978381453312614485997261
    mflintc:  -0.197509489410500448215003167800315435455566167479783814533126144859972605258055690987267084
    aflintc: [-0.197509489410500448215003167800315435455566167479783814533126144859972605258055690987267 +/- 2.20e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D03a_SphBesselJnRealPrime.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D03b_SphBesselJnCplxPrime.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C04_SphericalBessel/D03_SphBesselJnPrime.cs>`__. 











|newpage|


First derivative of the spherical Bessel function of the second kind, `y'_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_yn_prime(n, x, scaled=False)

    Returns `y'_n(x)`, the first derivative (with respect to `x`) of `y_n(x)`, the spherical Bessel function of the second kind. 

    If *scaled* is *True*, then `y'_{\nu}(x) \cdot \exp(-|\Im(x)|)` is returned, which means that for purely  real `x` just `y'_{\nu}(x)` is returned.  

    See also  Wikipedia :cite:p:`WikipediaFun143`, MathWorld :cite:p:`WolframFun143b`, NIST :cite:p:`DLMFun143`, BoostMath :cite:p:`BoostFun143`, :cite:t:`Ehrhardt2018` (3.1.6.2).

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 


    In all cases, the function is calculated as 

    `\displaystyle y'_n(x) = \frac{n y_{n-1}(x) - (n+1)y_{n+1}(x)}{2n+1}` for `|2n+1|>0.1` and `\displaystyle y'_n(x) = y_{n-1}(x) - \frac{n+1}{x} y_{n}(x)` otherwise.


    For `n \in \mathbb{Z}` and `x \in \mathbb{R}` the function is real-valued with  `y'_{-2}(0) = -1/3`, `y'_n(0) = 0` for `n < 0` and `n \ne -2`, `y'_{n}(0) = \infty` for even `n \ge 0` and `y'_{n}(0) =` NaN for odd `n>0`. We also have `y_n(-\infty) = 0` and `y_n(\infty) = 0`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_yn_prime(n, x, scaled=False)))
        fpm:  7.05476675032966
        mpm:  7.0547667503296613308106150163855311944807169539026857535919797981462995562379200681411576
        dpm:  7.0547667503296613308106150163855311944807169539026857535919797981462995562379200681411576
        gpm:  7.0547667503296613308106150163855311944807169539026857535919797981462995562379200681411576005
        apm: [7.0547667503296613308106150163855311944807169539026857535919797981462995562379200681411576 +/- 3.63e-89]
     math53:  7.05476675032966
      sreal:  7.054766
      dreal:  7.05476675032966
      ereal:  7.0547667503296613302
      qreal:  7.05476675032966133081061501638553
      oreal:  7.0547667503296613308106150163855311944807169539026857535919797981462994
      mreal:  7.0547667503296613308106150163855311944807169539026857535919797981462995562379200681411576
     sflint:  7.054766
     dflint:  7.05476675032966
     eflint:  7.0547667503296613302
     qflint:  7.05476675032966133081061501638553
     oflint:  7.0547667503296613308106150163855311944807169539026857535919797981462995
     mflint:  7.0547667503296613308106150163855311944807169539026857535919797981462995562379200681411576
     aflint: [7.054766750329661330810615016385531194480716953902685753591979798146299556237920068141158 +/- 4.95e-88]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_yn_prime(n, x, scaled=False)))
        fpm:  (0.217672424217738, 0.0612462187183035)
        mpm:  (0.2176724242177381660392000477198392667642, 0.06124621871830352605141303347310390178786)
    cmath53:  (0.217672424217738, 0.061246218718304)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_bessel_yn_prime(n, x, scaled=False))))
        fpm:  0.217672424217738
        mpm:  0.217672424217738166039200047719839266764268353207910186622136284386144907122153652333608439
        dpm:  0.217672424217738166039200047719839266764268353207910186622136284386144907122153652333608439
        gpm:  0.21767242421773816603920004771983926676426835320791018662213628438614490712215365233360843899
        apm: [0.2176724242177381660392000477198392667642683532079101866221362843861449071221536523336084 +/- 6.39e-89]
    cmath53:  0.217672424217738
    sflintc:  0.2176723
    dflintc:  0.217672424217738
    eflintc:  0.21767242421773816589
    qflintc:  0.217672424217738166039200047719839
    oflintc:  0.21767242421773816603920004771983926676426835320791018662213628438614491
    mflintc:  0.217672424217738166039200047719839266764268353207910186622136284386144907122153652333608438
    aflintc: [0.217672424217738166039200047719839266764268353207910186622136284386144907122153652333608 +/- 5.25e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_bessel_yn_prime(n, x, scaled=False))))
        fpm:  0.0612462187183035
        mpm:  0.0612462187183035260514130334731039017878449244932816944522642012596141797920795161260028845
        dpm:  0.0612462187183035260514130334731039017878449244932816944522642012596141797920795161260028845
        gpm:  0.061246218718303526051413033473103901787844924493281694452264201259614179792079516126002884502
        apm: [0.0612462187183035260514130334731039017878449244932816944522642012596141797920795161260029 +/- 3.91e-89]
    cmath53:  0.061246218718304
    sflintc:  0.0612463
    dflintc:  0.0612462187183035
    eflintc:  0.061246218718303526128
    qflintc:  0.0612462187183035260514130334731042
    oflintc:  0.06124621871830352605141303347310390178784492449328169445226420125961418
    mflintc:  0.0612462187183035260514130334731039017878449244932816944522642012596141797920795161260028853
    aflintc: [0.061246218718303526051413033473103901787844924493281694452264201259614179792079516126003 +/- 1.97e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D04a_SphBesselYnRealPrime.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D04b_SphBesselYnCplxPrime.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C04_SphericalBessel/D04_SphBesselYnPrime.cs>`__. 









|newpage|


Boost: Zeros `a_{n, m}` of the spherical Bessel function of the first kind: `j_{n}(a_{n, m})=0`
----------------------------------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_jn_zero(n, m)

    where ``ctx`` is ``math53`` or ``ctxboost``.


    For positive integers `n` and `m`, returns `a_{n, m}`, the `m`-th positive zero of the spherical Bessel function of the first kind `j_{n}(x)`.  


    See also  Wikipedia :cite:p:`WikipediaFun84`,  MathWorld :cite:p:`WolframFun141a`, NIST :cite:p:`DLMFun141`, BoostMath :cite:p:`BoostFun141`, Mpmath :cite:p:`MpmathFun141`.

    The function is calculated as `\displaystyle a_{n, m} = j_{n + \tfrac{1}{2}, m}`, where `j_{\nu, m}` is the `m`-th positive zero of the Bessel function of the first kind `J_{\nu}(x)`.


    See: https://dlmf.nist.gov/10.58



An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; m = 2; gui.setdps(90)
    >>> for ctx in gui.ctxlist_boost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_jn_zero(n, m)))
        fpm:  12.9665301727743
        mpm:  12.9665301727743445575483205579271837930135888938917716627609743441644716124498707155359937
        dpm:  12.9665301727743445575483205579271837930135888938917716627609743441644716124498707155359937
        gpm:  12.966530172774344557548320557927183793013588893891771662760974344164471612449870715535993699
        apm: [12.9665301727743445575483205579271837930135888938917716627609743441644716124498707155359937 +/- 2.56e-90]
     math53:  12.9665301727743
      sreal:  12.96653
      dreal:  12.9665301727743
      ereal:  12.966530172774344557
      qreal:  12.9665301727743445575483205579272
      oreal:  12.966530172774344557548320557927183793013588893891771662760974344164472
      mreal:  12.9665301727743445575483205579271837930135888938917716627609743441644716124498707155359937




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D05a_SphBesselJnZero.py>`__,  and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C04_SphericalBessel/D05_SphBesselJnZero.cs>`__. 









|newpage|


Boost: Zeros `b_{n, m}` of the spherical Bessel function of the second kind: `y_{n}(b_{n, m})=0`
----------------------------------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_yn_zero(n, m)

    where ``ctx`` is ``math53`` or ``ctxboost``.


    For positive integers `n` and `m`, returns `b_{n, m}`, the `m`-th positive zero of the spherical Bessel function of the second kind `y_{n}(x)`.  


    Returns the zero of the spherical Bessel function of the second kind.  See also  Wikipedia :cite:p:`WikipediaFun85`,  MathWorld :cite:p:`WolframFun141b`, NIST :cite:p:`DLMFun141`, BoostMath :cite:p:`BoostFun141`, Mpmath :cite:p:`MpmathFun141a`.


    The function is calculated as `\displaystyle b_{n, m} = y_{n + \tfrac{1}{2}, m}`, where `y_{\nu, m}` is the `m`-th positive zero of the Bessel function of the first kind `Y_{\nu}(x)`.



    See https://dlmf.nist.gov/10.58



An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; m = 2; gui.setdps(90)
    >>> for ctx in gui.ctxlist_boost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_jn_zero(n, m)))
        fpm:  11.2064973381951
        mpm:  11.2064973381950850205640944306248190109173866201703554839991488224926535496699278627107343
        dpm:  11.2064973381950850205640944306248190109173866201703554839991488224926535496699278627107343
        gpm:  11.206497338195085020564094430624819010917386620170355483999148822492653549669927862710734299
        apm: [11.2064973381950850205640944306248190109173866201703554839991488224926535496699278627107343 +/- 2.76e-90]
     math53:  11.2064973381951
      sreal:  11.2065
      dreal:  11.2064973381951
      ereal:  11.20649733819508502
      qreal:  11.2064973381950850205640944306248
      oreal:  11.206497338195085020564094430624819010917386620170355483999148822492654
      mreal:  11.2064973381950850205640944306248190109173866201703554839991488224926535496699278627107343


      

The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C04_SphericalBessel/D06a_SphBesselYnZero.py>`__,  and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C04_SphericalBessel/D06_SphBesselYnZero.cs>`__. 






