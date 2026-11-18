

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />






|newpage|

Coulomb, Whittaker and parabolic cylinder functions
==============================================================================================



Regular Coulomb wave function `F_{\ell}(\eta,x)`
-------------------------------------------------------------------------------

.. method:: ctx.coulomb_f(l, eta, x)

    where ``ctx`` is ``math53``` or ``ctxflint``.

    Returns the Coulomb wave function F. See also  Wikipedia :cite:p:`WikipediaFun1052`, MathWorld :cite:p:`WolframFun1052`, NIST :cite:p:`DLMFun1052`, :cite:t:`Ehrhardt2018` (3.1.10.4), Mpmath :cite:p:`MpmathFun1053`.

    Calculates the regular Coulomb wave function

    .. math ::  F_{\ell}(\eta,x) = \frac{1}{2i} \left(H^{(+)}_{\ell}(\eta,x) - H^{(-)}_{\ell}(\eta,x)  \right),

    where `H^{(+)}_{\ell}(\eta,x)` and `H^{(-)}_{\ell}(\eta,x)` are irregular Coulomb wave functions.


    Coulomb wave functions are solutions of the Coulomb wave equation

    .. math ::

        y'' + \left(1 - \frac{2 \eta}{z} - \frac{\ell(\ell+1)}{z^2}\right) y = 0

    which is the radial Schrödinger equation for a charged particle in a
    Coulomb potential `1/z`, where `\ell` is the orbital angular momentum and
    `\eta` is the Sommerfeld parameter.
    The standard solutions are named `F_{\ell}(\eta,z)` (regular
    at the origin `z = 0`) and `G_{\ell}(\eta,z)` (irregular at the origin).
    The irregular solutions
    `H^{\pm}_{\ell}(\eta,z) = G_{\ell}(\eta,z) \pm i F_{\ell}(\eta,z)`
    are also used. The redundant functions `H^{\pm}` are provided explicitly since taking
    the linear combination of *F* and *G* suffers from cancellation in
    parts of the complex plane.

    Coulomb wave functions are special cases of confluent hypergeometric functions. The normalization constants and connection formulas are discussed in :cite:t:`Dzieciol1999`, :cite:t:`Gaspard2018`, :cite:t:`Michel2007` and chapter 33 in NIST :cite:p:`DLMFun1052`. In this implementation, we define the analytic continuations of all the functions so that the branch cut with respect to *z* is placed on the negative real axis. 




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = 5; eta = 2.7; x = 1.3; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.coulomb_f(l, eta, x)))
        fpm:  5.88935148243641E-06
        mpm:  0.00000588935148243641457704728913666906889382269283540430709416543626505901429816306349155707061
        dpm:  0.00000588935148243641457704728913666906889382269283540430709416543626505901429816306349155707061
        gpm:  5.8893514824364145770472891366690688938226928354043070941654362650590142981630634915570706103e-06
        apm: [5.889351482436414577047289136669068893822692835404307094165436265059014298163063491557071e-6 +/- 5.13e-94]
     math53:  5.88935148243642E-06
     sflint:  5.88935E-06
     dflint:  5.88935148243641E-06
     eflint:  5.8893514824364145752e-06
     qflint:  5.88935148243641457704728913666907e-06
     oflint:  5.8893514824364145770472891366690688938226928354043070941654362650590143e-06
     mflint:  5.88935148243641457704728913666906889382269283540430709416543626505901429816306349155707057E-06
     aflint: [5.889351482436414577047289136669068893822692835404307094165436265059014298163063491557071e-6 +/- 6.93e-94]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.coulomb_f(l, eta, x)))
        fpm:  (0.99983587955112, -0.000161017588835076)
        mpm:  (0.9998358795511197936096176833895849330915, -0.0001610175888350764324777252607106789147347)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.coulomb_f(l, eta, x))))
        fpm:  0.000955134022682293
        mpm:  0.000955134022682293214194269324493094490632440413326042706809343895651341870582793516112929368
        dpm:  0.000955134022682293214194269324493094490632440413326042706809343895651341870582793516112929368
        gpm:  0.00095513402268229321419426932449309449063244041332604270680934389565134187058279351611292936801
        apm: [0.000955134022682293214194269324493094490632440413326042706809343895651341870582793516112929 +/- 5.95e-91]
    cmath53:  NaN
    sflintc:  0.000955134
    dflintc:  0.000955134022682293
    eflintc:  0.00095513402268229321417
    qflintc:  0.000955134022682293214194269324493095
    oflintc:  0.00095513402268229321419426932449309449063244041332604270680934389565134187
    mflintc:  0.000955134022682293214194269324493094490632440413326042706809343895651341870582793516112929407
    aflintc: [0.00095513402268229321419426932449309449063244041332604270680934389565134187058279351611293 +/- 1.12e-90]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.coulomb_f(l, eta, x))))
        fpm:  -0.000450382260916852
        mpm:  -0.000450382260916852281366652134065396011457565358775931182825281958174973966751078922436723968
        dpm:  -0.000450382260916852281366652134065396011457565358775931182825281958174973966751078922436723968
        gpm:  -0.000450382260916852281366652134065396011457565358775931182825281958174973966751078922436723968
        apm: [-0.000450382260916852281366652134065396011457565358775931182825281958174973966751078922436724 +/- 2.41e-91]
    cmath53:  NaN
    sflintc:  -0.0004503822
    dflintc:  -0.000450382260916853
    eflintc:  -0.00045038226091685228134
    qflintc:  -0.000450382260916852281366652134065396
    oflintc:  -0.00045038226091685228136665213406539601145756535877593118282528195817497398
    mflintc:  -0.00045038226091685228136665213406539601145756535877593118282528195817497396675107892243672398
    aflintc: [-0.000450382260916852281366652134065396011457565358775931182825281958174973966751078922436724 +/- 5.20e-91]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D01a_CoulombFReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D01b_CoulombFCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D01_CoulombF.cs>`__. 










|newpage|

.. _rst_mpm_coulombg: 

Irregular Coulomb wave function `G_{\ell}(\eta,z)`
-------------------------------------------------------------------------------

