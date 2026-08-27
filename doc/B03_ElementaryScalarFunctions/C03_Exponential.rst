

.. |newpage| raw:: latex

   \newpage




.. |br| raw:: html

   <br />






|newpage|

Exponential and related functions
===============================================================================




Exponential function `\exp(x) = e^x`
-------------------------------------------------------------------------------

.. method:: ctx.exp(z)

    where ``ctx`` is ``ctx_pm`` (see :ref:`Python contexts <rst_py_groups_of_contexts>` for details), ``ctx53``, ``ctxcpp``, ``ctxflint`` (see :ref:`.NET contexts <rst_net_groups_of_contexts>` for details).

    Returns `\exp(x)`, the exponential function of `x`. See also Wikipedia :cite:p:`WikipediaFun10`, MathWorld :cite:p:`WolframFun10`, NIST :cite:p:`DLMFun10`, :cite:t:`Ehrhardt2018` (4.2.34), Flint :cite:p:`FlintFun15`, Flint :cite:p:`FlintFun16`, Mpmath :cite:p:`MpmathFun10`. 


    For complex numbers, the exponential function satisfies `\exp(x + iy) = e^x (\cos y + i \sin y)`.



    |04a_TestExp_re| `\quad` |04b_TestExp_im| `\quad` |04c_TestExp_abs|

    .. |04a_TestExp_re| image:: ../_static/ExplicitSurfaces/CplxRoots/04a_TestExp_re.3D.xml.jpg
       :width: 30 %

    .. |04b_TestExp_im| image:: ../_static/ExplicitSurfaces/CplxRoots/04b_TestExp_im.3D.xml.jpg
       :width: 30 %

    .. |04c_TestExp_abs| image:: ../_static/ExplicitSurfaces/CplxRoots/04c_TestExp_abs.3D.xml.jpg
       :width: 30 %



    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in ctxlistreal: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp(x)))
            fpm:  0.00609674656551564
            mpm:  0.00609674656551563610713456478542490178906004208066809730839371569595697636773934832576013656
            dpm:  0.00609674656551563610713456478542490178906004208066809730839371569595697636773934832576013656
            ipm: [0.0060967465655156361071345647854249017890600420806680973083937156959569763677393483257601365613434,
                  0.0060967465655156361071345647854249017890600420806680973083937156959569763677393483257601365690139]
            gpm:  0.0060967465655156361071345647854249017890600420806680973083937156959569763677393483257601365623
            apm: [0.00609674656551563610713456478542490178906004208066809730839371569595697636773934832576013657 +/- 8.90e-93]
          dreal:  0.00609674656551564
          sreal:  0.006096747
          dreal:  0.00609674656551564
          ereal:  0.0060967465655156361078
          qreal:  0.0060967465655156361071345647854249
          oreal:  0.0060967465655156361071345647854249017890600420806680973083937156959569763
          mreal:  0.00609674656551563610713456478542490178906004208066809730839371569595697636773934832576013657
         sflint:  0.006096747
         dflint:  0.00609674656551564
         eflint:  0.0060967465655156361078
         qflint:  0.0060967465655156361071345647854249
         oflint:  0.0060967465655156361071345647854249017890600420806680973083937156959569764
         mflint:  0.00609674656551563610713456478542490178906004208066809730839371569595697636773934832576013657
         aflint: [0.0060967465655156361071345647854249017890600420806680973083937156959569763677393483257601366 +/- 4.16e-92]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp(x)))
            fpm:  (-0.00253714179646899, 0.00554375596403168)
            mpm:  (-0.0025371417964689871432868572987332349386956711932343, 0.0055437559640316803155849317223325676631201581872807)
        cmath53:  (-0.00253714179646899, 0.00554375596403168)
          qcplx:  (-0.00253714179646898714328685729873324, 0.00554375596403168031558493172233257)




    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D01a_ExpReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D01b_ExpCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B03_ElementaryScalarFunctions/C03_Exponential/D01_Exp.cs>`__. 








Auxiliary function `\mathrm{expj}(x) = e^{ix}` 
-------------------------------------------------------------------------------

.. method:: ctx.expj(z)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp``, ``ctxflint``.

    Returns `e^{iz} = \cos(z) + i \sin(z)`. See also Wikipedia :cite:p:`WikipediaFun1035`, MathWorld :cite:p:`WolframFun1035`, Mpmath :cite:p:`MpmathFun1035`.




    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 50
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.cplxctx.fmt(ctx.expj(x)))
            fpm:  (0.37797774271298, 0.925814682327732)
            mpm:  (0.37797774271298056332057555292898167089864157613427, 0.92581468232773229694614624754486331250940301635561)
            dpm:  (0.37797774271298056332057555292898167089864157613428, 0.9258146823277322969461462475448633125094030163556)
            ipm: ([0.3779777427129805633205755529289816708986415761342730157, 0.3779777427129805633205755529289816708986415761342837068], 
                  [0.9258146823277322969461462475448633125094030163556011089, 0.9258146823277322969461462475448633125094030163556064544])
            gpm:  (0.3779777427129805633205755529289816708986415761342737, 0.9258146823277322969461462475448633125094030163556051)
            apm: ([0.3779777427129805633205755529289816708986415761343 +/- 3.78e-50], [0.9258146823277322969461462475448633125094030163556 +/- 1.06e-50])
          dreal:  (0.37797774271298, 0.925814682327732)
          sreal:  (0.3779777, 0.9258147)
          dreal:  (0.37797774271298, 0.925814682327732)
          ereal:  (0.37797774271298056325, 0.92581468232773229699)
          qreal:  (0.377977742712980563320575552928981, 0.925814682327732296946146247544863)
          oreal:  (0.37797774271298056332057555292898167089864157613427757054176691301095088, 0.92581468232773229694614624754486331250940301635560394879705455193228186)
          mreal:  (0.37797774271298056332057555292898167089864157613429, 0.92581468232773229694614624754486331250940301635559)
         sflint:  (0.3779777, 0.9258147)
         dflint:  (0.37797774271298, 0.925814682327732)
         eflint:  (0.37797774271298056325, 0.92581468232773229699)
         qflint:  (0.377977742712980563320575552928981, 0.925814682327732296946146247544863)
         oflint:  (0.37797774271298056332057555292898167089864157613427757054176691301095088, 0.92581468232773229694614624754486331250940301635560394879705455193228185)
         mflint:  (0.37797774271298056332057555292898167089864157613429, 0.92581468232773229694614624754486331250940301635559)
         aflint: ([0.3779777427129805633205755529289816708986415761343 +/- 2.92e-50], [0.9258146823277322969461462475448633125094030163556 +/- 2.44e-50])



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.expj(x)))
            fpm:  (0.0511537248671967, 0.125295392257438)
            mpm:  (0.0511537248671967434898253949927467610442454662229, 0.1252953922574382533359994793180146319527429028572)
        cmath53:  (0.0511537248671967, 0.125295392257438)
          qcplx:  (0.0511537248671967434898253949927467, 0.125295392257438253335999479318014)



    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D02a_ExpjReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D02b_ExpjCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B03_ElementaryScalarFunctions/C03_Exponential/D03_Expjpi.cs>`__. 









