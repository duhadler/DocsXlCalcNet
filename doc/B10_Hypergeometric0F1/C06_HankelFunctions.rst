

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Hankel functions
===============================================================================


Hankel function of the first kind `H^{(1)}_{\nu}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.hankel_h1(nu, x, scaled=False)

    where ``ctx`` is ``math53`` or ``ctxboost``.


    Returns the Hankel function of the first kind, defined as `\displaystyle H^{(1)}_{\nu}(x) = J_{\nu}(x) + i Y_{\nu}(x)`.

    If *scaled* is *True*, then `\displaystyle H^{(1)e}_{\nu}(x) = H^{(1)}_{\nu}(x) \cdot \exp(-i x)` is returned, except for a real ``ctx`` where just `\displaystyle H^{(1)}_{\nu}(x)` is returned.  

    If ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `\nu, x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `\nu, x \in \mathbb{C}` is accepted. 



    See also  Wikipedia :cite:p:`WikipediaFun142`, MathWorld :cite:p:`WolframFun142a`, NIST :cite:p:`DLMFun142`, BoostMath :cite:p:`BoostFun142`, Mpmath :cite:p:`MpmathFun142a`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(40)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.cplxctx.fmt(ctx.hankel_h1(nu, x, scaled=False)))
        fpm:  (0.0239004453102261, -3.13767826537971)
        mpm:  (0.02390044531022607781718241181284764644696, -3.137678265379708257076691766724110580898)
        dpm:  (0.02390044531022607781718241181284764644696, -3.137678265379708257076691766724110580898)
        gpm:  (0.02390044531022607781718241181284764644696, -3.13767826537970825707669176672411058089799)
        apm: ([0.023900445310226077817182411812847646447 +/- 1.07e-40], [-3.1376782653797082570766917667241105809 +/- 2.47e-38])
     math53:  (0.0239004453102261, -3.1376782653797)
      sreal:  (0.02390045, -3.137678)
      dreal:  (0.0239004453102261, -3.13767826537971)
      ereal:  (0.02390044531022607785, -3.1376782653797082568)
      qreal:  (0.0239004453102260778171824118128477, -3.13767826537970825707669176672411)
      oreal:  (0.023900445310226077817182411812847646446962291892034415965676329390551645, -3.1376782653797082570766917667241105808985669230644643225412487974389585)
      mreal:  (0.02390044531022607781718241181284764644685, -3.137678265379708257076691766724110580898)
     sflint:  (0.02390045, -3.137678)
     dflint:  (0.0239004453102261, -3.13767826537971)
     eflint:  (0.023900445310226077822, -3.1376782653797082566)
     qflint:  (0.0239004453102260778171824118128477, -3.13767826537970825707669176672411)
     oflint:  (0.023900445310226077817182411812847646446962291892034415965676329390551636, -3.1376782653797082570766917667241105808985669230644643225412487974389586)
     mflint:  (0.02390044531022607781718241181284764644698, -3.137678265379708257076691766724110580897)
     aflint: ([0.023900445310226077817182411812847646447 +/- 4.43e-40], [-3.137678265379708257076691766724110581 +/- 2.04e-37])



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hankel_h1(nu, x, scaled=False)))
        fpm:  (0.553513029400475, -0.458108538929633)
        mpm:  (0.5535130294004753451539866140802354202485, -0.4581085389296331657650782138772903708147)
    cmath53:  (0.553513029400475, -0.458108538929633)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.hankel_h1(nu, x, scaled=False))))
        fpm:  0.553513029400475
        mpm:  0.55351302940047534515398661408023542024849544473801961621508840815324296975360147862450677
        dpm:  0.55351302940047534515398661408023542024849544473801961621508840815324296975360147862450677
        gpm:  0.55351302940047534515398661408023542024849544473801961621508840815324296975360147862450677
        apm: [0.553513029400475345153986614080235420248495444738019616215088408153242969753601478624507 +/- 3.04e-88]
    cmath53:  0.553513029400475
    sflintc:  0.5535129
    dflintc:  0.553513029400475
    eflintc:  0.55351302940047534499
    qflintc:  0.553513029400475345153986614080235
    oflintc:  0.55351302940047534515398661408023542024849544473801961621508840815324297
    mflintc:  0.553513029400475345153986614080235420248495444738019616215088408153242969753601478624506769
    aflintc: [0.553513029400475345153986614080235420248495444738019616215088408153242969753601478624507 +/- 4.14e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hankel_h1(nu, x, scaled=False))))
        fpm:  -0.458108538929633
        mpm:  -0.458108538929633165765078213877290370814666322386327948328279538248955839395945515581769005
        dpm:  -0.458108538929633165765078213877290370814666322386327948328279538248955839395945515581769005
        gpm:  -0.458108538929633165765078213877290370814666322386327948328279538248955839395945515581769005
        apm: [-0.458108538929633165765078213877290370814666322386327948328279538248955839395945515581769 +/- 1.07e-88]
    cmath53:  -0.458108538929633
    sflintc:  -0.4581086
    dflintc:  -0.458108538929633
    eflintc:  -0.45810853892963316578
    qflintc:  -0.45810853892963316576507821387729
    oflintc:  -0.45810853892963316576507821387729037081466632238632794832827953824895584
    mflintc:  -0.458108538929633165765078213877290370814666322386327948328279538248955839395945515581769005
    aflintc: [-0.458108538929633165765078213877290370814666322386327948328279538248955839395945515581769 +/- 2.70e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C06_HankelFunctions/D01a_HankelH1Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C06_HankelFunctions/D01b_HankelH1Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C06_HankelFunctions/D01_HankelH1.cs>`__. 






|newpage|

Hankel function of the second kind `H^{(2)}_{\nu}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.hankel_h2(nu, x, scaled=False)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Hankel function of the second kind, defined as `\displaystyle H^{(2)}_{\nu}(x) = J_{\nu}(x) - i Y_{\nu}(x)`.
    
    If *scaled* is *True*, then `\displaystyle H^{(2)e}_{\nu}(x) = H^{(2)}_{\nu}(x) \cdot \exp(i x)` is returned, except for a real ``ctx`` where just `\displaystyle H^{(2)}_{\nu}(x)` is returned.  

    If ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `\nu, x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `\nu \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `\nu, x \in \mathbb{C}` is accepted. 


    See also  Wikipedia :cite:p:`WikipediaFun142`, MathWorld :cite:p:`WolframFun142b`, NIST :cite:p:`DLMFun142`, BoostMath :cite:p:`BoostFun142`, Mpmath :cite:p:`MpmathFun142b`.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = 5.1; x = 2.7; gui.setdps(40)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.cplxctx.fmt(ctx.hankel_h2(nu, x, scaled=False)))
        fpm:  (0.0239004453102261, 3.13767826537971)
        mpm:  (0.02390044531022607781718241181284764644696, 3.137678265379708257076691766724110580898)
        dpm:  (0.02390044531022607781718241181284764644696, 3.137678265379708257076691766724110580898)
        gpm:  (0.02390044531022607781718241181284764644696, 3.13767826537970825707669176672411058089799)
        apm: ([0.023900445310226077817182411812847646447 +/- 1.07e-40], [3.1376782653797082570766917667241105809 +/- 2.47e-38])
     math53:  (0.0239004453102261, 3.1376782653797)
      sreal:  (0.02390045, 3.137678)
      dreal:  (0.0239004453102261, 3.13767826537971)
      ereal:  (0.02390044531022607785, 3.1376782653797082568)
      qreal:  (0.0239004453102260778171824118128477, 3.13767826537970825707669176672411)
      oreal:  (0.023900445310226077817182411812847646446962291892034415965676329390551645, 3.1376782653797082570766917667241105808985669230644643225412487974389585)
      mreal:  (0.02390044531022607781718241181284764644685, 3.137678265379708257076691766724110580898)
     sflint:  (0.02390045, 3.137678)
     dflint:  (0.0239004453102261, 3.13767826537971)
     eflint:  (0.023900445310226077822, 3.1376782653797082566)
     qflint:  (0.0239004453102260778171824118128477, 3.13767826537970825707669176672411)
     oflint:  (0.023900445310226077817182411812847646446962291892034415965676329390551636, 3.1376782653797082570766917667241105808985669230644643225412487974389586)
     mflint:  (0.02390044531022607781718241181284764644698, 3.137678265379708257076691766724110580897)
     aflint: ([0.023900445310226077817182411812847646447 +/- 4.43e-40], [-3.137678265379708257076691766724110581 +/- 2.04e-37])



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hankel_h2(nu, x, scaled=False)))
        fpm:  (-0.039472912472708, 0.589270222079381)
        mpm:  (-0.03947291247270798345360409154872685478406, 0.5892702220793809979677982801612831474944)
    cmath53:  (-0.0394729124727087, 0.58927022207938)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.hankel_h2(nu, x, scaled=False))))
        fpm:  -0.039472912472708
        mpm:  -0.0394729124727079834536040915487268547840164986158937292380015883370184365691027694706895519
        dpm:  -0.0394729124727079834536040915487268547840164986158937292380015883370184365691027694706895519
        gpm:  -0.039472912472707983453604091548726854784016498615893729238001588337018436569102769470689551901
        apm: [-0.039472912472707983453604091548726854784016498615893729238001588337018436569102769470690 +/- 5.18e-88]
    cmath53:  -0.0394729124727087
    sflintc:  -0.03947315
    dflintc:  -0.039472912472708
    eflintc:  -0.039472912472707983668
    qflintc:  -0.0394729124727079834536040915487276
    oflintc:  -0.039472912472707983453604091548726854784016498615893729238001588337018436
    mflintc:  -0.0394729124727079834536040915487268547840164986158937292380015883370184365691027694706895543
    aflintc: [-0.039472912472707983453604091548726854784016498615893729238001588337018436569102769470690 +/- 6.25e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> nu = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hankel_h2(nu, x, scaled=False))))
        fpm:  0.589270222079381
        mpm:  0.589270222079380997967798280161283147494409275011223163214134066587805977018790393845889366
        dpm:  0.589270222079380997967798280161283147494409275011223163214134066587805977018790393845889366
        gpm:  0.58927022207938099796779828016128314749440927501122316321413406658780597701879039384588936605
        apm: [0.589270222079380997967798280161283147494409275011223163214134066587805977018790393845889 +/- 4.67e-88]
    cmath53:  0.58927022207938
    sflintc:  0.5892701
    dflintc:  0.589270222079381
    eflintc:  0.5892702220793809978
    qflintc:  0.589270222079380997967798280161283
    oflintc:  0.58927022207938099796779828016128314749440927501122316321413406658780598
    mflintc:  0.589270222079380997967798280161283147494409275011223163214134066587805977018790393845889364
    aflintc: [0.589270222079380997967798280161283147494409275011223163214134066587805977018790393845889 +/- 6.31e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C06_HankelFunctions/D02a_HankelH2Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C06_HankelFunctions/D02b_HankelH2Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C06_HankelFunctions/D02_HankelH2.cs>`__. 










|newpage|

Spherical Hankel function of the first kind, `h^{(1)}_{\nu}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sph_hankel_h1(n, x, scaled=False)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the spherical Hankel function of the first kind, defined as `\displaystyle  h^{(1)}_{n}(x) = \sqrt{\tfrac{1}{2}\pi} \frac{1}{\sqrt{x}} H^{(1)}_{\nu}(x)= j_{\nu}(x) + i y_{\nu}(x)`.

    If *scaled* is *True*, then `\displaystyle h^{(1)e}_{n}(x) = \sqrt{\tfrac{1}{2}\pi} \frac{1}{\sqrt{x}} H^{(1)e}_{\nu}(x)` is returned.


    See also  Wikipedia :cite:p:`WikipediaFun144`, MathWorld :cite:p:`WolframFun144`, NIST :cite:p:`DLMFun144`, BoostMath :cite:p:`BoostFun144`.

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(40)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.cplxctx.fmt(ctx.sph_hankel_h1(n, x, scaled=False)))
        fpm:  (0.0103715220821118, -3.77254209230478)
        mpm:  (0.01037152208211175116555759695690409647603, -3.772542092304783685313311975972348145207)
        dpm:  (0.01037152208211175116555759695690409647603, -3.772542092304783685313311975972348145207)
        gpm:  (0.01037152208211175116555759695690409647603, -3.77254209230478368531331197597234814520702)
        apm: ([0.01037152208211175116555759695690409647603 +/- 5.20e-42], [-3.77254209230478368531331197597234814521 +/- 4.60e-39])
     math53:  (0.0103715220821118, -3.77254209230478)
      sreal:  (0.01037152, -3.772542)
      dreal:  (0.0103715220821117, -3.77254209230478)
      ereal:  (0.010371522082111751166, -3.772542092304783685)
      qreal:  (0.0103715220821117511655575969569041, -3.77254209230478368531331197597235)
      oreal:  (0.010371522082111751165557596956904096476029439027472912896664143483650511, -3.7725420923047836853133119759723481452066910159327490865545044676388325)
      mreal:  (0.01037152208211175116555759695690409647603, -3.772542092304783685313311975972348145206)
     sflint:  (0.01037152, -3.772542)
     dflint:  (0.0103715220821118, -3.77254209230478)
     eflint:  (0.010371522082111751166, -3.772542092304783685)
     qflint:  (0.0103715220821117511655575969569041, -3.77254209230478368531331197597235)
     oflint:  (0.010371522082111751165557596956904096476029439027472912896664143483650508, -3.7725420923047836853133119759723481452066910159327490865545044676388325)
     mflint:  (0.01037152208211175116555759695690409647603, -3.772542092304783685313311975972348145206)
     aflint: ([0.0103715220821117511655575969569040964760 +/- 4.43e-41], [-3.77254209230478368531331197597234814520 +/- 9.82e-39])



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_hankel_h1(n, x, scaled=False)))
        fpm:  (-0.171828028618029, -0.250044868730532)
        mpm:  (-0.1718280286180292497501863236237420507468, -0.2500448687305324342747186424664706430483)
    cmath53:  (-0.171828028618029, -0.250044868730532)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_hankel_h1(n, x, scaled=False))))
        fpm:  -0.171828028618029
        mpm:  -0.171828028618029249750186323623742050746752171699064108510539263521452280902578011679828725
        dpm:  -0.171828028618029249750186323623742050746752171699064108510539263521452280902578011679828725
        gpm:  -0.171828028618029249750186323623742050746752171699064108510539263521452280902578011679828725
        apm: [-0.1718280286180292497501863236237420507467521716990641085105392635214522809025780116798287 +/- 5.27e-89]
    cmath53:  -0.171828028618029
    sflintc:  -0.171828
    dflintc:  -0.171828028618029
    eflintc:  -0.17182802861802924977
    qflintc:  -0.171828028618029249750186323623742
    oflintc:  -0.17182802861802924975018632362374205074675217169906410851053926352145228
    mflintc:  -0.171828028618029249750186323623742050746752171699064108510539263521452280902578011679828725
    aflintc: [-0.171828028618029249750186323623742050746752171699064108510539263521452280902578011679829 +/- 3.62e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_hankel_h1(n, x, scaled=False))))
        fpm:  -0.250044868730532
        mpm:  -0.250044868730532434274718642466470643048281719202266822292039772788223323371625927207787515
        dpm:  -0.250044868730532434274718642466470643048281719202266822292039772788223323371625927207787515
        gpm:  -0.25004486873053243427471864246647064304828171920226682229203977278822332337162592720778751503
        apm: [-0.2500448687305324342747186424664706430482817192022668222920397727882233233716259272077875 +/- 4.31e-89]
    cmath53:  -0.250044868730532
    sflintc:  -0.2500448
    dflintc:  -0.250044868730532
    eflintc:  -0.25004486873053243423
    qflintc:  -0.25004486873053243427471864246647
    oflintc:  -0.25004486873053243427471864246647064304828171920226682229203977278822332
    mflintc:  -0.250044868730532434274718642466470643048281719202266822292039772788223323371625927207787514
    aflintc: [-0.250044868730532434274718642466470643048281719202266822292039772788223323371625927207788 +/- 5.79e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C06_HankelFunctions/D03a_SphHankelH1Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C06_HankelFunctions/D03b_SphHankelH1Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C06_HankelFunctions/D03_SphHankelH1.cs>`__. 








|newpage|

Spherical Hankel function of the second kind, `h^{(2)}_{\nu}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sph_hankel_h2(n, x, scaled=False)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the spherical Hankel function of the first kind, defined as `\displaystyle  h^{(2)}_{n}(x) = \sqrt{\tfrac{1}{2}\pi} \frac{1}{\sqrt{x}} H^{(2)}_{\nu}(x)= j_{\nu}(x) - i y_{\nu}(x)`.

    If *scaled* is *True*, then `\displaystyle h^{(2)e}_{n}(x) = \sqrt{\tfrac{1}{2}\pi} \frac{1}{\sqrt{x}} H^{(2)e}_{\nu}(x)` is returned.


    See also  Wikipedia :cite:p:`WikipediaFun144`, MathWorld :cite:p:`WolframFun144`, NIST :cite:p:`DLMFun144`, BoostMath :cite:p:`BoostFun144`.

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(40)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.cplxctx.fmt(ctx.sph_hankel_h2(n, x, scaled=False)))
        fpm:  (0.0103715220821118, -3.77254209230478)
        mpm:  (0.01037152208211175116555759695690409647603, 3.772542092304783685313311975972348145207)
        dpm:  (0.01037152208211175116555759695690409647603, -3.772542092304783685313311975972348145207)
        gpm:  (0.01037152208211175116555759695690409647603, -3.77254209230478368531331197597234814520702)
        apm: ([0.01037152208211175116555759695690409647603 +/- 5.20e-42], [3.77254209230478368531331197597234814521 +/- 4.60e-39])
     math53:  (0.0103715220821118, 3.77254209230478)
      sreal:  (0.01037152, 3.772542)
      dreal:  (0.0103715220821117, 3.77254209230478)
      ereal:  (0.010371522082111751166, 3.772542092304783685)
      qreal:  (0.0103715220821117511655575969569041, 3.77254209230478368531331197597235)
      oreal:  (0.010371522082111751165557596956904096476029439027472912896664143483650511, 3.7725420923047836853133119759723481452066910159327490865545044676388325)
      mreal:  (0.01037152208211175116555759695690409647603, 3.772542092304783685313311975972348145206)
     sflint:  (0.01037152, 3.772542)
     dflint:  (0.0103715220821118, 3.77254209230478)
     eflint:  (0.010371522082111751166, 3.772542092304783685)
     qflint:  (0.0103715220821117511655575969569041, 3.77254209230478368531331197597235)
     oflint:  (0.010371522082111751165557596956904096476029439027472912896664143483650508, 3.7725420923047836853133119759723481452066910159327490865545044676388325)
     mflint:  (0.01037152208211175116555759695690409647603, 3.772542092304783685313311975972348145206)
     aflint: ([0.0103715220821117511655575969569040964760 +/- 4.43e-41], [-3.77254209230478368531331197597234814520 +/- 9.82e-39])



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_hankel_h2(n, x, scaled=False)))
        fpm:  (-0.0797081913781384, -0.051387991658319)
        mpm:  (-0.07970819137813844921518997434789671528742, -0.05138799165831897654059872915009199052747)
    cmath53:  (-0.0797081913781378, -0.0513879916583191)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_hankel_h2(n, x, scaled=False))))
        fpm:  -0.0797081913781384
        mpm:  -0.0797081913781384492151899743478967152874386746814131482151581119437433891273104705500172577
        dpm:  -0.0797081913781384492151899743478967152874386746814131482151581119437433891273104705500172577
        gpm:  -0.079708191378138449215189974347896715287438674681413148215158111943743389127310470550017257705
        apm: [-0.0797081913781384492151899743478967152874386746814131482151581119437433891273104705500173 +/- 7.12e-89]
    cmath53:  -0.0797081913781378
    sflintc:  -0.07970809
    dflintc:  -0.0797081913781384
    eflintc:  -0.079708191378138449123
    qflintc:  -0.0797081913781384492151899743478964
    oflintc:  -0.079708191378138449215189974347896715287438674681413148215158111943743389
    mflintc:  -0.0797081913781384492151899743478967152874386746814131482151581119437433891273104705500172566
    aflintc: [-0.079708191378138449215189974347896715287438674681413148215158111943743389127310470550017 +/- 3.40e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_hankel_h2(n, x, scaled=False))))
        fpm:  -0.051387991658319
        mpm:  -0.0513879916583189765405987291500919905274525212092262210601300328353939963548283683357127811
        dpm:  -0.0513879916583189765405987291500919905274525212092262210601300328353939963548283683357127811
        gpm:  -0.051387991658318976540598729150091990527452521209226221060130032835393996354828368335712781101
        apm: [-0.0513879916583189765405987291500919905274525212092262210601300328353939963548283683357128 +/- 4.76e-89]
    cmath53:  -0.0513879916583191
    sflintc:  -0.05138806
    dflintc:  -0.051387991658319
    eflintc:  -0.051387991658318976603
    qflintc:  -0.0513879916583189765405987291500922
    oflintc:  -0.051387991658318976540598729150091990527452521209226221060130032835393996
    mflintc:  -0.0513879916583189765405987291500919905274525212092262210601300328353939963548283683357127818
    aflintc: [-0.051387991658318976540598729150091990527452521209226221060130032835393996354828368335713 +/- 3.08e-88]



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C06_HankelFunctions/D04a_SphHankelH2Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C06_HankelFunctions/D04b_SphHankelH2Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C06_HankelFunctions/D04_SphHankelH2.cs>`__. 