.. method:: ctx.coulomb_g(L, eta, x)

    where ``ctx`` is ``math53``` or ``ctxflint``.

    Returns the irregular Coulomb wave function.  See also  Wikipedia :cite:p:`WikipediaFun1052`, MathWorld :cite:p:`WolframFun1052`, NIST :cite:p:`DLMFun1052`, :cite:t:`Ehrhardt2018` (3.1.10.5), Mpmath :cite:p:`MpmathFun1054`.


    Calculates the irregular Coulomb wave function


    .. math ::  G_{\ell}(\eta,x) = \frac{1}{2} \left(H^{(+)}_{\ell}(\eta,x) - H^{(-)}_{\ell}(\eta,x)  \right),

    where `H^{(+)}_{\ell}(\eta,x)` and `H^{(-)}_{\ell}(\eta,x)` are irregular Coulomb wave functions.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = 5; eta = 2.7; x = 1.3; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.coulomb_g(l, eta, x)))
        fpm:  18503.6125168918
        mpm:  18503.6125168917605722357634638120233723936924116076396677005925449050603952031892855433037
        dpm:  18503.6125168917605722357634638120233723936924116076396677005925449050603952031892855433037
        gpm:  18503.612516891760572235763463812023372393692411607639667700592544905060395203189285543303699
        apm: [18503.61251689176057223576346381202337239369241160763966770059254490506039520318928554330 +/- 8.73e-84]
     math53:  18503.5989942829
     sflint:  18503.62
     dflint:  18503.6125168918
     eflint:  18503.612516891760578
     qflint:  18503.612516891760572235763463812
     oflint:  18503.612516891760572235763463812023372393692411607639667700592544905061
     mflint:  18503.6125168917605722357634638120233723936924116076396677005925449050603952031892855433032
     aflint: [18503.6125168917605722357634638120233723936924116076396677005925449050603952031892855433 +/- 1.02e-83]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.coulomb_g(l, eta, x)))
        fpm:  (46.1888255501048, 197.544736348848)
        mpm:  (46.18882555010475198188860439705187835305, 197.5447363488482151797467025255275907709)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.coulomb_g(l, eta, x))))
        fpm:  46.1888255501048
        mpm:  46.1888255501047519818886043970518783530445189452801829752672973590233745725001130850013221
        dpm:  46.1888255501047519818886043970518783530445189452801829752672973590233745725001130850013221
        gpm:  46.188825550104751981888604397051878353044518945280182975267297359023374572500113085001322103
        apm: [46.1888255501047519818886043970518783530445189452801829752672973590233745725001130850 +/- 1.04e-83]
    cmath53:  NaN
    sflintc:  46.18883
    dflintc:  46.1888255501047
    eflintc:  46.188825550104751987
    qflintc:  46.1888255501047519818886043970518
    oflintc:  46.188825550104751981888604397051878353044518945280182975267297359023372
    mflintc:  46.188825550104751981888604397051878353044518945280182975267297359023374572500113085001321
    aflintc: [46.18882555010475198188860439705187835304451894528018297526729735902337457250011308500 +/- 8.86e-84]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.coulomb_g(l, eta, x))))
        fpm:  197.544736348848
        mpm:  197.544736348848215179746702525527590770860261525975510498481443581587808194765302982747409
        dpm:  197.544736348848215179746702525527590770860261525975510498481443581587808194765302982747409
        gpm:  197.544736348848215179746702525527590770860261525975510498481443581587808194765302982747409
        apm: [197.5447363488482151797467025255275907708602615259755104984814435815878081947653029827 +/- 5.64e-83]
    cmath53:  NaN
    sflintc:  197.5447
    dflintc:  197.544736348848
    eflintc:  197.54473634884821519
    qflintc:  197.544736348848215179746702525528
    oflintc:  197.54473634884821517974670252552759077086026152597551049848144358158781
    mflintc:  197.544736348848215179746702525527590770860261525975510498481443581587808194765302982747409
    aflintc: [197.5447363488482151797467025255275907708602615259755104984814435815878081947653029827 +/- 5.49e-83]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D02a_CoulombGReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D02b_CoulombGCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D02_CoulombG.cs>`__. 







|newpage|

Irregular Coulomb wave function `H^{(+)}_{\ell}(\eta,x)`
-------------------------------------------------------------------------------

