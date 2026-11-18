

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />



|newpage|



Exponential integrals, and related functions
===============================================================================





Exponential integral `E_1(x)`
-------------------------------------------------------------------------------

.. method:: ctx.exp_integral_e1(x)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the exponential integral `\displaystyle E_1(x) =  \int_1^\infty \frac{e^{-xt}}{t} \, \mathrm{d}t, = e^{-z} U(1,1,z), \quad x \neq 0`. 


    For real `x<0` the integral can be calculated as `E_1(x) = -\mathrm{Ei}(-x)`. 

    See also   Wikipedia :cite:p:`WikipediaFun175`, MathWorld :cite:p:`WolframFun175`, NIST :cite:p:`DLMFun175`,  BoostMath :cite:p:`BoostFun175`, :cite:t:`Ehrhardt2018` (3.4.5), :cite:t:`Ehrhardt2018` (4.2.27), Flint :cite:p:`FlintFun175`, Flint :cite:p:`FlintFun176`, Mpmath :cite:p:`MpmathFun175`. 




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = 1.1; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp_integral_e1(x)))
        fpm:  0.18599090453604
        mpm:  0.185990904536040155697221974455445575345359795488344525791303914793131874091689492992521337
        dpm:  0.185990904536040155697221974455445575345359795488344525791303914793131874091689492992521337
        gpm:  0.185990904536040155697221974455445575345359795488344525791303914793131874091689492992521337
        apm: [0.18599090453604015569722197445544557534535979548834452579130391479313187409168949299252134 +/- 4.18e-90]
     math53:  0.18599090453604
      sreal:  0.1859909
      dreal:  0.18599090453604
      ereal:  0.18599090453604015572
      qreal:  0.185990904536040155697221974455446
      oreal:  0.18599090453604015569722197445544557534535979548834452579130391479313221
      mreal:  0.185990904536040155697221974455445575345359795488344525791303914793131874091689492992521365
     sflint:  0.1859909
     dflint:  0.18599090453604
     eflint:  0.18599090453604015569
     qflint:  0.185990904536040155697221974455446
     oflint:  0.18599090453604015569722197445544557534535979548834452579130391479313187
     mflint:  0.185990904536040155697221974455445575345359795488344525791303914793131874091689492992521337
     aflint: [0.18599090453604015569722197445544557534535979548834452579130391479313187409168949299252134 +/- 5.54e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp_integral_e1(x)))
        fpm:  (-3.08024551179863, 36.0369635572426)
        mpm:  (-3.0802455117986318114971655015854991261349288576449, 36.036963557242588407506190790127629224469361607029)
    cmath53:  (-3.08024551179877, 36.0369635572427)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.exp_integral_e1(x))))
        fpm:  -3.08024551179863
        mpm:  -3.08024551179863181149716550158549912613492885764490762273477716255367251422149251294267864
        dpm:  -3.08024551179863181149716550158549912613492885764490762273477716255367251422149251294267864
        gpm:  -3.08024551179863181149716550158549912613492885764490762273477716255367251422149251294267864
        apm: [-3.080245511798631811497165501585499126134928857644907622734777162553672514221492512942679 +/- 4.38e-88]
    cmath53:  -3.08024551179877
    sflintc:  -3.080246
    dflintc:  -3.08024551179863
    eflintc:  -3.0802455117986318116
    qflintc:  -3.0802455117986318114971655015855
    oflintc:  -3.0802455117986318114971655015854991261349288576449076227347771625536725
    mflintc:  -3.08024551179863181149716550158549912613492885764490762273477716255367251422149251294267869
    aflintc: [-3.080245511798631811497165501585499126134928857644907622734777162553672514221492512942679 +/- 5.30e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.exp_integral_e1(x))))
        fpm:  36.0369635572426
        mpm:  36.036963557242588407506190790127629224469361607028807644003889536814004205638596090840038
        dpm:  36.036963557242588407506190790127629224469361607028807644003889536814004205638596090840038
        gpm:  36.036963557242588407506190790127629224469361607028807644003889536814004205638596090840037998
        apm: [36.036963557242588407506190790127629224469361607028807644003889536814004205638596090840038 +/- 1.70e-88]
    cmath53:  36.0369635572427
    sflintc:  36.03696
    dflintc:  36.0369635572426
    eflintc:  36.036963557242588405
    qflintc:  36.0369635572425884075061907901276
    oflintc:  36.036963557242588407506190790127629224469361607028807644003889536814004
    mflintc:  36.0369635572425884075061907901276292244693616070288076440038895368140042056385960908400379
    aflintc: [36.036963557242588407506190790127629224469361607028807644003889536814004205638596090840038 +/- 4.12e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D01a_ExpIntegralE1Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D01b_ExpIntegralE1Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D01_ExpIntegralE1.cs>`__. 










|newpage|

Exponential integral `\mathrm{Ei}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.exp_integral_ei(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxboost`` or ``ctxflint``.

    Returns the exponential integral  `\displaystyle  \mathrm{Ei}(x) = -PV \int_{-x}^\infty \frac{e^{-t}}{t} \, \mathrm{d}t= PV \int_{-\infty}^x \frac{e^{t}}{t} \, \mathrm{d}t`. 
    
    For real `x<0` we have `\mathrm{Ei}(x) = -E_1(-x)`. 

    See also   Wikipedia :cite:p:`WikipediaFun175`, MathWorld :cite:p:`WolframFun175`, NIST :cite:p:`DLMFun175`,  BoostMath :cite:p:`BoostFun175`, :cite:t:`Ehrhardt2018` (3.4.7), :cite:t:`Ehrhardt2018` (4.2.27), Flint :cite:p:`FlintFun175`, Flint :cite:p:`FlintFun176`, Mpmath :cite:p:`MpmathFun176`. 



    The exponential integral `\mathrm{Ei}(z)` can also be calculated as
    using

    .. math ::

        \mathrm{Ei}(z) = -e^z U(1,1,-z) - \log(-z)
            + \frac{1}{2} \left(\log(z) - \log\left(\frac{1}{z}\right) \right)





    |06a_TestEi_re| `\quad` |06b_TestEi_im| `\quad` |06c_TestEi_abs|

    .. |06a_TestEi_re| image:: ../_static/ExplicitSurfaces/Cplx1F1/06a_TestEi_re.3D.xml.jpg
       :width: 30 %

    .. |06b_TestEi_im| image:: ../_static/ExplicitSurfaces/Cplx1F1/06b_TestEi_im.3D.xml.jpg
       :width: 30 %

    .. |06c_TestEi_abs| image:: ../_static/ExplicitSurfaces/Cplx1F1/06c_TestEi_abs.3D.xml.jpg
       :width: 30 %

       

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.








An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = 1.1; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp_integral_ei(x)))
        fpm:  2.1673782795634
        mpm:  2.16737827956340282358378734233807621497112737591639704719499002090327541763352339357795426
        dpm:  2.16737827956340282358378734233807621497112737591639704719499002090327541763352339357795426
        gpm:  2.1673782795634028235837873423380762149711273759163970471949900209032754176335233935779542602
        apm: [2.16737827956340282358378734233807621497112737591639704719499002090327541763352339357795426 +/- 2.88e-90]
     math53:  2.1673782795634
      sreal:  2.167378
      dreal:  2.1673782795634
      ereal:  2.1673782795634028236
      qreal:  2.16737827956340282358378734233808
      oreal:  2.1673782795634028235837873423380762149711273759163970471949900209032754
      mreal:  2.16737827956340282358378734233807621497112737591639704719499002090327541763352339357795426
     sflint:  2.167378
     dflint:  2.1673782795634
     eflint:  2.1673782795634028236
     qflint:  2.16737827956340282358378734233808
     oflint:  2.1673782795634028235837873423380762149711273759163970471949900209032754
     mflint:  2.16737827956340282358378734233807621497112737591639704719499002090327541763352339357795426
     aflint: [2.16737827956340282358378734233807621497112737591639704719499002090327541763352339357795426 +/- 4.80e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp_integral_ei(x)))
        fpm:  (0.00066296493824566, 3.14089086510677)
        mpm:  (0.00066296493824565954569798079068553101594424458743963, 3.1408908651067747929957286452838686544555363940927)
    cmath53:  (0.000662964938245659, 3.14089086510677)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.exp_integral_ei(x))))
        fpm:  0.00066296493824566
        mpm:  0.000662964938245659545697980790685531015944244587439628066771639362753019253056653823292982808
        dpm:  0.000662964938245659545697980790685531015944244587439628066771639362753019253056653823292982808
        gpm:  0.00066296493824565954569798079068553101594424458743962806677163936275301925305665382329298280796
        apm: [0.00066296493824565954569798079068553101594424458743962806677163936275301925305665382329298281 +/- 2.21e-93]
    cmath53:  0.000662964938245659
    sflintc:  0.000662965
    dflintc:  0.00066296493824566
    eflintc:  0.00066296493824565954575
    qflintc:  0.000662964938245659545697980790685531
    oflintc:  0.00066296493824565954569798079068553101594424458743962806677163936275301927
    mflintc:  0.000662964938245659545697980790685531015944244587439628066771639362753019253056653823292982809
    aflintc: [0.00066296493824565954569798079068553101594424458743962806677163936275301925305665382329298281 +/- 2.78e-93]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.exp_integral_ei(x))))
        fpm:  3.14089086510677
        mpm:  3.14089086510677479299572864528386865445553639409266499623348083983492341862164926022310663
        dpm:  3.14089086510677479299572864528386865445553639409266499623348083983492341862164926022310663
        gpm:  3.1408908651067747929957286452838686544555363940926649962334808398349234186216492602231066298
        apm: [3.14089086510677479299572864528386865445553639409266499623348083983492341862164926022310663 +/- 1.79e-90]
    cmath53:  3.14089086510677
    sflintc:  3.140891
    dflintc:  3.14089086510677
    eflintc:  3.1408908651067747929
    qflintc:  3.14089086510677479299572864528387
    oflintc:  3.1408908651067747929957286452838686544555363940926649962334808398349234
    mflintc:  3.14089086510677479299572864528386865445553639409266499623348083983492341862164926022310663
    aflintc: [3.14089086510677479299572864528386865445553639409266499623348083983492341862164926022310663 +/- 2.29e-90]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D02a_ExpIntegralEiReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D02b_ExpIntegralEiCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D02_ExpIntegralEi.cs>`__. 










|newpage|

Logarithmic integral `\mathrm{li}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.log_integral(z)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxflint``.

    Returns the logarithmic integral `\displaystyle \mathrm{li}(x) = PV \int_{0}^{x} \frac{1}{\log(t)} \, \mathrm{d}t, \quad (x \geq 0, x \neq 1)`. 
    
    For `x \neq 0` the integral is calculated as `\mathrm{li}(x)=\mathrm{Ei}(\log(x))`. 

    See also   Wikipedia :cite:p:`WikipediaFun177`, MathWorld :cite:p:`WolframFun177`, NIST :cite:p:`DLMFun177`, :cite:t:`Ehrhardt2018` (3.4.15), :cite:t:`Ehrhardt2018` (4.2.40), Flint :cite:p:`FlintFun175`, Flint :cite:p:`FlintFun176`, Mpmath :cite:p:`MpmathFun177`. 




    |07a_TestLi_re| `\quad` |07b_TestLi_im| `\quad` |07c_TestLi_abs|

    .. |07a_TestLi_re| image:: ../_static/ExplicitSurfaces/Cplx1F1/07a_TestLi_re.3D.xml.jpg
       :width: 30 %

    .. |07b_TestLi_im| image:: ../_static/ExplicitSurfaces/Cplx1F1/07b_TestLi_im.3D.xml.jpg
       :width: 30 %

    .. |07c_TestLi_abs| image:: ../_static/ExplicitSurfaces/Cplx1F1/07c_TestLi_abs.3D.xml.jpg
       :width: 30 %

       

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = 1.1; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.log_integral(x)))
        fpm:  -1.6757728303192
        mpm:  -1.67577283031919972349377327752683719091714592471177040178533986383063340431461378281065477
        dpm:  -1.67577283031919972349377327752683719091714592471177040178533986383063340431461378281065477
        gpm:  -1.67577283031919972349377327752683719091714592471177040178533986383063340431461378281065477
        apm: [-1.67577283031919972349377327752683719091714592471177040178533986383063340431461378281065477 +/- 7.41e-90]
     math53:  -1.6757728303192
      sreal:  -1.675773
      dreal:  -1.6757728303192
      ereal:  -1.6757728303191997232
      qreal:  -1.67577283031919972349377327752684
      oreal:  -1.6757728303191997234937732775268371909171459247117704017853398638306334
      mreal:  -1.67577283031919972349377327752683719091714592471177040178533986383063340431461378281065476
     sflint:  -1.675773
     dflint:  -1.6757728303192
     eflint:  -1.6757728303191997233
     qflint:  -1.67577283031919972349377327752684
     oflint:  -1.6757728303191997234937732775268371909171459247117704017853398638306334
     mflint:  -1.67577283031919972349377327752683719091714592471177040178533986383063340431461378281065476
     aflint: [-1.67577283031919972349377327752683719091714592471177040178533986383063340431461378281065476 +/- 7.02e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.log_integral(x)))
        fpm:  (0.220528354365236, 4.8773008040919)
        mpm:  (0.22052835436523574006385003712445957560602869341713, 4.8773008040918948759752534731229640860413151040781)
    cmath53:  (0.220528354365236, 4.87730080409189)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.log_integral(x))))
        fpm:  0.220528354365236
        mpm:  0.220528354365235740063850037124459575606028693417126387363046329349692716716610895896288599
        dpm:  0.220528354365235740063850037124459575606028693417126387363046329349692716716610895896288599
        gpm:  0.220528354365235740063850037124459575606028693417126387363046329349692716716610895896288599
        apm: [0.22052835436523574006385003712445957560602869341712638736304632934969271671661089589628860 +/- 2.10e-90]
    cmath53:  0.220528354365236
    sflintc:  0.2205284
    dflintc:  0.220528354365236
    eflintc:  0.22052835436523574008
    qflintc:  0.22052835436523574006385003712446
    oflintc:  0.22052835436523574006385003712445957560602869341712638736304632934969272
    mflintc:  0.2205283543652357400638500371244595756060286934171263873630463293496927167166108958962886
    aflintc: [0.22052835436523574006385003712445957560602869341712638736304632934969271671661089589628860 +/- 3.63e-90]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.log_integral(x))))
        fpm:  4.8773008040919
        mpm:  4.87730080409189487597525347312296408604131510407811670075196293073222845671991946889041268
        dpm:  4.87730080409189487597525347312296408604131510407811670075196293073222845671991946889041268
        gpm:  4.8773008040918948759752534731229640860413151040781167007519629307322284567199194688904126805
        apm: [4.87730080409189487597525347312296408604131510407811670075196293073222845671991946889041268 +/- 2.50e-90]
    cmath53:  4.87730080409189
    sflintc:  4.877301
    dflintc:  4.87730080409189
    eflintc:  4.8773008040918948759
    qflintc:  4.87730080409189487597525347312296
    oflintc:  4.8773008040918948759752534731229640860413151040781167007519629307322284
    mflintc:  4.87730080409189487597525347312296408604131510407811670075196293073222845671991946889041268
    aflintc: [4.8773008040918948759752534731229640860413151040781167007519629307322284567199194688904127 +/- 2.98e-89]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D03a_LogIntegralReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D03b_LogIntegralCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D03_LogIntegral.cs>`__. 













|newpage|

Hyperbolic sine integral `\mathrm{Shi}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sinh_integral(x)

    where ``ctx`` is ``math53``, ``ctxflint``.

    Returns the hyperbolic sine integral `\displaystyle \mathrm{Shi}(x) =  \int_0^x \frac{\sinh(t)}{t} \, \mathrm{d}t`. 

    See also   Wikipedia :cite:p:`WikipediaFun181`, MathWorld :cite:p:`WolframFun181`, NIST :cite:p:`DLMFun180`, :cite:t:`Ehrhardt2018` (3.4.17), Flint :cite:p:`FlintFun175`, Flint :cite:p:`FlintFun176`, Mpmath :cite:p:`MpmathFun181`. 

    For real `x` the integral is calculated using the relations `\displaystyle  \text{Shi}(x) = \tfrac{1}{2} \left(\text{Ei}(x)+\text{E}_1(x)\right)` for `x>0` and  `\mathrm{Shi}(x) = -\mathrm{Shi}(-x)` for `x<0`.

    For complex  `x` the integral is calculated using the relation `\displaystyle  \text{Shi}(x) = -i \text{Si}(ix)`. 





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = 1.1; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sinh_integral(x)))
        fpm:  1.17668459204972
        mpm:  1.1766845920497214896405046583967608951582435857023707864931469678482036458626064432852378
        dpm:  1.1766845920497214896405046583967608951582435857023707864931469678482036458626064432852378
        gpm:  1.1766845920497214896405046583967608951582435857023707864931469678482036458626064432852377999
        apm: [1.17668459204972148964050465839676089515824358570237078649314696784820364586260644328523780 +/- 1.19e-90]
     math53:  1.17668459204972
      sreal:  1.176685
      dreal:  1.17668459204972
      ereal:  1.1766845920497214896
      qreal:  1.17668459204972148964050465839676
      oreal:  1.1766845920497214896405046583967608951582435857023707864931469678482038
      mreal:  1.17668459204972148964050465839676089515824358570237078649314696784820364586260644328523781
     sflint:  1.176685
     dflint:  1.17668459204972
     eflint:  1.1766845920497214896
     qflint:  1.17668459204972148964050465839676
     oflint:  1.1766845920497214896405046583967608951582435857023707864931469678482037
     mflint:  1.1766845920497214896405046583967608951582435857023707864931469678482036458626064432852378
     aflint: [1.17668459204972148964050465839676089515824358570237078649314696784820364586260644328523780 +/- 1.66e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sinh_integral(x)))
        fpm:  (-1.53979127343019, 19.5889272111747)
        mpm:  (-1.5397912734301930759757337603974067975594923065287, 19.588927211174681600250959717705748939462449000561)
    cmath53:  (-1.53979127343019, 19.5889272111747)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sinh_integral(x))))
        fpm:  -1.53979127343019
        mpm:  -1.53979127343019307597573376039740679755949230652873399733400276159545974748421792955969283
        dpm:  -1.53979127343019307597573376039740679755949230652873399733400276159545974748421792955969283
        gpm:  -1.5397912734301930759757337603974067975594923065287339973340027615954597474842179295596928299
        apm: [-1.5397912734301930759757337603974067975594923065287339973340027615954597474842179295596928 +/- 4.36e-89]
    cmath53:  -1.53979127343019
    sflintc:  -1.539791
    dflintc:  -1.53979127343019
    eflintc:  -1.5397912734301930761
    qflintc:  -1.53979127343019307597573376039741
    oflintc:  -1.5397912734301930759757337603974067975594923065287339973340027615954598
    mflintc:  -1.53979127343019307597573376039740679755949230652873399733400276159545974748421792955969283
    aflintc: [-1.5397912734301930759757337603974067975594923065287339973340027615954597474842179295596928 +/- 4.26e-89]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sinh_integral(x))))
        fpm:  19.5889272111747
        mpm:  19.5889272111746816002509597177057489394624490005607363201186851883244638121301226755315723
        dpm:  19.5889272111746816002509597177057489394624490005607363201186851883244638121301226755315723
        gpm:  19.588927211174681600250959717705748939462449000560736320118685188324463812130122675531572299
        apm: [19.5889272111746816002509597177057489394624490005607363201186851883244638121301226755315723 +/- 2.48e-89]
    cmath53:  19.5889272111747
    sflintc:  19.58893
    dflintc:  19.5889272111747
    eflintc:  19.588927211174681598
    qflintc:  19.5889272111746816002509597177057
    oflintc:  19.588927211174681600250959717705748939462449000560736320118685188324464
    mflintc:  19.5889272111746816002509597177057489394624490005607363201186851883244638121301226755315723
    aflintc: [19.5889272111746816002509597177057489394624490005607363201186851883244638121301226755315723 +/- 3.57e-89]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D04a_SinhIntegralReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D04b_SinhIntegralCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D04_SinhIntegral.cs>`__. 







|newpage|

Hyperbolic cosine integral `\mathrm{Chi}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.cosh_integral(x)

    where ``ctx`` is ``math53``, ``ctxflint``.

    Note: Also ctx.chi(z), ctx.coshIntegral(z)

    Returns the hyperbolic cosine integral `\displaystyle \mathrm{Chi}(x) = -\int_x^{\infty} \frac{\cosh(t)}{t} \, \mathrm{d}t = \gamma + \log(x) + \int_0^x \frac{\cosh(t) - 1}{t} \, \mathrm{d}t`.

    See also   Wikipedia :cite:p:`WikipediaFun180`, MathWorld :cite:p:`WolframFun180`, NIST :cite:p:`DLMFun180`, :cite:t:`Ehrhardt2018` (3.4.1), Flint :cite:p:`FlintFun175`, Flint :cite:p:`FlintFun176`, Mpmath :cite:p:`MpmathFun180`. 



    For real `x` the integral is calculated using the relations `\displaystyle  \text{Chi}(x) = \tfrac{1}{2} \left(\text{Ei}(x)-\text{E}_1(x)\right)` for `x>0` and `\text{Chi}(x) = \text{Chi}(-x)` for `x<0`.

    For complex  `x` the integral is calculated using the relation `\displaystyle \text{Chi}(x) = \text{Ci}(i x) - \log(i x) + \log(x)`. 






