

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Polygamma and related functions
===============================================================================




.. _rst_mpm_polygamma: 

Polygamma function, `\psi^{(n)}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.polygamma(n, x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.


    Returns the polygamma function `\psi^{(n)}(x), \quad x \ne 0, -1, -2, \ldots` The function returns the Hurwitz zeta value `(-1)^{n+1}n!\zeta(n+1,x)` if `x` is positive; for `x<0` it is calculated from `\psi^{(n)}(1-x) + (-1)^{n+1}\psi^{(n)}(x) = (-1)^n \pi \frac{\mathrm{d}^n}{\mathrm{d}x^n} \cot(\pi x)`.

    See also   Wikipedia :cite:p:`WikipediaFun83`, MathWorld :cite:p:`WolframFun83`, NIST :cite:p:`DLMFun83`,  BoostMath :cite:p:`BoostFun83`, :cite:t:`Ehrhardt2018` (3.5.6.6), Flint :cite:p:`FlintFun71`,  Mpmath :cite:p:`MpmathFun83`.


    This function computes the polygamma function `\psi^{(n)}(x)`, i.e. the `n^{th}` derivative of the `\psi` function, with `n\geq 0` and `x\neq 0, -1, -2,\ldots`. For `x>0` the result is calculated as

    .. math :: \psi^{(n)}(x) = (-1)^{n+1} n! \: \Phi(1, n+1, x) = (-1)^{n+1} n! \zeta(n+1,x).

    The generalization to other values of *s* is due to Espinosa and Moll (see :cite:t:`Espinosa2004`) :

    .. math :: \psi(s,z) = \frac{\zeta'(s+1,z) + (\gamma + \psi(-s)) \zeta(s+1,z)}{\Gamma(-s)}


    


    |03a_TestPolygammaFlint_re| `\quad` |03b_TestPolygammaFlint_im| `\quad` |03c_TestPolygammaFlint_abs|

    .. |03a_TestPolygammaFlint_re| image:: ../_static/ExplicitSurfaces/CplxLerch/03a_TestPolygammaFlint_re.3D.xml.jpg
       :width: 30 %

    .. |03b_TestPolygammaFlint_im| image:: ../_static/ExplicitSurfaces/CplxLerch/03b_TestPolygammaFlint_im.3D.xml.jpg
       :width: 30 %

    .. |03c_TestPolygammaFlint_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/03c_TestPolygammaFlint_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.







    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 3; x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.polygamma(n, x)))
            fpm:  60014.240679133
            mpm:  60014.2406791329612341010511562216065754458994646865761656674457949881310817824602825542327
            dpm:  60014.2406791329612341010511562216065754458994646865761656674457949881310817824602825542327
            gpm:  60014.240679132961234101051156221606575445899464686576165667445794988131081782460282554232698
            apm: [60014.24067913296123410105115622160657544589946468657616566744579498813108178246028255424 +/- 7.28e-84]
         math53:  60014.2406791338
          sreal:  60014.47
          dreal:  60014.2406791338
          ereal:  60014.240679132961429
          qreal:  60014.2406791329612341010511562223
          oreal:  60014.240679132961234101051156221606575445899464686576165667445794988166
          mreal:  60014.2406791329612341010511562216065754458994646865761656674457949881310817824602825542351
         sflint:  60014.47
         dflint:  60014.2406791338
         eflint:  60014.240679132961443
         qflint:  60014.2406791329612341010511562223
         oflint:  60014.240679132961234101051156221606575445899464686576165667445794988165
         mflint:  60014.2406791329612341010511562216065754458994646865761656674457949881310817824602825542351
         aflint: [60014.24067913296123410105115622160657544589946468657616566744579498813108178246028255424 +/- 6.84e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 3; x = -5.1+2j;  gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.polygamma(n, x)))
            fpm:  (-0.000524225913727169, -0.0112138833424731)
            mpm:  (-0.00052422591372716913513511700597646157052311209010205, -0.011213883342473116367308886548396628371610786286177)
        cmath53:  (-0.000524225913760924, -0.0112138833425053)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 3; x = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.polygamma(n, x))))
            fpm:  -0.000524225913727169
            mpm:  -0.00052422591372716913513511700597646157052311209010213647580072706703363355593417416741891004
            dpm:  -0.00052422591372716913513511700597646157052311209010213647580072706703363355593417416741891004
            gpm:  -0.00052422591372716913513511700597646157052311209010213647580072706703363355593417416741891004
            apm: [-0.00052422591372716913513511700597646157052311209010213647580072706703363355593417416741891 +/- 1.94e-90]
        cmath53:  -0.000524225913760924
        sflintc:  -0.0005242241
        dflintc:  -0.000524225913727162
        eflintc:  -0.00052422591372716913349
        qflintc:  -0.000524225913727169135135117005976456
        oflintc:  -0.00052422591372716913513511700597646157052311209010213647580072706703363329
        mflintc:  -0.000524225913727169135135117005976461570523112090102136475800727067033633555934174167418910021
        aflintc: [-0.00052422591372716913513511700597646157052311209010213647580072706703363355593417416741891 +/- 1.56e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 3; x = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.polygamma(n, x))))
            fpm:  -0.0112138833424731
            mpm:  -0.011213883342473116367308886548396628371610786286177318124206497905510492660472860849283543
            dpm:  -0.011213883342473116367308886548396628371610786286177318124206497905510492660472860849283543
            gpm:  -0.011213883342473116367308886548396628371610786286177318124206497905510492660472860849283542999
            apm: [-0.01121388334247311636730888654839662837161078628617731812420649790551049266047286084928354 +/- 5.50e-90]
        cmath53:  -0.0112138833425053
        sflintc:  -0.01121388
        dflintc:  -0.0112138833424731
        eflintc:  -0.011213883342473116365
        qflintc:  -0.0112138833424731163673088865483966
        oflintc:  -0.011213883342473116367308886548396628371610786286177318124206497905510492
        mflintc:  -0.011213883342473116367308886548396628371610786286177318124206497905510492660472860849283543
        aflintc: [-0.01121388334247311636730888654839662837161078628617731812420649790551049266047286084928354 +/- 5.01e-90]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C02_Polygamma/D01a_PolygammaReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C02_Polygamma/D01b_PolygammaCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C02_Polygamma/D01_Polygamma.cs>`__. 