.. method:: ctx.coulomb_hplus(L, eta, x)

    where ``ctx`` is ``math53``` or ``ctxflint``.

    Returns the irregular Coulomb wave function.  See also  Wikipedia :cite:p:`WikipediaFun1052`, MathWorld :cite:p:`WolframFun1052`, NIST :cite:p:`DLMFun1052`, :cite:t:`Ehrhardt2018` (3.1.10.5), Mpmath :cite:p:`MpmathFun1054`.


    Calculates the irregular Coulomb wave function

    .. math :: H^{(+)}_{\ell}(\eta,x) = -2i(-2)^\ell e^{\pi \eta /2} e^{+i \sigma_{\ell}} x^{\ell+1} e^{+i x} U(\ell+1+i\eta, 2l+2,-2 i x),

    where `\sigma_{\ell} = \text{arg} \Gamma(\ell+1+i \eta)` is called the Coulomb phase shift.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = 5; eta = 2.7; x = 1.3; gui.setdps(40)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.cplxctx.fmt(ctx.coulomb_hplus(l, eta, x)))
        fpm:  (18503.6125168918, 5.88935148243641E-06)
        mpm:  (18503.61251689176057223576346381202337239, 0.000005889351482436414577047289136669068893822)
        dpm:  (18503.61251689176057223576346381202337239, 0.000005889351482436414577047289136669068893822)
        gpm:  (18503.61251689176057223576346381202337239, 5.88935148243641457704728913666906889382197e-06)
        apm: ([18503.61251689176057223576346381202337 +/- 3.68e-33], [5.8893514824364145770472891366690688938e-6 +/- 3.05e-44])
     math53:  (18503.5989942829, 5.88935148243642E-06)
     sflint:  (18503.62, 5.88935E-06)
     dflint:  (18503.6125168918, 5.88935148243641E-06)
     eflint:  (18503.612516891760578, 5.8893514824364145752e-06)
     qflint:  (18503.612516891760572235763463812, 5.88935148243641457704728913666907e-06)
     oflint:  (18503.612516891760572235763463812023372393692411607639667700592544905061, 5.8893514824364145770472891366690688938226928354043070941654362650590143e-06)
     mflint:  (18503.61251689176057223576346381202337232, 5.889351482436414577047289136669068893812E-06)
     aflint: ([18503.61251689176057223576346381202337 +/- 6.97e-33], [5.8893514824364145770472891366690688938e-6 +/- 6.80e-44])



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.coulomb_hplus(l, eta, x)))
        fpm:  (46.1892759323657, 197.545691482871)
        mpm:  (46.18927593236566883416997104918594374906, 197.5456914828708974729608967948520838654)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.coulomb_hplus(l, eta, x))))
        fpm:  46.1892759323657
        mpm:  46.1892759323656688341699710491859437490559765106389589064501226409815495464668641639237588
        dpm:  46.1892759323656688341699710491859437490559765106389589064501226409815495464668641639237588
        gpm:  46.1892759323656688341699710491859437490559765106389589064501226409815495464668641639237588
        apm: [46.1892759323656688341699710491859437490559765106389589064501226409815495464668641639 +/- 3.29e-83]
    cmath53:  NaN
    sflintc:  46.18928
    dflintc:  46.1892759323656
    eflintc:  46.18927593236566884
    qflintc:  46.1892759323656688341699710491859
    oflintc:  46.189275932365668834169971049185943749055976510638958906450122640981547
    mflintc:  46.1892759323656688341699710491859437490559765106389589064501226409815495464668641639237577
    aflintc: [46.1892759323656688341699710491859437490559765106389589064501226409815495464668641639 +/- 3.13e-83]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.coulomb_hplus(l, eta, x))))
        fpm:  197.545691482871
        mpm:  197.545691482870897472960896794852083865350893966388836541188252925483459536635885776263521
        dpm:  197.545691482870897472960896794852083865350893966388836541188252925483459536635885776263521
        gpm:  197.54569148287089747296089679485208386535089396638883654118825292548345953663588577626352101
        apm: [197.5456914828708974729608967948520838653508939663888365411882529254834595366358857763 +/- 4.55e-83]
    cmath53:  NaN
    sflintc:  197.5457
    dflintc:  197.545691482871
    eflintc:  197.54569148287089747
    qflintc:  197.545691482870897472960896794852
    oflintc:  197.54569148287089747296089679485208386535089396638883654118825292548346
    mflintc:  197.545691482870897472960896794852083865350893966388836541188252925483459536635885776263522
    aflintc: [197.5456914828708974729608967948520838653508939663888365411882529254834595366358857763 +/- 4.40e-83]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D03a_CoulombHplusReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D03b_CoulombHplusCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D03_CoulombHplus.cs>`__. 









|newpage|

Irregular Coulomb wave function `H^{(-)}_{\ell}(\eta,x)`
-------------------------------------------------------------------------------

.. method:: ctx.coulomb_hminus(L, eta, x)

    where ``ctx`` is ``math53``` or ``ctxflint``.

    Returns the irregular Coulomb wave function.  See also  Wikipedia :cite:p:`WikipediaFun1052`, MathWorld :cite:p:`WolframFun1052`, NIST :cite:p:`DLMFun1052`, :cite:t:`Ehrhardt2018` (3.1.10.5), Mpmath :cite:p:`MpmathFun1054`.



    Calculates the irregular Coulomb wave function

    .. math :: H^{(-)}_{\ell}(\eta,x) = +2i(-2)^\ell e^{\pi \eta /2} e^{+i \sigma_{\ell}} x^{\ell+1} e^{+i x} U(\ell+1+i\eta, 2l+2,-2 i x),

    where `\sigma_{\ell} = \text{arg} \Gamma(\ell+1+i \eta)` is called the Coulomb phase shift.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = 5; eta = 2.7; x = 1.3; gui.setdps(40)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.cplxctx.fmt(ctx.coulomb_hminus(l, eta, x)))
        fpm:  (18503.6125168918, -5.88935148243641E-06)
        mpm:  (18503.61251689176057223576346381202337239, -0.000005889351482436414577047289136669068893822)
        dpm:  (18503.61251689176057223576346381202337239, -0.000005889351482436414577047289136669068893822)
        gpm:  (18503.61251689176057223576346381202337239, -5.88935148243641457704728913666906889382197e-06)
        apm: ([18503.61251689176057223576346381202337 +/- 3.68e-33], [-5.8893514824364145770472891366690688938e-6 +/- 3.05e-44])
     math53:  (18503.5989942829, -5.88935148243642E-06)
     sflint:  (18503.62, -5.88935E-06)
     dflint:  (18503.6125168918, -5.88935148243641E-06)
     eflint:  (18503.612516891760578, -5.8893514824364145752e-06)
     qflint:  (18503.612516891760572235763463812, -5.88935148243641457704728913666907e-06)
     oflint:  (18503.612516891760572235763463812023372393692411607639667700592544905061, -5.8893514824364145770472891366690688938226928354043070941654362650590143e-06)
     mflint:  (18503.61251689176057223576346381202337232, -5.889351482436414577047289136669068893812E-06)
     aflint: ([18503.61251689176057223576346381202337 +/- 6.97e-33], [-5.8893514824364145770472891366690688938e-6 +/- 6.80e-44])



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.coulomb_hminus(l, eta, x)))
        fpm:  (46.1883751678438, 197.543781214826)
        mpm:  (46.18837516784383512960723774491781295703, 197.5437812148255328865325082562030976764)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.coulomb_hminus(l, eta, x))))
        fpm:  46.1883751678438
        mpm:  46.1883751678438351296072377449178129570330613799214070440844720770651995985333620060788854
        dpm:  46.1883751678438351296072377449178129570330613799214070440844720770651995985333620060788854
        gpm:  46.188375167843835129607237744917812957033061379921407044084472077065199598533362006078885399
        apm: [46.1883751678438351296072377449178129570330613799214070440844720770651995985333620061 +/- 3.02e-83]
    cmath53:  NaN
    sflintc:  46.18838
    dflintc:  46.1883751678438
    eflintc:  46.188375167843835133
    qflintc:  46.1883751678438351296072377449178
    oflintc:  46.188375167843835129607237744917812957033061379921407044084472077065197
    mflintc:  46.1883751678438351296072377449178129570330613799214070440844720770651995985333620060788843
    aflintc: [46.18837516784383512960723774491781295703306137992140704408447207706519959853336200608 +/- 8.66e-84]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> l = -5.1;  eta = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.coulomb_hminus(l, eta, x))))
        fpm:  197.543781214826
        mpm:  197.543781214825532886532508256203097676369629085562184455774634237692156852894720189231296
        dpm:  197.543781214825532886532508256203097676369629085562184455774634237692156852894720189231296
        gpm:  197.54378121482553288653250825620309767636962908556218445577463423769215685289472018923129599
        apm: [197.5437812148255328865325082562030976763696290855621844557746342376921568528947201892 +/- 4.03e-83]
    cmath53:  NaN
    sflintc:  197.5438
    dflintc:  197.543781214826
    eflintc:  197.54378121482553289
    qflintc:  197.543781214825532886532508256203
    oflintc:  197.54378121482553288653250825620309767636962908556218445577463423769216
    mflintc:  197.543781214825532886532508256203097676369629085562184455774634237692156852894720189231296
    aflintc: [197.54378121482553288653250825620309767636962908556218445577463423769215685289472018923 +/- 8.76e-84]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D04a_CoulombHminusReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D04b_CoulombHminusCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D04_CoulombHminus.cs>`__. 









