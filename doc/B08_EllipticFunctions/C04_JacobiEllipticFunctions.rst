

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Jacobi elliptic functions 
===============================================================================

For an introduction, see Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun155`, BoostMath :cite:p:`BoostFun155`, NIST :cite:p:`DLMFun155`, Mpmath :cite:p:`MpmathFun155`.





Jacobi elliptic function `\mathrm{sn}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_sn(x, k)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{sn}(x, k) = \sin(\mathrm{am}(x, k))`, where `\mathrm{am}(x, k)` denotes the Jacobi amplitude function, and `\mathrm{sn}(x, 0) = \sin(x)`. See also  BoostMath :cite:p:`BoostFun168`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun168`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.1), :cite:t:`Ehrhardt2018` (4.2.58).

    The version for  ``ecplx`` has the restriction that `k` must be real.
        

    |08a_TestJacobiSN_re| `\quad` |08b_TestJacobiSN_im| `\quad` |08c_TestJacobiSN_abs|

    .. |08a_TestJacobiSN_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/08a_TestJacobiSN_re.3D.xml.jpg
       :width: 30 %

    .. |08b_TestJacobiSN_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/08b_TestJacobiSN_im.3D.xml.jpg
       :width: 30 %

    .. |08c_TestJacobiSN_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/08c_TestJacobiSN_abs.3D.xml.jpg
       :width: 30 %


   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_sn(x, k)))
            fpm:  0.246362683303348
            mpm:  0.246362683303347826277469162079397089989016565898140408185238973486827694694540414709616695
            dpm:  0.246362683303347826277469162079397089989016565898140408185238973486827694694540414709616695
            gpm:  0.246362683303347826277469162079397089989016565898140408185238973486827694694540414709616695
            apm: [0.24636268330334782627746916207939708998901656589814040818523897348682769469454041470962 +/- 5.64e-87]
         math53:  0.246362683303348
          sreal:  0.2463627
          dreal:  0.246362683303348
          ereal:  0.24636268330334782655
          qreal:  0.246362683303347826277469162079397
          oreal:  0.24636268330334782627746916207939708998901656589814040818523897348682771
          mreal:  0.246362683303347826277469162079397089989016565898140408185238973486827694694540414709616694
         sflint:  0.2463627
         dflint:  0.246362683303348
         eflint:  0.24636268330334782628
         qflint:  0.246362683303347826277469162079397
         oflint:  0.24636268330334782627746916207939708998901656589814040818523897348682769
         mflint:  0.246362683303347826277469162079397089989016565898140408185238973486827694694540414709616714
         aflint: [0.24636268330334782627746916207939708998901656589814040818523897348682769469454041471 +/- 1.37e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_sn(x, k)))
            fpm:  (-0.00143593649241395, 0.0129568587163219)
            mpm:  (-0.001435936492413952023810483209758047557881, 0.01295685871632186859513739148971596910176)
        cmath53:  (-0.00143593649240608, 0.0129568587163203)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_sn(x, k))))
            fpm:  -0.00143593649241395
            mpm:  -0.00143593649241395202381048320975804755789336232106643768539979208978626689369070835343685193
            dpm:  -0.00143593649241395202381048320975804755789336232106643768539979208978626689369070835343685193
            gpm:  -0.0014359364924139520238104832097580475578933623210664376853997920897862668936907083534368519299
            apm: [-0.0014359364924139520238104832097580475578933623210664376853997920897862668936907083534 +/- 4.72e-86]
        cmath53:  -0.00143593649240608
        sflintc:  -0.001435871
        dflintc:  -0.00143593649241371
        eflintc:  -0.0014359364924139519649
        qflintc:  -0.00143593649241395202381048320975784
        oflintc:  -0.001435936492413952023810483209758047557893362321066437685399792089786
        mflintc:  -0.00143593649241395202381048320975804755789336232106643768539979208978626689369070835343682949
        aflintc: [-0.00143593649241395202381048320975804755789336232106643768539979208978626689369070835 +/- 6.17e-84]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_sn(x, k))))
            fpm:  0.0129568587163219
            mpm:  0.0129568587163218685951373914897159691017417392762947011250415073740150204333734241744899301
            dpm:  0.0129568587163218685951373914897159691017417392762947011250415073740150204333734241744899301
            gpm:  0.012956858716321868595137391489715969101741739276294701125041507374015020433373424174489930101
            apm: [0.0129568587163218685951373914897159691017417392762947011250415073740150204333734241745 +/- 2.05e-86]
        cmath53:  0.0129568587163203
        sflintc:  0.01295693
        dflintc:  0.0129568587163221
        eflintc:  0.012956858716321868659
        qflintc:  0.0129568587163218685951373914897162
        oflintc:  0.012956858716321868595137391489715969101741739276294701125041507374015
        mflintc:  0.0129568587163218685951373914897159691017417392762947011250415073740150204333734241744899587
        aflintc: [0.01295685871632186859513739148971596910174173927629470112504150737401502043337342417 +/- 7.22e-84]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D01a_JacobiSnReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D01b_JacobiSnCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D01_JacobiSn.cs>`__. 








|newpage|

Jacobi elliptic function `\mathrm{cn}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_cn(x, k)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{cn}(x, k) = \cos(\mathrm{am}(x, k))`, where `\mathrm{am}(x, k)` denotes the Jacobi amplitude function, and `\mathrm{cn}(x, 0) = \cos(x)`. See also  BoostMath :cite:p:`BoostFun158`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun158`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.2), :cite:t:`Ehrhardt2018` (4.2.18).

    The version for  ``ecplx`` has the restriction that `k` must be real.



    |09a_TestJacobiCN_re| `\quad` |09b_TestJacobiCN_im| `\quad` |09c_TestJacobiCN_abs|

    .. |09a_TestJacobiCN_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/09a_TestJacobiCN_re.3D.xml.jpg
       :width: 30 %

    .. |09b_TestJacobiCN_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/09b_TestJacobiCN_im.3D.xml.jpg
       :width: 30 %

    .. |09c_TestJacobiCN_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/09c_TestJacobiCN_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.






    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_cn(x, k)))
            fpm:  0.969177707273323
            mpm:  0.969177707273322678224481900625086532746690114216882486313007790123473968926133547388534709
            dpm:  0.969177707273322678224481900625086532746690114216882486313007790123473968926133547388534709
            gpm:  0.96917770727332267822448190062508653274669011421688248631300779012347396892613354738853470895
            apm: [0.9691777072733226782244819006250865327466901142168824863130077901234739689261335473885 +/- 4.76e-86]
         math53:  0.969177707273323
          sreal:  0.9691777
          dreal:  0.969177707273323
          ereal:  0.96917770727332267834
          qreal:  0.969177707273322678224481900625087
          oreal:  0.96917770727332267822448190062508653274669011421688248631300779012347395
          mreal:  0.96917770727332267822448190062508653274669011421688248631300779012347396892613354738853471
         sflint:  0.9691777
         dflint:  0.969177707273323
         eflint:  0.96917770727332267823
         qflint:  0.969177707273322678224481900625087
         oflint:  0.96917770727332267822448190062508653274669011421688248631300779012347397
         mflint:  0.969177707273322678224481900625086532746690114216882486313007790123473968926133547388534702
         aflint: [0.96917770727332267822448190062508653274669011421688248631300779012347396892613354739 +/- 5.13e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_cn(x, k)))
            fpm:  (-1.00008290587345, -1.8603683903155E-05)
            mpm:  (-1.000082905873448841175011671540975684772, -0.00001860368390315500780851516667835868544173)
        cmath53:  (-1.00008290587346, -1.86036838914253E-05)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_cn(x, k))))
            fpm:  -1.00008290587345
            mpm:  -1.00008290587344884117501167154097568477172574626012942606955752401378208147346675628809532
            dpm:  -1.00008290587344884117501167154097568477172574626012942606955752401378208147346675628809532
            gpm:  -1.0000829058734488411750116715409756847717257462601294260695575240137820814734667562880953199
            apm: [-1.000082905873448841175011671540975684771725746260129426069557524013782081473466756288 +/- 2.32e-85]
        cmath53:  -1.00008290587346
        sflintc:  -1.000083
        dflintc:  -1.00008290587345
        eflintc:  -1.0000829058734488412
        qflintc:  -1.00008290587344884117501167154098
        oflintc:  -1.00008290587344884117501167154097568477172574626012942606955752401378
        mflintc:  -1.00008290587344884117501167154097568477172574626012942606955752401378208147346675628809532
        aflintc: [-1.0000829058734488411750116715409756847717257462601294260695575240137820814734667563 +/- 7.28e-83]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_cn(x, k))))
            fpm:  -1.8603683903155E-05
            mpm:  -0.0000186036839031550078085151666783586854418636554450453209605262650494481654596404413556724113
            dpm:  -0.0000186036839031550078085151666783586854418636554450453209605262650494481654596404413556724113
            gpm:  -1.86036839031550078085151666783586854418636554450453209605262650494481654596404413556724113e-05
            apm: [-1.8603683903155007808515166678358685441863655445045320960526265049448165459640441e-5 +/- 4.93e-85]
        cmath53:  -1.86036838914253E-05
        sflintc:  -1.860294E-05
        dflintc:  -1.86036839031523E-05
        eflintc:  -1.8603683903155007136e-05
        qflintc:  -1.86036839031550078085151666783563e-05
        oflintc:  -1.860368390315500780851516667835868544186365544504532096052626505e-05
        mflintc:  -1.86036839031550078085151666783586854418636554450453209605262650494481654596404413556720285E-05
        aflintc: [-1.8603683903155007808515166678358685441863655445045320960526265049448165459640e-5 +/- 5.03e-82]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D02a_JacobiCnReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D02b_JacobiCnCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D02_JacobiCn.cs>`__. 







|newpage|

Jacobi elliptic function `\mathrm{dn}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_dn(x, k)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{dn}(x, k) = \sqrt{1 - k^2 \mathrm{sn}^2(x, k)}` with `\mathrm{dn}(x, 0) = 1`. See also  BoostMath :cite:p:`BoostFun161`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun161`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.3), :cite:t:`Ehrhardt2018` (4.2.26).

    The version for  ``ecplx`` has the restriction that `k` must be real.

    

    |10a_TestJacobiDN_re| `\quad` |10b_TestJacobiDN_im| `\quad` |10c_TestJacobiDN_abs|

    .. |10a_TestJacobiDN_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/10a_TestJacobiDN_re.3D.xml.jpg
       :width: 30 %

    .. |10b_TestJacobiDN_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/10b_TestJacobiDN_im.3D.xml.jpg
       :width: 30 %

    .. |10c_TestJacobiDN_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/10c_TestJacobiDN_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.







    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_dn(x, k)))
            fpm:  0.746683716260732
            mpm:  0.746683716260731746308110572441340458575984719909169504018167905669142900003266769486762092
            dpm:  0.746683716260731746308110572441340458575984719909169504018167905669142900003266769486762092
            gpm:  0.74668371626073174630811057244134045857598471990916950401816790566914290000326676948676209195
            apm: [0.7466837162607317463081105724413404585759847199091695040181679056691429000032667694868 +/- 5.06e-86]
         math53:  0.746683716260732
          sreal:  0.7466837
          dreal:  0.746683716260732
          ereal:  0.74668371626073174564
          qreal:  0.746683716260731746308110572441341
          oreal:  0.74668371626073174630811057244134045857598471990916950401816790566914286
          mreal:  0.746683716260731746308110572441340458575984719909169504018167905669142900003266769486762095
         sflint:  0.7466837
         dflint:  0.746683716260732
         eflint:  0.74668371626073174629
         qflint:  0.74668371626073174630811057244134
         oflint:  0.7466837162607317463081105724413404585759847199091695040181679056691429
         mflint:  0.746683716260731746308110572441340458575984719909169504018167905669142900003266769486762046
         aflint: [0.74668371626073174630811057244134045857598471990916950401816790566914290000326676949 +/- 6.57e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_dn(x, k)))
            fpm:  (-1.00007228950877, -0.000956560725679442)
            mpm:  (-1.000072289508773447925621775290900832565, -0.0009565607256794425237716971223176896357369)
        cmath53:  (-1.00007228950877, -0.000956560725669281)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_dn(x, k))))
            fpm:  -1.00007228950877
            mpm:  -1.0000722895087734479256217752909008325647350839762266457845258852413947727466683017029953
            dpm:  -1.0000722895087734479256217752909008325647350839762266457845258852413947727466683017029953
            gpm:  -1.0000722895087734479256217752909008325647350839762266457845258852413947727466683017029953
            apm: [-1.000072289508773447925621775290900832564735083976226645784525885241394772746668301703 +/- 1.55e-85]
        cmath53:  -1.00007228950877
        sflintc:  -1.000072
        dflintc:  -1.00007228950877
        eflintc:  -1.000072289508773448
        qflintc:  -1.0000722895087734479256217752909
        oflintc:  -1.00007228950877344792562177529090083256473508397622664578452588524139
        mflintc:  -1.0000722895087734479256217752909008325647350839762266457845258852413947727466683017029953
        aflintc: [-1.0000722895087734479256217752909008325647350839762266457845258852413947727466683017 +/- 5.99e-83]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_dn(x, k))))
            fpm:  -0.000956560725679442
            mpm:  -0.000956560725679442523771697122317689635735289516420598889387387777738180440932184663646331782
            dpm:  -0.000956560725679442523771697122317689635735289516420598889387387777738180440932184663646331782
            gpm:  -0.00095656072567944252377169712231768963573528951642059888938738777773818044093218466364633178204
            apm: [-0.000956560725679442523771697122317689635735289516420598889387387777738180440932184664 +/- 5.04e-85]
        cmath53:  -0.000956560725669281
        sflintc:  -0.0009565695
        dflintc:  -0.000956560725679474
        eflintc:  -0.00095656072567944253142
        qflintc:  -0.000956560725679442523771697122317717
        oflintc:  -0.00095656072567944252377169712231768963573528951642059888938738777774
        mflintc:  -0.0009565607256794425237716971223176896357352895164205988893873877777381804409321846636463356
        aflintc: [-0.0009565607256794425237716971223176896357352895164205988893873877777381804409321847 +/- 9.33e-83]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D03a_JacobiDnReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D03b_JacobiDnCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D03_JacobiDn.cs>`__. 






|newpage|

Jacobi elliptic function `\mathrm{nc}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_nc(x, k)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Jacobi elliptic function  `\mathrm{nc}(x, k) = 1/\mathrm{cn}(x, k)`, with `\mathrm{nc}(x, 0) = 1/\cos(x)`. See also  BoostMath :cite:p:`BoostFun163`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun163`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.4).




    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_nc(x, k)))
            fpm:  1.03180251928554
            mpm:  1.03180251928554210134149112819061701718554842312212495917928474564951190584338549190884984
            dpm:  1.03180251928554210134149112819061701718554842312212495917928474564951190584338549190884984
            gpm:  1.03180251928554210134149112819061701718554842312212495917928474564951190584338549190884984
            apm: [1.0318025192855421013414911281906170171855484231221249591792847456495119058433854919088 +/- 6.35e-86]
         math53:  1.03180251928554
          sreal:  1.031803
          dreal:  1.03180251928554
          ereal:  1.0318025192855421013
          qreal:  1.03180251928554210134149112819062
          oreal:  1.0318025192855421013414911281906170171855484231221249591792847456495119
          mreal:  1.03180251928554210134149112819061701718554842312212495917928474564951190584338549190884984
         sflint:  1.031803
         dflint:  1.03180251928554
         eflint:  1.0318025192855421014
         qflint:  1.03180251928554210134149112819062
         oflint:  1.0318025192855421013414911281906170171855484231221249591792847456495119
         mflint:  1.03180251928554210134149112819061701718554842312212495917928474564951190584338549190884985
         aflint: [1.03180251928554210134149112819061701718554842312212495917928474564951190584338549191 +/- 5.05e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_nc(x, k)))
            fpm:  (-0.999917100653354, 1.86005995709601E-05)
            mpm:  (-0.9999171006533542260038404975569555685111, 0.00001860059957096012916580975170124816908464)
        cmath53:  (-0.999917100653346, 1.86005995592801E-05)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_nc(x, k))))
            fpm:  -0.999917100653354
            mpm:  -0.999917100653354226003840497556955568511077732738528833839112104760283040109523945164280651
            dpm:  -0.999917100653354226003840497556955568511077732738528833839112104760283040109523945164280651
            gpm:  -0.99991710065335422600384049755695556851107773273852883383911210476028304010952394516428065098
            apm: [-0.999917100653354226003840497556955568511077732738528833839112104760283040109523945164 +/- 4.18e-85]
        cmath53:  -0.999917100653346
        sflintc:  -0.9999171
        dflintc:  -0.999917100653354
        eflintc:  -0.99991710065335422602
        qflintc:  -0.999917100653354226003840497556956
        oflintc:  -0.99991710065335422600384049755695556851107773273852883383911210476028
        mflintc:  -0.999917100653354226003840497556955568511077732738528833839112104760283040109523945164280651
        aflintc: [-0.999917100653354226003840497556955568511077732738528833839112104760283040109523945 +/- 2.26e-82]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_nc(x, k))))
            fpm:  1.86005995709601E-05
            mpm:  0.0000186005995709601291658097517012481690847862264002865461643371006863012883217592167815174094
            dpm:  0.0000186005995709601291658097517012481690847862264002865461643371006863012883217592167815174094
            gpm:  1.8600599570960129165809751701248169084786226400286546164337100686301288321759216781517409399e-05
            apm: [1.8600599570960129165809751701248169084786226400286546164337100686301288321759217e-5 +/- 3.55e-85]
        cmath53:  1.86005995592801E-05
        sflintc:  1.859986E-05
        dflintc:  1.86005995709574E-05
        eflintc:  1.8600599570960128495e-05
        qflintc:  1.86005995709601291658097517012458e-05
        oflintc:  1.860059957096012916580975170124816908478622640028654616433710069e-05
        mflintc:  1.86005995709601291658097517012481690847862264002865461643371006863012883217592167815170266E-05
        aflintc: [1.86005995709601291658097517012481690847862264002865461643371006863012883217592e-5 +/- 7.76e-83]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D04a_JacobiNcReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D04b_JacobiNcCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D04_JacobiNc.cs>`__. 








