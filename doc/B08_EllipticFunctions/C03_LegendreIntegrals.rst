

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />



|newpage|



Legendre elliptic integrals (elliptic modulus  `k`), and related functions
===============================================================================


For an overview see NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun148a`, Mpmath :cite:p:`MpmathFun148`. 



Legendre complete elliptic integral of the first kind, `K(k)`
-------------------------------------------------------------------------------

.. method:: ctx.elliptic_k(k)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxboost`` or ``ctxflint``.

    Returns the Legendre complete elliptic integral of the first kind,  `\displaystyle  K(k) = \int_0^{\pi/2} \frac{\mathrm{d}t}{\sqrt{1-k^2 \sin^2(t)}}`. See also  Wikipedia :cite:p:`WikipediaFun148`, MathWorld :cite:p:`WolframFun148`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun148`, :cite:t:`Ehrhardt2018` (3.2.1.2), :cite:t:`Ehrhardt2018` (4.2.30), Flint :cite:p:`FlintFun148`.

    

    |02a_TestEllk_re| `\quad` |02b_TestEllk_im| `\quad` |02c_TestEllk_abs|

    .. |02a_TestEllk_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/02a_TestEllk_re.3D.xml.jpg
       :width: 30 %

    .. |02b_TestEllk_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/02b_TestEllk_im.3D.xml.jpg
       :width: 30 %

    .. |02c_TestEllk_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/02c_TestEllk_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.



    
    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> k = 0.999; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_k(k)))
            fpm:  4.49559639584215
            mpm:  4.49559639584214417041360886203458158904715046937920055631301185630531198665310542012881672
            dpm:  4.49559639584214417041360886203458158904715046937920055631301185630531198665310542012881672
            gpm:  4.4955963958421441704136088620345815890471504693792005563130118563053119866531054201288167205
            apm: [4.495596395842144170413608862034581589047150469379200556313011856305311986653105420128817 +/- 4.10e-88]
         math53:  4.49559639584214
          sreal:  4.495603
          dreal:  4.49559639584215
          ereal:  4.4955963958421441659
          qreal:  4.49559639584214417041360886203458
          oreal:  4.4955963958421441704136088620345815890471504693792005563130118563053135
          mreal:  4.49559639584214417041360886203458158904715046937920055631301185630531198665310542012881684
         sflint:  4.495603
         dflint:  4.49559639584214
         eflint:  4.4955963958421441599
         qflint:  4.49559639584214417041360886203459
         oflint:  4.495596395842144170413608862034581589047150469379200556313011856305313
         mflint:  4.49559639584214417041360886203458158904715046937920055631301185630531198665310542012881679
         aflint: [4.495596395842144170413608862034581589047150469379200556313011856305311986653105420128817 +/- 4.56e-88]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> k = -5.1+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_k(k)))
            fpm:  (0.412861138519898, -0.444537001058635)
            mpm:  (0.4128611385198979320456432895510981582772, -0.4445370010586351730493198205023989255495)
        cmath53:  (0.412861138519898, -0.444537001058635)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> k = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_k(k))))
            fpm:  0.412861138519898
            mpm:  0.412861138519897932045643289551098158277235079565048658055536991689482633134708022507716961
            dpm:  0.412861138519897932045643289551098158277235079565048658055536991689482633134708022507716961
            gpm:  0.41286113851989793204564328955109815827723507956504865805553699168948263313470802250771696102
            apm: [0.41286113851989793204564328955109815827723507956504865805553699168948263313470802250771696 +/- 4.46e-90]
        cmath53:  0.412861138519898
        sflintc:  0.4128611
        dflintc:  0.412861138519898
        eflintc:  0.41286113851989793204
        qflintc:  0.412861138519897932045643289551098
        oflintc:  0.41286113851989793204564328955109815827723507956504865805553699168948263
        mflintc:  0.412861138519897932045643289551098158277235079565048658055536991689482633134708022507716961
        aflintc: [0.4128611385198979320456432895510981582772350795650486580555369916894826331347080225077170 +/- 5.07e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> k = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_k(k))))
            fpm:  -0.444537001058635
            mpm:  -0.444537001058635173049319820502398925549486846080510291919369830510892776823978056317419785
            dpm:  -0.444537001058635173049319820502398925549486846080510291919369830510892776823978056317419785
            gpm:  -0.44453700105863517304931982050239892554948684608051029191936983051089277682397805631741978503
            apm: [-0.44453700105863517304931982050239892554948684608051029191936983051089277682397805631741979 +/- 9.22e-90]
        cmath53:  -0.444537001058635
        sflintc:  -0.444537
        dflintc:  -0.444537001058635
        eflintc:  -0.44453700105863517306
        qflintc:  -0.444537001058635173049319820502399
        oflintc:  -0.44453700105863517304931982050239892554948684608051029191936983051089278
        mflintc:  -0.444537001058635173049319820502398925549486846080510291919369830510892776823978056317419785
        aflintc: [-0.4445370010586351730493198205023989255494868460805102919193698305108927768239780563174198 +/- 2.83e-89]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C03_LegendreIntegrals/D01a_EllipticKReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C03_LegendreIntegrals/D01b_EllipticKCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C03_LegendreIntegrals/D01_EllipticK.cs>`__. 








Legendre complete elliptic integral of the second kind, `E(k)`
-------------------------------------------------------------------------------

.. method:: ctx.elliptic_e(k)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxboost`` or ``ctxflint``.

    Note: the original names are: ctx.compEllint2(k), ctxboost.Ellint_2_K(k), mathc53.Elle(k), ctx.ellipticE(k).

    Returns the Legendre complete elliptic integral of the  second kind,  `\displaystyle  E(k) = \int_0^{\pi/2} \sqrt{1-k^2 \sin^2(t)} \, \mathrm{d}t`. See also Wikipedia :cite:p:`WikipediaFun149`, MathWorld :cite:p:`WolframFun149`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun149`, :cite:t:`Ehrhardt2018` (3.2.1.2), :cite:t:`Ehrhardt2018` (4.2.29), Flint :cite:p:`FlintFun148`.


    

    |03a_TestElle_re| `\quad` |03b_TestElle_im| `\quad` |03c_TestElle_abs|

    .. |03a_TestElle_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/03a_TestElle_re.3D.xml.jpg
       :width: 30 %

    .. |03b_TestElle_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/03b_TestElle_im.3D.xml.jpg
       :width: 30 %

    .. |03c_TestElle_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/03c_TestElle_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.




    
    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> k = 0.999; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_e(k)))
            fpm:  1.00399440996551
            mpm:  1.00399440996550781767268799600728352603614852308212166505638202231315734265580592590943982
            dpm:  1.00399440996550781767268799600728352603614852308212166505638202231315734265580592590943982
            gpm:  1.00399440996550781767268799600728352603614852308212166505638202231315734265580592590943982
            apm: [1.0039944099655078176726879960072835260361485230821216650563820223131573426558059259094 +/- 5.07e-86]
         math53:  1.00399440996551
          sreal:  1.003994
          dreal:  1.00399440996551
          ereal:  1.0039944099655078177
          qreal:  1.00399440996550781767268799600728
          oreal:  1.0039944099655078176726879960072835260361485230821216650563820223131573
          mreal:  1.00399440996550781767268799600728352603614852308212166505638202231315734265580592590943982
         sflint:  1.003994
         dflint:  1.00399440996551
         eflint:  1.0039944099655078178
         qflint:  1.00399440996550781767268799600728
         oflint:  1.0039944099655078176726879960072835260361485230821216650563820223131573
         mflint:  1.00399440996550781767268799600728352603614852308212166505638202231315734265580592590943982
         aflint: [1.0039944099655078176726879960072835260361485230821216650563820223131573426558059259094 +/- 6.52e-86]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> k = -5.1+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_e(k)))
            fpm:  (2.22225159488477, 4.83512279534018)
            mpm:  (2.222251594884769573257301475975204316725, 4.835122795340175539106605186636290159817)
        cmath53:  (2.22225159488477, 4.83512279534017)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> k = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_e(k))))
            fpm:  2.22225159488477
            mpm:  2.22225159488476957325730147597520431672512150844049418613088716079396165476155170759789194
            dpm:  2.22225159488476957325730147597520431672512150844049418613088716079396165476155170759789194
            gpm:  2.2222515948847695732573014759752043167251215084404941861308871607939616547615517075978919398
            apm: [2.22225159488476957325730147597520431672512150844049418613088716079396165476155170759789 +/- 3.32e-87]
        cmath53:  2.22225159488477
        sflintc:  2.222252
        dflintc:  2.22225159488477
        eflintc:  2.2222515948847695732
        qflintc:  2.2222515948847695732573014759752
        oflintc:  2.2222515948847695732573014759752043167251215084404941861308871607939617
        mflintc:  2.22225159488476957325730147597520431672512150844049418613088716079396165476155170759789194
        aflintc: [2.22225159488476957325730147597520431672512150844049418613088716079396165476155170759789 +/- 5.54e-87]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> k = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_e(k))))
            fpm:  4.83512279534018
            mpm:  4.83512279534017553910660518663629015981673489459156520062835442687981582130758552870534546
            dpm:  4.83512279534017553910660518663629015981673489459156520062835442687981582130758552870534546
            gpm:  4.8351227953401755391066051866362901598167348945915652006283544268798158213075855287053454601
            apm: [4.83512279534017553910660518663629015981673489459156520062835442687981582130758552870535 +/- 5.93e-87]
        cmath53:  4.83512279534017
        sflintc:  4.835123
        dflintc:  4.83512279534018
        eflintc:  4.835122795340175539
        qflintc:  4.83512279534017553910660518663629
        oflintc:  4.8351227953401755391066051866362901598167348945915652006283544268798158
        mflintc:  4.83512279534017553910660518663629015981673489459156520062835442687981582130758552870534544
        aflintc: [4.83512279534017553910660518663629015981673489459156520062835442687981582130758552870535 +/- 8.17e-87]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C03_LegendreIntegrals/D02a_EllipticEReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C03_LegendreIntegrals/D02b_EllipticECplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C03_LegendreIntegrals/D02_EllipticE.cs>`__. 








Legendre complete elliptic integral of the third kind, `\Pi(n; k)`
--------------------------------------------------------------------------------------------

.. method:: ctx.elliptic_pi(n, k)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    The original names are: ctx.compEllint3(n, k), ctxboost.Ellint3K(n, k), ctx.ellipticPi(n, k).

    Returns the Legendre complete elliptic integral of the third kind,  `\displaystyle  \Pi(n; k) = \int_0^{\pi/2} \frac{\mathrm{d}t}{(1-n \sin^2(t)) \sqrt{1-k^2 \sin^2(t)}}`. See also Wikipedia :cite:p:`WikipediaFun150`, MathWorld :cite:p:`WolframFun150`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun150`, :cite:t:`Ehrhardt2018` (3.2.1.3), Flint :cite:p:`FlintFun148`.


    
    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.75; k = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_pi(n, k)))
            fpm:  3.45371951091874
            mpm:  3.45371951091874214022306594719053865627319351575861381897538886138475179990928975308149617
            dpm:  3.45371951091874214022306594719053865627319351575861381897538886138475179990928975308149617
            gpm:  3.4537195109187421402230659471905386562731935157586138189753888613847517999092897530814961698
            apm: [3.45371951091874214022306594719053865627319351575861381897538886138475179990928975308149617 +/- 5.24e-90]
         math53:  3.45371951091874
          sreal:  3.45372
          dreal:  3.45371951091874
          ereal:  3.4537195109187421404
          qreal:  3.45371951091874214022306594719054
          oreal:  3.4537195109187421402230659471905386562731935157586138189753888613847518
          mreal:  3.45371951091874214022306594719053865627319351575861381897538886138475179990928975308149617
         sflint:  3.45372
         dflint:  3.45371951091874
         eflint:  3.4537195109187421402
         qflint:  3.45371951091874214022306594719054
         oflint:  3.4537195109187421402230659471905386562731935157586138189753888613847518
         mflint:  3.45371951091874214022306594719053865627319351575861381897538886138475179990928975308149617
         aflint: [3.45371951091874214022306594719053865627319351575861381897538886138475179990928975308149617 +/- 6.47e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.75+2j;  k = 0.5+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_pi(n, k)))
            fpm:  (0.572779786008571, 0.459694393428125)
            mpm:  (0.5727797860085711399838294215971751329219, 0.4596943934281249923073115636907141978338)
        cmath53:  (0.572779786007243, 0.459694390754977)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.75+2j;  k = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_pi(n, k))))
            fpm:  0.572779786008571
            mpm:  0.572779786008571139983829421597175132921868213404759731927542347345700001035568506711581903
            dpm:  0.572779786008571139983829421597175132921868213404759731927542347345700001035568506711581903
            gpm:  0.57277978600857113998382942159717513292186821340475973192754234734570000103556850671158190298
            apm: [0.572779786008571139983829421597175132921868213404759731927542347345700001035568506711581903 +/- 5.85e-91]
        cmath53:  0.572779786007243
        sflintc:  0.5727798
        dflintc:  0.572779786008571
        eflintc:  0.57277978600857113996
        qflintc:  0.572779786008571139983829421597175
        oflintc:  0.5727797860085711399838294215971751329218682134047597319275423473457
        mflintc:  0.572779786008571139983829421597175132921868213404759731927542347345700001035568506711581903
        aflintc: [0.57277978600857113998382942159717513292186821340475973192754234734570000103556850671158190 +/- 4.90e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.75+2j;  k = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_pi(n, k))))
            fpm:  0.459694393428125
            mpm:  0.459694393428124992307311563690714197833789740628806464470230838567582300634465662924063705
            dpm:  0.459694393428124992307311563690714197833789740628806464470230838567582300634465662924063705
            gpm:  0.459694393428124992307311563690714197833789740628806464470230838567582300634465662924063705
            apm: [0.459694393428124992307311563690714197833789740628806464470230838567582300634465662924063705 +/- 5.18e-91]
        cmath53:  0.459694390754977
        sflintc:  0.4596944
        dflintc:  0.459694393428125
        eflintc:  0.4596943934281249923
        qflintc:  0.459694393428124992307311563690714
        oflintc:  0.4596943934281249923073115636907141978337897406288064644702308385675823
        mflintc:  0.459694393428124992307311563690714197833789740628806464470230838567582300634465662924063705
        aflintc: [0.45969439342812499230731156369071419783378974062880646447023083856758230063446566292406370 +/- 5.60e-90]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C03_LegendreIntegrals/D06a_EllipticPiIncReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C03_LegendreIntegrals/D06b_EllipticPiIncCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C03_LegendreIntegrals/D06_EllipticPiInc.cs>`__. 











Legendre incomplete elliptic integral of the first kind, `F(\phi,k)`
---------------------------------------------------------------------------------------------

.. method:: ctx.elliptic_f(phi, k)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    The original names are: ctx.ellint1(phi, k), ctxboost.Ellint1F(phi, k), ctx.ellipticF(phi, k),

    Returns the Legendre incomplete elliptic integral of the first kind,  `\displaystyle  F(\phi,k) = \int_0^{\phi} \frac{\mathrm{d}t}{\sqrt{1-k^2 \sin^2(t)}}`. See also Wikipedia :cite:p:`WikipediaFun151`, MathWorld :cite:p:`WolframFun151`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun148`, :cite:t:`Ehrhardt2018` (3.2.1.6), Flint :cite:p:`FlintFun151`, Mpmath :cite:p:`MpmathFun151`. 


    
    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75; k = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_f(phi, k)))
            fpm:  0.766619034309097
            mpm:  0.766619034309096589544308918544212974274615994676877391995555431875730053660175730568144934
            dpm:  0.766619034309096589544308918544212974274615994676877391995555431875730053660175730568144934
            gpm:  0.76661903430909658954430891854421297427461599467687739199555543187573005366017573056814493401
            apm: [0.766619034309096589544308918544212974274615994676877391995555431875730053660175730568144934 +/- 5.33e-91]
         math53:  0.766619034309097
          sreal:  0.766619
          dreal:  0.766619034309097
          ereal:  0.7666190343090965895
          qreal:  0.766619034309096589544308918544213
          oreal:  0.76661903430909658954430891854421297427461599467687739199555543187573007
          mreal:  0.766619034309096589544308918544212974274615994676877391995555431875730053660175730568144934
         sflint:  0.766619
         dflint:  0.766619034309097
         eflint:  0.76661903430909658955
         qflint:  0.766619034309096589544308918544213
         oflint:  0.76661903430909658954430891854421297427461599467687739199555543187573005
         mflint:  0.766619034309096589544308918544212974274615994676877391995555431875730053660175730568144933
         aflint: [0.76661903430909658954430891854421297427461599467687739199555543187573005366017573056814493 +/- 5.36e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  k = 0.5+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_f(phi, k)))
            fpm:  (0.765484001590538, 0.716811007324015)
            mpm:  (0.7654840015905376023671074316195117424394, 0.7168110073240154565463774574292304907073)
        cmath53:  (0.765484001590424, 0.716811007323909)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  k = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_f(phi, k))))
            fpm:  0.765484001590538
            mpm:  0.765484001590537602367107431619511742439349801705500605047678788582183500826222059869603294
            dpm:  0.765484001590537602367107431619511742439349801705500605047678788582183500826222059869603294
            gpm:  0.76548400159053760236710743161951174243934980170550060504767878858218350082622205986960329395
            apm: [0.7654840015905376023671074316195117424393498017055006050476787885821835008262220598696033 +/- 2.06e-89]
        cmath53:  0.765484001590424
        sflintc:  0.765484
        dflintc:  0.765484001590538
        eflintc:  0.76548400159053760238
        qflintc:  0.765484001590537602367107431619512
        oflintc:  0.7654840015905376023671074316195117424393498017055006050476787885821835
        mflintc:  0.765484001590537602367107431619511742439349801705500605047678788582183500826222059869603293
        aflintc: [0.7654840015905376023671074316195117424393498017055006050476787885821835008262220598696033 +/- 6.53e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  k = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_f(phi, k))))
            fpm:  0.716811007324015
            mpm:  0.716811007324015456546377457429230490707306894691997369091488236003409127788189675445002334
            dpm:  0.716811007324015456546377457429230490707306894691997369091488236003409127788189675445002334
            gpm:  0.71681100732401545654637745742923049070730689469199736909148823600340912778818967544500233402
            apm: [0.7168110073240154565463774574292304907073068946919973690914882360034091277881896754450023 +/- 4.86e-89]
        cmath53:  0.716811007323909
        sflintc:  0.716811
        dflintc:  0.716811007324015
        eflintc:  0.71681100732401545653
        qflintc:  0.716811007324015456546377457429231
        oflintc:  0.71681100732401545654637745742923049070730689469199736909148823600340913
        mflintc:  0.716811007324015456546377457429230490707306894691997369091488236003409127788189675445002333
        aflintc: [0.7168110073240154565463774574292304907073068946919973690914882360034091277881896754450023 +/- 9.29e-89]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D01a_CarlsonRfReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D01b_CarlsonRfCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C01_CarlsonIntegrals/D01_CarlsonRf.cs>`__. 








Legendre incomplete elliptic integral of the second kind, `E(\phi,k)`
----------------------------------------------------------------------------------------------

.. method:: ctx.elliptic_e_inc(phi, k)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    The original names are: ctx.ellint2(phi, k), ctxboost.Ellint2E(phi, k), ctx.ellipticEInc(phi, k).

    Returns the Legendre incomplete elliptic integral of the second kind,  `\displaystyle  E(\phi,k) = \int_0^{\phi} \sqrt{1-k^2 \sin^2(t)} \, \mathrm{d}t`. See also Wikipedia :cite:p:`WikipediaFun152`, MathWorld :cite:p:`WolframFun152`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun149`, :cite:t:`Ehrhardt2018` (3.2.1.7), Flint :cite:p:`FlintFun151`, Mpmath :cite:p:`MpmathFun152`.


    
    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75; k = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_e_inc(phi, k)))
            fpm:  0.734000489648948
            mpm:  0.73400048964894783655867869469985453815532816696830115716437836741114082591153679844074225
            dpm:  0.73400048964894783655867869469985453815532816696830115716437836741114082591153679844074225
            gpm:  0.73400048964894783655867869469985453815532816696830115716437836741114082591153679844074225004
            apm: [0.73400048964894783655867869469985453815532816696830115716437836741114082591153679844074225 +/- 1.42e-90]
         math53:  0.734000489648948
          sreal:  0.7340005
          dreal:  0.734000489648948
          ereal:  0.73400048964894783654
          qreal:  0.734000489648947836558678694699855
          oreal:  0.73400048964894783655867869469985453815532816696830115716437836741114084
          mreal:  0.73400048964894783655867869469985453815532816696830115716437836741114082591153679844074225
         sflint:  0.7340005
         dflint:  0.734000489648948
         eflint:  0.73400048964894783654
         qflint:  0.734000489648947836558678694699855
         oflint:  0.73400048964894783655867869469985453815532816696830115716437836741114082
         mflint:  0.734000489648947836558678694699854538155328166968301157164378367411140825911536798440742249
         aflint: [0.73400048964894783655867869469985453815532816696830115716437836741114082591153679844074225 +/- 4.30e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  k = 0.5+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_e_inc(phi, k)))
            fpm:  (-1.76997464001058, 6.21831560029404)
            mpm:  (-1.769974640010579481200447835314572055914, 6.218315600294037841322441928413981817353)
        cmath53:  (-1.76997464001069, 6.21831560029393)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  k = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_e_inc(phi, k))))
            fpm:  -1.76997464001058
            mpm:  -1.76997464001057948120044783531457205591369573622043572225535166919440181325409243692378043
            dpm:  -1.76997464001057948120044783531457205591369573622043572225535166919440181325409243692378043
            gpm:  -1.76997464001057948120044783531457205591369573622043572225535166919440181325409243692378043
            apm: [-1.769974640010579481200447835314572055913695736220435722255351669194401813254092436923780 +/- 5.02e-88]
        cmath53:  -1.76997464001069
        sflintc:  -1.769975
        dflintc:  -1.76997464001058
        eflintc:  -1.7699746400105794812
        qflintc:  -1.76997464001057948120044783531457
        oflintc:  -1.7699746400105794812004478353145720559136957362204357222553516691944018
        mflintc:  -1.76997464001057948120044783531457205591369573622043572225535166919440181325409243692378042
        aflintc: [-1.769974640010579481200447835314572055913695736220435722255351669194401813254092436923780 +/- 7.29e-88]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  k = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_e_inc(phi, k))))
            fpm:  6.21831560029404
            mpm:  6.21831560029403784132244192841398181735273840004111474077438340963456399369473645235580439
            dpm:  6.21831560029403784132244192841398181735273840004111474077438340963456399369473645235580439
            gpm:  6.2183156002940378413224419284139818173527384000411147407743834096345639936947364523558043902
            apm: [6.2183156002940378413224419284139818173527384000411147407743834096345639936947364523558044 +/- 9.51e-89]
        cmath53:  6.21831560029393
        sflintc:  6.218316
        dflintc:  6.21831560029404
        eflintc:  6.2183156002940378412
        qflintc:  6.21831560029403784132244192841398
        oflintc:  6.218315600294037841322441928413981817352738400041114740774383409634564
        mflintc:  6.21831560029403784132244192841398181735273840004111474077438340963456399369473645235580436
        aflintc: [6.218315600294037841322441928413981817352738400041114740774383409634563993694736452355804 +/- 6.75e-88]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D01a_CarlsonRfReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D01b_CarlsonRfCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C01_CarlsonIntegrals/D01_CarlsonRf.cs>`__. 









Legendre incomplete elliptic integral of the third kind, `\Pi(n, \phi, k)`
----------------------------------------------------------------------------------------------------

.. method:: ctx.elliptic_pi_inc(n, phi, k)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    The original names are: ctx.ellint3(phi, n, k), ctxboost.Ellint3F(phi, n, k), ctx.ellipticPiInc(phi, n, k).

    Returns the Legendre incomplete elliptic integral of the third kind,  `\displaystyle  \Pi(n, \phi, k) = \int_0^{\phi} \frac{\mathrm{d}t}{(1-n \sin^2(t)) \sqrt{1-k^2 \sin^2(t)}}`. See also Wikipedia :cite:p:`WikipediaFun153`, MathWorld :cite:p:`WolframFun153`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun150`, :cite:t:`Ehrhardt2018` (3.2.1.8), Flint :cite:p:`FlintFun151`, Mpmath :cite:p:`MpmathFun153`. 


    
    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.55; phi = 0.18; k = 0.01; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_pi_inc(n, phi, k)))
            fpm:  0.181073791234071
            mpm:  0.181073791234070796886074613520839342602696824399845666145726335155522163242258509156477838
            dpm:  0.180019414729767598649270814679281843259961606637409883657068624908338267732377821404344358
            gpm:  0.18001941472976759864927081467928184325996160663740988365706862490833826773237782140434435799
            apm: [0.181073791234070796886074613520839342602696824399845666145726335155522163242258509156477838 +/- 2.30e-91]
         math53:  0.181969627516793
          sreal:  0.1810738
          dreal:  0.181073791234071
          ereal:  0.1810737912340707969
          qreal:  0.181073791234070796886074613520839
          oreal:  0.18107379123407079688607461352083934260269682439984566614572633515552217
          mreal:  0.181073791234070796886074613520839342602696824399845666145726335155522163242258509156477838
         sflint:  0.1810738
         dflint:  0.181073791234071
         eflint:  0.1810737912340707969
         qflint:  0.181073791234070796886074613520839
         oflint:  0.18107379123407079688607461352083934260269682439984566614572633515552216
         mflint:  0.181073791234070796886074613520839342602696824399845666145726335155522163242258509156477838
         aflint: [0.181073791234070796886074613520839342602696824399845666145726335155522163242258509156477838 +/- 8.25e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = -5.1+2j;  phi = 2.7+2j; k = 1.3+2j;  gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_pi_inc(n, phi, k)))
            fpm:  (0.322004007340083, 0.751422520797896)
            mpm:  (0.3220040073400829546054227879987298519782, 0.7514225207978954342344887938985768416085)
        cmath53:  (0.322004003941805, 0.751422522223148)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = -5.1+2j;  phi = 2.7+2j; k = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.m_elliptic_pi_inc(n, phi, k))))
            fpm:  0.322004007340083
            mpm:  0.322004007340082954605422787998728249731886004300657524161176238451434722979010479580052089
            dpm:  0.322004007340082954605422787998728249731886004300657524161176238451434722979010479580052089
            gpm:  0.32200400734008295460542278799872824973188600430065752416117623845143472297901047958005208902
            apm: [0.32200400734008295460542278799872824973188600430065752416075800800652392134031675476295 +/- 6.81e-87]
        cmath53:  0.322004003941805
        sflintc:  0.322004
        dflintc:  0.322004007340083
        eflintc:  0.32200400734008295461
        qflintc:  0.322004007340082954605422787998728
        oflintc:  0.32200400734008295460542278799872824973188600430065752416075800800652392
        mflintc:  0.322004007340082954605422787998728249731886004300657524160758008006523921340316754762945202
        aflintc: [0.3220040073400829546054227879987282497318860043006575241607580080065239213403167547629 +/- 5.07e-86]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = -5.1+2j;  phi = 2.7+2j; k = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.m_elliptic_pi_inc(n, phi, k))))
            fpm:  0.751422520797896
            mpm:  0.751422520797895434234488793898574144443223395508373219552455925979035549446564959995815034
            dpm:  0.751422520797895434234488793898574144443223395508373219552455925979035549446564959995815034
            gpm:  0.75142252079789543423448879389857414444322339550837321955245592597903554944656495999581503402
            apm: [0.75142252079789543423448879389857414444322339550837321955175189150717215360547480058603 +/- 6.12e-87]
        cmath53:  0.751422522223148
        sflintc:  0.7514225
        dflintc:  0.751422520797896
        eflintc:  0.75142252079789543422
        qflintc:  0.751422520797895434234488793898574
        oflintc:  0.75142252079789543423448879389857414444322339550837321955175189150717215
        mflintc:  0.751422520797895434234488793898574144443223395508373219551751891507172153605474800586026195
        aflintc: [0.7514225207978954342344887938985741444432233955083732195517518915071721536054748005860 +/- 3.25e-86]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D01a_CarlsonRfReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D01b_CarlsonRfCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C01_CarlsonIntegrals/D01_CarlsonRf.cs>`__. 