|newpage|

.. _rst_mpm_whitm: 

Whittaker function `M_{\kappa, \mu}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.whittaker_m(k, m, x)

    Returns `M_{\kappa, \mu}(x) = e^{-\frac{1}{2}x} x^{\frac{1}{2}+\mu} M(\tfrac{1}{2}+\mu-\kappa, 1+2\mu, x)`, the Whittaker function M.

    See also MathWorld :cite:p:`WolframFun1055a`,  Wikipedia :cite:p:`WikipediaFun1055`, :cite:t:`Ehrhardt2018` (3.8.9), NIST :cite:p:`DLMFun1055`, Mpmath :cite:p:`MpmathFun1055`.



    .. math :: M(k,m,z) = e^{-\frac{1}{2}z} z^{\frac{1}{2}+m} \,_1F_1(\tfrac{1}{2}+m-k, 1+2m, z)



    Evaluates the Whittaker function `M(k,m,z)`, which gives a solution
    to the Whittaker differential equation

    .. math ::

        \frac{d^2f}{\mathrm{d}z^2} + \left(-\frac{1}{4}+\frac{k}{z}+
          \frac{(\frac{1}{4}-m^2)}{z^2}\right) f = 0.

    A second solution is given by :ref:`whitw() <rst_mpm_whitw>`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> k = 5; m = 2.7; x = 1.3; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.whittaker_m(k, m, x)))
        fpm:  0.79817430396811
        mpm:  0.798174303968109525836656774218814914353665467759515150130910140106909676272381101784524832
        dpm:  0.798174303968109525836656774218814914353665467759515150130910140106909676272381101784524832
        gpm:  0.79817430396810952583665677421881491435366546775951515013091014010690967627238110178452483195
        apm: [0.7981743039681095258366567742188149143536654677595151501309101401069096762723811017845248 +/- 8.69e-89]
     math53:  0.79817430396811
     sflint:  0.7981743
     dflint:  0.79817430396811
     eflint:  0.79817430396810952578
     qflint:  0.798174303968109525836656774218815
     oflint:  0.79817430396810952583665677421881491435366546775951515013091014010690968
     mflint:  0.798174303968109525836656774218814914353665467759515150130910140106909676272381101784524832
     aflint: [0.798174303968109525836656774218814914353665467759515150130910140106909676272381101784525 +/- 3.86e-88]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> k = -5.1;  m = 2.7; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.whittaker_m(k, m, x)))
        fpm:  (-2.69960214312798, -46.65534206946)
        mpm:  (-2.699602143127975328190494893088810165697, -46.65534206946005059423752883319025968531)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> k = -5.1;  m = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.whittaker_m(k, m, x))))
        fpm:  -2.69960214312798
        mpm:  -2.69960214312797532819049489308881016569729548228413035675223799120001250409059977561480644
        dpm:  -2.69960214312797532819049489308881016569729548228413035675223799120001250409059977561480644
        gpm:  -2.6996021431279753281904948930888101656972954822841303567522379912000125040905997756148064399
        apm: [-2.69960214312797532819049489308881016569729548228413035675223799120001250409059977561481 +/- 8.47e-87]
    cmath53:  NaN
    sflintc:  -2.699599
    dflintc:  -2.69960214312798
    eflintc:  -2.6996021431279753253
    qflintc:  -2.69960214312797532819049489308881
    oflintc:  -2.6996021431279753281904948930888101656972954822841303567522379912000125
    mflintc:  -2.69960214312797532819049489308881016569729548228413035675223799120001250409059977561480641
    aflintc: [-2.6996021431279753281904948930888101656972954822841303567522379912000125040905997756148 +/- 2.48e-86]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> k = -5.1;  m = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.whittaker_m(k, m, x))))
        fpm:  -46.65534206946
        mpm:  -46.6553420694600505942375288331902596853078867581504597926378230927810846444175531861205103
        dpm:  -46.6553420694600505942375288331902596853078867581504597926378230927810846444175531861205103
        gpm:  -46.655342069460050594237528833190259685307886758150459792637823092781084644417553186120510297
        apm: [-46.65534206946005059423752883319025968530788675815045979263782309278108464441755318612051 +/- 5.28e-87]
    cmath53:  NaN
    sflintc:  -46.65534
    dflintc:  -46.65534206946
    eflintc:  -46.655342069460050591
    qflintc:  -46.6553420694600505942375288331903
    oflintc:  -46.655342069460050594237528833190259685307886758150459792637823092781085
    mflintc:  -46.6553420694600505942375288331902596853078867581504597926378230927810846444175531861205102
    aflintc: [-46.6553420694600505942375288331902596853078867581504597926378230927810846444175531861205 +/- 2.86e-86]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D05a_WhittakerMReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D05b_WhittakerMCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D05_WhittakerM.cs>`__. 









