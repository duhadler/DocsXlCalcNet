

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|

Polylogarithm and related functions
===============================================================================




.. _rst_mpm_polylog: 

Polylogarithm, `\mathrm{Li}_s(z)`
-------------------------------------------------------------------------------

.. method:: ctx.polylog(x, s)

    where ``ctx`` is ``math53``, ``ctxflint``.


    Returns the polylogarithm  of real order `s`, `\displaystyle \mathrm{Li}_s(x) = \sum_{k=1}^{\infty} \frac{x^k}{k^s}, \quad s \ge -1, |x| \le 1 \,`, or its analytic continuation. For `s\leq 1` there is the additional arguments restriction `z\neq 1`.

    See also   Wikipedia :cite:p:`WikipediaFun173`, MathWorld :cite:p:`WolframFun173`, NIST :cite:p:`DLMFun173`, :cite:t:`Ehrhardt2018` (3.6.12), Flint :cite:p:`FlintFun173`, Mpmath :cite:p:`MpmathFun173`. 


    Special cases are `\mathrm{Li}_s(0) = 0`, `\mathrm{Li}_s(1) = \zeta(s)`, `\mathrm{Li}_s(-1) =  -\eta(s)`. For `x>1` the real part of `\mathrm{Li}_s(x)` is returned.




    |05a_TestPolylog_re| `\quad` |05b_TestPolylog_im| `\quad` |05c_TestPolylog_abs|

    .. |05a_TestPolylog_re| image:: ../_static/ExplicitSurfaces/CplxLerch/05a_TestPolylog_re.3D.xml.jpg
       :width: 30 %

    .. |05b_TestPolylog_im| image:: ../_static/ExplicitSurfaces/CplxLerch/05b_TestPolylog_im.3D.xml.jpg
       :width: 30 %

    .. |05c_TestPolylog_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/05c_TestPolylog_abs.3D.xml.jpg
       :width: 30 %



    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.






    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.polylog(s, z)))
            fpm:  -3.59230678081745
            mpm:  -3.59230678081744905268295841911768506775707853728411898795542303384253225662673321560385487
            dpm:  -3.59230678081744905268295841911768506775707853728411898795542303384253225662673321560385487
            gpm:  -3.5923067808174490526829584191176850677570785372841189879554230338425322566267332156038548702
            apm: ([-3.592306780817449052682958419117685067757078537284118987955423033842532256626733215604 +/- 2.12e-85], 0)
         math53:  -3.59230678081745
         sflint:  -3.592307
         dflint:  -3.59230678081745
         eflint:  -3.5923067808174490526
         qflint:  -3.59230678081744905268295841911768
         oflint:  -3.5923067808174490526829584191176850677570785372841189879554230338425322
         mflint:  -3.59230678081744905268295841911768506775707853728411898795542303384253225662673321560385296
         aflint: [-3.592306780817449052682958419117685067757078537284118987955423033842532256626733215604 +/- 3.70e-85]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.polylog(s, z)))
            fpm:  (-3.6657967998322, 1.08257770822294)
            mpm:  (-3.6657967998322045210741430067366527731673112148532, 1.0825777082229407771765495069960308915177005851599)
        cmath53:  (-3.6657967998322, 1.08257770822294)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.polylog(s, z))))
            fpm:  -3.6657967998322
            mpm:  -3.66579679983220452107414300673665277316731121485315555771785592080266904639136248739217266
            dpm:  -3.66579679983220452107414300673665277316731121485315555771785592080266904639136248739217266
            gpm:  -3.6657967998322045210741430067366527731673112148531555577178559208026690463913624873921726599
            apm: [-3.665796799832204521074143006736652773167311214853155557717855920802669046391362487392 +/- 4.46e-85]
        cmath53:  -3.6657967998322
        sflintc:  -3.665797
        dflintc:  -3.6657967998322
        eflintc:  -3.6657967998322045211
        qflintc:  -3.66579679983220452107414300673665
        oflintc:  -3.665796799832204521074143006736652773167311214853155557717855920802669
        mflintc:  -3.66579679983220452107414300673665277316731121485315555771785592080266904639136248739217202
        aflintc: [-3.66579679983220452107414300673665277316731121485315555771785592080266904639136248739 +/- 3.18e-84]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.polylog(s, z))))
            fpm:  1.08257770822294
            mpm:  1.08257770822294077717654950699603089151770058515991635625785362032811000578169041759347163
            dpm:  1.08257770822294077717654950699603089151770058515991635625785362032811000578169041759347163
            gpm:  1.0825777082229407771765495069960308915177005851599163562578536203281100057816904175934716301
            apm: [1.082577708222940777176549506996030891517700585159916356257853620328110005781690417593 +/- 7.61e-85]
        cmath53:  1.08257770822294
        sflintc:  1.082578
        dflintc:  1.08257770822294
        eflintc:  1.0825777082229407772
        qflintc:  1.08257770822294077717654950699603
        oflintc:  1.08257770822294077717654950699603089151770058515991635625785362032811
        mflintc:  1.08257770822294077717654950699603089151770058515991635625785362032811000578169041759347177
        aflintc: [1.08257770822294077717654950699603089151770058515991635625785362032811000578169041759 +/- 4.49e-84]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D01a_PolylogarithmReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D01b_PolylogarithmCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D01_Polylogarithm.cs>`__. 






|newpage|

Trilogarithm Function, `\mathrm{Li}_3(z)`
-------------------------------------------------------------------------------

.. method:: ctx.trilog(x)

    Returns the trilogarithm  `\displaystyle \mathrm{trilog}(x) = \Re \displaystyle \mathrm{Li}_3(x)`. See also   Wikipedia :cite:p:`WikipediaFun174`, MathWorld :cite:p:`WolframFun174`, NIST :cite:p:`DLMFun174`, :cite:t:`Ehrhardt2018` (3.6.14), Mpmath :cite:p:`MpmathFun173`. 




    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.trilog(z)))
            fpm:  -3.59230678081745
            mpm:  -3.59230678081744905268295841911768506775707853728411898795542303384253225662673321560385487
            dpm:  -3.59230678081744905268295841911768506775707853728411898795542303384253225662673321560385487
            gpm:  -3.5923067808174490526829584191176850677570785372841189879554230338425322566267332156038548702
            apm: [-3.592306780817449052682958419117685067757078537284118987955423033842532256626733215604 +/- 2.12e-85]
         math53:  -3.59230678081745
         sflint:  -3.592307
         dflint:  -3.59230678081745
         eflint:  -3.5923067808174490526
         qflint:  -3.59230678081744905268295841911768
         oflint:  -3.5923067808174490526829584191176850677570785372841189879554230338425322
         mflint:  -3.59230678081744905268295841911768506775707853728411898795542303384253225662673321560385296
         aflint: [-3.592306780817449052682958419117685067757078537284118987955423033842532256626733215604 +/- 3.70e-85]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.trilog(z)))
            fpm:  (-3.6657967998322, 1.08257770822294)
            mpm:  (-3.6657967998322045210741430067366527731673112148532, 1.0825777082229407771765495069960308915177005851599)
        cmath53:  (-3.6657967998322, 1.08257770822294)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.trilog(z))))
            fpm:  -3.6657967998322
            mpm:  -3.66579679983220452107414300673665277316731121485315555771785592080266904639136248739217266
            dpm:  -3.66579679983220452107414300673665277316731121485315555771785592080266904639136248739217266
            gpm:  -3.6657967998322045210741430067366527731673112148531555577178559208026690463913624873921726599
            apm: [-3.665796799832204521074143006736652773167311214853155557717855920802669046391362487392 +/- 4.46e-85]
        cmath53:  -3.6657967998322
        sflintc:  -3.665797
        dflintc:  -3.6657967998322
        eflintc:  -3.6657967998322045211
        qflintc:  -3.66579679983220452107414300673665
        oflintc:  -3.665796799832204521074143006736652773167311214853155557717855920802669
        mflintc:  -3.66579679983220452107414300673665277316731121485315555771785592080266904639136248739217202
        aflintc: [-3.66579679983220452107414300673665277316731121485315555771785592080266904639136248739 +/- 3.18e-84]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.trilog(z))))
            fpm:  1.08257770822294
            mpm:  1.08257770822294077717654950699603089151770058515991635625785362032811000578169041759347163
            dpm:  1.08257770822294077717654950699603089151770058515991635625785362032811000578169041759347163
            gpm:  1.0825777082229407771765495069960308915177005851599163562578536203281100057816904175934716301
            apm: [1.082577708222940777176549506996030891517700585159916356257853620328110005781690417593 +/- 7.61e-85]
        cmath53:  1.08257770822294
        sflintc:  1.082578
        dflintc:  1.08257770822294
        eflintc:  1.0825777082229407772
        qflintc:  1.08257770822294077717654950699603
        oflintc:  1.08257770822294077717654950699603089151770058515991635625785362032811
        mflintc:  1.08257770822294077717654950699603089151770058515991635625785362032811000578169041759347177
        aflintc: [1.08257770822294077717654950699603089151770058515991635625785362032811000578169041759 +/- 4.49e-84]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D02a_TrilogarithmReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D02b_TrilogarithmCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D02_Trilogarithm.cs>`__. 











