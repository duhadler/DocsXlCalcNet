

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Jacobi theta functions and related functions
===============================================================================



The theta functions are functions of two variables:

* `z` is the *argument*, an arbitrary real or complex number

* `q` is the *nome*, which must be a real or complex number
  in the unit disk (i.e. `|q| < 1`). For `|q| \ll 1`, the
  series converge very quickly, so the Jacobi theta functions
  can efficiently be evaluated to high precision.

The compact notations `\theta_n(q) = \theta_n(0,q)`
and `\theta_n = \theta_n(0,q)` are also frequently
encountered. Finally, Jacobi theta functions are frequently
considered as functions of the half-period ratio `\tau`
and then usually denoted by `\theta_n(z|\tau)`.




Jacobi theta function `\theta_1(z, q)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_theta1(x, q)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the Jacobi theta function `\displaystyle  \theta_1(z,q) = 2 q^{1/4} \sum_{n=0}^{\infty} (-1)^n q^{n^2+n\,} \sin((2n+1)z)` 

    Note: the Amath version needs to be adapted.



    |JacobiTheta1|

    .. |JacobiTheta1| image:: ../_static/ExplicitSurfaces/RealFunctions/JacobiTheta1.3D.xml.jpg
       :width: 30 %


   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    See also Wikipedia :cite:p:`WikipediaFun170`, MathWorld :cite:p:`WolframFun170`, MathWorld :cite:p:`WolframFun170a`, NIST :cite:p:`DLMFun170`, :cite:t:`Ehrhardt2018` (3.2.13), Flint :cite:p:`FlintFun170`.


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -1.5; q = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_theta1(x, q)))
            fpm:  -2.11359196642346
            mpm:  -2.11359196642346138066904857916181790184266045594995231683646916266980968688255037484693934
            dpm:  -2.11359196642346138066904857916181790184266045594995231683646916266980968688255037484693934
            gpm:  -2.11359196642346138066904857916181790184266045594995231683646916266980968688255037484693934
            apm: [-2.1135919664234613806690485791618179018426604559499523168364691626698096868825503748469393 +/- 7.76e-89]
         math53:  -2.11359196642346
          sreal:  -2.113592
          dreal:  -2.11359196642346
          ereal:  -2.1135919664234613807
          qreal:  -2.11359196642346138066904857916182
          oreal:  -2.1135919664234613806690485791618179018426604559499523168364691626698097
          mreal:  -2.11359196642346138066904857916181790184266045594995231683646916266980968688255037484693934
         sflint:  -2.113592
         dflint:  -2.11359196642346
         eflint:  -2.1135919664234613807
         qflint:  -2.11359196642346138066904857916182
         oflint:  -2.1135919664234613806690485791618179018426604559499523168364691626698097
         mflint:  -2.11359196642346138066904857916181790184266045594995231683646916266980968688255037484693933
         aflint: [-2.113591966423461380669048579161817901842660455949952316836469162669809686882550374846939 +/- 4.90e-88]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_theta1(x, q)))
            fpm:  (-50.780836605528, 124.989381403456)
            mpm:  (-50.78083660552799331037816040836444156409, 124.9893814034556349615115347045906543912)
        cmath53:  (-50.7808366055273, 124.989381403456)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_theta1(x, q)))))
            fpm:  -50.780836605528
            mpm:  -50.7808366055279933103781604083644415640894604639170041582783080926866965607619206945120548
            dpm:  -50.7808366055279933103781604083644415640894604639170041582783080926866965607619206945120548
            gpm:  -50.780836605527993310378160408364441564089460463917004158278308092686696560761920694512054802
            apm: [-50.7808366055279933103781604083644415640894604639170041582783080926866965607619206945121 +/- 5.76e-86]
        cmath53:  -50.7808366055273
        sflintc:  -50.78085
        dflintc:  -50.7808366055281
        eflintc:  -50.780836605527993326
        qflintc:  -50.7808366055279933103781604083645
        oflintc:  -50.780836605527993310378160408364441564089460463917004158278308092686699
        mflintc:  -50.7808366055279933103781604083644415640894604639170041582783080926866965607619206945120544
        aflintc: [-50.7808366055279933103781604083644415640894604639170041582783080926866965607619206945121 +/- 9.10e-86]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_theta1(x, q))))
            fpm:  124.989381403456
            mpm:  124.989381403455634961511534704590654391193462966251350143993404798085540658482487179649021
            dpm:  124.989381403455634961511534704590654391193462966251350143993404798085540658482487179649021
            gpm:  124.98938140345563496151153470459065439119346296625135014399340479808554065848248717964902101
            apm: [124.9893814034556349615115347045906543911934629662513501439934047980855406584824871796490 +/- 3.23e-86]
        cmath53:  124.989381403456
        sflintc:  124.9894
        dflintc:  124.989381403456
        eflintc:  124.98938140345563497
        qflintc:  124.989381403455634961511534704591
        oflintc:  124.98938140345563496151153470459065439119346296625135014399340479808554
        mflintc:  124.98938140345563496151153470459065439119346296625135014399340479808554065848248717964902
        aflintc: [124.9893814034556349615115347045906543911934629662513501439934047980855406584824871796490 +/- 6.51e-86]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C05_JacobiThetafunctions/D01a_JacobiTheta1Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C05_JacobiThetafunctions/D01b_JacobiTheta1Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C05_JacobiThetafunctions/D01_JacobiTheta1.cs>`__. 