|newpage|

.. _rst_mpm_whitw: 

Whittaker function `W_{\kappa, \mu}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.whittaker_w(k, m, x)

    Returns `W_{\kappa, \mu}(x) = e^{-\frac{1}{2}x} x^{\frac{1}{2}+\mu} U(\tfrac{1}{2}+\mu-\kappa, 1+2\mu, x)`, the Whittaker function W.

    See also MathWorld :cite:p:`WolframFun1055b`,  Wikipedia :cite:p:`WikipediaFun1055`, :cite:t:`Ehrhardt2018` (3.8.10), NIST :cite:p:`DLMFun1055`, Mpmath :cite:p:`MpmathFun1056`.


    .. math :: W(k,m,z) = e^{-\frac{1}{2}z} z^{\frac{1}{2}+m} U(\tfrac{1}{2}+m-k, 1+2m, z).


    Evaluates the Whittaker function `W(k,m,z)`, which gives a second
    solution to the Whittaker differential equation.



An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> k = 5; m = 2.7; x = 1.3; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.whittaker_w(k, m, x)))
        fpm:  64.0201709328783
        mpm:  64.0201709328783439066926612306882396896675048674298614729426720368314733656279134086053193
        dpm:  64.0201709328783439066926612306882396896675048674298614729426720368314733656279134086053193
        gpm:  64.020170932878343906692661230688239689667504867429861472942672036831473365627913408605319301
        apm: [64.02017093287834390669266123068823968966750486742986147294267203683147336562791340860532 +/- 7.30e-87]
     math53:  64.0201709328784
     sflint:  64.02018
     dflint:  64.0201709328783
     eflint:  64.020170932878343914
     qflint:  64.0201709328783439066926612306883
     oflint:  64.020170932878343906692661230688239689667504867429861472942672036831473
     mflint:  64.0201709328783439066926612306882396896675048674298614729426720368314733656279134086053194
     aflint: [64.0201709328783439066926612306882396896675048674298614729426720368314733656279134086053 +/- 3.86e-86]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> k = -5.1;  m = 2.7; x = 1.3+2j;  gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.whittaker_w(k, m, x)))
        fpm:  (-0.000101352054023801, 0.000120715443487022)
        mpm:  (-0.0001013520540238005436412447912024863091665, 0.0001207154434870222009430247385007532181291)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> k = -5.1;  m = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.whittaker_w(k, m, x))))
        fpm:  -0.000101352054023801
        mpm:  -0.000101352054023800543641244791202486309166539064282156674108855756133313166598167852671097582
        dpm:  -0.000101352054023800543641244791202486309166539064282156674108855756133313166598167852671097582
        gpm:  -0.000101352054023800543641244791202486309166539064282156674108855756133313166598167852671097582
        apm: [-0.000101352054023800543641244791202486309166539064282156674108855756133313166598167852671 +/- 2.00e-88]
    cmath53:  NaN
    sflintc:  -0.0001013521
    dflintc:  -0.000101352054023801
    eflintc:  -0.00010135205402380054367
    qflintc:  -0.000101352054023800543641244791202486
    oflintc:  -0.00010135205402380054364124479120248630916653906428215667410885575613331317
    mflintc:  -0.000101352054023800543641244791202486309166539064282156674108855756133313166598167852671097582
    aflintc: [-0.000101352054023800543641244791202486309166539064282156674108855756133313166598167852671 +/- 4.32e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> k = -5.1;  m = 2.7; x = 1.3+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.whittaker_w(k, m, x))))
        fpm:  0.000120715443487022
        mpm:  0.000120715443487022200943024738500753218129123842275405360916288697612036192671831917788295895
        dpm:  0.000120715443487022200943024738500753218129123842275405360916288697612036192671831917788295895
        gpm:  0.000120715443487022200943024738500753218129123842275405360916288697612036192671831917788295895
        apm: [0.000120715443487022200943024738500753218129123842275405360916288697612036192671831917788 +/- 4.01e-88]
    cmath53:  NaN
    sflintc:  0.0001207155
    dflintc:  0.000120715443487022
    eflintc:  0.00012071544348702220098
    qflintc:  0.000120715443487022200943024738500753
    oflintc:  0.00012071544348702220094302473850075321812912384227540536091628869761203619
    mflintc:  0.000120715443487022200943024738500753218129123842275405360916288697612036192671831917788295895
    aflintc: [0.000120715443487022200943024738500753218129123842275405360916288697612036192671831917788 +/- 6.41e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D06a_WhittakerWReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D06b_WhittakerWCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D06_WhittakerW.cs>`__. 








|newpage|