|newpage|

Dilogarithm Function, `\mathrm{Li}_2(z)`
-------------------------------------------------------------------------------

.. method:: ctx.dilog(x)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxflint``.

    Returns the dilogarithm  `\displaystyle \mathrm{dilog}(x) = \Re \displaystyle \mathrm{Li}_2(x) = -\Re \int_0^x \frac{\log(1-t)}{t} \, \mathrm{d}t`.

    See also   Wikipedia :cite:p:`WikipediaFun174`, MathWorld :cite:p:`WolframFun174`, NIST :cite:p:`DLMFun174`, :cite:t:`Ehrhardt2018` (3.6.13), :cite:t:`Ehrhardt2018` (4.2.25), Flint :cite:p:`FlintFun174`, Mpmath :cite:p:`MpmathFun173`. 


    Note that there is some confusion about the naming: some authors and/or computer algebra systems use `\text{dilog}(x) = \text{Li}_2(1-x)` and then call `\text{Li}_2(x)` Spence function/integral or similar.



    |06a_TestDilog_re| `\quad` |06b_TestDilog_im| `\quad` |06c_TestDilog_abs|

    .. |06a_TestDilog_re| image:: ../_static/ExplicitSurfaces/CplxLerch/06a_TestDilog_re.3D.xml.jpg
       :width: 30 %

    .. |06b_TestDilog_im| image:: ../_static/ExplicitSurfaces/CplxLerch/06b_TestDilog_im.3D.xml.jpg
       :width: 30 %

    .. |06c_TestDilog_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/06c_TestDilog_abs.3D.xml.jpg
       :width: 30 %


   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.dilog(z)))
            fpm:  -2.78492424355145
            mpm:  -2.78492424355145023674683789014343022176784251837845092302363253649419317396204793066075053
            dpm:  -2.78492424355145023674683789014343022176784251837845092302363253649419317396204793066075053
            gpm:  -2.7849242435514502367468378901434302217678425183784509230236325364941931739620479306607505301
            apm: [-2.78492424355145023674683789014343022176784251837845092302363253649419317396204793066075053 +/- 6.01e-90]
         math53:  -2.78492424355145
         sflint:  -2.784924
         dflint:  -2.78492424355145
         eflint:  -2.7849242435514502368
         qflint:  -2.78492424355145023674683789014343
         oflint:  -2.7849242435514502367468378901434302217678425183784509230236325364941932
         mflint:  -2.78492424355145023674683789014343022176784251837845092302363253649419317396204793066075052
         aflint: [-2.78492424355145023674683789014343022176784251837845092302363253649419317396204793066075052 +/- 6.29e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.dilog(z)))
            fpm:  (-2.8572793756887, 0.69714968425694)
            mpm:  (-2.8572793756887021669801494465599471426459186349772, 0.69714968425694008041041348380021789329105112919996)
        cmath53:  (-2.8572793756887, 0.69714968425694)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.dilog(z))))
            fpm:  -2.8572793756887
            mpm:  -2.85727937568870216698014944655994714264591863497719893774429749320478586258285880227466774
            dpm:  -2.85727937568870216698014944655994714264591863497719893774429749320478586258285880227466774
            gpm:  -2.85727937568870216698014944655994714264591863497719893774429749320478586258285880227466774
            apm: [-2.85727937568870216698014944655994714264591863497719893774429749320478586258285880227466774 +/- 1.15e-90]
        cmath53:  -2.8572793756887
        sflintc:  -2.857279
        dflintc:  -2.8572793756887
        eflintc:  -2.8572793756887021669
        qflintc:  -2.85727937568870216698014944655995
        oflintc:  -2.8572793756887021669801494465599471426459186349771989377442974932047859
        mflintc:  -2.85727937568870216698014944655994714264591863497719893774429749320478586258285880227466774
        aflintc: [-2.85727937568870216698014944655994714264591863497719893774429749320478586258285880227466774 +/- 3.60e-90]



    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.dilog(z))))
            fpm:  0.69714968425694
            mpm:  0.697149684256940080410413483800217893291051129199962089441280579605082594964114817555508751
            dpm:  0.697149684256940080410413483800217893291051129199962089441280579605082594964114817555508751
            gpm:  0.697149684256940080410413483800217893291051129199962089441280579605082594964114817555508751
            apm: [0.697149684256940080410413483800217893291051129199962089441280579605082594964114817555508751 +/- 8.31e-91]
        cmath53:  0.69714968425694
        sflintc:  0.6971497
        dflintc:  0.69714968425694
        eflintc:  0.69714968425694008044
        qflintc:  0.697149684256940080410413483800218
        oflintc:  0.6971496842569400804104134838002178932910511291999620894412805796050826
        mflintc:  0.697149684256940080410413483800217893291051129199962089441280579605082594964114817555508751
        aflintc: [0.69714968425694008041041348380021789329105112919996208944128057960508259496411481755550875 +/- 1.32e-90]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D03a_DilogarithmReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D03b_DilogarithmCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D03_Dilogarithm.cs>`__. 











|newpage|

.. _rst_mpm_clsin: 

Generalized Clausen sine function
-------------------------------------------------------------------------------

.. method:: ctx.clausen_sin(s, z)


    Returns the Clausen sine function. See also  Wikipedia :cite:p:`WikipediaFun1017`, MathWorld :cite:p:`WolframFun1017`, Mpmath :cite:p:`MpmathFun1017`. 

    Computes the Clausen sine function, defined formally by the series

    .. math ::

        \mathrm{Cl}_s(z) = \sum_{k=1}^{\infty} \frac{\sin(kz)}{k^s}.

    The special case `\mathrm{Cl}_2(z)` (i.e. ``clsin(2,z)``) is the classical
    "Clausen function". More generally, the Clausen function is defined for
    complex `s` and `z`, even when the series does not converge. The
    Clausen function is related to the polylogarithm (:ref:`polylog() <rst_mpm_polylog>`) as

    .. math ::

        \mathrm{Cl}_s(z) = \frac{1}{2i}\left(\mathrm{Li}_s\left(e^{iz}\right) -
                           \mathrm{Li}_s\left(e^{-iz}\right)\right)

        = \mathrm{Im}\left[\mathrm{Li}_s(e^{iz})\right] \quad (s, z \in \mathbb{R}),

    and this representation can be taken to provide the analytic continuation of the
    series. The complementary function :ref:`clcos() <rst_mpm_clcos>` gives the corresponding
    cosine sum.




    |07a_TestClausenSin_re| `\quad` |07b_TestClausenSin_im| `\quad` |07c_TestClausenSin_abs|

    .. |07a_TestClausenSin_re| image:: ../_static/ExplicitSurfaces/CplxLerch/07a_TestClausenSin_re.3D.xml.jpg
       :width: 30 %

    .. |07b_TestClausenSin_im| image:: ../_static/ExplicitSurfaces/CplxLerch/07b_TestClausenSin_im.3D.xml.jpg
       :width: 30 %

    .. |07c_TestClausenSin_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/07c_TestClausenSin_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.






    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.clausen_sin(s, z)))
            fpm:  0.984792489041676
            mpm:  0.984792489041675707094021249880239039475449523281953568438230241694538082819749557027289059
            dpm:  0.984792489041675707094021249880239039475449523281953568438230241694538082819749557027289059
            gpm:  0.98479248904167570709402124988023903947544952328195356843823024169453808281974955702728905903
            apm: [0.984792489041675707094021249880239039475449523281953568438230241694538082819749557027 +/- 6.32e-85]
         math53:  0.984792489041676
         sflint:  0.9847925
         dflint:  0.984792489041676
         eflint:  0.9847924890416757071
         qflint:  0.984792489041675707094021249880239
         oflint:  0.9847924890416757070940212498802390394754495232819535684382302416945381
         mflint:  0.984792489041675707094021249880239039475449523281953568438230241694538082819749557027288946
         aflint: [0.984792489041675707094021249880239039475449523281953568438230241694538082819749557027 +/- 8.40e-85]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.clausen_sin(s, z)))
            fpm:  (2.94319983545188, -0.393921066278159)
            mpm:  (2.9431998354518824686313778666007361552782801239068, -0.39392106627815930988131758810008099763433080106612)
        cmath53:  (2.94319983545188, -0.39392106627816)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.clausen_sin(s, z))))
            fpm:  2.94319983545188
            mpm:  2.94319983545188246863137786660073615527828012390684774746328564938672167653354055839925423
            dpm:  2.94319983545188246863137786660073615527828012390684774746328564938672167653354055839925423
            gpm:  2.9431998354518824686313778666007361552782801239068477474632856493867216765335405583992542298
            apm: [2.943199835451882468631377866600736155278280123906847747463285649386721676533540558399 +/- 5.72e-85]
        cmath53:  2.94319983545188
        sflintc:  2.9432
        dflintc:  2.94319983545188
        eflintc:  2.9431998354518824686
        qflintc:  2.94319983545188246863137786660074
        oflintc:  2.9431998354518824686313778666007361552782801239068477474632856493867217
        mflintc:  2.94319983545188246863137786660073615527828012390684774746328564938672167653354055839925423
        aflintc: [2.94319983545188246863137786660073615527828012390684774746328564938672167653354055840 +/- 1.73e-84]



    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.clausen_sin(s, z))))
            fpm:  -0.393921066278159
            mpm:  -0.393921066278159309881317588100080997634330801066109478167767628696515397919930812002386474
            dpm:  -0.393921066278159309881317588100080997634330801066109478167767628696515397919930812002386474
            gpm:  -0.39392106627815930988131758810008099763433080106610947816776762869651539791993081200238647401
            apm: [-0.393921066278159309881317588100080997634330801066109478167767628696515397919930812002 +/- 7.44e-85]
        cmath53:  -0.39392106627816
        sflintc:  -0.3939213
        dflintc:  -0.39392106627816
        eflintc:  -0.39392106627815931004
        qflintc:  -0.393921066278159309881317588100082
        oflintc:  -0.3939210662781593098813175881000809976343308010661094781677676286965154
        mflintc:  -0.393921066278159309881317588100080997634330801066109478167767628696515397919930812002385891
        aflintc: [-0.39392106627815930988131758810008099763433080106610947816776762869651539791993081200 +/- 3.33e-84]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D04a_ClausenSinReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D04b_ClausenSinCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D04_ClausenSin.cs>`__. 