|newpage|

Jacobi theta function `\theta_2(z, q)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_theta2(x, q)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the Jacobi theta function `\displaystyle  \theta_2(z,q) = 2 q^{1/4} \sum_{n=0}^{\infty} q^{n^{2\,} + n} \cos((2n+1)z)` 


    Note: the Amath version needs to be adapted.



    |JacobiTheta2|

    .. |JacobiTheta2| image:: ../_static/ExplicitSurfaces/RealFunctions/JacobiTheta2.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.






    See also Wikipedia :cite:p:`WikipediaFun170`, MathWorld :cite:p:`WolframFun170`, MathWorld :cite:p:`WolframFun170a`, NIST :cite:p:`DLMFun170`, :cite:t:`Ehrhardt2018` (3.2.13), Flint :cite:p:`FlintFun170`.


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -1.5; q = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_theta2(x, q)))
            fpm:  0.0392511904453161
            mpm:  0.0392511904453160541241090737285952043842825247841919631803697983896127042847128388887346914
            dpm:  0.0392511904453160541241090737285952043842825247841919631803697983896127042847128388887346914
            gpm:  0.039251190445316054124109073728595204384282524784191963180369798389612704284712838888734691399
            apm: [0.03925119044531605412410907372859520438428252478419196318036979838961270428471283888873469 +/- 3.05e-90]
         math53:  0.039251190445316
          sreal:  0.03925122
          dreal:  0.039251190445316
          ereal:  0.039251190445316054144
          qreal:  0.0392511904453160541241090737285952
          oreal:  0.039251190445316054124109073728595204384282524784191963180369798389612703
          mreal:  0.0392511904453160541241090737285952043842825247841919631803697983896127042847128388887346915
         sflint:  0.03925119
         dflint:  0.0392511904453161
         eflint:  0.039251190445316054124
         qflint:  0.0392511904453160541241090737285952
         oflint:  0.039251190445316054124109073728595204384282524784191963180369798389612704
         mflint:  0.0392511904453160541241090737285952043842825247841919631803697983896127042847128388887346925
         aflint: [0.03925119044531605412410907372859520438428252478419196318036979838961270428471283888873469 +/- 9.18e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_theta2(x, q)))
            fpm:  (-788.730030824563, -973.103865381616)
            mpm:  (-788.730030824562882021701528729479717359, -973.1038653816155973430758747938973577377)
        cmath53:  (-788.730030824566, -973.103865381615)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_theta2(x, q)))))
            fpm:  -788.730030824563
            mpm:  -788.730030824562882021701528729479717359057533221038303968344425731569663005345603872930402
            dpm:  -788.730030824562882021701528729479717359057533221038303968344425731569663005345603872930402
            gpm:  -788.73003082456288202170152872947971735905753322103830396834442573156966300534560387293040204
            apm: [-788.7300308245628820217015287294797173590575332210383039683444257315696630053456038729304 +/- 3.73e-86]
        cmath53:  -788.730030824566
        sflintc:  -788.73
        dflintc:  -788.730030824563
        eflintc:  -788.73003082456288199
        qflintc:  -788.73003082456288202170152872948
        oflintc:  -788.73003082456288202170152872947971735905753322103830396834442573156965
        mflintc:  -788.730030824562882021701528729479717359057533221038303968344425731569663005345603872930394
        aflintc: [-788.730030824562882021701528729479717359057533221038303968344425731569663005345603872930 +/- 5.33e-85]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_theta2(x, q))))
            fpm:  -973.103865381616
            mpm:  -973.103865381615597343075874793897357737695783789144158174270424078377380553945366633288522
            dpm:  -973.103865381615597343075874793897357737695783789144158174270424078377380553945366633288522
            gpm:  -973.10386538161559734307587479389735773769578378914415817427042407837738055394536663328852196
            apm: [-973.1038653816155973430758747938973577376957837891441581742704240783773805539453666332885 +/- 5.46e-86]
        cmath53:  -973.103865381615
        sflintc:  -973.1039
        dflintc:  -973.103865381616
        eflintc:  -973.10386538161559739
        qflintc:  -973.103865381615597343075874793897
        oflintc:  -973.10386538161559734307587479389735773769578378914415817427042407837739
        mflintc:  -973.103865381615597343075874793897357737695783789144158174270424078377380553945366633288514
        aflintc: [-973.103865381615597343075874793897357737695783789144158174270424078377380553945366633289 +/- 6.22e-85]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C05_JacobiThetafunctions/D02a_JacobiTheta2Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C05_JacobiThetafunctions/D02b_JacobiTheta2Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C05_JacobiThetafunctions/D02_JacobiTheta2.cs>`__. 