Auxiliary function `\mathrm{expjpi}(x) = e^{i \pi x} = (-1)^x`
---------------------------------------------------------------------------------------

.. method:: ctx.expjpi(z)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns `e^{i \pi z} = \cos(\pi z) + i \sin(\pi z)`. See also Wikipedia :cite:p:`WikipediaFun1035`, MathWorld :cite:p:`WolframFun1035`, Flint :cite:p:`FlintFun16`, Mpmath :cite:p:`MpmathFun1036`. 

    Evaluation is accurate near zeros (see also :ref:`cospi() <rst_xreal_cospi>` and :ref:`sinpi() <rst_xreal_sinpi>`):





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 50
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.cplxctx.fmt(ctx.expjpi(x)))
            fpm:  (-0.951056516295154, 0.309016994374946)
            mpm:  (-0.95105651629515357211643933337938214340569863412575, 0.30901699437494742410229341718281905886015458990287)
            dpm:  (-0.95105651629515357211643933337938214340569863412575, 0.30901699437494742410229341718281905886015458990288)
            ipm: ([-0.951056516295153572116439333379382143405698634125765038, -0.951056516295153572116439333379382143405698634125736974], [0.3090169943749474241022934171828190588601545899028378188, 0.3090169943749474241022934171828190588601545899029200063])
            gpm:  (-0.9510565162951535721164393333793821434056986341257517, 0.3090169943749474241022934171828190588601545899028786)
            apm: ([-0.9510565162951535721164393333793821434056986341258 +/- 5.79e-50], [0.3090169943749474241022934171828190588601545899029 +/- 6.59e-50])
          dreal:  (-0.951056516295154, 0.309016994374946)
          sreal:  (-0.9510566, 0.3090167)
          dreal:  (-0.951056516295154, 0.309016994374946)
          ereal:  (-0.95105651629515357222, 0.30901699437494742386)
          qreal:  (-0.951056516295153572116439333379382, 0.309016994374947424102293417182818)
          oreal:  (-0.95105651629515357211643933337938214340569863412575022244730564443015319, 0.30901699437494742410229341718281905886015458990288143106772431135263019)
          mreal:  (-0.95105651629515357211643933337938214340569863412573, 0.30901699437494742410229341718281905886015458990293)
         sflint:  (-0.9510566, 0.3090167)
         dflint:  (-0.951056516295154, 0.309016994374946)
         eflint:  (-0.95105651629515357222, 0.30901699437494742383)
         qflint:  (-0.951056516295153572116439333379382, 0.309016994374947424102293417182818)
         oflint:  (-0.95105651629515357211643933337938214340569863412575022244730564443015318, 0.30901699437494742410229341718281905886015458990288143106772431135263019)
         mflint:  (-0.95105651629515357211643933337938214340569863412573, 0.30901699437494742410229341718281905886015458990292)
         aflint: ([-0.9510565162951535721164393333793821434056986341257 +/- 6.44e-50], [0.3090169943749474241022934171828190588601545899029 +/- 8.93e-50])



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.expjpi(x)))
            fpm:  (-0.00177604357879891, 0.000577071540119742)
            mpm:  (-0.0017760435787989049642054631852541036755960880447526, 0.00057707154011974403113330884851121775451896357682577)
        cmath53:  (-0.00177604357725158, 0.000577071540703855)
          qcplx:  (-0.00177604357879890496420546318529556, 0.000577071540119744031133308848517094)



    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D03a_ExpjpiReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D03b_ExpjpiCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B03_ElementaryScalarFunctions/C03_Exponential/D03_Expjpi.cs>`__. 








Exponential function with base `10`, `\mathrm{exp10}(x) = 10^z`
-----------------------------------------------------------------------------------------

.. method:: ctx.exp10(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns `\mathrm{exp10}(x) = 10^z = \exp(x \cdot \log(10))`, the  base-10 exponential function of `z`. See also Wikipedia :cite:p:`WikipediaFun12`, MathWorld :cite:p:`WolframFun10`, NIST :cite:p:`DLMFun10`, :cite:t:`Ehrhardt2018` (4.2.36), Mpmath :cite:p:`MpmathFun18`. 




    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>>     for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp10(x))
            fpm:  7.94328234724282E-06
            mpm:  0.00000794328234724281502065918282836387932588960631755484332092323929316955697191487537497095251
            dpm:  0.00000794328234724281502065918282836387932588960631755484332092323929316955697191487537497095252
            ipm: [0.0000079432823472428150206591828283638793258896063175548433209232392931695569719148753749709524789891,
                  0.0000079432823472428150206591828283638793258896063175548433209232392931695569719148753749709525445325]
            gpm:  7.9432823472428150206591828283638793258896063175548433209232392931695569719148753749709525146e-06
            apm: [7.943282347242815020659182828363879325889606317554843320923239293169556971914875374970953e-6 +/- 5.13e-94]
          dreal:  7.94328234724282E-06
          sreal:  7.943281E-06
          dreal:  7.94328234724281E-06
          ereal:  7.9432823472428150204e-06
          qreal:  7.94328234724281502065918282836389e-06
          oreal:  7.9432823472428150206591828283638793258896063175548433209232392931695569e-06
          mreal:  7.94328234724281502065918282836387932588960631755484332092323929316955697191487537497095253E-06
         sflint:  7.943284E-06
         dflint:  7.94328234724282E-06
         eflint:  7.9432823472428150221e-06
         qflint:  7.94328234724281502065918282836388e-06
         oflint:  7.9432823472428150206591828283638793258896063175548433209232392931695572e-06
         mflint:  7.94328234724281502065918282836387932588960631755484332092323929316955697191487537497095253E-06
         aflint: [7.943282347242815020659182828363879325889606317554843320923239293169556971914875374970953e-6 +/- 5.60e-94]


    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp10(x)))
            fpm:  (-8.50038314869339E-07, -7.89766859973711E-06)
            mpm:  (-0.0000008500383148693386092398053603383376816809556042249, -0.0000078976685997371034342479584101601100277547297776704)
        cmath53:  (-8.50038314869336E-07, -7.89766859973711E-06)
          qcplx:  (-8.50038314869338609239805360338339e-07, -7.89766859973710343424795841016012e-06)



    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D04a_Exp10Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D04b_Exp10Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B03_ElementaryScalarFunctions/C03_Exponential/D04_Exp10.cs>`__. 