|newpage|

Jacobi elliptic function `\mathrm{sc}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_sc(x, k)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Jacobi elliptic function  `\mathrm{sc}(x, k) = \mathrm{sn}(x, k)/\mathrm{cn}(x, k)`. See also  BoostMath :cite:p:`BoostFun166`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun166`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.5).




    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_sc(x, k)))
            fpm:  0.25419763729034
            mpm:  0.254197637290340446568833303692720684163750610220405803964891493073733507552416997494302416
            dpm:  0.254197637290340446568833303692720684163750610220405803964891493073733507552416997494302416
            gpm:  0.25419763729034044656883330369272068416375061022040580396489149307373350755241699749430241599
            apm: [0.25419763729034044656883330369272068416375061022040580396489149307373350755241699749430 +/- 8.17e-87]
         math53:  0.25419763729034
          sreal:  0.2541976
          dreal:  0.25419763729034
          ereal:  0.25419763729034044683
          qreal:  0.25419763729034044656883330369272
          oreal:  0.25419763729034044656883330369272068416375061022040580396489149307373353
          mreal:  0.254197637290340446568833303692720684163750610220405803964891493073733507552416997494302415
         sflint:  0.2541976
         dflint:  0.25419763729034
         eflint:  0.25419763729034044656
         qflint:  0.254197637290340446568833303692721
         oflint:  0.25419763729034044656883330369272068416375061022040580396489149307373351
         mflint:  0.254197637290340446568833303692720684163750610220405803964891493073733507552416997494302438
         aflint: [0.25419763729034044656883330369272068416375061022040580396489149307373350755241699749 +/- 6.28e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_sc(x, k)))
            fpm:  (0.00143557644887623, -0.0129558113104794)
            mpm:  (0.001435576448876226275220573401414661179617, -0.01295581131047940863122322611414938353368)
        cmath53:  (0.0014355764488685, -0.0129558113104777)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_sc(x, k))))
            fpm:  0.00143557644887623
            mpm:  0.00143557644887622627522057340141466117962970633276702286947561670938934315983733537419422004
            dpm:  0.00143557644887622627522057340141466117962970633276702286947561670938934315983733537419422004
            gpm:  0.0014355764488762262752205734014146611796297063327670228694756167093893431598373353741942200401
            apm: [0.0014355764488762262752205734014146611796297063327670228694756167093893431598373353742 +/- 1.81e-86]
        cmath53:  0.0014355764488685
        sflintc:  0.001435511
        dflintc:  0.00143557644887598
        eflintc:  0.0014355764488762262163
        qflintc:  0.00143557644887622627522057340141445
        oflintc:  0.001435576448876226275220573401414661179629706332767022869475616709389
        mflintc:  0.00143557644887622627522057340141466117962970633276702286947561670938934315983733537419419761
        aflintc: [0.00143557644887622627522057340141466117962970633276702286947561670938934315983733537 +/- 7.80e-84]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_sc(x, k))))
            fpm:  -0.0129558113104794
            mpm:  -0.0129558113104794086312232261141493835336712117441837306242935871734918320607963029150229863
            dpm:  -0.0129558113104794086312232261141493835336712117441837306242935871734918320607963029150229863
            gpm:  -0.0129558113104794086312232261141493835336712117441837306242935871734918320607963029150229863
            apm: [-0.0129558113104794086312232261141493835336712117441837306242935871734918320607963029150 +/- 3.53e-86]
        cmath53:  -0.0129558113104777
        sflintc:  -0.01295588
        dflintc:  -0.0129558113104797
        eflintc:  -0.012955811310479408695
        qflintc:  -0.0129558113104794086312232261141496
        oflintc:  -0.012955811310479408631223226114149383533671211744183730624293587173492
        mflintc:  -0.0129558113104794086312232261141493835336712117441837306242935871734918320607963029150230148
        aflintc: [-0.01295581131047940863122322611414938353367121174418373062429358717349183206079630292 +/- 8.58e-84]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D05a_JacobiScReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D05b_JacobiScCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D05_JacobiSc.cs>`__. 









|newpage|

Jacobi elliptic function `\mathrm{dc}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_dc(x, k)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{dc}(x, k) = \mathrm{dn}(x, k)/\mathrm{cn}(x, k)`. See also  BoostMath :cite:p:`BoostFun160`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun160`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.6).



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_dc(x, k)))
            fpm:  0.770430139547314
            mpm:  0.770430139547313914002540510081163800017336821479199508488452564388996252749623613774534154
            dpm:  0.770430139547313914002540510081163800017336821479199508488452564388996252749623613774534154
            gpm:  0.77043013954731391400254051008116380001733682147919950848845256438899625274962361377453415396
            apm: [0.7704301395473139140025405100811638000173368214791995084884525643889962527496236137745 +/- 5.75e-86]
         math53:  0.770430139547314
          sreal:  0.7704301
          dreal:  0.770430139547314
          ereal:  0.7704301395473139132
          qreal:  0.770430139547313914002540510081164
          oreal:  0.77043013954731391400254051008116380001733682147919950848845256438899623
          mreal:  0.770430139547313914002540510081163800017336821479199508488452564388996252749623613774534156
         sflint:  0.7704301
         dflint:  0.770430139547314
         eflint:  0.77043013954731391402
         qflint:  0.770430139547313914002540510081164
         oflint:  0.77043013954731391400254051008116380001733682147919950848845256438899625
         mflint:  0.770430139547313914002540510081163800017336821479199508488452564388996252749623613774534112
         aflint: [0.7704301395473139140025405100811638000173368214791995084884525643889962527496236138 +/- 3.19e-83]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_dc(x, k)))
            fpm:  (0.999989401961978, 0.000937879483221091)
            mpm:  (0.9999894019619776509370305298096806984388, 0.0009378794832210906850586523670526543724379)
        cmath53:  (0.999989401961969, 0.00093787948322266)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_dc(x, k))))
            fpm:  0.999989401961978
            mpm:  0.999989401961977650937030529809680698438799162086748661121605886341046483177241785033659694
            dpm:  0.999989401961977650937030529809680698438799162086748661121605886341046483177241785033659694
            gpm:  0.999989401961977650937030529809680698438799162086748661121605886341046483177241785033659694
            apm: [0.999989401961977650937030529809680698438799162086748661121605886341046483177241785034 +/- 6.27e-85]
        cmath53:  0.999989401961969
        sflintc:  0.9999894
        dflintc:  0.999989401961978
        eflintc:  0.99998940196197765094
        qflintc:  0.999989401961977650937030529809681
        oflintc:  0.99998940196197765093703052980968069843879916208674866112160588634105
        mflintc:  0.999989401961977650937030529809680698438799162086748661121605886341046483177241785033659698
        aflintc: [0.999989401961977650937030529809680698438799162086748661121605886341046483177241785 +/- 1.52e-82]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_dc(x, k))))
            fpm:  0.000937879483221091
            mpm:  0.00093787948322109068505865236705265437243614812496909298239714836332670632898313771412599112
            dpm:  0.00093787948322109068505865236705265437243614812496909298239714836332670632898313771412599112
            gpm:  0.00093787948322109068505865236705265437243614812496909298239714836332670632898313771412599112003
            apm: [0.000937879483221090685058652367052654372436148124969092982397148363326706328983137714 +/- 4.13e-85]
        cmath53:  0.00093787948322266
        sflintc:  0.000937889
        dflintc:  0.000937879483221125
        eflintc:  0.00093787948322109069338
        qflintc:  0.000937879483221090685058652367052684
        oflintc:  0.00093787948322109068505865236705265437243614812496909298239714836333
        mflintc:  0.00093787948322109068505865236705265437243614812496909298239714836332670632898313771412599532
        aflintc: [0.000937879483221090685058652367052654372436148124969092982397148363326706328983138 +/- 4.04e-82]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D06a_JacobiDcReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D06b_JacobiDcCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D06_JacobiDc.cs>`__. 









|newpage|

Jacobi elliptic function `\mathrm{nd}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_nd(x, k)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{nd}(x, k) = 1/\mathrm{dn}(x, k)`. See also  BoostMath :cite:p:`BoostFun164`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun164`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.7).


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_nd(x, k)))
            fpm:  1.339255133362
            mpm:  1.33925513336199991580695493045228013276830198154167950243356563694228650730218356592783958
            dpm:  1.33925513336199991580695493045228013276830198154167950243356563694228650730218356592783958
            gpm:  1.3392551333619999158069549304522801327683019815416795024335656369422865073021835659278395801
            apm: [1.3392551333619999158069549304522801327683019815416795024335656369422865073021835659278 +/- 6.23e-86]
         math53:  1.339255133362
          sreal:  1.339255
          dreal:  1.339255133362
          ereal:  1.339255133361999917
          qreal:  1.33925513336199991580695493045228
          oreal:  1.3392551333619999158069549304522801327683019815416795024335656369422866
          mreal:  1.33925513336199991580695493045228013276830198154167950243356563694228650730218356592783957
         sflint:  1.339255
         dflint:  1.339255133362
         eflint:  1.3392551333619999158
         qflint:  1.33925513336199991580695493045228
         oflint:  1.3392551333619999158069549304522801327683019815416795024335656369422865
         mflint:  1.33925513336199991580695493045228013276830198154167950243356563694228650730218356592783966
         aflint: [1.33925513336199991580695493045228013276830198154167950243356563694228650730218356593 +/- 8.13e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_nd(x, k)))
            fpm:  (-0.999926800907445, 0.000956421567057086)
            mpm:  (-0.9999268009074447559594166467982401739957, 0.0009564215670570859148277443891970915557337)
        cmath53:  (-0.999926800907446, 0.000956421567046943)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_nd(x, k))))
            fpm:  -0.999926800907445
            mpm:  -0.999926800907444755959416646798240173995720946856839178131881128862313360096294454416847958
            dpm:  -0.999926800907444755959416646798240173995720946856839178131881128862313360096294454416847958
            gpm:  -0.99992680090744475595941664679824017399572094685683917813188112886231336009629445441684795802
            apm: [-0.999926800907444755959416646798240173995720946856839178131881128862313360096294454417 +/- 3.02e-85]
        cmath53:  -0.999926800907446
        sflintc:  -0.9999268
        dflintc:  -0.999926800907445
        eflintc:  -0.99992680090744475596
        qflintc:  -0.99992680090744475595941664679824
        oflintc:  -0.99992680090744475595941664679824017399572094685683917813188112886231
        mflintc:  -0.999926800907444755959416646798240173995720946856839178131881128862313360096294454416847953
        aflintc: [-0.9999268009074447559594166467982401739957209468568391781318811288623133600962944544 +/- 7.39e-83]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_nd(x, k))))
            fpm:  0.000956421567057086
            mpm:  0.000956421567057085914827744389197091555732066186535024569472462037319965133848198518333626274
            dpm:  0.000956421567057085914827744389197091555732066186535024569472462037319965133848198518333626274
            gpm:  0.00095642156705708591482774438919709155573206618653502456947246203731996513384819851833362627402
            apm: [0.000956421567057085914827744389197091555732066186535024569472462037319965133848198518 +/- 4.84e-85]
        cmath53:  0.000956421567046943
        sflintc:  0.0009564303
        dflintc:  0.000956421567057117
        eflintc:  0.00095642156705708592243
        qflintc:  0.000956421567057085914827744389197119
        oflintc:  0.00095642156705708591482774438919709155573206618653502456947246203732
        mflintc:  0.000956421567057085914827744389197091555732066186535024569472462037319965133848198518333630082
        aflintc: [0.0009564215670570859148277443891970915557320661865350245694724620373199651338481985 +/- 7.54e-83]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D07a_JacobiNdReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D07b_JacobiNdCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D07_JacobiNd.cs>`__. 








|newpage|

Jacobi elliptic function `\mathrm{sd}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_sd(x, k)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{sd}(x, k) = \mathrm{sn}(x, k)/\mathrm{dn}(x, k)`. See also  BoostMath :cite:p:`BoostFun167`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun167`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.8).


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_sd(x, k)))
            fpm:  0.329942488282845
            mpm:  0.329942488282845243040280271863010270433896896261901373621983882606828968523463406322155886
            dpm:  0.329942488282845243040280271863010270433896896261901373621983882606828968523463406322155886
            gpm:  0.32994248828284524304028027186301027043389689626190137362198388260682896852346340632215588601
            apm: [0.3299424882828452430402802718630102704338968962619013736219838826068289685234634063222 +/- 5.29e-86]
         math53:  0.329942488282845
          sreal:  0.3299425
          dreal:  0.329942488282845
          ereal:  0.3299424882828452437
          qreal:  0.32994248828284524304028027186301
          oreal:  0.32994248828284524304028027186301027043389689626190137362198388260682901
          mreal:  0.329942488282845243040280271863010270433896896261901373621983882606828968523463406322155884
         sflint:  0.3299425
         dflint:  0.329942488282845
         eflint:  0.32994248828284524305
         qflint:  0.32994248828284524304028027186301
         oflint:  0.32994248828284524304028027186301027043389689626190137362198388260682897
         mflint:  0.329942488282845243040280271863010270433896896261901373621983882606828968523463406322155932
         aflint: [0.32994248828284524304028027186301027043389689626190137362198388260682896852346340632 +/- 4.94e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_sd(x, k)))
            fpm:  (0.00142343916404814, -0.0129572836466517)
            mpm:  (0.001423439164048138538282895249542689078959, -0.01295728364665173633754514556032261843824)
        cmath53:  (0.00142343916404041, -0.0129572836466502)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_sd(x, k))))
            fpm:  0.00142343916404814
            mpm:  0.00142343916404813853828289524954268907897171541608762678977310820554373181497341819800907679
            dpm:  0.00142343916404813853828289524954268907897171541608762678977310820554373181497341819800907679
            gpm:  0.0014234391640481385382828952495426890789717154160876267897731082055437318149734181980090767899
            apm: [0.0014234391640481385382828952495426890789717154160876267897731082055437318149734181980 +/- 2.16e-86]
        cmath53:  0.00142343916404041
        sflintc:  0.001423373
        dflintc:  0.0014234391640479
        eflintc:  0.0014234391640481384792
        qflintc:  0.00142343916404813853828289524954248
        oflintc:  0.001423439164048138538282895249542689078971715416087626789773108205544
        mflintc:  0.00142343916404813853828289524954268907897171541608762678977310820554373181497341819800905426
        aflintc: [0.00142343916404813853828289524954268907897171541608762678977310820554373181497341820 +/- 5.55e-84]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_sd(x, k))))
            fpm:  -0.0129572836466517
            mpm:  -0.0129572836466517363375451455603226184382253125933316997753390611786772884107426514454312726
            dpm:  -0.0129572836466517363375451455603226184382253125933316997753390611786772884107426514454312726
            gpm:  -0.012957283646651736337545145560322618438225312593331699775339061178677288410742651445431272601
            apm: [-0.0129572836466517363375451455603226184382253125933316997753390611786772884107426514454 +/- 4.38e-86]
        cmath53:  -0.0129572836466502
        sflintc:  -0.01295736
        dflintc:  -0.012957283646652
        eflintc:  -0.012957283646651736402
        qflintc:  -0.0129572836466517363375451455603228
        oflintc:  -0.012957283646651736337545145560322618438225312593331699775339061178677
        mflintc:  -0.012957283646651736337545145560322618438225312593331699775339061178677288410742651445431301
        aflintc: [-0.01295728364665173633754514556032261843822531259333169977533906117867728841074265145 +/- 8.12e-84]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D08a_JacobiSdReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D08b_JacobiSdCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D08_JacobiSd.cs>`__. 








|newpage|

Jacobi elliptic function `\mathrm{cd}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_cd(x, k)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{cd}(x, k) = \mathrm{cn}(x, k)/\mathrm{dn}(x, k)`. See also  BoostMath :cite:p:`BoostFun157`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun157`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.9).


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_cd(x, k)))
            fpm:  1.29797621960581
            mpm:  1.29797621960581107921236513233122226129120330630252416223083509073288421018094000442198266
            dpm:  1.29797621960581107921236513233122226129120330630252416223083509073288421018094000442198266
            gpm:  1.2979762196058110792123651323312222612912033063025241622308350907328842101809400044219826599
            apm: [1.2979762196058110792123651323312222612912033063025241622308350907328842101809400044220 +/- 5.66e-86]
         math53:  1.29797621960581
          sreal:  1.297976
          dreal:  1.29797621960581
          ereal:  1.2979762196058110805
          qreal:  1.29797621960581107921236513233122
          oreal:  1.2979762196058110792123651323312222612912033063025241622308350907328842
          mreal:  1.29797621960581107921236513233122226129120330630252416223083509073288421018094000442198265
         sflint:  1.297976
         dflint:  1.29797621960581
         eflint:  1.2979762196058110792
         qflint:  1.29797621960581107921236513233122
         oflint:  1.2979762196058110792123651323312222612912033063025241622308350907328842
         mflint:  1.29797621960581107921236513233122226129120330630252416223083509073288421018094000442198273
         aflint: [1.2979762196058110792123651323312222612912033063025241622308350907328842101809400044 +/- 3.27e-83]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_cd(x, k)))
            fpm:  (1.00000971850522, -0.000937898537892113)
            mpm:  (1.000009718505223404869550820340153335644, -0.0009378985378921129796949253864534576262996)
        cmath53:  (1.00000971850523, -0.000937898537893714)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_cd(x, k))))
            fpm:  1.00000971850522
            mpm:  1.00000971850522340486955082034015333564355632727648390420653310010217073212945301569795485
            dpm:  1.00000971850522340486955082034015333564355632727648390420653310010217073212945301569795485
            gpm:  1.0000097185052234048695508203401533356435563272764839042065331001021707321294530156979548499
            apm: [1.000009718505223404869550820340153335643556327276483904206533100102170732129453015698 +/- 3.32e-85]
        cmath53:  1.00000971850523
        sflintc:  1.00001
        dflintc:  1.00000971850522
        eflintc:  1.0000097185052234048
        qflintc:  1.00000971850522340486955082034015
        oflintc:  1.00000971850522340486955082034015333564355632727648390420653310010217
        mflintc:  1.00000971850522340486955082034015333564355632727648390420653310010217073212945301569795484
        aflintc: [1.000009718505223404869550820340153335643556327276483904206533100102170732129453016 +/- 4.20e-82]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_cd(x, k))))
            fpm:  -0.000937898537892113
            mpm:  -0.000937898537892112979694925386453457626297786033495630557524697596842405323750135037460240752
            dpm:  -0.000937898537892112979694925386453457626297786033495630557524697596842405323750135037460240752
            gpm:  -0.00093789853789211297969492538645345762629778603349563055752469759684240532375013503746024075196
            apm: [-0.000937898537892112979694925386453457626297786033495630557524697596842405323750135037 +/- 7.47e-85]
        cmath53:  -0.000937898537893714
        sflintc:  -0.000937908
        dflintc:  -0.000937898537892147
        eflintc:  -0.00093789853789211298798
        qflintc:  -0.000937898537892112979694925386453487
        oflintc:  -0.00093789853789211297969492538645345762629778603349563055752469759684
        mflintc:  -0.000937898537892112979694925386453457626297786033495630557524697596842405323750135037460244943
        aflintc: [-0.000937898537892112979694925386453457626297786033495630557524697596842405323750135 +/- 1.56e-82]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D09a_JacobiCdReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D09b_JacobiCdCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D09_JacobiCd.cs>`__. 







|newpage|

Jacobi elliptic function `\mathrm{ns}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_ns(x, k)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{ns}(x, k) =1/\mathrm{sn}(x, k)`. See also  BoostMath :cite:p:`BoostFun165`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun165`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.10).


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_ns(x, k)))
            fpm:  4.05905629290737
            mpm:  4.05905629290737224520592861711093742809422391716997418692889131532500272844863224787342039
            dpm:  4.05905629290737224520592861711093742809422391716997418692889131532500272844863224787342039
            gpm:  4.0590562929073722452059286171109374280942239171699741869288913153250027284486322478734203899
            apm: [4.0590562929073722452059286171109374280942239171699741869288913153250027284486322478734 +/- 5.88e-86]
         math53:  4.05905629290737
          sreal:  4.059056
          dreal:  4.05905629290737
          ereal:  4.0590562929073722405
          qreal:  4.05905629290737224520592861711094
          oreal:  4.0590562929073722452059286171109374280942239171699741869288913153250025
          mreal:  4.05905629290737224520592861711093742809422391716997418692889131532500272844863224787342041
         sflint:  4.059056
         dflint:  4.05905629290737
         eflint:  4.0590562929073722453
         qflint:  4.05905629290737224520592861711094
         oflint:  4.0590562929073722452059286171109374280942239171699741869288913153250027
         mflint:  4.05905629290737224520592861711093742809422391716997418692889131532500272844863224787342008
         aflint: [4.0590562929073722452059286171109374280942239171699741869288913153250027284486322479 +/- 4.28e-83]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_ns(x, k)))
            fpm:  (-8.44956300141373, -76.2427827430807)
            mpm:  (-8.449563001413728865924406112654300964258, -76.24278274308066539050121775217493190718)
        cmath53:  (-8.44956300137055, -76.2427827430997)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_ns(x, k))))
            fpm:  -8.44956300141373
            mpm:  -8.44956300141372886592440611265430096434694471086050931081620380186523336443108146730146271
            dpm:  -8.44956300141372886592440611265430096434694471086050931081620380186523336443108146730146271
            gpm:  -8.4495630014137288659244061126543009643469447108605093108162038018652333644310814673014627098
            apm: [-8.4495630014137288659244061126543009643469447108605093108162038018652333644310814673 +/- 7.50e-83]
        cmath53:  -8.44956300137055
        sflintc:  -8.449093
        dflintc:  -8.44956300141201
        eflintc:  -8.449563001413728445
        qflintc:  -8.44956300141372886592440611265281
        oflintc:  -8.449563001413728865924406112654300964346944710860509310816203801865
        mflintc:  -8.44956300141372886592440611265430096434694471086050931081620380186523336443108146730129706
        aflintc: [-8.4495630014137288659244061126543009643469447108605093108162038018652333644310815 +/- 5.21e-80]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_ns(x, k))))
            fpm:  -76.2427827430807
            mpm:  -76.2427827430806653905012177521749319072447861718548027508717713459112315570179047842066646
            dpm:  -76.2427827430806653905012177521749319072447861718548027508717713459112315570179047842066646
            gpm:  -76.242782743080665390501217752174931907244786171854802750871771345911231557017904784206664602
            apm: [-76.2427827430806653905012177521749319072447861718548027508717713459112315570179047842 +/- 8.02e-83]
        cmath53:  -76.2427827430997
        sflintc:  -76.24245
        dflintc:  -76.2427827430795
        eflintc:  -76.242782743080665102
        qflintc:  -76.2427827430806653905012177521739
        oflintc:  -76.242782743080665390501217752174931907244786171854802750871771345911
        mflintc:  -76.2427827430806653905012177521749319072447861718548027508717713459112315570179047842065295
        aflintc: [-76.2427827430806653905012177521749319072447861718548027508717713459112315570179048 +/- 3.52e-80]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D10a_JacobiNsReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D10b_JacobiNsCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D10_JacobiNs.cs>`__. 







|newpage|

Jacobi elliptic function `\mathrm{cs}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_cs(x, k)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{cs}(x, k) = \mathrm{cn}(x, k)/\mathrm{sn}(x, k)`. See also  BoostMath :cite:p:`BoostFun159`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun159`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.11).


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_cs(x, k)))
            fpm:  3.93394687165332
            mpm:  3.93394687165331953304550369931588124225463082511052391296207837623316215105737099092871194
            dpm:  3.93394687165331953304550369931588124225463082511052391296207837623316215105737099092871194
            gpm:  3.93394687165331953304550369931588124225463082511052391296207837623316215105737099092871194
            apm: [3.933946871653319533045503699315881242254630825110523912962078376233162151057370990929 +/- 3.78e-85]
         math53:  3.93394687165332
          sreal:  3.933947
          dreal:  3.93394687165332
          ereal:  3.9339468716533195292
          qreal:  3.93394687165331953304550369931589
          oreal:  3.9339468716533195330455036993158812422546308251105239129620783762331618
          mreal:  3.93394687165331953304550369931588124225463082511052391296207837623316215105737099092871196
         sflint:  3.933947
         dflint:  3.93394687165332
         eflint:  3.9339468716533195331
         qflint:  3.93394687165331953304550369931588
         oflint:  3.9339468716533195330455036993158812422546308251105239129620783762331622
         mflint:  3.93394687165331953304550369931588124225463082511052391296207837623316215105737099092871161
         aflint: [3.9339468716533195330455036993158812422546308251105239129620783762331621510573709909 +/- 5.92e-83]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_cs(x, k)))
            fpm:  (8.44884512318457, 76.2492609105773)
            mpm:  (8.448845123184572888950086660025145690217, 76.24926091057734882266959202557231002141)
        cmath53:  (8.44884512314235, 76.2492609105969)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_cs(x, k))))
            fpm:  8.44884512318457
            mpm:  8.44884512318457288895008666002514569030576363491727318445904276364996073936065071081800078
            dpm:  8.44884512318457288895008666002514569030576363491727318445904276364996073936065071081800078
            gpm:  8.4488451231845728889500866600251456903057636349172731844590427636499607393606507108180007801
            apm: [8.448845123184572888950086660025145690305763634917273184459042763649960739360650711 +/- 2.68e-82]
        cmath53:  8.44884512314235
        sflintc:  8.448375
        dflintc:  8.44884512318285
        eflintc:  8.4488451231845724679
        qflintc:  8.44884512318457288895008666002365
        oflintc:  8.44884512318457288895008666002514569030576363491727318445904276365
        mflintc:  8.44884512318457288895008666002514569030576363491727318445904276364996073936065071081783514
        aflintc: [8.4488451231845728889500866600251456903057636349172731844590427636499607393606507 +/- 3.54e-80]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_cs(x, k))))
            fpm:  76.2492609105773
            mpm:  76.2492609105773488226695920255723100214706206178248558600114202948415014090915382485360034
            dpm:  76.2492609105773488226695920255723100214706206178248558600114202948415014090915382485360034
            gpm:  76.249260910577348822669592025572310021470620617824855860011420294841501409091538248536003393
            apm: [76.249260910577348822669592025572310021470620617824855860011420294841501409091538249 +/- 5.50e-82]
        cmath53:  76.2492609105969
        sflintc:  76.24893
        dflintc:  76.2492609105762
        eflintc:  76.249260910577348532
        qflintc:  76.2492609105773488226695920255713
        oflintc:  76.24926091057734882266959202557231002147062061782485586001142029484
        mflintc:  76.2492609105773488226695920255723100214706206178248558600114202948415014090915382485358682
        aflintc: [76.2492609105773488226695920255723100214706206178248558600114202948415014090915382 +/- 7.31e-80]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D11a_JacobiCsReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D11b_JacobiCsCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D11_JacobiCs.cs>`__. 








|newpage|

Jacobi elliptic function `\mathrm{ds}(x, k)`
-------------------------------------------------------------------------------

.. method:: ctx.jacobi_ds(x, k)

    where ``ctx`` is ``math53`` or ``ctxboost``.

    Returns the Jacobi elliptic function `\mathrm{ds}(x, k) = \mathrm{dn}(x, k)/\mathrm{sn}(x, k)`. See also  BoostMath :cite:p:`BoostFun162`, Wikipedia :cite:p:`WikipediaFun155`, MathWorld :cite:p:`WolframFun162`, NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.11.12).


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; k = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_ds(x, k)))
            fpm:  3.03083123729959
            mpm:  3.03083123729958598745829070479893361212837724818300643486395269157289361108401193506219445
            dpm:  3.03083123729958598745829070479893361212837724818300643486395269157289361108401193506219445
            gpm:  3.0308312372995859874582907047989336121283772481830064348639526915728936110840119350621944498
            apm: [3.0308312372995859874582907047989336121283772481830064348639526915728936110840119350622 +/- 8.56e-86]
         math53:  3.03083123729959
          sreal:  3.030831
          dreal:  3.03083123729959
          ereal:  3.0308312372995859815
          qreal:  3.03083123729958598745829070479894
          oreal:  3.0308312372995859874582907047989336121283772481830064348639526915728933
          mreal:  3.03083123729958598745829070479893361212837724818300643486395269157289361108401193506219447
         sflint:  3.030831
         dflint:  3.03083123729959
         eflint:  3.0308312372995859876
         qflint:  3.03083123729958598745829070479893
         oflint:  3.0308312372995859874582907047989336121283772481830064348639526915728936
         mflint:  3.03083123729958598745829070479893361212837724818300643486395269157289361108401193506219403
         aflint: [3.0308312372995859874582907047989336121283772481830064348639526915728936110840119351 +/- 6.34e-83]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.jacobi_ds(x, k)))
            fpm:  (8.37724296458391, 76.256376816509)
            mpm:  (8.377242964583910045918666958996255296959, 76.25637681650898988928226771791955757037)
        cmath53:  (8.37724296454147, 76.2563768165278)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.jacobi_ds(x, k))))
            fpm:  8.37724296458391
            mpm:  8.37724296458391004591866695899625529704855804447501617628231625408759307142455432431936164
            dpm:  8.37724296458391004591866695899625529704855804447501617628231625408759307142455432431936164
            gpm:  8.3772429645839100459186669589962552970485580444750161762823162540875930714245543243193616395
            apm: [8.377242964583910045918666958996255297048558044475016176282316254087593071424554324 +/- 4.06e-82]
        cmath53:  8.37724296454147
        sflintc:  8.376772
        dflintc:  8.37724296458219
        eflintc:  8.3772429645839096247
        qflintc:  8.37724296458391004591866695899476
        oflintc:  8.37724296458391004591866695899625529704855804447501617628231625409
        mflintc:  8.37724296458391004591866695899625529704855804447501617628231625408759307142455432431919585
        aflintc: [8.3772429645839100459186669589962552970485580444750161762823162540875930714245543 +/- 4.86e-80]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.jacobi_ds(x, k))))
            fpm:  76.256376816509
            mpm:  76.2563768165089898892822677179195575704306943475020838978054731203821864125333374551377197
            dpm:  76.2563768165089898892822677179195575704306943475020838978054731203821864125333374551377197
            gpm:  76.256376816508989889282267717919557570430694347502083897805473120382186412533337455137719705
            apm: [76.256376816508989889282267717919557570430694347502083897805473120382186412533337455 +/- 2.24e-82]
        cmath53:  76.2563768165278
        sflintc:  76.25604
        dflintc:  76.2563768165078
        eflintc:  76.256376816508989601
        qflintc:  76.2563768165089898892822677179185
        oflintc:  76.256376816508989889282267717919557570430694347502083897805473120382
        mflintc:  76.2563768165089898892822677179195575704306943475020838978054731203821864125333374551375848
        aflintc: [76.2563768165089898892822677179195575704306943475020838978054731203821864125333375 +/- 6.91e-80]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D12a_JacobiDsReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D12b_JacobiDsCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C04_JacobiEllipticFunctions/D12_JacobiDs.cs>`__. 