|newpage|

Jacobi theta function `\theta_3(z, q)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_theta3(x, q)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.


    Returns the Jacobi theta function `\displaystyle  \theta_3(z,q) = 1 + 2 \sum_{n=1}^{\infty} q^{n^2\,} \cos(2 n z)` 



    Note: the Amath version needs to be adapted.



    |JacobiTheta3|

    .. |JacobiTheta3| image:: ../_static/ExplicitSurfaces/RealFunctions/JacobiTheta3.3D.xml.jpg
       :width: 30 %


   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.






    See also Wikipedia :cite:p:`WikipediaFun170`, MathWorld :cite:p:`WolframFun170`, MathWorld :cite:p:`WolframFun170a`, NIST :cite:p:`DLMFun170`, :cite:t:`Ehrhardt2018` (3.2.13), Flint :cite:p:`FlintFun170`.


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -1.5; q = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_theta3(x, q)))
            fpm:  0.126495393762763
            mpm:  0.126495393762762598701888433352100380638483071560362656246275916619695793139049359803626692
            dpm:  0.126495393762762598701888433352100380638483071560362656246275916619695793139049359803626692
            gpm:  0.126495393762762598701888433352100380638483071560362656246275916619695793139049359803626692
            apm: [0.12649539376276259870188843335210038063848307156036265624627591661969579313904935980362669 +/- 3.48e-90]
         math53:  0.126495393762763
          sreal:  0.1264954
          dreal:  0.126495393762763
          ereal:  0.12649539376276259869
          qreal:  0.1264953937627625987018884333521
          oreal:  0.12649539376276259870188843335210038063848307156036265624627591661969579
          mreal:  0.126495393762762598701888433352100380638483071560362656246275916619695793139049359803626691
         sflint:  0.1264954
         dflint:  0.126495393762763
         eflint:  0.1264953937627625987
         qflint:  0.1264953937627625987018884333521
         oflint:  0.12649539376276259870188843335210038063848307156036265624627591661969579
         mflint:  0.126495393762762598701888433352100380638483071560362656246275916619695793139049359803626691
         aflint: [0.1264953937627625987018884333521003806384830715603626562462759166196957931390493598036267 +/- 1.82e-89]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_theta3(x, q)))
            fpm:  (-788.853981893901, -973.061264832878)
            mpm:  (-788.8539818939012432600295903235863318626, -973.0612648328778632847669709840011675127)
        cmath53:  (-788.853981893904, -973.061264832879)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_theta3(x, q)))))
            fpm:  -788.853981893901
            mpm:  -788.853981893901243260029590323586331862572558924085902768235801520210016453593987078971379
            dpm:  -788.853981893901243260029590323586331862572558924085902768235801520210016453593987078971379
            gpm:  -788.85398189390124326002959032358633186257255892408590276823580152021001645359398707897137906
            apm: [-788.8539818939012432600295903235863318625725589240859027682358015202100164535939870789714 +/- 6.04e-86]
        cmath53:  -788.853981893904
        sflintc:  -788.8539
        dflintc:  -788.853981893901
        eflintc:  -788.85398189390124324
        qflintc:  -788.853981893901243260029590323586
        oflintc:  -788.85398189390124326002959032358633186257255892408590276823580152021001
        mflintc:  -788.853981893901243260029590323586331862572558924085902768235801520210016453593987078971371
        aflintc: [-788.853981893901243260029590323586331862572558924085902768235801520210016453593987078971 +/- 5.11e-85]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_theta3(x, q))))
            fpm:  -973.061264832878
            mpm:  -973.061264832877863284766970984001167512672246578896662701689828132385101085389051573377376
            dpm:  -973.061264832877863284766970984001167512672246578896662701689828132385101085389051573377376
            gpm:  -973.06126483287786328476697098400116751267224657889666270168982813238510108538905157337737601
            apm: [-973.0612648328778632847669709840011675126722465788966627016898281323851010853890515733774 +/- 6.32e-86]
        cmath53:  -973.061264832879
        sflintc:  -973.0613
        dflintc:  -973.061264832878
        eflintc:  -973.06126483287786333
        qflintc:  -973.061264832877863284766970984001
        oflintc:  -973.06126483287786328476697098400116751267224657889666270168982813238511
        mflintc:  -973.061264832877863284766970984001167512672246578896662701689828132385101085389051573377368
        aflintc: [-973.061264832877863284766970984001167512672246578896662701689828132385101085389051573377 +/- 5.05e-85]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C05_JacobiThetafunctions/D03a_JacobiTheta3Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C05_JacobiThetafunctions/D03b_JacobiTheta3Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C05_JacobiThetafunctions/D03_JacobiTheta3.cs>`__. 