|newpage|

.. _rst_mpm_clcos: 

Generalized Clausen cosine function
-------------------------------------------------------------------------------

.. method:: ctx.clausen_cos(s, z)


    Returns the Clausen cosine function. See also  Wikipedia :cite:p:`WikipediaFun1017`, MathWorld :cite:p:`WolframFun1017`, Mpmath :cite:p:`MpmathFun1018`. 

    Computes the Clausen cosine function, defined formally by the series

    .. math ::  \mathrm{\widetilde{Cl}}_s(z) = \sum_{k=1}^{\infty} \frac{\cos(kz)}{k^s}.

    This function is complementary to the Clausen sine function :ref:`clsin() <rst_mpm_clsin>`. In terms of the polylogarithm,

    .. math ::

        \mathrm{\widetilde{Cl}}_s(z) =
            \frac{1}{2}\left(\mathrm{Li}_s\left(e^{iz}\right) +
            \mathrm{Li}_s\left(e^{-iz}\right)\right)

        = \mathrm{Re}\left[\mathrm{Li}_s(e^{iz})\right] \quad (s, z \in \mathbb{R}).



    |08a_TestClausenCos_re| `\quad` |08b_TestClausenCos_im| `\quad` |08c_TestClausenCos_abs|

    .. |08a_TestClausenCos_re| image:: ../_static/ExplicitSurfaces/CplxLerch/08a_TestClausenCos_re.3D.xml.jpg
       :width: 30 %

    .. |08b_TestClausenCos_im| image:: ../_static/ExplicitSurfaces/CplxLerch/08b_TestClausenCos_im.3D.xml.jpg
       :width: 30 %

    .. |08c_TestClausenCos_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/08c_TestClausenCos_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.







    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.clausen_cos(s, z)))
            fpm:  0.263015360836684
            mpm:  0.263015360836683999575663792621316298941092111811794747998617149962662412816883329886667947
            dpm:  0.263015360836683999575663792621316298941092111811794747998617149962662412816883329886667947
            gpm:  0.26301536083668399957566379262131629894109211181179474799861714996266241281688332988666794702
            apm: [0.263015360836683999575663792621316298941092111811794747998617149962662412816883329887 +/- 9.15e-85]
         math53:  0.263015360836684
         sflint:  0.2630153
         dflint:  0.263015360836684
         eflint:  0.2630153608366839995
         qflint:  0.263015360836683999575663792621316
         oflint:  0.2630153608366839995756637926213162989410921118117947479986171499626624
         mflint:  0.26301536083668399957566379262131629894109211181179474799861714996266241281688332988666804
         aflint: [0.26301536083668399957566379262131629894109211181179474799861714996266241281688332989 +/- 4.49e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.clausen_cos(s, z)))
            fpm:  (-0.344486427690057, -2.81634388274335)
            mpm:  (-0.34448642769005725778776413504912418010560633226575, -2.8163438827433454496150966851781611110811241418611)
        cmath53:  (-0.344486427690058, -2.81634388274334)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.clausen_cos(s, z))))
            fpm:  -0.344486427690057
            mpm:  -0.344486427690057257787764135049124180105606332265745854129961424362331225453989888515278536
            dpm:  -0.344486427690057257787764135049124180105606332265745854129961424362331225453989888515278536
            gpm:  -0.34448642769005725778776413504912418010560633226574585412996142436233122545398988851527853602
            apm: [-0.344486427690057257787764135049124180105606332265745854129961424362331225453989888515 +/- 6.36e-85]
        cmath53:  -0.344486427690058
        sflintc:  -0.3444866
        dflintc:  -0.344486427690058
        eflintc:  -0.34448642769005725797
        qflintc:  -0.344486427690057257787764135049125
        oflintc:  -0.3444864276900572577877641350491241801056063322657458541299614243623313
        mflintc:  -0.344486427690057257787764135049124180105606332265745854129961424362331225453989888515277956
        aflintc: [-0.34448642769005725778776413504912418010560633226574585412996142436233122545398988852 +/- 5.67e-84]



    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.clausen_cos(s, z))))
            fpm:  -2.81634388274335
            mpm:  -2.81634388274334544961509668517816111108112414186109470760443407223622674573228589139384074
            dpm:  -2.81634388274334544961509668517816111108112414186109470760443407223622674573228589139384074
            gpm:  -2.8163438827433454496150966851781611110811241418610947076044340722362267457322858913938407399
            apm: [-2.816343882743345449615096685178161111081124141861094707604434072236226745732285891394 +/- 4.77e-85]
        cmath53:  -2.81634388274334
        sflintc:  -2.816344
        dflintc:  -2.81634388274334
        eflintc:  -2.8163438827433454495
        qflintc:  -2.81634388274334544961509668517816
        oflintc:  -2.8163438827433454496150966851781611110811241418610947076044340722362267
        mflintc:  -2.81634388274334544961509668517816111108112414186109470760443407223622674573228589139384075
        aflintc: [-2.81634388274334544961509668517816111108112414186109470760443407223622674573228589139 +/- 4.83e-84]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D05a_ClausenCosReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D05b_ClausenCosCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D05_ClausenCos.cs>`__. 








|newpage|


Classical Clausen function, `\mathrm{Cl}_2(x)`
-------------------------------------------------------------------------------

.. method:: ctx.clausen2(x)

    Returns the Clausen function `\displaystyle \mathrm{Cl}_2(x) = \Im \displaystyle \mathrm{Li}_2(e^{ix}) =  \int_0^x \log|2\sin(t/2)| \, \mathrm{d}t`.

    See also: Wikipedia :cite:p:`WikipediaFun1017`, MathWorld :cite:p:`WolframFun1017`, :cite:t:`Ehrhardt2018` (3.6.15), Mpmath :cite:p:`MpmathFun1018`. 





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.clausen2(z)))
            fpm:  1.00733027926371
            mpm:  1.00733027926371335731903919114910196644495848163260043631927853333772301585636178945990179
            dpm:  1.00733027926371335731903919114910196644495848163260043631927853333772301585636178945990179
            gpm:  1.0073302792637133573190391911491019664449584816326004363192785333377230158563617894599017901
            apm: [1.00733027926371335731903919114910196644495848163260043631927853333772301585636178945990179 +/- 7.67e-90]
         math53:  1.00733027926371
         sflint:  1.00733
         dflint:  1.00733027926371
         eflint:  1.0073302792637133573
         qflint:  1.0073302792637133573190391911491
         oflint:  1.007330279263713357319039191149101966444958481632600436319278533337723
         mflint:  1.00733027926371335731903919114910196644495848163260043631927853333772301585636178945990179
         aflint: [1.0073302792637133573190391911491019664449584816326004363192785333377230158563617894599018 +/- 1.96e-89]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.clausen2(z)))
            fpm:  (2.08677665798307, -0.911259782750703)
            mpm:  (2.0867766579830742983728938589197577049903840682259, -0.91125978275070287331460388989466652560123973103466)
        cmath53:  (2.08677665798307, -0.911259782750703)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.clausen2(z))))
            fpm:  2.08677665798307
            mpm:  2.08677665798307429837289385891975770499038406822595433856744499539090115409926923531576142
            dpm:  2.08677665798307429837289385891975770499038406822595433856744499539090115409926923531576142
            gpm:  2.08677665798307429837289385891975770499038406822595433856744499539090115409926923531576142
            apm: [2.08677665798307429837289385891975770499038406822595433856744499539090115409926923531576142 +/- 7.55e-90]
        cmath53:  2.08677665798307
        sflintc:  2.086776
        dflintc:  2.08677665798307
        eflintc:  2.0867766579830742983
        qflintc:  2.08677665798307429837289385891976
        oflintc:  2.0867766579830742983728938589197577049903840682259543385674449953909011
        mflintc:  2.08677665798307429837289385891975770499038406822595433856744499539090115409926923531576141
        aflintc: [2.0867766579830742983728938589197577049903840682259543385674449953909011540992692353157614 +/- 2.39e-89]



    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.clausen2(z))))
            fpm:  -0.911259782750703
            mpm:  -0.911259782750702873314603889894666525601239731034656698757671411098684425881374794293937069
            dpm:  -0.911259782750702873314603889894666525601239731034656698757671411098684425881374794293937069
            gpm:  -0.91125978275070287331460388989466652560123973103465669875767141109868442588137479429393706905
            apm: [-0.91125978275070287331460388989466652560123973103465669875767141109868442588137479429393707 +/- 3.21e-90]
        cmath53:  -0.911259782750703
        sflintc:  -0.9112599
        dflintc:  -0.911259782750703
        eflintc:  -0.9112597827507028734
        qflintc:  -0.911259782750702873314603889894667
        oflintc:  -0.91125978275070287331460388989466652560123973103465669875767141109868444
        mflintc:  -0.911259782750702873314603889894666525601239731034656698757671411098684425881374794293937069
        aflintc: [-0.91125978275070287331460388989466652560123973103465669875767141109868442588137479429393707 +/- 8.42e-90]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D06a_Clausen2Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D06b_Clausen2Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D06_Clausen2.cs>`__. 