Exponential function with base `2`, `\mathrm{exp2}(x) = 2^x`
---------------------------------------------------------------------------------------------

.. method:: ctx.exp2(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns `\mathrm{exp2}(x) = 2^x = \exp(x \cdot \log(2))`, the  base-2 exponential function of `x`. See also Wikipedia :cite:p:`WikipediaFun13`, MathWorld :cite:p:`WolframFun10`, NIST :cite:p:`DLMFun10`,  :cite:t:`Ehrhardt2018` (4.2.35).




    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp2(x)))
            fpm:  0.0291572809855252
            mpm:  0.0291572809855252317494169770671856927196009363859841887156405432964186568847051108626158585
            dpm:  0.0291572809855252317494169770671856927196009363859841887156405432964186568847051108626158585
            ipm: [0.0291572809855252317494169770671856927196009363859841887156405432964186568847051108626158585305,
                  0.029157280985525231749416977067185692719600936385984188715640543296418656884705110862615858591864]
            gpm:  0.029157280985525231749416977067185692719600936385984188715640543296418656884705110862615858538
            apm: [0.0291572809855252317494169770671856927196009363859841887156405432964186568847051108626158586 +/- 8.98e-92]
          dreal:  0.0291572809855252
          sreal:  0.02915728
          dreal:  0.0291572809855252
          ereal:  0.029157280985525231751
          qreal:  0.0291572809855252317494169770671857
          oreal:  0.029157280985525231749416977067185692719600936385984188715640543296418657
          mreal:  0.0291572809855252317494169770671856927196009363859841887156405432964186568847051108626158586
         sflint:  0.02915728
         dflint:  0.0291572809855252
         eflint:  0.029157280985525231751
         qflint:  0.0291572809855252317494169770671857
         oflint:  0.029157280985525231749416977067185692719600936385984188715640543296418657
         mflint:  0.0291572809855252317494169770671856927196009363859841887156405432964186568847051108626158586
         aflint: [0.029157280985525231749416977067185692719600936385984188715640543296418656884705110862615859 +/- 5.38e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp2(x)))
            fpm:  (0.00534910656134485, 0.0286624160437366)
            mpm:  (0.0053491065613448526660310040295797895499084770752861, 0.028662416043736589994269252987760995841700161519681)
        cmath53:  (0.00534910656134486, 0.0286624160437366)
          qcplx:  (0.00534910656134485266603100402957979, 0.028662416043736589994269252987761)



    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D05a_Exp2Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D05b_Exp2Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B03_ElementaryScalarFunctions/C03_Exponential/D05_Exp2.cs>`__. 










.. _rst_xreal_expm1: 

Auxiliary function `\mathrm{expm1}(x) = e^x-1`
-------------------------------------------------------------------------------

.. method:: ctx.expm1(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns `\mathrm{expm1}(x) = \exp(x)-1 = e^x-1`, computed accurately also for small `x`. See also Wikipedia :cite:p:`WikipediaFun11`, MathWorld :cite:p:`WolframFun10`, NIST :cite:p:`DLMFun10`,  BoostMath :cite:p:`BoostFun10`,  :cite:t:`Ehrhardt2018` (4.2.37), Flint :cite:p:`FlintFun15`, Flint :cite:p:`FlintFun16`, Mpmath :cite:p:`MpmathFun11`.





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.expm1(x)))
            fpm:  -0.993903253434484
            mpm:  -0.993903253434484363892865435214575098210939957919331902691606284304043023632260651674239863
            dpm:  -0.993903253434484363892865435214575098210939957919331902691606284304043023632260651674239863
            ipm: [-0.99390325343448436389286543521457509821093995791933190269160628430404302363226065167423986352495,
                  -0.99390325343448436389286543521457509821093995791933190269160628430404302363226065167423986340222]
            gpm:  -0.9939032534344843638928654352145750982109399579193319026916062843040430236322606516742398634
            apm: [-0.993903253434484363892865435214575098210939957919331902691606284304043023632260651674239863 +/- 5.31e-91]
          dreal:  -0.993903253434484
          sreal:  -0.9939033
          dreal:  -0.993903253434484
          ereal:  -0.99390325343448436389
          qreal:  -0.993903253434484363892865435214575
          oreal:  -0.99390325343448436389286543521457509821093995791933190269160628430404302
          mreal:  -0.993903253434484363892865435214575098210939957919331902691606284304043023632260651674239864
         sflint:  -0.9939033
         dflint:  -0.993903253434484
         eflint:  -0.99390325343448436389
         qflint:  -0.993903253434484363892865435214575
         oflint:  -0.99390325343448436389286543521457509821093995791933190269160628430404302
         mflint:  -0.993903253434484363892865435214575098210939957919331902691606284304043023632260651674239864
         aflint: [-0.993903253434484363892865435214575098210939957919331902691606284304043023632260651674239863 +/- 6.53e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.expm1(x)))
            fpm:  (-1.00253714179647, 0.00554375596403168)
            mpm:  (-1.0025371417964689871432868572987332349386956711932, 0.0055437559640316803155849317223325676631201581872807)
        cmath53:  (-1.00253714179647, 0.00554375596403168)
          qcplx:  (-1.00253714179646898714328685729873, 0.00554375596403168031558493172233257)



    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D06a_Expm1Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D06b_Expm1Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B03_ElementaryScalarFunctions/C03_Exponential/D06_Expm1.cs>`__. 