|newpage|

Jacobi theta function `\theta_4(z, q)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_theta4(x, q)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the Jacobi theta function `\displaystyle  \theta_4(z,q) = 1 + 2 \sum_{n=1}^{\infty} (-q)^{n^2\,} \cos(2 n z)` 


    Note: the Amath version needs to be adapted.



    |JacobiTheta4|

    .. |JacobiTheta4| image:: ../_static/ExplicitSurfaces/RealFunctions/JacobiTheta4.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    See also Wikipedia :cite:p:`WikipediaFun170`, MathWorld :cite:p:`WolframFun170`, MathWorld :cite:p:`WolframFun170a`, NIST :cite:p:`DLMFun170`, :cite:t:`Ehrhardt2018` (3.2.13), Flint :cite:p:`FlintFun170`.


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -1.5; q = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_theta4(x, q)))
            fpm:  2.11359868269649
            mpm:  2.11359868269648781628303165240842491940069427464811703149818811558563778179460529781768584
            dpm:  2.11359868269648781628303165240842491940069427464811703149818811558563778179460529781768584
            gpm:  2.1135986826964878162830316524084249194006942746481170314981881155856377817946052978176858401
            apm: [2.1135986826964878162830316524084249194006942746481170314981881155856377817946052978176858 +/- 7.57e-89]
         math53:  2.11359868269649
          sreal:  2.113599
          dreal:  2.11359868269649
          ereal:  2.1135986826964878163
          qreal:  2.11359868269648781628303165240842
          oreal:  2.1135986826964878162830316524084249194006942746481170314981881155856378
          mreal:  2.11359868269648781628303165240842491940069427464811703149818811558563778179460529781768584
         sflint:  2.113599
         dflint:  2.11359868269649
         eflint:  2.1135986826964878163
         qflint:  2.11359868269648781628303165240842
         oflint:  2.1135986826964878162830316524084249194006942746481170314981881155856378
         mflint:  2.11359868269648781628303165240842491940069427464811703149818811558563778179460529781768583
         aflint: [2.113598682696487816283031652408424919400694274648117031498188115585637781794605297817686 +/- 3.37e-88]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_theta4(x, q)))
            fpm:  (97.0420581423974, -162.552773270404)
            mpm:  (97.04205814239744070936237059955972078898, -162.5527732704038409081633683852591175902)
        cmath53:  (97.0420581423972, -162.552773270404)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_theta4(x, q)))))
            fpm:  97.0420581423974
            mpm:  97.0420581423974407093623705995597207889784394122898731971128570177755528004071376783754542
            dpm:  97.0420581423974407093623705995597207889784394122898731971128570177755528004071376783754542
            gpm:  97.042058142397440709362370599559720788978439412289873197112857017775552800407137678375454201
            apm: [97.0420581423974407093623705995597207889784394122898731971128570177755528004071376783755 +/- 6.04e-86]
        cmath53:  97.0420581423972
        sflintc:  97.04208
        dflintc:  97.0420581423975
        eflintc:  97.042058142397440726
        qflintc:  97.0420581423974407093623705995598
        oflintc:  97.042058142397440709362370599559720788978439412289873197112857017775555
        mflintc:  97.0420581423974407093623705995597207889784394122898731971128570177755528004071376783754532
        aflintc: [97.042058142397440709362370599559720788978439412289873197112857017775552800407137678375 +/- 5.07e-85]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.0+2j;  q = 0.5+0.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_theta4(x, q))))
            fpm:  -162.552773270404
            mpm:  -162.552773270403840908163368385259117590182379208164746903702433461088193073238559000409487
            dpm:  -162.552773270403840908163368385259117590182379208164746903702433461088193073238559000409487
            gpm:  -162.552773270403840908163368385259117590182379208164746903702433461088193073238559000409487
            apm: [-162.5527732704038409081633683852591175901823792081647469037024334610881930732385590004095 +/- 2.86e-86]
        cmath53:  -162.552773270404
        sflintc:  -162.5528
        dflintc:  -162.552773270404
        eflintc:  -162.55277327040384092
        qflintc:  -162.552773270403840908163368385259
        oflintc:  -162.55277327040384090816336838525911759018237920816474690370243346108819
        mflintc:  -162.552773270403840908163368385259117590182379208164746903702433461088193073238559000409485
        aflintc: [-162.5527732704038409081633683852591175901823792081647469037024334610881930732385590004095 +/- 6.86e-86]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C05_JacobiThetafunctions/D04a_JacobiTheta4Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C05_JacobiThetafunctions/D04b_JacobiTheta4Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C05_JacobiThetafunctions/D04_JacobiTheta4.cs>`__. 