|newpage|

Bose-Einstein integrals, `G_s(x)`
-------------------------------------------------------------------------------

.. method:: ctx.bose_einstein(s, x)

    Returns the Bose-Einstein integral of real order `s`, `\displaystyle G_s(x) = \frac{1}{\Gamma(s+1)} \int_0^{\infty} \frac{t^s}{e^{t-x}-1} = \text{Li}_{s+1}(e^x) \,`. If `x>0` the real part of `G_s(x)` is returned.

    See also: MathWorld :cite:p:`WolframFun173d`, :cite:t:`Ehrhardt2018` (3.6.7), NIST :cite:p:`DLMFun173d`.



    .. math :: G_{s}(x)=\frac{1}{\Gamma\left(s+1\right)}\int_{0}^{\infty}\frac{t^{s}}{e^{t-x}-1}\mathrm{d}t,






    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.bose_einstein(s, z)))
            fpm:  0.00609907251359716
            mpm:  0.00609907251359715778948345143328488952391085192157053328748187147053954984101828423855788772
            dpm:  0.00609907251359715778948345143328488952391085192157053328748187147053954984101828423855788772
            gpm:  0.0060990725135971577894834514332848895239108519215705332874818714705395498410182842385578877202
            apm: [0.0060990725135971577894834514332848895239108519215705332874818714705395498410182842385578877 +/- 7.27e-92]
         math53:  0.00609907251359716
         sflint:  0.006099073
         dflint:  0.00609907251359716
         eflint:  0.0060990725135971577901
         qflint:  0.00609907251359715778948345143328489
         oflint:  0.0060990725135971577894834514332848895239108519215705332874818714705395499
         mflint:  0.00609907251359715778948345143328488952391085192157053328748187147053954984101828423855788761
         aflint: [0.006099072513597157789483451433284889523910851921570533287481871470539549841018284238557888 +/- 6.25e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.bose_einstein(s, z)))
            fpm:  (-0.00253865761980183, 0.00554199702575756)
            mpm:  (-0.0025386576198018260938786643669900371159757807691764, 0.0055419970257575581780296280208652254346013213180112)
        cmath53:  (-0.00253865761980192, 0.00554199702575756)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.bose_einstein(s, z))))
            fpm:  -0.00253865761980183
            mpm:  -0.00253865761980182609387866436699003711597578076917638206676388764543641399960446539535433417
            dpm:  -0.00253865761980182609387866436699003711597578076917638206676388764543641399960446539535433417
            gpm:  -0.0025386576198018260938786643669900371159757807691763820667638876454364139996044653953543341701
            apm: [-0.0025386576198018260938786643669900371159757807691763820667638876454364139996044653953543342 +/- 5.38e-92]
        cmath53:  -0.00253865761980192
        sflintc:  -0.002538658
        dflintc:  -0.00253865761980183
        eflintc:  -0.002538657619801826094
        qflintc:  -0.00253865761980182609387866436699004
        oflintc:  -0.002538657619801826093878664366990037115975780769176382066763887645436414
        mflintc:  -0.00253865761980182609387866436699003711597578076917638206676388764543641399960446539535433414
        aflintc: [-0.002538657619801826093878664366990037115975780769176382066763887645436413999604465395354334 +/- 2.02e-91]



    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.bose_einstein(s, z))))
            fpm:  0.00554199702575756
            mpm:  0.00554199702575755817802962802086522543460132131801121626335311798142421985260125824932258359
            dpm:  0.00554199702575755817802962802086522543460132131801121626335311798142421985260125824932258359
            gpm:  0.0055419970257575581780296280208652254346013213180112162633531179814242198526012582493225835897
            apm: [0.0055419970257575581780296280208652254346013213180112162633531179814242198526012582493225836 +/- 5.60e-92]
        cmath53:  0.00554199702575756
        sflintc:  0.005541997
        dflintc:  0.00554199702575756
        eflintc:  0.0055419970257575581785
        qflintc:  0.00554199702575755817802962802086523
        oflintc:  0.0055419970257575581780296280208652254346013213180112162633531179814242199
        mflintc:  0.00554199702575755817802962802086522543460132131801121626335311798142421985260125824932258354
        aflintc: [0.005541997025757558178029628020865225434601321318011216263353117981424219852601258249322584 +/- 5.87e-91]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D07a_BoseEinsteinReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D07b_BoseEinsteinCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D07_BoseEinstein.cs>`__. 












|newpage|

Fermi-Dirac integrals, `F_s(x)`
-------------------------------------------------------------------------------

.. method:: ctx.fermi_dirac(s, x)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the Fermi-Dirac integral of order `s`, `\displaystyle F_s(x) = \frac{1}{\Gamma(s+1)} \int_0^{\infty} \frac{t^s}{e^{t-x}+1} = -\text{Li}_{s+1}(-e^x) \,`.

    See also:  Wikipedia :cite:p:`WikipediaFun173c`, MathWorld :cite:p:`WolframFun173c`, :cite:t:`Ehrhardt2018` (3.6.8.1).







    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.fermi_dirac(s, z)))
            fpm:  0.00609442621296756
            mpm:  0.00609442621296755808001300356598951669876164680231260209001221542612655257184778508751074592
            dpm:  0.00609442621296755808001300356598951669876164680231260209001221542612655257184778508751074592
            gpm:  0.0060944262129675580800130035659895166987616468023126020900122154261265525718477850875107459203
            apm: [0.0060944262129675580800130035659895166987616468023126020900122154261265525718477850875107459 +/- 4.24e-92]
         math53:  0.00609442621296756
         sflint:  0.006094427
         dflint:  0.00609442621296756
         eflint:  0.0060944262129675580807
         qflint:  0.00609442621296755808001300356598952
         oflint:  0.0060944262129675580800130035659895166987616468023126020900122154261265527
         mflint:  0.00609442621296755808001300356598951669876164680231260209001221542612655257184778508751074585
         aflint: [0.006094426212967558080013003565989516698761646802312602090012215426126552571847785087510746 +/- 2.73e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.fermi_dirac(s, z)))
            fpm:  (-0.0025356206005197, 0.00554551333881991)
            mpm:  (-0.002535620600519696565611618161725294710866277372125, 0.0055455133388199054701762911801650382731300046098141)
        cmath53:  (-0.00253562060051969, 0.00554551333881991)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.fermi_dirac(s, z))))
            fpm:  -0.0025356206005197
            mpm:  -0.00253562060051969656561161816172529471086627737212499545049057680080172160415910209703947957
            dpm:  -0.00253562060051969656561161816172529471086627737212499545049057680080172160415910209703947957
            gpm:  -0.0025356206005196965656116181617252947108662773721249954504905768008017216041591020970394795698
            apm: [-0.0025356206005196965656116181617252947108662773721249954504905768008017216041591020970394796 +/- 7.42e-92]
        cmath53:  -0.00253562060051969
        sflintc:  -0.002535621
        dflintc:  -0.0025356206005197
        eflintc:  -0.0025356206005196965658
        qflintc:  -0.0025356206005196965656116181617253
        oflintc:  -0.0025356206005196965656116181617252947108662773721249954504905768008017216
        mflintc:  -0.00253562060051969656561161816172529471086627737212499545049057680080172160415910209703947951
        aflintc: [-0.002535620600519696565611618161725294710866277372124995450490576800801721604159102097039480 +/- 5.92e-91]



    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.fermi_dirac(s, z))))
            fpm:  0.00554551333881991
            mpm:  0.00554551333881990547017629118016503827313000460981409278564115553879581250654180291061989778
            dpm:  0.00554551333881990547017629118016503827313000460981409278564115553879581250654180291061989778
            gpm:  0.0055455133388199054701762911801650382731300046098140927856411555387958125065418029106198977802
            apm: [0.005545513338819905470176291180165038273130004609814092785641155538795812506541802910619898 +/- 3.03e-91]
        cmath53:  0.00554551333881991
        sflintc:  0.005545514
        dflintc:  0.00554551333881991
        eflintc:  0.0055455133388199054707
        qflintc:  0.00554551333881990547017629118016504
        oflintc:  0.0055455133388199054701762911801650382731300046098140927856411555387958126
        mflintc:  0.00554551333881990547017629118016503827313000460981409278564115553879581250654180291061989766
        aflintc: [0.005545513338819905470176291180165038273130004609814092785641155538795812506541802910619898 +/- 5.62e-91]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D08a_FermiDiracReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D08b_FermiDiracCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D08_FermiDirac.cs>`__. 










