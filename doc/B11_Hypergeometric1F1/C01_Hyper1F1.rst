

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />






Hypergeometric Functions `\,_1F_1` (Kummer) and `U` (Tricomi)
===============================================================================






Kummer's Confluent Hypergeometric Function `{}_1F_1(a,b;x)`
------------------------------------------------------------------------------------------

.. method:: ctx.hyperg_1f1(a, b, x)

    Returns `\displaystyle {}_1F_1(a,b;x)`, the confluent hypergeometric function of the first kind, where `b \ne 0,-1,-2,\ldots`.

    See also  Wikipedia :cite:p:`WikipediaFun91`, MathWorld :cite:p:`WolframFun91`, NIST :cite:p:`DLMFun91`,  BoostMath :cite:p:`BoostFun91`, :cite:t:`Ehrhardt2018` (3.8.3), :cite:t:`AbramowitzFun91`, Flint :cite:p:`FlintFun90`, Flint :cite:p:`FlintFun90a`, Mpmath :cite:p:`MpmathFun91`. 

    Here `a, b` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `a,b \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `a, b \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `a, b, x \in \mathbb{C}` is accepted. 


    The function is defined as `\displaystyle {}_1F_1(a,b;x) = \sum_{k=0}^\infty\frac{(a)_k}{(b)_k} \frac{z^k}{k!}`.



    |01a_TestHypergeom1F1_re| `\quad` |01b_TestHypergeom1F1_im| `\quad` |01c_TestHypergeom1F1_abs|

    .. |01a_TestHypergeom1F1_re| image:: ../_static/ExplicitSurfaces/Cplx1F1/01a_TestHypergeom1F1_re.3D.xml.jpg
       :width: 30 %

    .. |01b_TestHypergeom1F1_im| image:: ../_static/ExplicitSurfaces/Cplx1F1/01b_TestHypergeom1F1_im.3D.xml.jpg
       :width: 30 %

    .. |01c_TestHypergeom1F1_abs| image:: ../_static/ExplicitSurfaces/Cplx1F1/01c_TestHypergeom1F1_abs.3D.xml.jpg
       :width: 30 %

       

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.