Parabolic cylinder function `D_{\nu}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.pcfd(nu, x)

    Returns Whittaker’s parabolic cylinder function `D_n(z) = U(-n-1/2, z)` (see :ref:`pcfu() <rst_mpm_pcfu>`).

    See also: MathWorld :cite:p:`WolframFun1057a`,  Wikipedia :cite:p:`WikipediaFun1057`, NIST :cite:p:`DLMFun1057`, Mpmath :cite:p:`MpmathFun1057`, :cite:t:`Ehrhardt2018` (3.8.11.1).




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 1.5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.pcfd(n, x)))
        fpm:  0.680965884934572
        mpm:  0.680965884934571536524419329732251406548296412067212249270664716023196807338280034549935358
        dpm:  0.680965884934571536524419329732251406548296412067212249270664716023196807338280034549935358
        gpm:  0.68096588493457153652441932973225140654829641206721224927066471602319680733828003454993535798
        apm: [0.68096588493457153652441932973225140654829641206721224927066471602319680733828003454994 +/- 6.92e-87]
     math53:  0.680965884934572
     sflint:  0.6809658
     dflint:  0.680965884934572
     eflint:  0.68096588493457153651
     qflint:  0.680965884934571536524419329732251
     oflint:  0.68096588493457153652441932973225140654829641206721224927066471602319681
     mflint:  0.680965884934571536524419329732251406548296412067212249270664716023196807338280034549935358
     aflint: [0.68096588493457153652441932973225140654829641206721224927066471602319680733828003454994 +/- 6.48e-87]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.pcfd(n, x)))
        fpm:  (0.000181017061070944, 0.00045500605294389)
        mpm:  (0.00018101706107094424979738988149197772233304675704802, 0.00045500605294389001129497560808425702562338092042967)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.pcfd(n, x))))
        fpm:  0.000181017061070944
        mpm:  0.00018101706107094424979738988149197772233304675704801792621006229300578645759239839760804103
        dpm:  0.00018101706107094424979738988149197772233304675704801792621006229300578645759239839760804103
        gpm:  0.00018101706107094424979738988149197772233304675704801792621006229300578645759239839760804102999
        apm: [0.0001810170610709442497973898814919777223330467570480179262100622930057864575923983976 +/- 1.89e-86]
    cmath53:  NaN
    sflintc:  0.0001810171
    dflintc:  0.000181017061070944
    eflintc:  0.00018101706107094424979
    qflintc:  0.000181017061070944249797389881491978
    oflintc:  0.00018101706107094424979738988149197772233304675704801792621006229300578646
    mflintc:  0.00018101706107094424979738988149197772233304675704801792621006229300578645759239839760804103
    aflintc: [0.0001810170610709442497973898814919777223330467570480179262100622930057864575923983976 +/- 1.68e-86]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.pcfd(n, x))))
        fpm:  0.00045500605294389
        mpm:  0.000455006052943890011294975608084257025623380920429665742859438660879894719196113077851299536
        dpm:  0.000455006052943890011294975608084257025623380920429665742859438660879894719196113077851299536
        gpm:  0.00045500605294389001129497560808425702562338092042966574285943866087989471919611307785129953598
        apm: [0.0004550060529438900112949756080842570256233809204296657428594386608798947191961130779 +/- 5.95e-86]
    cmath53:  NaN
    sflintc:  0.0004550061
    dflintc:  0.00045500605294389
    eflintc:  0.00045500605294389001131
    qflintc:  0.000455006052943890011294975608084257
    oflintc:  0.00045500605294389001129497560808425702562338092042966574285943866087989472
    mflintc:  0.000455006052943890011294975608084257025623380920429665742859438660879894719196113077851299536
    aflintc: [0.0004550060529438900112949756080842570256233809204296657428594386608798947191961130779 +/- 5.74e-86]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D07a_CylinderDReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D07b_CylinderDCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D07_CylinderD.cs>`__. 








|newpage|

.. _rst_mpm_pcfu: 

Parabolic cylinder function `U(a, x)`
-------------------------------------------------------------------------------