An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = 1.1; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.cosh_integral(x)))
        fpm:  0.990693687513681
        mpm:  0.990693687513681333943282683941315319812883790214026260701843053055071771770916950292716463
        dpm:  0.990693687513681333943282683941315319812883790214026260701843053055071771770916950292716463
        gpm:  0.99069368751368133394328268394131531981288379021402626070184305305507177177091695029271646297
        apm: [0.99069368751368133394328268394131531981288379021402626070184305305507177177091695029271646 +/- 3.00e-90]
     math53:  0.990693687513681
      sreal:  0.9906937
      dreal:  0.990693687513681
      ereal:  0.99069368751368133393
      qreal:  0.990693687513681333943282683941315
      oreal:  0.99069368751368133394328268394131531981288379021402626070184305305507161
      mreal:  0.990693687513681333943282683941315319812883790214026260701843053055071771770916950292716449
     sflint:  0.9906937
     dflint:  0.990693687513681
     eflint:  0.99069368751368133398
     qflint:  0.990693687513681333943282683941315
     oflint:  0.99069368751368133394328268394131531981288379021402626070184305305507178
     mflint:  0.990693687513681333943282683941315319812883790214026260701843053055071771770916950292716462
     aflint: [0.99069368751368133394328268394131531981288379021402626070184305305507177177091695029271646 +/- 3.32e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.cosh_integral(x)))
        fpm:  (1.54045423836844, -16.4480363460679)
        mpm:  (1.5404542383684387355214317411880923285754365511162, -16.448036346067906807255231072421880285006912606468)
    cmath53:  (1.54045423836844, -16.4480363460679)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.cosh_integral(x))))
        fpm:  1.54045423836844
        mpm:  1.54045423836843873552143174118809232857543655111617362540077440095821276673727458338298581
        dpm:  1.54045423836843873552143174118809232857543655111617362540077440095821276673727458338298581
        gpm:  1.54045423836843873552143174118809232857543655111617362540077440095821276673727458338298581
        apm: [1.5404542383684387355214317411880923285754365511161736254007744009582127667372745833829858 +/- 2.62e-89]
    cmath53:  1.54045423836844
    sflintc:  1.540454
    dflintc:  1.54045423836844
    eflintc:  1.5404542383684387356
    qflintc:  1.54045423836843873552143174118809
    oflintc:  1.5404542383684387355214317411880923285754365511161736254007744009582128
    mflintc:  1.54045423836843873552143174118809232857543655111617362540077440095821276673727458338298581
    aflintc: [1.5404542383684387355214317411880923285754365511161736254007744009582127667372745833829858 +/- 2.53e-89]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.cosh_integral(x))))
        fpm:  -16.4480363460679
        mpm:  -16.4480363460679068072552310724218802850069126064680713238852043484895403935084734153084657
        dpm:  -16.4480363460679068072552310724218802850069126064680713238852043484895403935084734153084657
        gpm:  -16.4480363460679068072552310724218802850069126064680713238852043484895403935084734153084657
        apm: [-16.4480363460679068072552310724218802850069126064680713238852043484895403935084734153084657 +/- 5.50e-89]
    cmath53:  -16.4480363460679
    sflintc:  -16.44803
    dflintc:  -16.4480363460679
    eflintc:  -16.448036346067906805
    qflintc:  -16.4480363460679068072552310724219
    oflintc:  -16.44803634606790680725523107242188028500691260646807132388520434848954
    mflintc:  -16.4480363460679068072552310724218802850069126064680713238852043484895403935084734153084657
    aflintc: [-16.4480363460679068072552310724218802850069126064680713238852043484895403935084734153084657 +/- 7.34e-89]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D05a_CoshIntegralReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D05b_CoshIntegralCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D05_CoshIntegral.cs>`__. 











|newpage|

Generalized exponential integral `E_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.exp_integral_en(n, z)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.


    Returns the generalized exponential integral of integer order `\displaystyle E_n(x) = \int_{1}^{\infty} \frac{e^{-xt}}{t^n} \, \mathrm{d}t, \quad (n \geq 0)`.

    See also   Wikipedia :cite:p:`WikipediaFun175`, MathWorld :cite:p:`WolframFun176`, NIST :cite:p:`DLMFun176`,  BoostMath :cite:p:`BoostFun176`, :cite:t:`Ehrhardt2018` (3.4.12), Mpmath :cite:p:`MpmathFun176a`. 

    The function can be generalized for complex `s` and complex `z` using

    .. math :: \text{E}_{1-s}(z) = z^{-s} \Gamma(s,z).




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 4; x = 1.1; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp_integral_en(n, x)))
        fpm:  0.0758006821109131
        mpm:  0.075800682110913068367744087428312948302942983786008632309283952575736304300843797054929354
        dpm:  0.075800682110913068367744087428312948302942983786008632309283952575736304300843797054929354
        gpm:  0.075800682110913068367744087428312948302942983786008632309283952575736304300843797054929354002
        apm: [0.07580068211091306836774408742831294830294298378600863230928395257573630430084379705492935 +/- 5.41e-90]
     math53:  0.0758006821109131
      sreal:  0.07580068
      dreal:  0.0758006821109129
      ereal:  0.075800682110913068489
      qreal:  0.0758006821109130683677440874283132
      oreal:  0.075800682110913068367744087428312948302942983786008632309283952575736238
      mreal:  0.0758006821109130683677440874283129483029429837860086323092839525757363043008437970549293409
     sflint:  0.07580068
     dflint:  0.0758006821109131
     eflint:  0.075800682110913068367
     qflint:  0.0758006821109130683677440874283129
     oflint:  0.075800682110913068367744087428312948302942983786008632309283952575736304
     mflint:  0.0758006821109130683677440874283129483029429837860086323092839525757363043008437970549293541
     aflint: [0.07580068211091306836774408742831294830294298378600863230928395257573630430084379705492935 +/- 7.06e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 4+2j; x = -5.1+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.exp_integral_en(n, x)))
        fpm:  (-35.3770113219049, 36.3828832170989)
        mpm:  (-35.377011321904852827424165438138238679318459910563, 36.382883217098884167491313826657376375507498020383)
    cmath53:  (NaN, NaN)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 4; x = -5.1+2j; gui.setdps(50)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.exp_integral_en(n, x))))
        fpm:  -35.3770113219049
        mpm:  -35.377011321904852827424165438138238679318459910563
        dpm:  -35.377011321904852827424165438138238679318459910563
        gpm:  -35.37701132190485282742416543813823867931845991056298
        apm: [-35.37701132190485282742416543813823867931845991056 +/- 6.01e-48]
    cmath53:  NaN
    sflintc:  -35.37701
    dflintc:  -35.3770113219048
    eflintc:  -35.377011321904852825
    qflintc:  -35.3770113219048528274241654381382
    oflintc:  -35.377011321904852827424165438138238679318459910563090333762404239289339
    mflintc:  -35.377011321904852827424165438138238679318459910564
    aflintc: [-35.3770113219048528274241654381382386793184599106 +/- 5.24e-47]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 4; x = -5.1+2j; gui.setdps(50)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.exp_integral_en(n, x))))
        fpm:  36.3828832170989
        mpm:  36.382883217098884167491313826657376375507498020383
        dpm:  36.382883217098884167491313826657376375507498020383
        gpm:  36.38288321709888416749131382665737637550749802038296
        apm: [36.38288321709888416749131382665737637550749802038 +/- 5.92e-48]
    cmath53:  NaN
    sflintc:  36.38288
    dflintc:  36.3828832170989
    eflintc:  36.382883217098884163
    qflintc:  36.3828832170988841674913138266574
    oflintc:  36.382883217098884167491313826657376375507498020383194438464443166493281
    mflintc:  36.382883217098884167491313826657376375507498020382
    aflintc: [36.3828832170988841674913138266573763755074980204 +/- 3.27e-47]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D06a_ExpIntegralEnReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D06b_ExpIntegralEnCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D06_ExpIntegralEn.cs>`__. 









|newpage|

Sine integral `\mathrm{Si}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sin_integral(z)

    where ``ctx`` is ``math53``, ``ctxflint``.


    Returns the sine integral `\displaystyle \mathrm{Si}(x) =  \int_0^x \frac{\sin(t)}{t} \, \mathrm{d}t`, and `\mathrm{Si}(x) = -\mathrm{Si}(-x)` for `x<0`.

    See also   Wikipedia :cite:p:`WikipediaFun179`, MathWorld :cite:p:`WolframFun179`, NIST :cite:p:`DLMFun178`, :cite:t:`Ehrhardt2018` (3.4.18), Flint :cite:p:`FlintFun175`, Flint :cite:p:`FlintFun176`, Mpmath :cite:p:`MpmathFun179`.


    For complex `z`, the sine integral `\mathrm{Si}(z)` can be computed using

    .. math ::

        \mathrm{Si}(z) = \frac{i}{2} \left[
            e^{iz} U(1,1,-iz) - e^{-iz} U(1,1,iz) + 
            \log(-iz) - \log(iz) \right]

    .. math ::

        \mathrm{Si}(z) = z {}_1F_2(\tfrac{1}{2}; \tfrac{3}{2}, \tfrac{3}{2}; -\tfrac{z^2}{4})

    and an automatic algorithm choice.





    |13a_TestSinIntegral_re| `\quad` |13b_TestSinIntegral_im| `\quad` |13c_TestSinIntegral_abs|

    .. |13a_TestSinIntegral_re| image:: ../_static/ExplicitSurfaces/Cplx1F1/13a_TestSinIntegral_re.3D.xml.jpg
       :width: 30 %

    .. |13b_TestSinIntegral_im| image:: ../_static/ExplicitSurfaces/Cplx1F1/13b_TestSinIntegral_im.3D.xml.jpg
       :width: 30 %

    .. |13c_TestSinIntegral_abs| image:: ../_static/ExplicitSurfaces/Cplx1F1/13c_TestSinIntegral_abs.3D.xml.jpg
       :width: 30 %

       

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.