|newpage|

.. _rst_mpm_legendre_chi: 

Legendre's Chi function, `\chi_s(x)`
-------------------------------------------------------------------------------

.. method:: ctx.legendre_chi(s, x)

    Returns Legendre's Chi function, defined as `\displaystyle \chi_s(x) = \sum_{n=0}^{\infty} \frac{x^{2n+1}}{(2n+1)^s} = \tfrac{1}{2} \left( \text{Li}_s(x) - \text{Li}_s(-x) \right) \,`, for `s\ge 0, |x|\le 1`.

    See also:  Wikipedia :cite:p:`WikipediaFun173b`, MathWorld :cite:p:`WolframFun173b`, :cite:t:`Ehrhardt2018` (3.6.9).





    |09a_TestLegendreChi_re| `\quad` |09b_TestLegendreChi_im| `\quad` |09c_TestLegendreChi_abs|

    .. |09a_TestLegendreChi_re| image:: ../_static/ExplicitSurfaces/CplxLerch/09a_TestLegendreChi_re.3D.xml.jpg
       :width: 30 %

    .. |09b_TestLegendreChi_im| image:: ../_static/ExplicitSurfaces/CplxLerch/09b_TestLegendreChi_im.3D.xml.jpg
       :width: 30 %

    .. |09c_TestLegendreChi_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/09c_TestLegendreChi_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.legendre_chi(s, z)))
            fpm:  -4.21634989008759
            mpm:  -4.21634989008758703451404242625218848848010890845072412213724281952803680501340307131859895
            dpm:  -4.21634989008758703451404242625218848848010890845072412213724281952803680501340307131859895
            gpm:  -4.2163498900875870345140424262521884884801089084507241221372428195280368050134030713185989498
            apm: [-4.216349890087587034514042426252188488480108908450724122137242819528036805013403071319 +/- 5.29e-85]
         math53:  -4.21634989008759
         sflint:  -4.21635
         dflint:  -4.21634989008759
         eflint:  -4.2163498900875870344
         qflint:  -4.21634989008758703451404242625219
         oflint:  -4.2163498900875870345140424262521884884801089084507241221372428195280368
         mflint:  -4.21634989008758703451404242625218848848010890845072412213724281952803680501340307131859852
         aflint: [-4.216349890087587034514042426252188488480108908450724122137242819528036805013403071319 +/- 8.69e-85]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.legendre_chi(s, z)))
            fpm:  (-3.36807891622459, 3.01743198627304)
            mpm:  (-3.3680789162245861913742738728347912282005225744247, 3.0174319862730446772050684527666868515847537227401)
        cmath53:  (-3.36807891622459, 3.01743198627304)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.legendre_chi(s, z))))
            fpm:  -3.36807891622459
            mpm:  -3.3680789162245861913742738728347912282005225744247459691380979095137669575270215034729097
            dpm:  -3.3680789162245861913742738728347912282005225744247459691380979095137669575270215034729097
            gpm:  -3.3680789162245861913742738728347912282005225744247459691380979095137669575270215034729096998
            apm: [-3.368078916224586191374273872834791228200522574424745969138097909513766957527021503473 +/- 4.38e-85]
        cmath53:  -3.36807891622459
        sflintc:  -3.368079
        dflintc:  -3.36807891622459
        eflintc:  -3.3680789162245861914
        qflintc:  -3.36807891622458619137427387283479
        oflintc:  -3.368078916224586191374273872834791228200522574424745969138097909513767
        mflintc:  -3.36807891622458619137427387283479122820052257442474596913809790951376695752702150347290952
        aflintc: [-3.36807891622458619137427387283479122820052257442474596913809790951376695752702150347 +/- 4.02e-84]



    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.legendre_chi(s, z))))
            fpm:  3.01743198627304
            mpm:  3.01743198627304467720506845276668685158475372274010683327212795524197193109435376369115498
            dpm:  3.01743198627304467720506845276668685158475372274010683327212795524197193109435376369115498
            gpm:  3.0174319862730446772050684527666868515847537227401068332721279552419719310943537636911549799
            apm: [3.017431986273044677205068452766686851584753722740106833272127955241971931094353763691 +/- 4.64e-85]
        cmath53:  3.01743198627304
        sflintc:  3.017432
        dflintc:  3.01743198627304
        eflintc:  3.0174319862730446772
        qflintc:  3.01743198627304467720506845276669
        oflintc:  3.0174319862730446772050684527666868515847537227401068332721279552419719
        mflintc:  3.01743198627304467720506845276668685158475372274010683327212795524197193109435376369115502
        aflintc: [3.01743198627304467720506845276668685158475372274010683327212795524197193109435376369 +/- 2.20e-84]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D09a_LegendreChiReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D09b_LegendreChiCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D09_LegendreChi.cs>`__. 










|newpage|

.. _rst_mpm_ti: 

Generalized inverse tangent integral
-------------------------------------------------------------------------------

.. method:: ctx.inverse_tan_integral(s, z)

    Returns the generalized inverse tangent integral `Ti_s(z)`, which can be expressed in terms of polylogarithms:
    
    .. math ::  \mathrm {Ti} _{s}(z)={1 \over 2i}\left[\mathrm {Li} _{s}(iz)-\mathrm {Li} _{s}(-iz)\right].

    The relation in particular implies:

    .. math ::  \mathrm {Ti} _{0}(z)={z \over 1+z^{2}},\quad \mathrm {Ti} _{1}(z)=\arctan z,\quad \mathrm {Ti} _{2}(z)=\int _{0}^{z}{\arctan t \over t}\mathrm{d}t,\quad \ldots ~\quad \mathrm {Ti} _{n+1}(z)=\int _{0}^{z}{\frac {\mathrm {Ti} _{n}(t)}{t}}\mathrm{d}t,

    which explains the function name.

    See also: Wikipedia :cite:p:`WikipediaFun173a`, MathWorld :cite:p:`WolframFun173a`, :cite:t:`Ehrhardt2018` (3.6.17).



    |10a_TestTangentInt_re| `\quad` |10b_TestTangentInt_im| `\quad` |10c_TestTangentInt_abs|

    .. |10a_TestTangentInt_re| image:: ../_static/ExplicitSurfaces/CplxLerch/10a_TestTangentInt_re.3D.xml.jpg
       :width: 30 %

    .. |10b_TestTangentInt_im| image:: ../_static/ExplicitSurfaces/CplxLerch/10b_TestTangentInt_im.3D.xml.jpg
       :width: 30 %

    .. |10c_TestTangentInt_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/10c_TestTangentInt_abs.3D.xml.jpg
       :width: 30 %



    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.inverse_tan_integral(s, z)))
            fpm:  -3.82687109377201
            mpm:  -3.82687109377200959456767235528550630273683154471206495252003604997526349631365827951254078
            dpm:  -3.82687109377200959456767235528550630273683154471206495252003604997526349631365827951254078
            gpm:  -3.82687109377200959456767235528550630273683154471206495252003604997526349631365827951254078
            apm: [-3.826871093772009594567672355285506302736831544712064952520036049975263496313658279513 +/- 7.14e-85]
         math53:  -3.82687109377201
         sflint:  -3.826871
         dflint:  -3.82687109377201
         eflint:  -3.8268710937720095944
         qflint:  -3.82687109377200959456767235528551
         oflint:  -3.8268710937720095945676723552855063027368315447120649525200360499752635
         mflint:  -3.82687109377200959456767235528550630273683154471206495252003604997526349631365827951254069
         aflint: [-3.82687109377200959456767235528550630273683154471206495252003604997526349631365827951 +/- 3.41e-84]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.inverse_tan_integral(s, z)))
            fpm:  (-3.93019424226452, 1.0648751979531)
            mpm:  (-3.9301942422645179790729604006463680121426642176632, 1.0648751979531028577248417201938102837739584605486)
        cmath53:  (-3.93019424226452, 1.0648751979531)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.inverse_tan_integral(s, z))))
            fpm:  -3.93019424226452
            mpm:  -3.9301942422645179790729604006463680121426642176631923401383833025305873692888129527788785
            dpm:  -3.9301942422645179790729604006463680121426642176631923401383833025305873692888129527788785
            gpm:  -3.9301942422645179790729604006463680121426642176631923401383833025305873692888129527788785
            apm: [-3.930194242264517979072960400646368012142664217663192340138383302530587369288812952779 +/- 4.44e-85]
        cmath53:  -3.93019424226452
        sflintc:  -3.930194
        dflintc:  -3.93019424226452
        eflintc:  -3.930194242264517979
        qflintc:  -3.93019424226451797907296040064637
        oflintc:  -3.9301942422645179790729604006463680121426642176631923401383833025305874
        mflintc:  -3.93019424226451797907296040064636801214266421766319234013838330253058736928881295277887845
        aflintc: [-3.93019424226451797907296040064636801214266421766319234013838330253058736928881295278 +/- 2.22e-84]



    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> s = 3; z = -5.1+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.inverse_tan_integral(s, z))))
            fpm:  1.0648751979531
            mpm:  1.06487519795310285772484172019381028377395846054864783844891884891880596573417832135842314
            dpm:  1.06487519795310285772484172019381028377395846054864783844891884891880596573417832135842314
            gpm:  1.06487519795310285772484172019381028377395846054864783844891884891880596573417832135842314
            apm: [1.064875197953102857724841720193810283773958460548647838448918848918805965734178321358 +/- 8.19e-85]
        cmath53:  1.0648751979531
        sflintc:  1.064875
        dflintc:  1.0648751979531
        eflintc:  1.0648751979531028577
        qflintc:  1.06487519795310285772484172019381
        oflintc:  1.064875197953102857724841720193810283773958460548647838448918848918806
        mflintc:  1.06487519795310285772484172019381028377395846054864783844891884891880596573417832135842266
        aflintc: [1.06487519795310285772484172019381028377395846054864783844891884891880596573417832136 +/- 2.88e-84]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D10a_InverseTanIntegralReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C03_Polylogarithm/D10b_InverseTanIntegralCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C03_Polylogarithm/D10_InverseTanIntegral.cs>`__. 