.. method:: ctx.pcfu(a, x)

    Returns the parabolic cylinder function `U(a, x)`.

    See also: MathWorld :cite:p:`WolframFun1057`,  Wikipedia :cite:p:`WikipediaFun1057`, :cite:t:`Ehrhardt2018` (3.8.11.2), NIST :cite:p:`DLMFun1057`, Mpmath :cite:p:`MpmathFun1058`.

    The function is defined, for arbitrary `z`, as


    .. math ::  U\left(a,z\right)=U\left(a,0\right)u_{1}(a,z)+U'\left(a,0\right)u_{2}(a,z),


    .. math ::  u_{1}(a,z)=e^{-\tfrac{1}{4}z^{2}} \,_1F_1\left(\tfrac{1}{2}a+\tfrac{1}{4},\tfrac{1}{2},\tfrac{1}{2}z^{2}\right)=e^{\tfrac{1}{4}z^{2}} \,_1F_1\left(-\tfrac{1}{2}a+\tfrac{1}{4},\tfrac{1}{2},-\tfrac{1}{2}z^{2}\right),


    .. math :: u_{2}(a,z)=ze^{-\tfrac{1}{4}z^{2}} \,_1F_1\left(\tfrac{1}{2}a+\tfrac{3}{4},\tfrac{3}{2},\tfrac{1}{2}z^{2}\right)=ze^{\tfrac{1}{4}z^{2}} \,_1F_1\left(-\tfrac{1}{2}a+\tfrac{3}{4},\tfrac{3}{2},-\tfrac{1}{2}z^{2}\right).


    .. math :: U\left(a,0\right)=\frac{\sqrt{\pi}}{2^{\frac{1}{2}a+\frac{1}{4}}\Gamma\left(\frac{3}{4}+\frac{1}{2}a\right)}, \quad \text{and } U'\left(a,0\right)=-\frac{\sqrt{\pi}}{2^{\frac{1}{2}a-\frac{1}{4}}\Gamma\left(\frac{1}{4}+\frac{1}{2}a\right)},





    For `\Re(z) > 0`, the function may be in terms of the confluent U-function (see :ref:`hyperu() <rst_mpm_hyperu>`) by


    .. math :: U(a,z) = 2^{-\frac{1}{4}-\frac{a}{2}} e^{-\frac{1}{4} z^2} U\left(\frac{a}{2}+\frac{1}{4}, \frac{1}{2}, \frac{1}{2}z^2\right)




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 1.5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.pcfu(a, x)))
        fpm:  0.0164414733965039
        mpm:  0.0164414733965039477438676029072587944961459494133193797704852070748879605831436985863363827
        dpm:  0.0164414733965039477438676029072587944961459494133193797704852070748879605831436985863363827
        gpm:  0.016441473396503947743867602907258794496145949413319379770485207074887960583143698586336382701
        apm: [0.0164414733965039477438676029072587944961459494133193797704852070748879605831436985863364 +/- 7.37e-89]
     math53:  0.016441473396504
     sflint:  0.01644147
     dflint:  0.0164414733965039
     eflint:  0.016441473396503947743
     qflint:  0.0164414733965039477438676029072588
     oflint:  0.016441473396503947743867602907258794496145949413319379770485207074887961
     mflint:  0.0164414733965039477438676029072587944961459494133193797704852070748879605831436985863363827
     aflint: [0.0164414733965039477438676029072587944961459494133193797704852070748879605831436985863364 +/- 6.27e-89]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.pcfu(a, x)))
        fpm:  (64.5636072062979, 94.3801136664775)
        mpm:  (64.563607206297915881118665925636845216105371461904, 94.380113666477483214704511005918123429233342094829)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.pcfu(a, x))))
        fpm:  64.5636072062979
        mpm:  64.5636072062979158811186659256368452161053714619040361873424633655491150647395150813217056
        dpm:  64.5636072062979158811186659256368452161053714619040361873424633655491150647395150813217056
        gpm:  64.563607206297915881118665925636845216105371461904036187342463365549115064739515081321705599
        apm: [64.56360720629791588111866592563684521610537146190403618734246336554911506473951508132171 +/- 6.47e-87]
    cmath53:  NaN
    sflintc:  64.56361
    dflintc:  64.5636072062979
    eflintc:  64.563607206297915886
    qflintc:  64.5636072062979158811186659256369
    oflintc:  64.563607206297915881118665925636845216105371461904036187342463365549115
    mflintc:  64.5636072062979158811186659256368452161053714619040361873424633655491150647395150813217057
    aflintc: [64.56360720629791588111866592563684521610537146190403618734246336554911506473951508132171 +/- 5.96e-87]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.pcfu(a, x))))
        fpm:  94.3801136664775
        mpm:  94.3801136664774832147045110059181234292333420948306917757188561450140347174909117664635532
        dpm:  94.3801136664774832147045110059181234292333420948306917757188561450140347174909117664635532
        gpm:  94.380113666477483214704511005918123429233342094830691775718856145014034717490911766463553201
        apm: [94.38011366647748321470451100591812342923334209483069177571885614501403471749091176646355 +/- 5.09e-87]
    cmath53:  NaN
    sflintc:  94.38009
    dflintc:  94.3801136664775
    eflintc:  94.380113666477483188
    qflintc:  94.380113666477483214704511005918
    oflintc:  94.380113666477483214704511005918123429233342094830691775718856145014035
    mflintc:  94.3801136664774832147045110059181234292333420948306917757188561450140347174909117664635529
    aflintc: [94.38011366647748321470451100591812342923334209483069177571885614501403471749091176646355 +/- 4.58e-87]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D08a_CylinderUReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D08b_CylinderUCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D08_CylinderU.cs>`__. 






|newpage|

Parabolic cylinder function `V(a,x)`
-------------------------------------------------------------------------------

.. method:: ctx.pcfv(a, x)

    Returns the  parabolic cylinder function `\displaystyle V(a,x)`, which can be
    represented in terms of :ref:`pcfu() <rst_mpm_pcfu>` as

    .. math ::

        V(a,z) = \frac{\Gamma(a+\tfrac{1}{2}) (U(a,-z)-\sin(\pi a) U(a,z)}{\pi}.


    See also: MathWorld :cite:p:`WolframFun1057`,  Wikipedia :cite:p:`WikipediaFun1057`, :cite:t:`Ehrhardt2018` (3.8.11.3), NIST :cite:p:`DLMFun1057`, Mpmath :cite:p:`MpmathFun1059`.

    In DAMath, this is restricted to `2a \in \mathbb{Z}`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 1.5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.pcfv(a, x)))
        fpm:  13.3292440261492
        mpm:  13.3292440261492192822328203582272519422318296524267567012447561768716686874290336906408675
        dpm:  13.3292440261492192822328203582272519422318296524267567012447561768716686874290336906408675
        gpm:  13.3292440261492192822328203582272519422318296524267567012447561768716686874290336906408675
        apm: [13.3397109932002892699158488661772105288236609897090884783592001596614909226174117930219098 +/- 8.68e-89]
     math53:  13.3292440261492
     sflint:  13.33971
     dflint:  13.3397109932003
     eflint:  13.339710993200289271
     qflint:  13.3397109932002892699158488661772
     oflint:  13.339710993200289269915848866177210528823660989709088478359200159661491
     mflint:  13.3397109932002892699158488661772105288236609897090884783592001596614909226174117930219098
     aflint: [13.339710993200289269915848866177210528823660989709088478359200159661490922617411793021910 +/- 3.06e-88]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.pcfv(a, x)))
        fpm:  (-1.53428479303462, 1.04769917580707)
        mpm:  (-1.534284793034621400823381695357521673626482900735, 1.0476991758070663034529873136696117993730950661251)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.pcfv(a, x))))
        fpm:  -1.53428479303462
        mpm:  -1.53428479303462140082338169535752167362648290073499306526636390693895118796071668166374964
        dpm:  -1.53428479303462140082338169535752167362648290073499306526636390693895118796071668166374964
        gpm:  -1.5342847930346214008233816953575216736264829007349930652663639069389511879607166816637496401
        apm: [-7.544158780829613708531011026779542505940657026601404848391992542458792952742656861844001 +/- 7.46e-88]
    cmath53:  NaN
    sflintc:  -7.544154
    dflintc:  -7.54415878082961
    eflintc:  -7.544158780829613704
    qflintc:  -7.54415878082961370853101102677953
    oflintc:  -7.544158780829613708531011026779542505940657026601404848391992542458793
    mflintc:  -7.5441587808296137085310110267795425059406570266014048483919925424587929527426568618440007
    aflintc: [-7.54415878082961370853101102677954250594065702660140484839199254245879295274265686184400 +/- 1.27e-87]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.pcfv(a, x))))
        fpm:  1.04769917580707
        mpm:  1.04769917580706630345298731366961179937309506612504351507834083598705349412257137988770863
        dpm:  1.04769917580706630345298731366961179937309506612504351507834083598705349412257137988770863
        gpm:  1.04769917580706630345298731366961179937309506612504351507834083598705349412257137988770863
        apm: [-7.737630743521982830575163603385261178462135244096592810245419480593000763986558156213140 +/- 6.74e-88]
    cmath53:  NaN
    sflintc:  -7.73762
    dflintc:  -7.73763074352198
    eflintc:  -7.7376307435219828209
    qflintc:  -7.73763074352198283057516360338523
    oflintc:  -7.7376307435219828305751636033852611784621352440965928102454194805930008
    mflintc:  -7.73763074352198283057516360338526117846213524409659281024541948059300076398655815621314021
    aflintc: [-7.737630743521982830575163603385261178462135244096592810245419480593000763986558156213140 +/- 9.46e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D09a_CylinderVReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D09b_CylinderVCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D09_CylinderV.cs>`__. 