An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; b = 2.7; x = 1.3; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_1f1(a, b, x)))
        fpm:  8.98942175782942
        mpm:  8.98942175782941528598329378083466559111282173140626014421874435226211517496469860724020926
        dpm:  8.98942175782941528598329378083466559111282173140626014421874435226211517496469860724020926
        gpm:  8.98942175782941528598329378083466559111282173140626014421874435226211517496469860724020926
        apm: [8.989421757829415285983293780834665591112821731406260144218744352262115174964698607240209 +/- 9.32e-88]
     math53:  8.98942175782941
      sreal:  8.989421
      dreal:  8.98942175782942
      ereal:  8.9894217578294152863
      qreal:  8.98942175782941528598329378083466
      oreal:  8.9894217578294152859832937808346655911128217314062601442187443522621153
      mreal:  8.98942175782941528598329378083466559111282173140626014421874435226211517496469860724020924
     sflint:  8.989421
     dflint:  8.98942175782941
     eflint:  8.9894217578294152845
     qflint:  8.98942175782941528598329378083466
     oflint:  8.9894217578294152859832937808346655911128217314062601442187443522621151
     mflint:  8.98942175782941528598329378083466559111282173140626014421874435226211517496469860724020922
     aflint: [8.98942175782941528598329378083466559111282173140626014421874435226211517496469860724021 +/- 3.42e-87]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = 2.7; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_1f1(a, b, x)))
        fpm:  (-1.26265135733387, 0.714595229722949)
        mpm:  (-1.262651357333871172831654174014904638046, 0.7145952297229490165812035440634853476471)
    cmath53:  (-1.26265135733387, 0.714595229722949)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.hyperg_1f1(a, b, x))))
        fpm:  -1.26265135733387
        mpm:  -1.26265135733387117283165417401490463804577789563601028546031857745089972627539223319181443
        dpm:  -1.26265135733387117283165417401490463804577789563601028546031857745089972627539223319181443
        gpm:  -1.26265135733387117283165417401490463804577789563601028546031857745089972627539223319181443
        apm: [-1.262651357333871172831654174014904638045777895636010285460318577450899726275392233191814 +/- 5.43e-88]
    cmath53:  -1.26265135733387
    sflintc:  -1.262651
    dflintc:  -1.26265135733387
    eflintc:  -1.2626513573338711729
    qflintc:  -1.2626513573338711728316541740149
    oflintc:  -1.2626513573338711728316541740149046380457778956360102854603185774508997
    mflintc:  -1.26265135733387117283165417401490463804577789563601028546031857745089972627539223319181443
    aflintc: [-1.262651357333871172831654174014904638045777895636010285460318577450899726275392233191814 +/- 8.26e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hyperg_1f1(a, b, x))))
        fpm:  0.714595229722949
        mpm:  0.714595229722949016581203544063485347647129233644979265183735214996686716488327307949061172
        dpm:  0.714595229722949016581203544063485347647129233644979265183735214996686716488327307949061172
        gpm:  0.71459522972294901658120354406348534764712923364497926518373521499668671648832730794906117196
        apm: [0.714595229722949016581203544063485347647129233644979265183735214996686716488327307949061 +/- 2.48e-88]
    cmath53:  0.714595229722949
    sflintc:  0.7145951
    dflintc:  0.714595229722949
    eflintc:  0.71459522972294901643
    qflintc:  0.714595229722949016581203544063485
    oflintc:  0.7145952297229490165812035440634853476471292336449792651837352149966867
    mflintc:  0.714595229722949016581203544063485347647129233644979265183735214996686716488327307949061165
    aflintc: [0.714595229722949016581203544063485347647129233644979265183735214996686716488327307949061 +/- 4.30e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D01a_Hyperg1F1Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D01b_Hyperg1F1Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C01_Hyper1F1/D01_Hyperg1F1.cs>`__. 







|newpage|

Regularized Kummer Confluent Hypergeometric Function, `{}_1\widetilde{F}_1(a,b;x)`
--------------------------------------------------------------------------------------------------

.. method:: ctx.hyperg_1f1r(a, b, x)

    Returns `\displaystyle {}_1\widetilde{F}_1(a,b;z)`, the regularized Kummer confluent hypergeometric function.

    See also   Wikipedia :cite:p:`WikipediaFun91`, MathWorld :cite:p:`WolframFun91a`, NIST :cite:p:`DLMFun91`,  BoostMath :cite:p:`BoostFun91`, :cite:t:`Ehrhardt2018` (3.8.4), :cite:t:`AbramowitzFun91`, Flint :cite:p:`FlintFun90`, Flint :cite:p:`FlintFun90a`, Mpmath :cite:p:`MpmathFun91`. 

    Here `a, b` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `a,b \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `a, b \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `a, b, x \in \mathbb{C}` is accepted. 


    We have `\displaystyle {}_1\widetilde{F}_1(a,b;z)  = \frac{1}{\Gamma(b)} {}_1F_1(a;b;z) = \mathbf{M}(a,b;x) = \frac{1}{\Gamma(b)} M(a;b;z)`, for `b \ne 0, -1, -2, \cdots`.
    
    If `b = 0, -1, -2, \cdots = -n`, the corresponding limit `\displaystyle {}_1\widetilde{F}_1(a,b;x)  =  \frac{(a)_{n+1}}{(n+1)!} x^{n+1} {}_1F_1(a+n+1,n+2;x)` is calculated.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; b = -2; x = 1.3; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_1f1r(a, b, x)))
        fpm:  876.989426044385
        mpm:  876.989426044384810391892967824953914395627298796862274790273390666343658622328439526522241
        dpm:  876.989426044384810391892967824953914395627298796862274790273390666343658622328439526522241
        gpm:  876.98942604438481039189296782495391439562729879686227479027339066634365862232843952652224106
        apm: [876.98942604438481039189296782495391439562729879686227479027339066634365862232843952652224 +/- 6.36e-87]
     math53:  876.989426044385
      sreal:  876.9902
      dreal:  876.989426044385
      ereal:  876.98942604438481058
      qreal:  876.989426044384810391892967824954
      oreal:  876.98942604438481039189296782495391439562729879686227479027339066634356
      mreal:  876.98942604438481039189296782495391439562729879686227479027339066634365862232843952652224
     sflint:  876.9892
     dflint:  876.989426044385
     eflint:  876.98942604438481019
     qflint:  876.989426044384810391892967824954
     oflint:  876.98942604438481039189296782495391439562729879686227479027339066634365
     mflint:  876.989426044384810391892967824953914395627298796862274790273390666343658622328439526522232
     aflint: [876.9894260443848103918929678249539143956272987968622747902733906663436586223284395265222 +/- 5.02e-86]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = -2; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_1f1r(a, b, x)))
        fpm:  (9.96815410799804, -112.974634558282)
        mpm:  (9.968154107998041438417694433213529261529, -112.9746345582820055335342631558697974011)
    cmath53:  (9.96815410799805, -112.974634558282)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = -2; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.hyperg_1f1r(a, b, x))))
        fpm:  9.96815410799804
        mpm:  9.96815410799804143841769443321352926152639720971382570804471838656515483397673063489152589
        dpm:  9.96815410799804143841769443321352926152639720971382570804471838656515483397673063489152589
        gpm:  9.9681541079980414384176944332135292615263972097138257080447183865651548339767306348915258906
        apm: [9.968154107998041438417694433213529261526397209713825708044718386565154833976730634891526 +/- 4.18e-88]
    cmath53:  9.96815410799805
    sflintc:  9.968167
    dflintc:  9.96815410799806
    eflintc:  9.9681541079980414506
    qflintc:  9.96815410799804143841769443321354
    oflintc:  9.9681541079980414384176944332135292615263972097138257080447183865651554
    mflintc:  9.96815410799804143841769443321352926152639720971382570804471838656515483397673063489152603
    aflintc: [9.96815410799804143841769443321352926152639720971382570804471838656515483397673063489153 +/- 4.96e-87]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = -2; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hyperg_1f1r(a, b, x))))
        fpm:  -112.974634558282
        mpm:  -112.974634558282005533534263155869797401095127166893914172606469108893867368352678669332399
        dpm:  -112.974634558282005533534263155869797401095127166893914172606469108893867368352678669332399
        gpm:  -112.97463455828200553353426315586979740109512716689391417260646910889386736835267866933239901
        apm: [-112.974634558282005533534263155869797401095127166893914172606469108893867368352678669332399 +/- 7.91e-88]
    cmath53:  -112.974634558282
    sflintc:  -112.9746
    dflintc:  -112.974634558282
    eflintc:  -112.97463455828200552
    qflintc:  -112.97463455828200553353426315587
    oflintc:  -112.97463455828200553353426315586979740109512716689391417260646910889387
    mflintc:  -112.974634558282005533534263155869797401095127166893914172606469108893867368352678669332398
    aflintc: [-112.97463455828200553353426315586979740109512716689391417260646910889386736835267866933240 +/- 3.83e-87]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D02a_Hyperg1F1rReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D02b_Hyperg1F1rCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C01_Hyper1F1/D02_Hyperg1F1r.cs>`__. 







|newpage|

.. _rst_mpm_hyperu: 

Tricomi's Confluent Hypergeometric Function, `U(a,b;x)`
--------------------------------------------------------------------------------------

.. method:: ctx.hyperg_u(a, b, x)

    Returns Tricomi's confluent hypergeometric function of the second kind, `\displaystyle U(a,b;x)`.

    See also   Wikipedia :cite:p:`WikipediaFun91`, MathWorld :cite:p:`WolframFun93`, NIST :cite:p:`DLMFun91`, :cite:t:`Ehrhardt2018` (3.8.5), Flint :cite:p:`FlintFun90`, Flint :cite:p:`FlintFun90a`, Mpmath :cite:p:`MpmathFun93`. 

    Here `a, b` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `a,b \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `a, b \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `a, b, x \in \mathbb{C}` is accepted. 


    For all `z \ne 0` and `b \notin \mathbb{Z}` (but valid for all `b` as a limit) we have


    .. math:: U(a,b;x) = \frac{\Gamma(1-b)}{\Gamma(1+a-b)} M(a,b;c;z) + \frac{\Gamma(1-b)}{\Gamma(a)} x^{1-b} M(1+a-b,2-b;x) 




    |02a_TestHypergeomU_re| `\quad` |02b_TestHypergeomU_im| `\quad` |02c_TestHypergeomU_abs|

    .. |02a_TestHypergeomU_re| image:: ../_static/ExplicitSurfaces/Cplx1F1/02a_TestHypergeomU_re.3D.xml.jpg
       :width: 30 %

    .. |02b_TestHypergeomU_im| image:: ../_static/ExplicitSurfaces/Cplx1F1/02b_TestHypergeomU_im.3D.xml.jpg
       :width: 30 %

    .. |02c_TestHypergeomU_abs| image:: ../_static/ExplicitSurfaces/Cplx1F1/02c_TestHypergeomU_abs.3D.xml.jpg
       :width: 30 %

       

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.






An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 5.1; b = 2.7; x = 1.3; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_u(a, b, x)))
        fpm:  0.00294626430562465
        mpm:  0.00294626430562465278706926273364571578933674633427271010942479545241319384227816652303176372
        dpm:  0.00294626430562465278706926273364571578933674633427271010942479545241319384227816652303176372
        gpm:  0.00294626430562465278706926273364571578933674633427271010942479545241319384227816652303176372
        apm: [0.00294626430562465278706926273364571578933674633427271010942479545241319384227816652303 +/- 3.05e-87]
     math53:  0.00294626430562466
      sreal:  0.002946377
      dreal:  0.00294626430562772
      ereal:  0.0029462643056246541444
      qreal:  0.0029462643056246527870692627336459
      oreal:  0.0029462643056246527870692627336457157893367463342727101094247954524163776
      mreal:  0.00294626430562465278706926273364571578933674633427271010942479545241319384227816652303177312
     sflint:  0.002946265
     dflint:  0.00294626430562466
     eflint:  0.0029462643056246527881
     qflint:  0.00294626430562465278706926273364572
     oflint:  0.002946264305624652787069262733645715789336746334272710109424795452413194
     mflint:  0.00294626430562465278706926273364571578933674633427271010942479545241319384227816652303178098
     aflint: [0.00294626430562465278706926273364571578933674633427271010942479545241319384227816652303 +/- 6.43e-87]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = 2.7; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_u(a, b, x)))
        fpm:  (3108.56847458544, -634.312767471239)
        mpm:  (3108.568474585442422094579141160536048793, -634.3127674712391290583937277485500471336)
    cmath53:  (3108.56847458544, -634.312767471241)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.hyperg_u(a, b, x))))
        fpm:  3108.56847458544
        mpm:  3108.56847458544242209457914116053604879329435838332811506651093284634340529653301911758911
        dpm:  3108.56847458544242209457914116053604879329435838332811506651093284634340529653301911758911
        gpm:  3108.5684745854424220945791411605360487932943583833281150665109328463434052965330191175891102
        apm: [3108.568474585442422094579141160536048793294358383328115066510932846343405296533019117589 +/- 4.77e-85]
    cmath53:  3108.56847458544
    sflintc:  3108.568
    dflintc:  3108.56847458544
    eflintc:  3108.5684745854424216
    qflintc:  3108.56847458544242209457914116053
    oflintc:  3108.5684745854424220945791411605360487932943583833281150665109328463433
    mflintc:  3108.5684745854424220945791411605360487932943583833281150665109328463434052965330191175891
    aflintc: [3108.56847458544242209457914116053604879329435838332811506651093284634340529653301911759 +/- 2.11e-84]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  b = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hyperg_u(a, b, x))))
        fpm:  -634.312767471239
        mpm:  -634.312767471239129058393727748550047133478380929765934321600174139642743098040775491714948
        dpm:  -634.312767471239129058393727748550047133478380929765934321600174139642743098040775491714948
        gpm:  -634.31276747123912905839372774855004713347838092976593432160017413964274309804077549171494803
        apm: [-634.312767471239129058393727748550047133478380929765934321600174139642743098040775491715 +/- 3.22e-85]
    cmath53:  -634.312767471241
    sflintc:  -634.3132
    dflintc:  -634.312767471241
    eflintc:  -634.31276747123912946
    qflintc:  -634.312767471239129058393727748552
    oflintc:  -634.31276747123912905839372774855004713347838092976593432160017413964283
    mflintc:  -634.312767471239129058393727748550047133478380929765934321600174139642743098040775491714948
    aflintc: [-634.312767471239129058393727748550047133478380929765934321600174139642743098040775491715 +/- 9.28e-85]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D03a_HypergUReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D03b_HypergUCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C01_Hyper1F1/D03_HypergU.cs>`__. 







|newpage|

Generalized Laguerre polynomials, `L^{(a)}_n (x)`
-------------------------------------------------------------------------------

.. method:: ctx.laguerre_l(n, a, x)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Note: ctx.laguerre(z, n, alpha)

    Returns `\displaystyle L^{(a)}_n (x) = \binom{n+a}{n} M(-n,a+1,x) = \frac{\Gamma(n+a+1)}{\Gamma(n+1)\Gamma(a+1)} {}_1F_1(-n,a+1,x)`, the generalized Laguerre polynomials of degree `n \geq 0` with parameter `a; x \geq 0` and `a > -1` are the standard ranges. 
    
    For integer degree `n \ge 0` and integer order `m \ge 0`, we have, as a special case, the (associated) Laguerre polynomial  `L_n^m(x) = L_n^{(m)}(x)`. If `m = 0`, it is just called Laguerre polynomial: `L_n(x) = L_n^0(x) = L_n^{(0)}(x)` 

    These polynomials are orthogonal on the interval `(0,\infty)`, with respect to the weight function `w(x) = e^{-x}x^a`. The following standard recurrence formulas are used:

    .. math::
       :nowrap:

       \begin{eqnarray}
        L^{(a)}_0 (x) & = & 1 \\
        L^{(a)}_1 (x) & = & -x+1+a \nonumber \\ 
        nL^{(a)}_n (x)& = & (2n+a-1-x) L^{(a)}_{n-1}(x) - (n+a-1)  L^{(a)}_{n-2}(x).  \nonumber
       \end{eqnarray}

    See also  Wikipedia :cite:p:`WikipediaFun134`, MathWorld :cite:p:`WolframFun134`, NIST :cite:p:`DLMFun134`,  BoostMath :cite:p:`BoostFun134`, :cite:t:`Ehrhardt2018` (3.7.10) and  (3.7.12), Flint :cite:p:`FlintFun134`, Flint :cite:p:`FlintFun135`, Mpmath :cite:p:`MpmathFun134`. 




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; a = 2; x = 1.3; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.laguerre_l(n, a, x)))
        fpm:  -1.81241191666667
        mpm:  -1.81241191666666666666666666666666666666666666666666666666666666666666666666666666666666667
        dpm:  -1.81241191666666666666666666666666666666666666666666666666666666666666666666666666666666667
        gpm:  -1.8124119166666666666666666666666666666666666666666666666666666666666666666666666666666666701
        apm: [-1.8124119166666666666666666666666666666666666666666666666666666666666666666666666666666667 +/- 7.87e-89]
     math53:  -1.81241191666667
      sreal:  -1.812412
      dreal:  -1.81241191666667
      ereal:  -1.8124119166666666671
      qreal:  -1.81241191666666666666666666666667
      oreal:  -1.8124119166666666666666666666666666666666666666666666666666666666666666
      mreal:  -1.81241191666666666666666666666666666666666666666666666666666666666666666666666666666666667
     sflint:  -1.812412
     dflint:  -1.81241191666667
     eflint:  -1.8124119166666666664
     qflint:  -1.81241191666666666666666666666667
     oflint:  -1.8124119166666666666666666666666666666666666666666666666666666666666667
     mflint:  -1.81241191666666666666666666666666666666666666666666666666666666666666666666666666666666668
     aflint: [-1.812411916666666666666666666666666666666666666666666666666666666666666666666666666666667 +/- 4.32e-88]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  a = 2.7; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.laguerre_l(n, a, x)))
        fpm:  (8.81119194731359, -6.29915350365142)
        mpm:  (8.811191947313586729172237742368715736829, -6.299153503651418120813381437065069742676)
    cmath53:  (8.81119194731355, -6.2991535036514)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  a = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.laguerre_l(n, a, x))))
        fpm:  8.81119194731359
        mpm:  8.81119194731358672917223774236871573683078077425792642739568340500515475985222369468299179
        dpm:  8.81119194731358672917223774236871573683078077425792642739568340500515475985222369468299179
        gpm:  8.8111919473135867291722377423687157368307807742579264273956834050051547598522236946829917899
        apm: [8.81119194731358672917223774236871573683078077425792642739568340500515475985222369468299 +/- 2.74e-87]
    cmath53:  8.81119194731355
    sflintc:  8.811183
    dflintc:  8.81119194731355
    eflintc:  8.8111919473135867208
    qflintc:  8.81119194731358672917223774236869
    oflintc:  8.8111919473135867291722377423687157368307807742579264273956834050051535
    mflintc:  8.81119194731358672917223774236871573683078077425792642739568340500515475985222369468299166
    aflintc: [8.81119194731358672917223774236871573683078077425792642739568340500515475985222369468299 +/- 5.10e-87]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  a = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.laguerre_l(n, a, x))))
        fpm:  -6.29915350365142
        mpm:  -6.29915350365141812081338143706506974267693725934822421048134284403904793611296552717155153
        dpm:  -6.29915350365141812081338143706506974267693725934822421048134284403904793611296552717155153
        gpm:  -6.29915350365141812081338143706506974267693725934822421048134284403904793611296552717155153
        apm: [-6.29915350365141812081338143706506974267693725934822421048134284403904793611296552717155 +/- 2.26e-87]
    cmath53:  -6.2991535036514
    sflintc:  -6.299148
    dflintc:  -6.2991535036514
    eflintc:  -6.2991535036514181155
    qflintc:  -6.29915350365141812081338143706505
    oflintc:  -6.2991535036514181208133814370650697426769372593482242104813428440390471
    mflintc:  -6.29915350365141812081338143706506974267693725934822421048134284403904793611296552717155145
    aflintc: [-6.29915350365141812081338143706506974267693725934822421048134284403904793611296552717155 +/- 4.04e-87]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D04a_LaguerreLReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D04b_LaguerreLCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C01_Hyper1F1/D04_LaguerreL.cs>`__. 








        

