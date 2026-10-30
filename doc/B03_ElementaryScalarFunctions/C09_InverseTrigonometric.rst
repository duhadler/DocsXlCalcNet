

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />






|newpage|

Inverse trigonometric functions, in radians
===============================================================================

For a general introduction to inverse trigonometric functions, see  Wikipedia :cite:p:`WikipediaFun50`,  NIST :cite:p:`DLMFun50`.




Inverse sine, `\mathrm{asin}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.asin(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp``, ``ctxflint``.

    Returns the inverse sine of `x`, `\mathrm{asin}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun51`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.13), Mpmath :cite:p:`MpmathFun51`.

    The inverse sine can be expressed in terms of the inverse tangent as `\displaystyle \mathrm{asin}(x) = \mathrm{atan}\left(\frac{x}{\sqrt{1-x^2}}  \right)`. The domain is the open interval `(-1, 1)`. We have `\sin(\mathrm{asin}(x)) = x` for all `x`, but `\mathrm{asin}(\sin(x)) = x` only for `-\pi/2 < x < \pi/2`.


    The inverse sine can be expressed in terms of related functions (with the principal-branch log and square root):

    .. math :: \mathrm{asin}(z) = -i \log\left(iz + \sqrt{1-z^2} \right)


    The inverse sine has two branch points: `x = \pm 1`.The branch cuts are placed along the line segments `(-\infty, -1)` and `(+1, +\infty)`. 
    Since `-1 \le \sin(x) \le 1` for real `x`, the inverse sine is real-valued only for `-1 \le x \le 1`.
    On this interval, it is defined to be a monotonically increasing function assuming values between `-\pi/2` and `\pi/2`.




    |02a_TestAsin_re| `\quad` |02b_TestAsin_im| `\quad` |02c_TestAsin_abs|

    .. |02a_TestAsin_re| image:: ../_static/ExplicitSurfaces/CplxTrig/02a_TestAsin_re.3D.xml.jpg
       :width: 30 %

    .. |02b_TestAsin_im| image:: ../_static/ExplicitSurfaces/CplxTrig/02b_TestAsin_im.3D.xml.jpg
       :width: 30 %

    .. |02c_TestAsin_abs| image:: ../_static/ExplicitSurfaces/CplxTrig/02c_TestAsin_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.



    

    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.asin(x)))
            fpm:  0.523598775598299
            mpm:  0.523598775598298873077107230546583814032861566562517636829157432051302734381034833104672471
            dpm:  0.523598775598298873077107230546583814032861566562517636829157432051302734381034833104672471
            ipm: [0.52359877559829887307710723054658381403286156656251763682915743205130273438103483310467247076724,
                  0.52359877559829887307710723054658381403286156656251763682915743205130273438103483310467247101269]
            gpm:  0.52359877559829887307710723054658381403286156656251763682915743205130273438103483310467247089
            apm: [0.523598775598298873077107230546583814032861566562517636829157432051302734381034833104672471 +/- 4.48e-91]
         math53:  0.523598775598299
          sreal:  0.5235988
          dreal:  0.523598775598299
          ereal:  0.52359877559829887307
          qreal:  0.523598775598298873077107230546584
          oreal:  0.52359877559829887307710723054658381403286156656251763682915743205130273
          mreal:  0.523598775598298873077107230546583814032861566562517636829157432051302734381034833104672471
         sflint:  0.5235988
         dflint:  0.523598775598299
         eflint:  0.52359877559829887307
         qflint:  0.523598775598298873077107230546584
         oflint:  0.52359877559829887307710723054658381403286156656251763682915743205130273
         mflint:  0.523598775598298873077107230546583814032861566562517636829157432051302734381034833104672471
         aflint: [0.52359877559829887307710723054658381403286156656251763682915743205130273438103483310467247 +/- 1.02e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.asin(x)))
            fpm:  (-1.19130130401227, 2.3877960445782)
            mpm:  (-1.1913013040122696682262786974138918546152906903327, 2.3877960445782021699561212768720476189495083854716)
        cmath53:  (-1.19130130401227, 2.38779604457821)
          qcplx:  (-1.19130130401226966822627869741389, 2.38779604457820216995612127687205)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.asin(x))))
            fpm:  -1.19130130401227
            mpm:  -1.19130130401226966822627869741389185461529069033271151351756290307416506948616588422755156
            dpm:  -1.19130130401226966822627869741389185461529069033271151351756290307416506948616588422755156
            ipm: [-1.1913013040122696682262786974138918546152906903327115135175629030741650694861658842275515795759,
                  -1.1913013040122696682262786974138918546152906903327115135175629030741650694861658842275515476668]
            gpm:  -1.1913013040122696682262786974138918546152906903327115135175629030741650694861658842275515636
            apm: [-1.1913013040122696682262786974138918546152906903327115135175629030741650694861658842275516 +/- 6.35e-89]
        cmath53:  -1.19130130401227
          scplx:  -1.191301
          dcplx:  -1.19130130401227
          ecplx:  -1.1913013040122696683
          qcplx:  -1.19130130401226966822627869741389
          ocplx:  -1.1913013040122696682262786974138918546152906903327115135175629030741651
          mcplx:  -1.19130130401226966822627869741389185461529069033271151351756290307416506948616588422755156
        sflintc:  -1.191301
        dflintc:  -1.19130130401227
        eflintc:  -1.1913013040122696682
        qflintc:  -1.19130130401226966822627869741389
        oflintc:  -1.1913013040122696682262786974138918546152906903327115135175629030741651
        mflintc:  -1.19130130401226966822627869741389185461529069033271151351756290307416506948616588422755156
        aflintc: [-1.1913013040122696682262786974138918546152906903327115135175629030741650694861658842275516 +/- 8.88e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.asin(x))))
            fpm:  2.3877960445782
            mpm:  2.38779604457820216995612127687204761894950838547156210189345318461152736761261505266094818
            dpm:  2.38779604457820216995612127687204761894950838547156210189345318461152736761261505266094818
            ipm: [2.387796044578202169956121276872047618949508385471562101893453184611527367612615052660948158087,
                  2.3877960445782021699561212768720476189495083854715621018934531846115273676126150526609481963779]
            gpm:  2.3877960445782021699561212768720476189495083854715621018934531846115273676126150526609481767
            apm: [2.3877960445782021699561212768720476189495083854715621018934531846115273676126150526609482 +/- 6.84e-89]
        cmath53:  2.38779604457821
          scplx:  2.387796
          dcplx:  2.38779604457821
          ecplx:  2.3877960445782021701
          qcplx:  2.38779604457820216995612127687205
          ocplx:  2.3877960445782021699561212768720476189495083854715621018934531846115271
          mcplx:  2.38779604457820216995612127687204761894950838547156210189345318461152736761261505266094818
        sflintc:  2.387796
        dflintc:  2.3877960445782
        eflintc:  2.3877960445782021699
        qflintc:  2.38779604457820216995612127687205
        oflintc:  2.3877960445782021699561212768720476189495083854715621018934531846115274
        mflintc:  2.38779604457820216995612127687204761894950838547156210189345318461152736761261505266094818
        aflintc: [2.387796044578202169956121276872047618949508385471562101893453184611527367612615052660948 +/- 2.50e-88]










Inverse cosine, `\mathrm{acos}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.acos(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp``, ``ctxflint``.

    Returns the inverse cosine of `x`, `\mathrm{acos}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun52`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.3), Flint :cite:p:`FlintFun50`, Flint :cite:p:`FlintFun51`, Mpmath :cite:p:`MpmathFun52`.

    The inverse cosine can be expressed in terms of the inverse tangent as `\displaystyle \mathrm{acos}(x) = \mathrm{atan}\left(\frac{\sqrt{1-x^2}}{x}  \right)`. The domain is the open interval `(-1, 1)`. We have `\cos(\mathrm{acos}(x)) = x` for all `x`, but `\mathrm{acos}(\cos(x)) = x` only for `0 \le x < \pi`.


    The inverse cosine can be expressed in terms of related functions (with the principal-branch log and square root):

    .. math :: \mathrm{acos}(z) = \frac{\pi}{2} + i \log\left(iz + \sqrt{1-z^2} \right)

    The inverse cosine has two branch points: `x = \pm 1`.The branch cuts are placed along the line segments `(-\infty, -1)` and `(+1, +\infty)`. 

    Since `-1 \le \cos(x) \le 1` for real `x`, the inverse cosine is real-valued only for `-1 \le x \le 1`, where it is a monotonically decreasing function assuming values between `+\pi` and `0`.

    

    |04a_TestAcos_re| `\quad` |04b_TestAcos_im| `\quad` |04c_TestAcos_abs|

    .. |04a_TestAcos_re| image:: ../_static/ExplicitSurfaces/CplxTrig/04a_TestAcos_re.3D.xml.jpg
       :width: 30 %

    .. |04b_TestAcos_im| image:: ../_static/ExplicitSurfaces/CplxTrig/04b_TestAcos_im.3D.xml.jpg
       :width: 30 %

    .. |04c_TestAcos_abs| image:: ../_static/ExplicitSurfaces/CplxTrig/04c_TestAcos_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.


    

    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.acos(x)))
            fpm:  1.0471975511966
            mpm:  1.04719755119659774615421446109316762806572313312503527365831486410260546876206966620934494
            dpm:  1.04719755119659774615421446109316762806572313312503527365831486410260546876206966620934494
            ipm: [1.0471975511965977461542144610931676280657231331250352736583148641026054687620696662093449415345,
                  1.0471975511965977461542144610931676280657231331250352736583148641026054687620696662093449420254]
            gpm:  1.0471975511965977461542144610931676280657231331250352736583148641026054687620696662093449418
            apm: [1.04719755119659774615421446109316762806572313312503527365831486410260546876206966620934494 +/- 2.37e-90]
         math53:  1.0471975511966
          sreal:  1.047198
          dreal:  1.0471975511966
          ereal:  1.0471975511965977461
          qreal:  1.04719755119659774615421446109317
          oreal:  1.0471975511965977461542144610931676280657231331250352736583148641026055
          mreal:  1.04719755119659774615421446109316762806572313312503527365831486410260546876206966620934494
         sflint:  1.047198
         dflint:  1.0471975511966
         eflint:  1.0471975511965977461
         qflint:  1.04719755119659774615421446109317
         oflint:  1.0471975511965977461542144610931676280657231331250352736583148641026055
         mflint:  1.04719755119659774615421446109316762806572313312503527365831486410260546876206966620934494
         aflint: [1.04719755119659774615421446109316762806572313312503527365831486410260546876206966620934494 +/- 3.63e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.acos(x)))
            fpm:  (2.76209763080717, -2.3877960445782)
            mpm:  (2.7620976308071662874576003890536432967138753900203, -2.3877960445782021699561212768720476189495083854716)
        cmath53:  (2.76209763080717, -2.3877960445782)
          qcplx:  (2.76209763080716628745760038905364, -2.38779604457820216995612127687205)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.acos(x))))
            fpm:  2.76209763080717
            mpm:  2.76209763080716628745760038905364329671387539002026442400503519922807327262927038354156898
            dpm:  2.76209763080716628745760038905364329671387539002026442400503519922807327262927038354156898
            ipm: [2.7620976308071662874576003890536432967138753900202644240050351992280732726292703835415689603367,
                  2.7620976308071662874576003890536432967138753900202644240050351992280732726292703835415689922458]
            gpm:  2.7620976308071662874576003890536432967138753900202644240050351992280732726292703835415689765
            apm: [2.7620976308071662874576003890536432967138753900202644240050351992280732726292703835415690 +/- 5.09e-89]
        cmath53:  2.76209763080717
          scplx:  2.762098
          dcplx:  2.76209763080717
          ecplx:  2.7620976308071662876
          qcplx:  2.76209763080716628745760038905364
          ocplx:  2.7620976308071662874826831771169849568316620254219182090742035280741651
          mcplx:  2.76209763080716628745760038905364329671387539002026442400503519922807327262927038354156898
        sflintc:  2.762098
        dflintc:  2.76209763080717
        eflintc:  2.7620976308071662874
        qflintc:  2.76209763080716628745760038905364
        oflintc:  2.7620976308071662874576003890536432967138753900202644240050351992280733
        mflintc:  2.76209763080716628745760038905364329671387539002026442400503519922807327262927038354156898
        aflintc: [2.7620976308071662874576003890536432967138753900202644240050351992280732726292703835415690 +/- 7.98e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.acos(x))))
            fpm:  -2.3877960445782
            mpm:  -2.38779604457820216995612127687204761894950838547156210189345318461152736761261505266094818
            dpm:  -2.38779604457820216995612127687204761894950838547156210189345318461152736761261505266094818
            ipm: [-2.3877960445782021699561212768720476189495083854715621018934531846115273676126150526609481963779,
                  -2.387796044578202169956121276872047618949508385471562101893453184611527367612615052660948158087]
            gpm:  -2.3877960445782021699561212768720476189495083854715621018934531846115273676126150526609481767
            apm: [-2.3877960445782021699561212768720476189495083854715621018934531846115273676126150526609482 +/- 6.84e-89]
        cmath53:  -2.3877960445782
          scplx:  -2.387796
          dcplx:  -2.3877960445782
          ecplx:  -2.3877960445782021701
          qcplx:  -2.38779604457820216995612127687205
          ocplx:  -2.3877960445782021699561212768720476189495083854715621018934531846115271
          mcplx:  -2.38779604457820216995612127687204761894950838547156210189345318461152736761261505266094818
        sflintc:  -2.387796
        dflintc:  -2.3877960445782
        eflintc:  -2.3877960445782021699
        qflintc:  -2.38779604457820216995612127687205
        oflintc:  -2.3877960445782021699561212768720476189495083854715621018934531846115274
        mflintc:  -2.38779604457820216995612127687204761894950838547156210189345318461152736761261505266094818
        aflintc: [-2.387796044578202169956121276872047618949508385471562101893453184611527367612615052660948 +/- 2.50e-88]










