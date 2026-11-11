

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Lerch’s transcendent and Lerch’s zeta
===============================================================================


.. _rst_mpm_lerchphi: 

Lerch's transcendent, `\Phi(x,s,a)`
-------------------------------------------------------------------------------

.. method:: ctx.lerch_phi(s, z, a)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the Lerch transcendent `\Phi(z, s, a)`. See also  Wikipedia :cite:p:`WikipediaFun1007`, MathWorld :cite:p:`WolframFun1007`, NIST :cite:p:`DLMFun1007`, :cite:t:`Ehrhardt2018` (3.6.10), Flint :cite:p:`FlintFun1007`,  Mpmath :cite:p:`MpmathFun1007`.  
    
    
    The function is defined for `|z| < 1` and `\Re{a} > 0` by

    .. math ::  \Phi(z,s,a) = \sum_{k=0}^{\infty} \frac{z^k}{(a+k)^s}

    and generally by the recurrence `\Phi(z,s,a) = z \Phi(z,s,a+1) + a^{-s}` along with the integral representation valid for `\Re{a} > 0`

    .. math :: \Phi(z,s,a) = \frac{1}{2 a^s} +  \int_0^{\infty} \frac{z^t}{(a+t)^s} \mathrm{d}t -  2 \int_0^{\infty} \frac{\sin(t \log z - s  \mathrm{arctan}(t/a)}{(a^2 + t^2)^{s/2} (e^{2 \pi t}-1)} \mathrm{d}t.


    The Amath implementation requires `x \le 1, s \ge -1, a \ge 0`. We have also `\Phi(x,0,a) = 1/(1-x)` and `\Phi(x,s,0) = \text{Li}_s(x)`.



    See also: https://fredrikj.net/blog/2022/02/computing-the-lerch-transcendent/



    |01_0a_TestLerchPhiFlint_0_re| `\quad` |01_0b_TestLerchPhiFlint_0_im| `\quad` |01_0c_TestLerchPhiFlint_0_abs|

    .. |01_0a_TestLerchPhiFlint_0_re| image:: ../_static/ExplicitSurfaces/CplxLerch/01_0a_TestLerchPhiFlint_0_re.3D.xml.jpg
       :width: 30 %

    .. |01_0b_TestLerchPhiFlint_0_im| image:: ../_static/ExplicitSurfaces/CplxLerch/01_0b_TestLerchPhiFlint_0_im.3D.xml.jpg
       :width: 30 %

    .. |01_0c_TestLerchPhiFlint_0_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/01_0c_TestLerchPhiFlint_0_abs.3D.xml.jpg
       :width: 30 %


    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    |01_1a_TestLerchPhiFlint_1_re| `\quad` |01_1b_TestLerchPhiFlint_1_im| `\quad` |01_1c_TestLerchPhiFlint_1_abs|

    .. |01_1a_TestLerchPhiFlint_1_re| image:: ../_static/ExplicitSurfaces/CplxLerch/01_1a_TestLerchPhiFlint_1_re.3D.xml.jpg
       :width: 30 %

    .. |01_1b_TestLerchPhiFlint_1_im| image:: ../_static/ExplicitSurfaces/CplxLerch/01_1b_TestLerchPhiFlint_1_im.3D.xml.jpg
       :width: 30 %

    .. |01_1c_TestLerchPhiFlint_1_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/01_1c_TestLerchPhiFlint_1_abs.3D.xml.jpg
       :width: 30 %


   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.






    |01_2a_TestLerchPhiFlint_2_re| `\quad` |01_2b_TestLerchPhiFlint_2_im| `\quad` |01_2c_TestLerchPhiFlint_2_abs|

    .. |01_2a_TestLerchPhiFlint_2_re| image:: ../_static/ExplicitSurfaces/CplxLerch/01_2a_TestLerchPhiFlint_2_re.3D.xml.jpg
       :width: 30 %

    .. |01_2b_TestLerchPhiFlint_2_im| image:: ../_static/ExplicitSurfaces/CplxLerch/01_2b_TestLerchPhiFlint_2_im.3D.xml.jpg
       :width: 30 %

    .. |01_2c_TestLerchPhiFlint_2_abs| image:: ../_static/ExplicitSurfaces/CplxLerch/01_2c_TestLerchPhiFlint_2_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.










    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -0.8; s = -0.5; a = 0.3; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.lerch_phi(z, s, a)))
            fpm:  0.123808328418779
            mpm:  0.123808328418778929202068596100771367142889320531989172565355231698781813985907582795703294
            dpm:  0.123808328418778929202068596100771367142889320531989172565355231698781813985907582795703294
            gpm:  0.12380832841877892920206859610077136714288932053198917256535523169878181398590758279570329399
            apm: [0.1238083284187789292020685961007713671428893205319891725653552316987818139859075827957033 +/- 1.52e-89]
         math53:  0.123808328418779
         sflint:  0.1238083
         dflint:  0.123808328418779
         eflint:  0.12380832841877892921
         qflint:  0.123808328418778929202068596100771
         oflint:  0.12380832841877892920206859610077136714288932053198917256535523169878181
         mflint:  0.123808328418778929202068596100771367142889320531989172565355231698781813985907582795703294
         aflint: [0.1238083284187789292020685961007713671428893205319891725653552316987818139859075827957033 +/- 1.36e-89]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j;  s = 2.7+2j; a = 1.3+2j;  gui.setdps(40)
        >>> for ctx in [fpm, mpm]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.lerch_phi(z, s, a)))
            fpm:  (-0.0627085773238789, 0.285173796041804)
            mpm:  (-0.06270857732387887100910083293243429602788, 0.2851737960418038082249546738603097815877)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j;  s = 2.7+2j; a = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.lerch_phi(z, s, a))))
            fpm:  -0.0627085773238789
            mpm:  -0.0627085773238788710091008329324342960278883509709070343376000077605998033488008546398116272
            dpm:  -0.0627085773238788710091008329324342960278883509709070343376000077605998033488008546398116272
            gpm:  -0.062708577323878871009100832932434296027888350970907034337600007760599803348800854639811627196
            apm: [-0.0627085773238788710091008329324342960278883509709070343376000077605998033488008546398116 +/- 9.36e-89]
        cmath53:  NaN
        sflintc:  -0.06270856
        dflintc:  -0.0627085773238788
        eflintc:  -0.062708577323878870987
        qflintc:  -0.0627085773238788710091008329324342
        oflintc:  -0.062708577323878871009100832932434296027888350970907034337600007760599801
        mflintc:  -0.0627085773238788710091008329324342960278883509709070343376000077605998033488008546398116277
        aflintc: [-0.062708577323878871009100832932434296027888350970907034337600007760599803348800854639812 +/- 5.97e-88]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> z = -5.1+2j;  s = 2.7+2j; a = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.lerch_phi(z, s, a))))
            fpm:  0.285173796041804
            mpm:  0.285173796041803808224954673860309781587704300529277183606049018295125045429867544686889185
            dpm:  0.285173796041803808224954673860309781587704300529277183606049018295125045429867544686889185
            gpm:  0.285173796041803808224954673860309781587704300529277183606049018295125045429867544686889185
            apm: [0.2851737960418038082249546738603097815877043005292771836060490182951250454298675446868892 +/- 8.01e-89]
        cmath53:  NaN
        sflintc:  0.2851738
        dflintc:  0.285173796041804
        eflintc:  0.28517379604180380823
        qflintc:  0.28517379604180380822495467386031
        oflintc:  0.28517379604180380822495467386030978158770430052927718360604901829512504
        mflintc:  0.285173796041803808224954673860309781587704300529277183606049018295125045429867544686889191
        aflintc: [0.285173796041803808224954673860309781587704300529277183606049018295125045429867544686889 +/- 4.18e-88]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C01_LerchPhi/D01a_LerchPhiReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C01_LerchPhi/D01b_LerchPhiCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C01_LerchPhi/D01_LerchPhi.cs>`__. 








|newpage|

.. _rst_mpm_lerchzeta: 

Lerch's zeta
-------------------------------------------------------------------------------


.. method:: ctx.lerch_zeta(lambda1, alpha, s)



    Returns the lerch zeta function.  See also  Wikipedia :cite:p:`WikipediaFun1007`, :cite:t:`Apostol1951`, :cite:t:`Ferreira2004`.

    The Lerch zeta function is given by

    .. math:: L(\lambda_1 ,\alpha ,s)=\sum _{n=0}^{\infty }{\frac {e^{2\pi i\lambda n}}{(n+\alpha )^{s}}}.


    The Lerch zeta function is related to the Lerch transcendent by

    .. math::  L(\lambda_1 ,\alpha ,s) = \,\Phi (e^{2\pi i\lambda_1 },s,\alpha ).



    For `\lambda_1` rational, `L(\lambda_1 ,\alpha ,s)` may be expressed as a finite sum over the Hurwitz zeta-function. Suppose `\lambda_1 =\frac {p}{q}` with `p,q \in \mathbb {Z}`  and `q>0`. Then `z=\omega =e^{2\pi i{\frac {p}{q}}}` and `\omega ^{q}=1`.

    .. math :: L(\lambda_1 ,\alpha ,s) = \Phi (\omega ,s,\alpha )=\sum _{n=0}^{\infty }{\frac {\omega ^{n}}{(n+\alpha )^{s}}} = \sum _{m=0}^{q-1}\omega ^{m}q^{-s}\zeta \left(s,{\frac {m+\alpha }{q}} \right)




    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> lambda1 = -5.1+2j;  alpha = 2.7+2j; s = 1.3+2j;  gui.setdps(40)
        >>> for ctx in [fpm, mpm]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.lerch_zeta(lambda1, alpha, s)))
            fpm:  (-0.735918248768655, 0.0821281539931932)
            mpm:  (-0.7359182487686553128664233111902630210224, 0.08212815399319318865207981672221221256608)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> lambda1 = -5.1+2j;  alpha = 2.7+2j; s = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.lerch_zeta(lambda1, alpha, s))))
            fpm:  -0.735918248768655
            mpm:  -0.735918248768655312866423311190263021022352264694369727202201322123643908010177136691707872
            dpm:  -0.735918248768655312866423311190263021022352264694369727202201322123643908010177136691707872
            gpm:  -0.73591824876865531286642331119026302102235226469436972720220132212364390801017713669170787203
            apm: [-0.735918248768655312866423311190263021022352264694369727202201322123643908010177136691707872 +/- 8.39e-91]
        cmath53:  NaN
        sflintc:  -0.7359183
        dflintc:  -0.735918248768655
        eflintc:  -0.7359182487686553129
        qflintc:  -0.735918248768655312866423311190263
        oflintc:  -0.7359182487686553128664233111902630210223522646943697272022013221236439
        mflintc:  -0.735918248768655312866423311190263021022352264694369727202201322123643908010177136691707872
        aflintc: [-0.73591824876865531286642331119026302102235226469436972720220132212364390801017713669170787 +/- 2.64e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> lambda1 = -5.1+2j;  alpha = 2.7+2j; s = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.lerch_zeta(lambda1, alpha, s))))
            fpm:  0.0821281539931932
            mpm:  0.0821281539931931886520798167222122125660847272863618298052586518730029623613629007457575332
            dpm:  0.0821281539931931886520798167222122125660847272863618298052586518730029623613629007457575332
            gpm:  0.082128153993193188652079816722212212566084727286361829805258651873002962361362900745757533207
            apm: [0.082128153993193188652079816722212212566084727286361829805258651873002962361362900745757533 +/- 4.95e-91]
        cmath53:  NaN
        sflintc:  0.08212814
        dflintc:  0.0821281539931932
        eflintc:  0.082128153993193188639
        qflintc:  0.0821281539931931886520798167222122
        oflintc:  0.082128153993193188652079816722212212566084727286361829805258651873002964
        mflintc:  0.082128153993193188652079816722212212566084727286361829805258651873002962361362900745757533
        aflintc: [0.082128153993193188652079816722212212566084727286361829805258651873002962361362900745757533 +/- 5.28e-91]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B09_LerchPhi/C01_LerchPhi/D02b_LerchZetaCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B09_LerchPhi/C01_LerchPhi/D02_LerchZeta.cs>`__. 