|newpage|

TriGamma function, `\psi'(x)`
-------------------------------------------------------------------------------

.. method:: ctx.trigamma(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the trigamma function `\psi'(x), \quad x \ne 0, -1, -2, \ldots` 

    The function returns the Hurwitz zeta value `\zeta(2, x)` if `x` is positive; for `x < 0` the polygamma reflection formula  for `n = 1` is used to compute the result

    .. math :: \psi'(x) = \left(\frac{\pi}{\sin(\pi x)} \right)^2 - \zeta(2,1-x).


    See also  Wikipedia :cite:p:`WikipediaFun126`, MathWorld :cite:p:`WolframFun126`, NIST :cite:p:`DLMFun83`,  BoostMath :cite:p:`BoostFun126`, :cite:t:`Ehrhardt2018` (3.5.6.3).

    



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.trigamma(x)))
            fpm:  103.177737033728
            mpm:  103.177737033727691639492460953759978802337324355671226160828191349385204905784205813902832
            dpm:  103.177737033727691639492460953759978802337324355671226160828191349385204905784205813902832
            gpm:  103.177737033727691639492460953759978802337324355671226160828191349385204905784205813902832
            apm: [103.17773703372769163949246095375997880233732435567122616082819134938520490578420581390283 +/- 5.59e-87]
         math53:  103.177737033728
          sreal:  103.1779
          dreal:  103.177737033728
          ereal:  103.17773703372769181
          qreal:  103.177737033727691639492460953761
          oreal:  103.17773703372769163949246095375997880233732435567122616082819134938523
          mreal:  103.177737033727691639492460953759978802337324355671226160828191349385204905784205813902834
         sflint:  103.1779
         dflint:  103.177737033728
         eflint:  103.17773703372769181
         qflint:  103.177737033727691639492460953761
         oflint:  103.17773703372769163949246095375997880233732435567122616082819134938523
         mflint:  103.177737033727691639492460953759978802337324355671226160828191349385204905784205813902834
         aflint: [103.17773703372769163949246095375997880233732435567122616082819134938520490578420581390283 +/- 5.25e-87]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.trigamma(x)))
            fpm:  (-0.158277569088854, -0.0561444064628947)
            mpm:  (-0.15827756908885356349806974466301297334751102312693, -0.056144406462894665897875977655550930493714366549291)
        cmath53:  (-0.158277569088852, -0.0561444064628938)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.trigamma(x))))
            fpm:  -0.158277569088854
            mpm:  -0.15827756908885356349806974466301297334751102312693291890156707911538083038134432319695028
            dpm:  -0.15827756908885356349806974466301297334751102312693291890156707911538083038134432319695028
            gpm:  -0.15827756908885356349806974466301297334751102312693291890156707911538083038134432319695028001
            apm: [-0.15827756908885356349806974466301297334751102312693291890156707911538083038134432319695028 +/- 9.72e-91]
        cmath53:  -0.158277569088852
        sflintc:  -0.1582776
        dflintc:  -0.158277569088854
        eflintc:  -0.1582775690888535635
        qflintc:  -0.158277569088853563498069744663013
        oflintc:  -0.15827756908885356349806974466301297334751102312693291890156707911538083
        mflintc:  -0.15827756908885356349806974466301297334751102312693291890156707911538083038134432319695028
        aflintc: [-0.158277569088853563498069744663012973347511023126932918901567079115380830381344323196950280 +/- 9.50e-91]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.trigamma(x))))
            fpm:  -0.0561444064628947
            mpm:  -0.0561444064628946658978759776555509304937143665492910768796710480058852667394712475389268799
            dpm:  -0.0561444064628946658978759776555509304937143665492910768796710480058852667394712475389268799
            gpm:  -0.056144406462894665897875977655550930493714366549291076879671048005885266739471247538926879902
            apm: [-0.05614440646289466589787597765555093049371436654929107687967104800588526673947124753892688 +/- 1.12e-90]
        cmath53:  -0.0561444064628938
        sflintc:  -0.05614441
        dflintc:  -0.0561444064628947
        eflintc:  -0.056144406462894665899
        qflintc:  -0.0561444064628946658978759776555509
        oflintc:  -0.056144406462894665897875977655550930493714366549291076879671048005885267
        mflintc:  -0.0561444064628946658978759776555509304937143665492910768796710480058852667394712475389268799
        aflintc: [-0.05614440646289466589787597765555093049371436654929107687967104800588526673947124753892688 +/- 9.57e-91]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C02_Polygamma/D02a_TrigammaReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C02_Polygamma/D02b_TrigammaCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C02_Polygamma/D02_Trigamma.cs>`__. 






|newpage|

.. _rst_mpm_digamma: 

DiGamma function `\psi(x)`
-------------------------------------------------------------------------------

.. method:: ctx.digamma(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxboost``, ``ctxflint``.



    Returns the digamma function `\displaystyle \psi(x) = \frac{\mathrm{d}(\log\Gamma(x)}{\mathrm{d}x} = \frac{\Gamma'(x)}{\Gamma(x)}, \quad x \ne 0, -1, -2, \ldots`.

    See also  Wikipedia :cite:p:`WikipediaFun125`, MathWorld :cite:p:`WolframFun125`, NIST :cite:p:`DLMFun83`,  BoostMath :cite:p:`BoostFun125`, :cite:t:`Ehrhardt2018` (3.5.6.1), :cite:t:`Ehrhardt2018` (4.2.50), Flint :cite:p:`FlintFun70`, Flint :cite:p:`FlintFun71`, Mpmath :cite:p:`MpmathFun126`. 


    This function returns the digamma or `\psi` function, which is defines as

    .. math :: \psi(x) = \frac{d(\log \Gamma(x))}{\mathrm{d}x} = \frac{\Gamma'(x)}{\Gamma(x)}, \quad x \neq 0, -1, -2,\ldots

    If `x<0` it is transformed to positive values with the reflection formula

    .. math :: \psi(1-x)=\psi(x) + \pi \cot(\pi x)

    and for `0<x<12` the recurrence formula

    .. math :: \psi(x+1)=\psi(x) + \frac{1}{x}




    |04a_TestDigamma_re| `\quad` |04b_TestDigamma_im| `\quad` |04c_TestDigamma_abs|

    .. |04a_TestDigamma_re| image:: ../_static/ExplicitSurfaces/CplxLerch/04a_TestDigamma_re.3D.xml.jpg
       :width: 30 %

    .. |04b_TestDigamma_im| image:: ../_static/ExplicitSurfaces/CplxLerch/04b_TestDigamma_im.3D.xml.jpg
       :width: 30 %

    .. |04c_TestDigamma_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/04c_TestDigamma_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.digamma(x)))
            fpm:  11.3929159508926
            mpm:  11.392915950892563475589824681034358205660820639737918434775306568519978694422886714474036
            dpm:  11.392915950892563475589824681034358205660820639737918434775306568519978694422886714474036
            gpm:  11.392915950892563475589824681034358205660820639737918434775306568519978694422886714474035999
            apm: [11.392915950892563475589824681034358205660820639737918434775306568519978694422886714474036 +/- 1.89e-88]
         math53:  11.3929159508926
          sreal:  11.39293
          dreal:  11.3929159508926
          ereal:  11.392915950892563485
          qreal:  11.3929159508925634755898246810344
          oreal:  11.39291595089256347558982468103435820566082063973791843477530656851998
          mreal:  11.3929159508925634755898246810343582056608206397379184347753065685199786944228867144740361
         sflint:  11.39293
         dflint:  11.3929159508926
         eflint:  11.392915950892563485
         qflint:  11.3929159508925634755898246810344
         oflint:  11.39291595089256347558982468103435820566082063973791843477530656851998
         mflint:  11.3929159508925634755898246810343582056608206397379184347753065685199786944228867144740361
         aflint: [11.392915950892563475589824681034358205660820639737918434775306568519978694422886714474036 +/- 1.67e-88]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.digamma(x)))
            fpm:  (1.7837140682953, 2.79932726862651)
            mpm:  (1.7837140682953037106936654419329450623187548800597, 2.7993272686265128614158998442643293562643462934658)
        cmath53:  (1.7837140682953, 2.79932726862651)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.digamma(x))))
            fpm:  1.7837140682953
            mpm:  1.7837140682953037106936654419329450623187548800597137510964552131511106705402054698328295
            dpm:  1.7837140682953037106936654419329450623187548800597137510964552131511106705402054698328295
            gpm:  1.7837140682953037106936654419329450623187548800597137510964552131511106705402054698328295001
            apm: [1.7837140682953037106936654419329450623187548800597137510964552131511106705402054698328295 +/- 5.48e-89]
        cmath53:  1.7837140682953
        sflintc:  1.783714
        dflintc:  1.7837140682953
        eflintc:  1.7837140682953037107
        qflintc:  1.78371406829530371069366544193294
        oflintc:  1.7837140682953037106936654419329450623187548800597137510964552131511107
        mflintc:  1.7837140682953037106936654419329450623187548800597137510964552131511106705402054698328295
        aflintc: [1.7837140682953037106936654419329450623187548800597137510964552131511106705402054698328295 +/- 4.40e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.digamma(x))))
            fpm:  2.79932726862651
            mpm:  2.79932726862651286141589984426432935626434629346575923137043775091988182703698883206001115
            dpm:  2.79932726862651286141589984426432935626434629346575923137043775091988182703698883206001115
            gpm:  2.7993272686265128614158998442643293562643462934657592313704377509198818270369888320600111501
            apm: [2.799327268626512861415899844264329356264346293465759231370437750919881827036988832060011 +/- 2.03e-88]
        cmath53:  2.79932726862651
        sflintc:  2.799327
        dflintc:  2.79932726862651
        eflintc:  2.7993272686265128614
        qflintc:  2.79932726862651286141589984426433
        oflintc:  2.7993272686265128614158998442643293562643462934657592313704377509198818
        mflintc:  2.79932726862651286141589984426432935626434629346575923137043775091988182703698883206001115
        aflintc: [2.7993272686265128614158998442643293562643462934657592313704377509198818270369888320600111 +/- 9.14e-89]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C02_Polygamma/D03a_DigammaReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C02_Polygamma/D03b_DigammaCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C02_Polygamma/D03_Digamma.cs>`__. 








|newpage|

Harmonic number function, `H_x`
-------------------------------------------------------------------------------

.. method:: ctx.harmonic(x)

    Returns the Harmonic number  `H_x = \psi(x+1) + \gamma, \quad x \ne -1, -2, \ldots`.

    See also:  Wikipedia :cite:p:`WikipediaFun127`, MathWorld :cite:p:`WolframFun127a`, :cite:t:`Ehrhardt2018` (3.6.20), Mpmath :cite:p:`MpmathFun127`.




    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.harmonic(x)))
            fpm:  2.30130362533007
            mpm:  2.3013036253300709329145045792892307520042975648337991224817096515600771260992411710317625
            dpm:  2.3013036253300709329145045792892307520042975648337991224817096515600771260992411710317625
            gpm:  2.3013036253300709329145045792892307520042975648337991224817096515600771260992411710317625
            apm: [2.3013036253300709329145045792892307520042975648337991224817096515600771260992411710317625 +/- 1.40e-89]
         math53:  2.30130362533007
         sflint:  2.301304
         dflint:  2.30130362533007
         eflint:  2.3013036253300709329
         qflint:  2.30130362533007093291450457928923
         oflint:  2.3013036253300709329145045792892307520042975648337991224817096515600771
         mflint:  2.3013036253300709329145045792892307520042975648337991224817096515600771260992411710317625
         aflint: [2.3013036253300709329145045792892307520042975648337991224817096515600771260992411710317625 +/- 1.44e-89]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.harmonic(x)))
            fpm:  (2.19098638098091, 2.73268281677713)
            mpm:  (2.1909863809809085473081748662372735180193614002715, 2.7326828167771293225955066419984179933853059735724)
        cmath53:  (2.19098638098091, 2.73268281677713)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.harmonic(x))))
            fpm:  2.19098638098091
            mpm:  2.19098638098090854730817486623727351801936140027154671344770728642318266256278850131626107
            dpm:  2.19098638098090854730817486623727351801936140027154671344770728642318266256278850131626107
            gpm:  2.1909863809809085473081748662372735180193614002715467134477072864231826625627885013162610702
            apm: [2.190986380980908547308174866237273518019361400271546713447707286423182662562788501316 +/- 3.59e-85]
        cmath53:  2.19098638098091
        sflintc:  2.190986
        dflintc:  2.19098638098091
        eflintc:  2.1909863809809085474
        qflintc:  2.19098638098090854730817486623727
        oflintc:  2.1909863809809085473081748662372735180193614002715467134477072864231827
        mflintc:  2.19098638098090854730817486623727351801936140027154671344770728642318266256278850131626107
        aflintc: [2.190986380980908547308174866237273518019361400271546713447707286423182662562788501316 +/- 3.39e-85]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.harmonic(x))))
            fpm:  2.73268281677713
            mpm:  2.73268281677712932259550664199841799338530597357239035432945141303251095066244701266647566
            dpm:  2.73268281677712932259550664199841799338530597357239035432945141303251095066244701266647566
            gpm:  2.7326828167771293225955066419984179933853059735723903543294514130325109506624470126664756599
            apm: [2.732682816777129322595506641998417993385305973572390354329451413032510950662447012666 +/- 5.73e-85]
        cmath53:  2.73268281677713
        sflintc:  2.732683
        dflintc:  2.73268281677713
        eflintc:  2.7326828167771293227
        qflintc:  2.73268281677712932259550664199842
        oflintc:  2.7326828167771293225955066419984179933853059735723903543294514130325109
        mflintc:  2.73268281677712932259550664199841799338530597357239035432945141303251095066244701266647566
        aflintc: [2.732682816777129322595506641998417993385305973572390354329451413032510950662447012666 +/- 5.54e-85]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C02_Polygamma/D04a_HarmonicReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C02_Polygamma/D04b_HarmonicCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C02_Polygamma/D04_Harmonic.cs>`__. 