Auxiliary function `\mathrm{exp10m1}(x) = 10^x - 1`
-------------------------------------------------------------------------------

.. method:: ctx.exp10m1(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns `10^x - 1 = \mathrm{expm1}(x \cdot \log(10))`. See also  :ref:`expm1() <rst_xreal_expm1>`.





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp10m1(x)))
            fpm:  -0.999992056717653
            mpm:  -0.999992056717652757184979340817171636120674110393682445156679076760706830443028085124625029
            dpm:  -0.999992056717652757184979340817171636120674110393682445156679076760706830443028085124625029
            ipm: [-0.99999205671765275718497934081717163612067411039368244515667907676070683044302808512462502915426,
                  -0.99999205671765275718497934081717163612067411039368244515667907676070683044302808512462502903153]
            gpm:  -0.99999205671765275718497934081717163612067411039368244515667907676070683044302808512462502903
            apm: [-0.999992056717652757184979340817171636120674110393682445156679076760706830443028085124625029 +/- 1.55e-91]
          dreal:  -0.999992056717653
          sreal:  -0.9999921
          dreal:  -0.999992056717653
          ereal:  -0.99999205671765275719
          qreal:  -0.999992056717652757184979340817172
          oreal:  -0.99999205671765275718497934081717163612067411039368244515667907676070683
          mreal:  -0.999992056717652757184979340817171636120674110393682445156679076760706830443028085124625029
         sflint:  -0.9999921
         dflint:  -0.999992056717653
         eflint:  -0.99999205671765275719
         qflint:  -0.999992056717652757184979340817172
         oflint:  -0.99999205671765275718497934081717163612067411039368244515667907676070683
         mflint:  -0.999992056717652757184979340817171636120674110393682445156679076760706830443028085124625029
         aflint: [-0.999992056717652757184979340817171636120674110393682445156679076760706830443028085124625029 +/- 7.06e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp10m1(x)))
            fpm:  (-1.00000085003831, -7.89766859973711E-06)
            mpm:  (-1.0000008500383148693386092398053603383376816809556, -0.0000078976685997371034342479584101601100277547297776704)
        cmath53:  (-1.00000085003831, -7.8976685997371E-06)
          qcplx:  (-1.00000085003831486933860923980536, -7.89766859973710343424795841016012e-06)



    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D07a_Exp10m1Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D07b_Exp10m1Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B03_ElementaryScalarFunctions/C03_Exponential/D07_Exp10m1.cs>`__. 








Auxiliary function `\mathrm{exp2m1}(x) = 2^x - 1`
-------------------------------------------------------------------------------

.. method:: ctx.exp2m1(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns `2^x - 1 = \mathrm{expm1}(x \cdot \log(2))`. See also  :ref:`expm1() <rst_xreal_expm1>`.




    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp2m1(x)))
            fpm:  -0.970842719014475
            mpm:  -0.970842719014474768250583022932814307280399063614015811284359456703581343115294889137384141
            dpm:  -0.970842719014474768250583022932814307280399063614015811284359456703581343115294889137384141
            ipm: [-0.9708427190144747682505830229328143072803990636140158112843594567035813431152948891373841415347,
                  -0.97084271901447476825058302293281430728039906361401581128435945670358134311529488913738414128924]
            gpm:  -0.97084271901447476825058302293281430728039906361401581128435945670358134311529488913738414141
            apm: [-0.970842719014474768250583022932814307280399063614015811284359456703581343115294889137384141 +/- 5.79e-91]
          dreal:  -0.970842719014475
          sreal:  -0.9708427
          dreal:  -0.970842719014475
          ereal:  -0.97084271901447476827
          qreal:  -0.970842719014474768250583022932814
          oreal:  -0.97084271901447476825058302293281430728039906361401581128435945670358134
          mreal:  -0.970842719014474768250583022932814307280399063614015811284359456703581343115294889137384142
         sflint:  -0.9708427
         dflint:  -0.970842719014475
         eflint:  -0.97084271901447476827
         qflint:  -0.970842719014474768250583022932814
         oflint:  -0.97084271901447476825058302293281430728039906361401581128435945670358134
         mflint:  -0.970842719014474768250583022932814307280399063614015811284359456703581343115294889137384142
         aflint: [-0.970842719014474768250583022932814307280399063614015811284359456703581343115294889137384141 +/- 7.68e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp2m1(x)))
            fpm:  (-0.994650893438655, 0.0286624160437366)
            mpm:  (-0.99465089343865514733396899597042021045009152292471, 0.028662416043736589994269252987760995841700161519681)
        cmath53:  (-0.994650893438655, 0.0286624160437366)
          qcplx:  (-0.99465089343865514733396899597042, 0.028662416043736589994269252987761)



    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D08a_Exp2m1Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B03_ElementaryScalarFunctions/C03_Exponential/D08b_Exp2m1Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B03_ElementaryScalarFunctions/C03_Exponential/D08_Exp2m1.cs>`__. 