|newpage|

.. _rst_mpm_pcfw: 

Parabolic cylinder function `W(a,x)`
-------------------------------------------------------------------------------

.. method:: ctx.pcfw(a, z)


    Returns the parabolic cylinder function `W(a,z)`.  See also  Wikipedia :cite:p:`WikipediaFun1057`, MathWorld :cite:p:`WolframFun1057`, NIST :cite:p:`DLMFun1057`, Mpmath :cite:p:`MpmathFun1060`.

    The function is defined as


    .. math :: W\left(a,x\right)=W\left(a,0\right)w_{1}(a,x)+W'\left(a,0\right)w_{2}(a,x).

    .. math :: W\left(a,0\right)=2^{-\frac{3}{4}}\left|\frac{\Gamma\left(\tfrac{1}{4}+\tfrac{1}{2}ia\right)}{\Gamma\left(\tfrac{3}{4}+\tfrac{1}{2}ia\right)}\right|^{\frac{1}{2}}, \quad  W'\left(a,0\right)=-2^{-\frac{1}{4}}\left|\frac{\Gamma\left(\tfrac{3}{4}+\tfrac{1}{2}ia\right)}{\Gamma\left(\tfrac{1}{4}+\tfrac{1}{2}ia\right)}\right|^{\frac{1}{2}}.

    .. math :: w_{1}(a,x)=e^{-\frac{1}{4}ix^{2}} \,_1F_1\left(\tfrac{1}{4}-\tfrac{1}{2}ia,\tfrac{1}{2},\tfrac{1}{2}ix^{2}\right), \quad  w_{2}(a,x)=xe^{-\frac{1}{4}ix^{2}} \,_1F_1\left(\tfrac{3}{4}-\tfrac{1}{2}ia,\tfrac{3}{2},\tfrac{1}{2}ix^{2}\right).


    The function can also be represented as


    .. math ::

        W\left(a,x\right) = \sqrt{k/2}\,e^{\frac{1}{4}\pi a} \left[e^{i\rho} U\left(ia,xe^{-\pi i/4}\right)  +  e^{-i\rho} U\left(-ia,xe^{\pi i/4}\right) \right].



An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = 1.5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.pcfw(a, x)))
        fpm:  0.0554599157078833
        mpm:  0.0554599157078832884700460788626779371166131022146535257889240218214541927607290757482162533
        dpm:  0.0554599157078832884700460788626779371166131022146535257889240218214541927607290757482162533
        gpm:  0.0554599157078832884700460788626779371166131022146535257889240218214541927607290757482162533
        apm: [0.055459915707883288470046078862677937116613102214653525788924021821454192760729075748216 +/- 3.98e-88]
     math53:  NaN
     sflint:  0.05545991
     dflint:  0.0554599157078833
     eflint:  0.055459915707883288469
     qflint:  0.0554599157078832884700460788626779
     oflint:  0.055459915707883288470046078862677937116613102214653525788924021821454193
     mflint:  0.0554599157078832884700460788626779371166131022146535257889240218214541927607290757482162533
     aflint: [0.055459915707883288470046078862677937116613102214653525788924021821454192760729075748216 +/- 3.70e-88]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.pcfw(a, x)))
        fpm:  (47.9035135597494, -26.9728420233505)
        mpm:  (47.903513559749422160651860184487410853024064426131, -26.972842023350458978476319241700599779773330880745)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.pcfw(a, x))))
        fpm:  47.9035135597494
        mpm:  47.9035135597494221606518601844874108530240644261311401523670725449095827620024894310141237
        dpm:  47.9035135597494221606518601844874108530240644261311401523670725449095827620024894310141237
        gpm:  47.9035135597494221606518601844874108530240644261311401523670725449095827620024894310141237
        apm: [47.90351355974942216065186018448741085302406442613114015236707254490958276200248943101412 +/- 6.50e-87]
    cmath53:  NaN
    sflintc:  47.90351
    dflintc:  47.9035135597494
    eflintc:  47.903513559749422157
    qflintc:  47.9035135597494221606518601844874
    oflintc:  47.903513559749422160651860184487410853024064426131140152367072544909583
    mflintc:  47.9035135597494221606518601844874108530240644261311401523670725449095827620024894310141236
    aflintc: [47.90351355974942216065186018448741085302406442613114015236707254490958276200248943101412 +/- 5.92e-87]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> a = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.pcfw(a, x))))
        fpm:  -26.9728420233505
        mpm:  -26.9728420233504589784763192417005997797733308807448726846675673865520151501715854417318441
        dpm:  -26.9728420233504589784763192417005997797733308807448726846675673865520151501715854417318441
        gpm:  -26.9728420233504589784763192417005997797733308807448726846675673865520151501715854417318441
        apm: [-26.97284202335045897847631924170059977977333088074487268466756738655201515017158544173184 +/- 6.78e-87]
    cmath53:  NaN
    sflintc:  -26.97285
    dflintc:  -26.9728420233505
    eflintc:  -26.972842023350458981
    qflintc:  -26.9728420233504589784763192417006
    oflintc:  -26.972842023350458978476319241700599779773330880744872684667567386552015
    mflintc:  -26.9728420233504589784763192417005997797733308807448726846675673865520151501715854417318441
    aflintc: [-26.97284202335045897847631924170059977977333088074487268466756738655201515017158544173184 +/- 6.31e-87]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D10a_CylinderWReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C03_CoulombPcf/D10b_CylinderWCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C03_CoulombPcf/D10_CylinderW.cs>`__. 