Inverse tangent, `\mathrm{atan}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.atan(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns the inverse tangent of `x`, `\mathrm{atan}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun53`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.15), Flint :cite:p:`FlintFun50`, Flint :cite:p:`FlintFun51`, Mpmath :cite:p:`MpmathFun53`.

    The inverse tangent can be defined as `\displaystyle \mathrm{atan}(x) = \int_0^x \frac{1}{t^2+1} \mathrm{d}t`. This is a real-valued function for all real `x`, with range `(-\pi/2, \pi/2)`. We have `\tan(\mathrm{atan}(x)) = x` for all `x`, but
    `\mathrm{atan}(\tan(x)) = x` only for `-\pi/2 < x < \pi/2`.


    The inverse tangent can be expressed in terms of related functions (with the principal-branch log and square root):

    .. math :: \mathrm{atan}(z) = \frac{i}{2}\left(\log(1-iz)-\log(1+iz)\right)

    The inverse tangent has two branch points: `x = \pm i`.The branch cuts are placed along the line segments `(-i \infty, -i)` and `(+i, +i \infty)`. 

    

    |06a_TestAtan_re| `\quad` |06b_TestAtan_im| `\quad` |06c_TestAtan_abs|

    .. |06a_TestAtan_re| image:: ../_static/ExplicitSurfaces/CplxTrig/06a_TestAtan_re.3D.xml.jpg
       :width: 30 %

    .. |06b_TestAtan_im| image:: ../_static/ExplicitSurfaces/CplxTrig/06b_TestAtan_im.3D.xml.jpg
       :width: 30 %

    .. |06c_TestAtan_abs| image:: ../_static/ExplicitSurfaces/CplxTrig/06c_TestAtan_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.




    

    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.atan(x)))
            fpm:  -1.37717433393895
            mpm:  -1.37717433393895123711452991735723439631999570427166494986510785941035068110178031204564014
            dpm:  -1.37717433393895123711452991735723439631999570427166494986510785941035068110178031204564014
            ipm: [-1.3771743339389512371145299173572343963199957042716649498651078594103506811017803120456401413474,
                  -1.3771743339389512371145299173572343963199957042716649498651078594103506811017803120456401411019]
            gpm:  -1.3771743339389512371145299173572343963199957042716649498651078594103506811017803120456401413
            apm: [-1.37717433393895123711452991735723439631999570427166494986510785941035068110178031204564014 +/- 1.39e-90]
         math53:  -1.37717433393895
          sreal:  -1.377174
          dreal:  -1.37717433393895
          ereal:  -1.3771743339389512372
          qreal:  -1.37717433393895123711452991735723
          oreal:  -1.3771743339389512371145299173572343963199957042716649498651078594103507
          mreal:  -1.37717433393895123711452991735723439631999570427166494986510785941035068110178031204564014
         sflint:  -1.377174
         dflint:  -1.37717433393895
         eflint:  -1.3771743339389512372
         qflint:  -1.37717433393895123711452991735723
         oflint:  -1.3771743339389512371145299173572343963199957042716649498651078594103507
         mflint:  -1.37717433393895123711452991735723439631999570427166494986510785941035068110178031204564014
         aflint: [-1.37717433393895123711452991735723439631999570427166494986510785941035068110178031204564014 +/- 1.38e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.atan(x)))
            fpm:  (-1.40174528959347, 0.0648566417905125)
            mpm:  (-1.4017452895934665144846819019147736665947537418285, 0.06485664179051252554472654475180858140223527545368)
        cmath53:  (-1.40174528959347, 0.0648566417905124)
          qcplx:  (-1.40174528959346651448468190191477, 0.0648566417905125255447265447518086)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.atan(x))))
            fpm:  -1.40174528959347
            mpm:  -1.40174528959346651448468190191477366659475374182854393550257091498150492441698232369370692
            dpm:  -1.40174528959346651448468190191477366659475374182854393550257091498150492441698232369370692
            ipm: [-1.4017452895934665144846819019147736665947537418285439355025709149815049244169823236937069231902,
                  -1.4017452895934665144846819019147736665947537418285439355025709149815049244169823236937069226993]
            gpm:  -1.4017452895934665144846819019147736665947537418285439355025709149815049244169823236937069229
            apm: [-1.40174528959346651448468190191477366659475374182854393550257091498150492441698232369370692 +/- 3.56e-90]
        cmath53:  -1.40174528959347
          scplx:  -1.401745
          dcplx:  -1.40174528959347
          ecplx:  -1.4017452895934665144
          qcplx:  -1.40174528959346651448468190191477
          ocplx:  -1.4017452895934665144846819019147736665947537418285439355025709149815049
          mcplx:  -1.40174528959346651448468190191477366659475374182854393550257091498150492441698232369370692
        sflintc:  -1.401745
        dflintc:  -1.40174528959347
        eflintc:  -1.4017452895934665145
        qflintc:  -1.40174528959346651448468190191477
        oflintc:  -1.4017452895934665144846819019147736665947537418285439355025709149815049
        mflintc:  -1.40174528959346651448468190191477366659475374182854393550257091498150492441698232369370692
        aflintc: [-1.40174528959346651448468190191477366659475374182854393550257091498150492441698232369370692 +/- 4.54e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.atan(x))))
            fpm:  0.0648566417905125
            mpm:  0.0648566417905125255447265447518085814022352754536797170766419766175619321953305536983513479
            dpm:  0.0648566417905125255447265447518085814022352754536797170766419766175619321953305536983513479
            ipm: [0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351347840685,
                  0.06485664179051252554472654475180858140223527545367971707664197661756193219533055369835134808614]
            gpm:  0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351347948
            apm: [0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351348 +/- 7.17e-91]
        cmath53:  0.0648566417905124
          scplx:  0.06485665
          dcplx:  0.0648566417905124
          ecplx:  0.064856641790512525533
          qcplx:  0.0648566417905125255447265447518086
          ocplx:  0.064856641790512525544726544751808581402235275453679717076641976617561931
          mcplx:  0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351348
        sflintc:  0.06485664
        dflintc:  0.0648566417905125
        eflintc:  0.064856641790512525547
        qflintc:  0.0648566417905125255447265447518086
        oflintc:  0.064856641790512525544726544751808581402235275453679717076641976617561933
        mflintc:  0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351348
        aflintc: [0.06485664179051252554472654475180858140223527545367971707664197661756193219533055369835135 +/- 5.09e-90]









Inverse tangent, 2 arguments, `\mathrm{atan2}(y, x)`
-------------------------------------------------------------------------------

.. method:: ctx.atan2(y, x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns the inverse tangent of `x` and `y`. See also  Wikipedia :cite:p:`WikipediaFun119`, MathWorld :cite:p:`WolframFun53`, Flint :cite:p:`FlintFun50`, Flint :cite:p:`FlintFun51`,  Mpmath :cite:p:`MpmathFun119`.

    Computes the two-argument arctangent, `\mathrm{atan2}(y, x)`, giving the signed angle between the positive `x`-axis and the point `(x, y)` in the 2D plane. This function is defined for real `x` and `y` only.

    The two-argument arctangent essentially computes `\mathrm{atan}(y/x)`, but accounts for the signs of both `x` and `y` to give the angle for the correct quadrant. 


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> y = 5.1; x = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.atan2(y, x)))
            fpm:  1.08389709498363
            mpm:  1.08389709498362753153953709483645410050050210405221744334334986632744865312977482202908971
            dpm:  1.08389709498362758755078878763714666907944274366486890003663480678600630355748881348272185
            ipm: [1.0838970949836275315395370948364541005005021040522174433433498663274486531297748220290897123973,
                  1.0838970949836275315395370948364541005005021040522174433433498663274486531297748220290897126428]
            gpm:  1.0838970949836275315395370948364541005005021040522174433433498663274486531297748220290897126
            apm: [1.08389709498362758755078878763714666907944274366486890003663480678600630355748881348272185 +/- 2.75e-90]
         math53:  1.08389709498363
          sreal:  1.083897
          dreal:  1.08389709498363
          ereal:  1.0838970949836275875
          qreal:  1.08389709498362758755078878763715
          oreal:  1.0838970949836275875507887876371466690794427436648689000366348067860063
          mreal:  1.08389709498362758755078878763714666907944274366486890003663480678600630355748881348272185
         sflint:  1.083897
         dflint:  1.08389709498363
         eflint:  1.0838970949836275875
         qflint:  1.08389709498362758755078878763715
         oflint:  1.0838970949836275875507887876371466690794427436648689000366348067860063
         mflint:  1.08389709498362758755078878763714666907944274366486890003663480678600630355748881348272185
         aflint: [1.08389709498362758755078878763714666907944274366486890003663480678600630355748881348272185 +/- 3.12e-90]








Inverse cotangent, `\mathrm{acot}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.acot(x)


    Returns the inverse cotangent of `x`, `\mathrm{acot}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun56`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.5).

    

    |12a_TestAcot_re| `\quad` |12b_TestAcot_im| `\quad` |12c_TestAcot_abs|

    .. |12a_TestAcot_re| image:: ../_static/ExplicitSurfaces/CplxTrig/12a_TestAcot_re.3D.xml.jpg
       :width: 30 %

    .. |12b_TestAcot_im| image:: ../_static/ExplicitSurfaces/CplxTrig/12b_TestAcot_im.3D.xml.jpg
       :width: 30 %

    .. |12c_TestAcot_abs| image:: ../_static/ExplicitSurfaces/CplxTrig/12c_TestAcot_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.





    The inverse cotangent can be expressed in terms of the inverse tangent as `\displaystyle \mathrm{acot}(x) =  \mathrm{atan}\left(\frac{1}{x} \right)`. This is a real-valued function for all real `x`, with range `(0, \pi)`.


    The inverse cotangent can be expressed in terms of related functions (with the principal-branch log and square root):
    
    .. math :: \mathrm{acot}(z) =  \frac{i}{2} \left[ \log \left(1 - \frac{i}{z} \right) -  \log \left(1 + \frac{i}{z} \right) \right]= \mathrm{atan}\left(\frac{1}{z}\right)

    

    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> or ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.acot(x)))
            fpm:  -0.193621992855945
            mpm:  -0.193621992855945382116791774282517045778588995415887960622364436743557522041324187268377271
            dpm:  -0.193621992855945382116791774282517045778588995415887960622364436743557522041324187268377271
            ipm: [-0.19362199285594538211679177428251704577858899541588796062236443674355752204132418726837727144526,
                  -0.19362199285594538211679177428251704577858899541588796062236443674355752204132418726837727132253]
            gpm:  -0.19362199285594538211679177428251704577858899541588796062236443674355752204132418726837727135
            apm: [-0.193621992855945382116791774282517045778588995415887960622364436743557522041324187268377271 +/- 4.81e-91]
         math53:  -0.193621992855945
          sreal:  -0.193622
          dreal:  -0.193621992855945
          ereal:  -0.19362199285594538211
          qreal:  -0.193621992855945382116791774282517
          oreal:  -0.19362199285594538211679177428251704577858899541588796062236443674355752
          mreal:  -0.193621992855945382116791774282517045778588995415887960622364436743557522041324187268377271
         sflint:  -0.193622
         dflint:  -0.193621992855945
         eflint:  -0.19362199285594538211
         qflint:  -0.193621992855945382116791774282517
         oflint:  -0.19362199285594538211679177428251704577858899541588796062236443674355752
         mflint:  -0.193621992855945382116791774282517045778588995415887960622364436743557522041324187268377271
         aflint: [-0.193621992855945382116791774282517045778588995415887960622364436743557522041324187268377271 +/- 4.71e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.acot(x)))
            fpm:  (-0.16905103720143, -0.0648566417905125)
            mpm:  (-0.16905103720143010474663978972497777550383095785901, -0.06485664179051252554472654475180858140223527545368)
        cmath53:  (-0.16905103720143, -0.0648566417905126)
          qcplx:  (-0.169051037201430104746639789724978, -0.0648566417905125255447265447518086)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.acot(x))))
            fpm:  -0.16905103720143
            mpm:  -0.16905103720143010474663978972497777550383095785900897498490138117240327872612217562031049
            dpm:  -0.16905103720143010474663978972497777550383095785900897498490138117240327872612217562031049
            ipm: [-0.1690510372014301047466397897249777755038309578590089749849013811724032787261221756203104898479,
                  -0.16905103720143010474663978972497777550383095785900897498490138117240327872612217562031048969449]
            gpm:  -0.16905103720143010474663978972497777550383095785900897498490138117240327872612217562031048976
            apm: [-0.169051037201430104746639789724977775503830957859008974984901381172403278726122175620310490 +/- 5.54e-91]
        cmath53:  -0.16905103720143
          scplx:  -0.169051
          dcplx:  -0.16905103720143
          ecplx:  -0.16905103720143010475
          qcplx:  -0.169051037201430104746639789724978
          ocplx:  -0.16905103720143010474663978972497777550383095785900897498490138117240328
          mcplx:  -0.16905103720143010474663978972497777550383095785900897498490138117240327872612217562031049
        sflintc:  -0.169051
        dflintc:  -0.16905103720143
        eflintc:  -0.16905103720143010475
        qflintc:  -0.169051037201430104746639789724978
        oflintc:  -0.16905103720143010474663978972497777550383095785900897498490138117240328
        mflintc:  -0.16905103720143010474663978972497777550383095785900897498490138117240327872612217562031049
        aflintc: [-0.16905103720143010474663978972497777550383095785900897498490138117240327872612217562031049 +/- 1.53e-90]
        8.22e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.acot(x))))
            fpm:  -0.0648566417905125
            mpm:  -0.0648566417905125255447265447518085814022352754536797170766419766175619321953305536983513479
            dpm:  -0.0648566417905125255447265447518085814022352754536797170766419766175619321953305536983513479
            ipm: [-0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351348009435,
                  -0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351347794662]
            gpm:  -0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351347948
            apm: [-0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351348 +/- 2.70e-91]
        cmath53:  -0.0648566417905126
          scplx:  -0.06485662
          dcplx:  -0.0648566417905125
          ecplx:  -0.06485664179051252556
          qcplx:  -0.0648566417905125255447265447518086
          ocplx:  -0.064856641790512525544726544751808581402235275453679717076641976617561939
          mcplx:  -0.0648566417905125255447265447518085814022352754536797170766419766175619321953305536983513479
        sflintc:  -0.06485664
        dflintc:  -0.0648566417905125
        eflintc:  -0.064856641790512525547
        qflintc:  -0.0648566417905125255447265447518086
        oflintc:  -0.064856641790512525544726544751808581402235275453679717076641976617561933
        mflintc:  -0.0648566417905125255447265447518085814022352754536797170766419766175619321953305536983513479
        aflintc: [-0.064856641790512525544726544751808581402235275453679717076641976617561932195330553698351348 +/- 9.19e-91]