An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = 1.1; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sin_integral(x)))
        fpm:  1.02868521867373
        mpm:  1.02868521867373352203173166616981946558405192241128961126882268745922046213548087710546124
        dpm:  1.02868521867373352203173166616981946558405192241128961126882268745922046213548087710546124
        gpm:  1.0286852186737335220317316661698194655840519224112896112688226874592204621354808771054612401
        apm: [1.02868521867373352203173166616981946558405192241128961126882268745922046213548087710546124 +/- 2.98e-90]
     math53:  1.02868521867373
     sflint:  1.028685
     dflint:  1.02868521867373
     eflint:  1.0286852186737335221
     qflint:  1.02868521867373352203173166616982
     oflint:  1.0286852186737335220317316661698194655840519224112896112688226874592205
     mflint:  1.02868521867373352203173166616981946558405192241128961126882268745922046213548087710546124
     aflint: [1.02868521867373352203173166616981946558405192241128961126882268745922046213548087710546124 +/- 3.43e-90]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sin_integral(x)))
        fpm:  (-1.19561685415352, -0.564278138989367)
        mpm:  (-1.1956168541535218232245774332269273099797414841213, -0.56427813898936714823860686028687779728645674048531)
    cmath53:  (-1.19561685415352, -0.564278138989368)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sin_integral(x))))
        fpm:  -1.19561685415352
        mpm:  -1.19561685415352182322457743322692730997974148412131037583118491590252833876396308469265238
        dpm:  -1.19561685415352182322457743322692730997974148412131037583118491590252833876396308469265238
        gpm:  -1.19561685415352182322457743322692730997974148412131037583118491590252833876396308469265238
        apm: [-1.19561685415352182322457743322692730997974148412131037583118491590252833876396308469265238 +/- 5.31e-90]
    cmath53:  -1.19561685415352
    sflintc:  -1.195617
    dflintc:  -1.19561685415352
    eflintc:  -1.1956168541535218232
    qflintc:  -1.19561685415352182322457743322693
    oflintc:  -1.1956168541535218232245774332269273099797414841213103758311849159025283
    mflintc:  -1.19561685415352182322457743322692730997974148412131037583118491590252833876396308469265238
    aflintc: [-1.19561685415352182322457743322692730997974148412131037583118491590252833876396308469265238 +/- 5.95e-90]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sin_integral(x))))
        fpm:  -0.564278138989367
        mpm:  -0.564278138989367148238606860286877797286456740485305214321947036027847563320420750873230064
        dpm:  -0.564278138989367148238606860286877797286456740485305214321947036027847563320420750873230064
        gpm:  -0.56427813898936714823860686028687779728645674048530521432194703602784756332042075087323006399
        apm: [-0.56427813898936714823860686028687779728645674048530521432194703602784756332042075087323006 +/- 5.66e-90]
    cmath53:  -0.564278138989368
    sflintc:  -0.5642782
    dflintc:  -0.564278138989367
    eflintc:  -0.56427813898936714828
    qflintc:  -0.564278138989367148238606860286878
    oflintc:  -0.56427813898936714823860686028687779728645674048530521432194703602784757
    mflintc:  -0.564278138989367148238606860286877797286456740485305214321947036027847563320420750873230065
    aflintc: [-0.56427813898936714823860686028687779728645674048530521432194703602784756332042075087323006 +/- 5.94e-90]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D07a_SinIntegralReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D07b_SinIntegralCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D07_SinIntegral.cs>`__. 









|newpage|

Cosine integral `\mathrm{Ci}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.cos_integral(z)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the cosine integral `\displaystyle \mathrm{Ci}(x) = -\int_x^{\infty} \frac{\cos(t)}{t} \, \mathrm{d}t = \gamma + \log(x) + \int_0^x \frac{\cos(t) - 1}{t} \, \mathrm{d}t`, and `\text{Ci}(x) = \text{Ci}(-x)` for `x<0`.


    For complex `z`, the cosine integral `\mathrm{Ci}(z)`, can be computed using

    .. math ::

        \mathrm{Ci}(z) = \log(z) - \frac{1}{2} \left[
            e^{iz} U(1,1,-iz) + e^{-iz} U(1,1,iz) + 
            \log(-iz) + \log(iz) \right]


    See also   Wikipedia :cite:p:`WikipediaFun178`, MathWorld :cite:p:`WolframFun178`, NIST :cite:p:`DLMFun178`, :cite:t:`Ehrhardt2018` (3.4.2), Flint :cite:p:`FlintFun175`, Flint :cite:p:`FlintFun176`, Mpmath :cite:p:`MpmathFun178`.




    |12a_TestCosIntegral_re| `\quad` |12b_TestCosIntegral_im| `\quad` |12c_TestCosIntegral_abs|

    .. |12a_TestCosIntegral_re| image:: ../_static/ExplicitSurfaces/Cplx1F1/12a_TestCosIntegral_re.3D.xml.jpg
       :width: 30 %

    .. |12b_TestCosIntegral_im| image:: ../_static/ExplicitSurfaces/Cplx1F1/12b_TestCosIntegral_im.3D.xml.jpg
       :width: 30 %

    .. |12c_TestCosIntegral_abs| image:: ../_static/ExplicitSurfaces/Cplx1F1/12c_TestCosIntegral_abs.3D.xml.jpg
       :width: 30 %

       

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = 1.1; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.cos_integral(x)))
        fpm:  0.384873377424651
        mpm:  0.384873377424650815498332396661457354043695076787709991856388693439696252284825746468070062
        dpm:  0.384873377424650815498332396661457354043695076787709991856388693439696252284825746468070062
        gpm:  0.38487337742465081549833239666145735404369507678770999185638869343969625228482574646807006203
        apm: [0.384873377424650815498332396661457354043695076787709991856388693439696252284825746468070062 +/- 3.20e-91]
     math53:  0.384873377424651
     sflint:  0.3848734
     dflint:  0.384873377424651
     eflint:  0.38487337742465081551
     qflint:  0.384873377424650815498332396661457
     oflint:  0.38487337742465081549833239666145735404369507678770999185638869343969625
     mflint:  0.384873377424650815498332396661457354043695076787709991856388693439696252284825746468070062
     aflint: [0.384873377424650815498332396661457354043695076787709991856388693439696252284825746468070062 +/- 4.61e-91]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(50)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.cos_integral(x)))
        fpm:  (-0.586802618859697, 2.76365403098315)
        mpm:  (-0.5868026188596967594971386824607582145811828090505, 2.7636540309831487656009159792127002972517516388949)
    cmath53:  (-0.586802618859697, 2.76365403098315)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.cos_integral(x))))
        fpm:  -0.586802618859697
        mpm:  -0.586802618859696759497138682460758214581182809050496414478338763969608161679445377146956408
        dpm:  -0.586802618859696759497138682460758214581182809050496414478338763969608161679445377146956408
        gpm:  -0.58680261885969675949713868246075821458118280905049641447833876396960816167944537714695640796
        apm: [-0.58680261885969675949713868246075821458118280905049641447833876396960816167944537714695641 +/- 2.23e-90]
    cmath53:  -0.586802618859697
    sflintc:  -0.5868027
    dflintc:  -0.586802618859697
    eflintc:  -0.58680261885969675953
    qflintc:  -0.586802618859696759497138682460758
    oflintc:  -0.58680261885969675949713868246075821458118280905049641447833876396960817
    mflintc:  -0.586802618859696759497138682460758214581182809050496414478338763969608161679445377146956409
    aflintc: [-0.58680261885969675949713868246075821458118280905049641447833876396960816167944537714695641 +/- 2.50e-90]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> x = -5.1+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.cos_integral(x))))
        fpm:  2.76365403098315
        mpm:  2.76365403098314876560091597921270029725175163889493154210945197852357758996053608606989524
        dpm:  2.76365403098314876560091597921270029725175163889493154210945197852357758996053608606989524
        gpm:  2.7636540309831487656009159792127002972517516388949315421094519785235775899605360860698952402
        apm: [2.76365403098314876560091597921270029725175163889493154210945197852357758996053608606989524 +/- 4.31e-90]
    cmath53:  2.76365403098315
    sflintc:  2.763654
    dflintc:  2.76365403098315
    eflintc:  2.7636540309831487657
    qflintc:  2.7636540309831487656009159792127
    oflintc:  2.7636540309831487656009159792127002972517516388949315421094519785235776
    mflintc:  2.76365403098314876560091597921270029725175163889493154210945197852357758996053608606989524
    aflintc: [2.76365403098314876560091597921270029725175163889493154210945197852357758996053608606989524 +/- 4.21e-90]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D08a_CosIntegralReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D08b_CosIntegralCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B11_Hypergeometric1F1/C05_ExponentialIntegrals/D08_CosIntegral.cs>`__. 