|newpage|

Hermite polynomial (physicist), `H_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.hermite_h(n, z)

    Returns `\displaystyle  H_n(z)`, the Hermite polynomial (physicist) of degree `n`. 

    See also  Wikipedia :cite:p:`WikipediaFun135`, MathWorld :cite:p:`WolframFun135`, NIST :cite:p:`DLMFun134`,  BoostMath :cite:p:`BoostFun135`, :cite:t:`Ehrhardt2018` (3.7.7) and (3.8.11.4), :cite:t:`Ehrhardt2018` Flint :cite:p:`FlintFun134`, Flint :cite:p:`FlintFun135`, Mpmath :cite:p:`MpmathFun135`. 

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, then `n \in \mathbb{R}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflint`` then `n, x \in \mathbb{C}` is accepted. 

    We have `\displaystyle  H_n(z) = 2^n \sqrt{\pi} \left( \frac{1}{\Gamma\left(\frac{1-n}{2}\right)} \,_1F_1\left(-\frac{n}{2}, \frac{1}{2}, z^2\right) - \frac{2z}{\Gamma\left(-\frac{n}{2}\right)} \,_1F_1\left(\frac{1-n}{2}, \frac{3}{2}, z^2\right) \right)`, where `\displaystyle \frac{1}{\Gamma\left(n \right)}` is evaluated calling the reciprocal gamma function. 

    For integer `n \ge 0`, the `H_n` are orthogonal on the interval `(-\infty, \infty)`, with respect to the weight function `w(x) = e^{-x^2}`. They can be computed with the standard recurrence formulas:

    .. math::
       :nowrap:

       \begin{eqnarray}
        H_0 (x) & = & 1 \\
        H_1 (x) & = & 2x \nonumber \\ 
        H_n (x)& = & 2x H_{n-1}(x) - 2(n-1)  H_{n-2}(x).  \nonumber
       \end{eqnarray}




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hermite_h(n, x)))
        fpm:  1766.37024
        mpm:  1766.37024
        dpm:  1766.37024
        gpm:  1766.3702399999999999999999999999999999999999999999999999999999999999999999999999999999999999
        apm: [1766.3702400000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.19e-86]
     math53:  1766.37024
      sreal:  1766.37
      dreal:  1766.37024
      ereal:  1766.3702400000000003
      qreal:  1766.37024
      oreal:  1766.37024
      mreal:  1766.37024
     sflint:  1766.37
     dflint:  1766.37024
     eflint:  1766.3702400000000002
     qflint:  1766.37024
     oflint:  1766.37024
     mflint:  1766.37024
     aflint: [1766.3702400000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 2.63e-86]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hermite_h(n, x)))
        fpm:  (-4.10606785936604E-05, -1.83142168217381E-05)
        mpm:  (-0.00004106067859366043473983236740211790796731398103704, -0.000018314216821738127590986158229215326070323540027072)
    cmath53:  (-4.10606632927533E-05, -1.83142071695269E-05)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.hermite_h(n, x))))
        fpm:  -4.10606785936604E-05
        mpm:  -0.0000410606785936604347398323674021179079673139810370395445841575916441457551995320193779065386
        dpm:  -0.0000410606785936604347398323674021179079673139810370395445841575916441457551995320193779065386
        gpm:  -4.1060678593660434739832367402117907967313981037039544584157591644145755199532019377906538599e-05
        apm: [-4.106067859366043473983236740211790796731398103703954458415759164414575519953202e-5 +/- 3.49e-84]
    cmath53:  -4.10606632927533E-05
    sflintc:  -4.105626E-05
    dflintc:  -4.10606785936604E-05
    eflintc:  -4.1060678593660434743e-05
    qflintc:  -4.10606785936604347398323674021179e-05
    oflintc:  -4.10606785936604347398323674021179079673139810370395445841575916441e-05
    mflintc:  -4.10606785936604347398323674021179079673139810370395445841575916441457551995320193778690925E-05
    aflintc: [-4.106067859366043473983236740211790796731398103703954458415759164414575519953202e-5 +/- 3.70e-84]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hermite_h(n, x))))
        fpm:  -1.83142168217381E-05
        mpm:  -0.0000183142168217381275909861582292153260703235400270718963283122417212316393843276994699631656
        dpm:  -0.0000183142168217381275909861582292153260703235400270718963283122417212316393843276994699631656
        gpm:  -1.8314216821738127590986158229215326070323540027071896328312241721231639384327699469963165602e-05
        apm: [-1.831421682173812759098615822921532607032354002707189632831224172123163938432770e-5 +/- 3.40e-84]
    cmath53:  -1.83142071695269E-05
    sflintc:  -1.831568E-05
    dflintc:  -1.83142168217381E-05
    eflintc:  -1.8314216821738127596e-05
    qflintc:  -1.83142168217381275909861582292153e-05
    oflintc:  -1.83142168217381275909861582292153260703235400270718963283122417212e-05
    mflintc:  -1.83142168217381275909861582292153260703235400270718963283122417212316393843276994699192258E-05
    aflintc: [-1.831421682173812759098615822921532607032354002707189632831224172123163938432770e-5 +/- 3.60e-84]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D05a_HermiteHReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D05b_HermiteHCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C01_Hyper1F1/D05_HermiteH.cs>`__. 












|newpage|

Hermite polynomials (probabilist) `\operatorname{He}_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.hermite_he(n,x)

    Returns `\operatorname{He}_n(x) = 2^{-n/2} H_n(x/\sqrt{2})`, the  probabilist's Hermite polynomial of degree `n \ge 0`. 


    For integer `n`, the `\operatorname{He}_n` are orthogonal on the interval `(-\infty, \infty)`, with respect to the weight function `w(x) = \exp(-x^2/2)`. They are computed with the standard recurrence formulas:

    .. math::
       :nowrap:

       \begin{eqnarray}
        \operatorname{He}_0 (x) & = & 1 \\
        \operatorname{He}_1 (x) & = & x \nonumber \\ 
        \operatorname{He}_n (x)& = & x \operatorname{He}_{n-1}(x) - (n-1)  \operatorname{He}_{n-2}(x).  \nonumber
       \end{eqnarray}

    See also  Wikipedia :cite:p:`WikipediaFun135`, MathWorld :cite:p:`WolframFun135`, NIST :cite:p:`DLMFun134`,  BoostMath :cite:p:`BoostFun135`, :cite:t:`Ehrhardt2018` (3.7.8), Flint :cite:p:`FlintFun134`, Flint :cite:p:`FlintFun135`, Mpmath :cite:p:`MpmathFun135`. 




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hermite_h(n, x)))
        fpm:  2.7
        mpm:  2.7
        dpm:  2.7
        gpm:  2.6999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999
        apm: [2.70000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 2.63e-90]
     math53:  2.7
      sreal:  2.7
      dreal:  2.7
      ereal:  2.7
      qreal:  2.7
      oreal:  2.7
      mreal:  2.7
     sflint:  2.7
     dflint:  2.7
     eflint:  2.7
     qflint:  2.7
     oflint:  2.7
     mflint:  2.7
     aflint: [2.70000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 9.41e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hermite_he(n, x)))
        fpm:  (-0.000815130595647044, -0.00076023436629128)
        mpm:  (-0.00081513059564704377828482042020873578942579777366155, -0.00076023436629128022971095617674488773095952693580264)
    cmath53:  (-0.00081513059577206, -0.000760234366302415)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.hermite_he(n, x))))
        fpm:  -0.000815130595647044
        mpm:  -0.000815130595647043778284820420208735789425797773661551606432741143582336393867768062533286905
        dpm:  -0.000815130595647043778284820420208735789425797773661551606432741143582336393867768062533286905
        gpm:  -0.00081513059564704377828482042020873578942579777366155160643274114358233639386776806253328690503
        apm: [-0.0008151305956470437782848204202087357894257977736615516064327411435823363938677680625 +/- 7.97e-86]
    cmath53:  -0.00081513059577206
    sflintc:  -0.0008151312
    dflintc:  -0.000815130595647044
    eflintc:  -0.00081513059564704377834
    qflintc:  -0.000815130595647043778284820420208736
    oflintc:  -0.00081513059564704377828482042020873578942579777366155160643274114358233877
    mflintc:  -0.000815130595647043778284820420208735789425797773661551606432741143582336393867768062533304679
    aflintc: [-0.000815130595647043778284820420208735789425797773661551606432741143582336393867768063 +/- 6.15e-85]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hermite_he(n, x))))
        fpm:  -0.00076023436629128
        mpm:  -0.000760234366291280229710956176744887730959526935802635616477642209256880755775110944247745822
        dpm:  -0.000760234366291280229710956176744887730959526935802635616477642209256880755775110944247745822
        gpm:  -0.00076023436629128022971095617674488773095952693580263561647764220925688075577511094424774582195
        apm: [-0.0007602343662912802297109561767448877309595269358026356164776422092568807557751109442 +/- 9.41e-86]
    cmath53:  -0.000760234366302415
    sflintc:  -0.0007602327
    dflintc:  -0.000760234366291281
    eflintc:  -0.00076023436629128022969
    qflintc:  -0.000760234366291280229710956176744888
    oflintc:  -0.00076023436629128022971095617674488773095952693580263561647764220925687876
    mflintc:  -0.000760234366291280229710956176744887730959526935802635616477642209256880755775110944247734366
    aflintc: [-0.000760234366291280229710956176744887730959526935802635616477642209256880755775110944 +/- 3.95e-85]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D06a_HermiteHeReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C01_Hyper1F1/D06b_HermiteHeCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C01_Hyper1F1/D06_HermiteHe.cs>`__. 