Inverse cosecant, `\mathrm{acsc}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.acsc(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns the inverse cosecant of `x`, `\mathrm{acsc}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun55`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.9), Mpmath :cite:p:`MpmathFun55`.

    The inverse cosecant can be expressed in terms of the inverse sine as `\displaystyle \mathrm{acsc}(x) = \mathrm{asin}\left(\frac{1}{x} \right)`.  The domain is `\displaystyle \mathbb {R} \setminus (-1,1)`, i.e. `|x|>0`. 


    The inverse cosecant can be expressed in terms of related functions (with the principal-branch log and square root):

    .. math :: \mathrm{acsc}(z) = -i \log \left( \sqrt{1-\frac{1}{z^2}} + \frac{i}{z} \right) = \mathrm{asin}\left(\frac{1}{z}\right)

    

    |10a_TestAcsc_re| `\quad` |10b_TestAcsc_im| `\quad` |10c_TestAcsc_abs|

    .. |10a_TestAcsc_re| image:: ../_static/ExplicitSurfaces/CplxTrig/10a_TestAcsc_re.3D.xml.jpg
       :width: 30 %

    .. |10b_TestAcsc_im| image:: ../_static/ExplicitSurfaces/CplxTrig/10b_TestAcsc_im.3D.xml.jpg
       :width: 30 %

    .. |10c_TestAcsc_abs| image:: ../_static/ExplicitSurfaces/CplxTrig/10c_TestAcsc_abs.3D.xml.jpg
       :width: 30 %

   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.


    

    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in ctxlistreal: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sin(x)))
            fpm:  -0.197357109550372
            mpm:  -0.197357109550372065893789686962141884141473808557824839492732966280377489304430681652313645
            dpm:  -0.197357109550372065893789686962141884141473808557824839492732966280377489304430681652313645
            ipm: [-0.19735710955037206589378968696214188414147380855782483949273296628037748930443068165231364555354,
                  -0.19735710955037206589378968696214188414147380855782483949273296628037748930443068165231364540013]
            gpm:  -0.19735710955037206589378968696214188414147380855782483949273296628037748930443068165231364546
            apm: [-0.197357109550372065893789686962141884141473808557824839492732966280377489304430681652313645 +/- 6.51e-91]
         math53:  -0.197357109550372
          sreal:  -0.1973571
          dreal:  -0.197357109550372
          ereal:  -0.19735710955037206589
          qreal:  -0.197357109550372065893789686962142
          oreal:  -0.19735710955037206589378968696214188414147380855782483949273296628037749
          mreal:  -0.197357109550372065893789686962141884141473808557824839492732966280377489304430681652313645
         sflint:  -0.1973571
         dflint:  -0.197357109550372
         eflint:  -0.19735710955037206589
         qflint:  -0.197357109550372065893789686962142
         oflint:  -0.19735710955037206589378968696214188414147380855782483949273296628037749
         mflint:  -0.197357109550372065893789686962141884141473808557824839492732966280377489304430681652313645
         aflint: [-0.197357109550372065893789686962141884141473808557824839492732966280377489304430681652313645 +/- 7.56e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.acsc(x)))
            fpm:  (-0.170379238366547, -0.067572171292378)
            mpm:  (-0.17037923836654687019105383528103117410866341554603, -0.067572171292377961289703980926987705875074592221143)
        cmath53:  (-0.170379238366547, -0.067572171292378)
          qcplx:  (-0.170379238366546870191053835281031, -0.0675721712923779612897039809269877)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.acsc(x))))
            fpm:  -0.170379238366547
            mpm:  -0.170379238366546870191053835281031174108663415546033067117477087880965076425635005191518965
            dpm:  -0.170379238366546870191053835281031174108663415546033067117477087880965076425635005191518965
            ipm: [-0.17037923836654687019105383528103117410866341554603306711747708788096507642563500519151896477641,
                  -0.17037923836654687019105383528103117410866341554603306711747708788096507642563500519151896453096]
            gpm:  -0.17037923836654687019105383528103117410866341554603306711747708788096507642563500519151896465
            apm: [-0.170379238366546870191053835281031174108663415546033067117477087880965076425635005191518965 +/- 6.19e-91]
        cmath53:  -0.170379238366547
          scplx:  -0.1703792
          dcplx:  -0.170379238366547
          ecplx:  -0.1703792383665468702
          qcplx:  -0.170379238366546870191053835281031
          ocplx:  -0.17037923836654687019105383528103117410866341554603306711747708788096508
          mcplx:  -0.170379238366546870191053835281031174108663415546033067117477087880965076425635005191518965
        sflintc:  -0.1703792
        dflintc:  -0.170379238366547
        eflintc:  -0.1703792383665468702
        qflintc:  -0.170379238366546870191053835281031
        oflintc:  -0.17037923836654687019105383528103117410866341554603306711747708788096508
        mflintc:  -0.170379238366546870191053835281031174108663415546033067117477087880965076425635005191518965
        aflintc: [-0.17037923836654687019105383528103117410866341554603306711747708788096507642563500519151896 +/- 5.49e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.acsc(x))))
            fpm:  -0.067572171292378
            mpm:  -0.0675721712923779612897039809269877058750745922211429785685607278428359543578990242870985657
            dpm:  -0.0675721712923779612897039809269877058750745922211429785685607278428359543578990242870985657
            ipm: [-0.067572171292377961289703980926987705875074592221142978568560727842835954357899024287098565986466,
                  -0.067572171292377961289703980926987705875074592221142978568560727842835954357899024287098565495556]
            gpm:  -0.06757217129237796128970398092698770587507459222114297856856072784283595435789902428709856568
            apm: [-0.06757217129237796128970398092698770587507459222114297856856072784283595435789902428709857 +/- 5.03e-90]
        cmath53:  -0.067572171292378
          scplx:  -0.06757224
          dcplx:  -0.0675721712923778
          ecplx:  -0.067572171292377961204
          qcplx:  -0.0675721712923779612897039809269877
          ocplx:  -0.067572171292377961289703980926987705875074592221142978568560727842835949
          mcplx:  -0.067572171292377961289703980926987705875074592221142978568560727842835954357899024287098565
        sflintc:  -0.06757218
        dflintc:  -0.067572171292378
        eflintc:  -0.067572171292377961292
        qflintc:  -0.0675721712923779612897039809269877
        oflintc:  -0.067572171292377961289703980926987705875074592221142978568560727842835955
        mflintc:  -0.067572171292377961289703980926987705875074592221142978568560727842835954357899024287098565
        aflintc: [-0.06757217129237796128970398092698770587507459222114297856856072784283595435789902428709856 +/- 6.92e-90]








Inverse secant, `\mathrm{asec}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.asec(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.


    Returns the inverse secant of `x`, `\mathrm{asec}(x)`. See also  Wikipedia :cite:p:`WikipediaFun50`,  MathWorld :cite:p:`WolframFun54`,  NIST :cite:p:`DLMFun50`, :cite:t:`Ehrhardt2018` (4.2.11), Mpmath :cite:p:`MpmathFun54`.

    The inverse secant can be expressed in terms of the inverse cosine as `\displaystyle \mathrm{asec}(x) = \mathrm{acos}\left(\frac{1}{x} \right)`. The domain is `\displaystyle \mathbb {R} \setminus (-1,1)`, i.e. `|x|>0`. 


    The inverse secant can be expressed in terms of related functions (with the principal-branch log and square root):

    .. math :: \mathrm{asec}(z) = -i \log \left( \sqrt{\frac{1}{z^2}-1} + \frac{1}{z} \right) = \mathrm{acos}\left(\frac{1}{z}\right)

    

    |08a_TestAsec_re| `\quad` |08b_TestAsec_im| `\quad` |08c_TestAsec_abs|

    .. |08a_TestAsec_re| image:: ../_static/ExplicitSurfaces/CplxTrig/08a_TestAsec_re.3D.xml.jpg
       :width: 30 %

    .. |08b_TestAsec_im| image:: ../_static/ExplicitSurfaces/CplxTrig/08b_TestAsec_im.3D.xml.jpg
       :width: 30 %

    .. |08c_TestAsec_abs| image:: ../_static/ExplicitSurfaces/CplxTrig/08c_TestAsec_abs.3D.xml.jpg
       :width: 30 %


   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.



    

    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.asec(x)))
            fpm:  1.76815343634527
            mpm:  1.76815343634526868512511137860189332624005850824537774998020526243428569244753518096633106
            dpm:  1.76815343634526868512511137860189332624005850824537774998020526243428569244753518096633106
            ipm: [1.7681534363452686851251113786018933262400585082453777499802052624342856924475351809663310580393,
                  1.7681534363452686851251113786018933262400585082453777499802052624342856924475351809663310582848]
            gpm:  1.768153436345268685125111378601893326240058508245377749980205262434285692447535180966331058
            apm: [1.76815343634526868512511137860189332624005850824537774998020526243428569244753518096633106 +/- 2.52e-90]
         math53:  1.76815343634527
          sreal:  1.768153
          dreal:  1.76815343634527
          ereal:  1.7681534363452686852
          qreal:  1.76815343634526868512511137860189
          oreal:  1.7681534363452686851251113786018933262400585082453777499802052624342857
          mreal:  1.76815343634526868512511137860189332624005850824537774998020526243428569244753518096633106
         sflint:  1.768153
         dflint:  1.76815343634527
         eflint:  1.7681534363452686852
         qflint:  1.76815343634526868512511137860189
         oflint:  1.7681534363452686851251113786018933262400585082453777499802052624342857
         mflint:  1.76815343634526868512511137860189332624005850824537774998020526243428569244753518096633106
         aflint: [1.76815343634526868512511137860189332624005850824537774998020526243428569244753518096633106 +/- 5.30e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.asec(x)))
            fpm:  (1.74117556516144, 0.067572171292378)
            mpm:  (1.7411755651614434894223755269207826162072481152336, 0.067572171292377961289703980926987705875074592221143)
        cmath53:  (1.74117556516144, 0.067572171292378)
          qcplx:  (1.74117556516144348942237552692078, 0.0675721712923779612897039809269877)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.asec(x))))
            fpm:  1.74117556516144
            mpm:  1.74117556516144348942237552692078261620724811523358597760494938403487327956873950450553638
            dpm:  1.74117556516144348942237552692078261620724811523358597760494938403487327956873950450553638
            ipm: [1.7411755651614434894223755269207826162072481152335859776049493840348732795687395045055363770474,
                  1.7411755651614434894223755269207826162072481152335859776049493840348732795687395045055363775384]
            gpm:  1.7411755651614434894223755269207826162072481152335859776049493840348732795687395045055363773
            apm: [1.74117556516144348942237552692078261620724811523358597760494938403487327956873950450553638 +/- 3.35e-90]
        cmath53:  1.74117556516144
          scplx:  1.741176
          dcplx:  1.74117556516144
          ecplx:  1.7411755651614434895
          qcplx:  1.74117556516144348942237552692078
          ocplx:  1.7411755651614434894474583149841242763250347506352397626741177128809651
          mcplx:  1.74117556516144348942237552692078261620724811523358597760494938403487327956873950450553638
        sflintc:  1.741176
        dflintc:  1.74117556516144
        eflintc:  1.7411755651614434894
        qflintc:  1.74117556516144348942237552692078
        oflintc:  1.7411755651614434894223755269207826162072481152335859776049493840348733
        mflintc:  1.74117556516144348942237552692078261620724811523358597760494938403487327956873950450553638
        aflintc: [1.74117556516144348942237552692078261620724811523358597760494938403487327956873950450553638 +/- 5.53e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.asec(x))))
            fpm:  0.067572171292378
            mpm:  0.0675721712923779612897039809269877058750745922211429785685607278428359543578990242870985657
            dpm:  0.0675721712923779612897039809269877058750745922211429785685607278428359543578990242870985657
            ipm: [0.067572171292377961289703980926987705875074592221142978568560727842835954357899024287098565495556,
                  0.067572171292377961289703980926987705875074592221142978568560727842835954357899024287098565986466]
            gpm:  0.06757217129237796128970398092698770587507459222114297856856072784283595435789902428709856568
            apm: [0.06757217129237796128970398092698770587507459222114297856856072784283595435789902428709857 +/- 5.03e-90]
        cmath53:  0.067572171292378
          scplx:  0.06757224
          dcplx:  0.0675721712923782
          ecplx:  0.067572171292377961204
          qcplx:  0.0675721712923779612897039809269877
          ocplx:  0.067572171292377961289703980926987705875074592221142978568560727842835949
          mcplx:  0.067572171292377961289703980926987705875074592221142978568560727842835954357899024287098565
        sflintc:  0.06757218
        dflintc:  0.067572171292378
        eflintc:  0.067572171292377961292
        qflintc:  0.0675721712923779612897039809269877
        oflintc:  0.067572171292377961289703980926987705875074592221142978568560727842835955
        mflintc:  0.067572171292377961289703980926987705875074592221142978568560727842835954357899024287098565
        aflintc: [0.06757217129237796128970398092698770587507459222114297856856072784283595435789902428709856 +/- 6.92e-90]







