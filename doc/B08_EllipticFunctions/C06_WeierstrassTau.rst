

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Weierstrass elliptic functions, in terms of elliptic period ratio `\tau`
=======================================================================================================


.. _rst_mpm_wpg_by_tau: 

Weierstrass function `\wp(z| \tau)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_p_t(z, tau)


    Computes Weierstrass's elliptic function in terms of half-period `\omega_1` and elliptic period ratio `\tau`. 

    We have `\wp(tz| t \omega, \tau) = t^{-2} \wp(z| \omega, \tau)`.

    See also MathWorld :cite:p:`WolframFun190`, Flint :cite:p:`FlintFun190`.


    See also: https://dlmf.nist.gov/23.2


    .. math :: \wp(z, \tau, \omega=1) = \frac{1}{z^2} + \sum_{n^2+m^2 \ne 0}  \left[ \frac{1}{(z+m+n\tau)^2} - \frac{1}{(m+n\tau)^2} \right]

    which satisfies `\wp(z, \tau, \omega=1) = \wp(z + 1, \tau, \omega=1) = \wp(z + \tau, \tau, \omega=1)`. To evaluate the function efficiently, we use the formula (with with `q = e^{\pi i \tau}`)


    .. math :: \wp(z, \tau) = \pi^3 \theta_2^2(0,q) \theta_3^2(0,q)  \frac{\theta_4^2(\pi z,q)}{\theta_1^2(\pi z,q)} - \frac{\pi^3}{3} \left[ \theta_2^4(0,q) + \theta_3^4(0,q)\right].



    .. math :: \wp(tz| t \omega_1, t \omega_2) = t^{-2} \wp(z| \omega_1, \omega_2)




    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.weierstrass_p_t(x, tau)))
            fpm:  (-7.2543494503698, -0.131922508660363)
            mpm:  (-7.254349450369797280072152621242700239356, -0.131922508660363125611061408823267684624)
        cmath53:  (-7.25434945036978, -0.13192250866036)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.weierstrass_p_t(x, tau))))
            fpm:  -7.2543494503698
            mpm:  -7.25434945036979728007215262124270023935688016437392781746239599266690022627124751019982783
            dpm:  -7.25434945036979728007215262124270023935688016437392781746239599266690022627124751019982783
            gpm:  -7.2543494503697972800721526212427002393568801643739278174623959926669002262712475101998278298
            apm: [-7.25434945036979728007215262124270023935688016437392781746239599266690022627124751019983 +/- 3.45e-87]
        cmath53:  -7.25434945036978
        sflintc:  -7.254347
        dflintc:  -7.2543494503698
        eflintc:  -7.2543494503697972778
        qflintc:  -7.2543494503697972800721526212427
        oflintc:  -7.2543494503697972800721526212427002393568801643739278174623959926669003
        mflintc:  -7.25434945036979728007215262124270023935688016437392781746239599266690022627124751019982765
        aflintc: [-7.25434945036979728007215262124270023935688016437392781746239599266690022627124751019983 +/- 6.51e-87]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.weierstrass_p_t(x, tau))))
            fpm:  -0.131922508660363
            mpm:  -0.131922508660363125611061408823267684624303607998590362391427636233079685872490471504434127
            dpm:  -0.131922508660363125611061408823267684624303607998590362391427636233079685872490471504434127
            gpm:  -0.13192250866036312561106140882326768462430360799859036239142763623307968587249047150443412699
            apm: [-0.13192250866036312561106140882326768462430360799859036239142763623307968587249047150443 +/- 5.35e-87]
        cmath53:  -0.13192250866036
        sflintc:  -0.1319214
        dflintc:  -0.131922508660365
        eflintc:  -0.13192250866036312458
        qflintc:  -0.131922508660363125611061408823269
        oflintc:  -0.13192250866036312561106140882326768462430360799859036239142763623307975
        mflintc:  -0.131922508660363125611061408823267684624303607998590362391427636233079685872490471504434119
        aflintc: [-0.13192250866036312561106140882326768462430360799859036239142763623307968587249047150443 +/- 8.14e-87]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C06_WeierstrassTau/D01_WeistrassPTauCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C06_WeierstrassTau/D01_Weierstrass_p_t.cs>`__. 












.. _rst_mpm_wpg_prime_by_tau: 

Weierstrass function, first derivative: `\wp'z| \tau)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_p_prime_t(z, tau)

    Computes the  first derivative of Weierstrass's elliptic function in terms of half-period `\omega_1` and elliptic period ratio `\tau`. 

    We have `\wp'(tz| t \omega, \tau) = t^{-3} \wp'(z| \omega, \tau)`.


    The Weierstrass elliptic function satisfies the differential equation `[\wp'(z, \tau)]^2 = 4 [\wp(z,\tau)]^3 - g_2 \wp(z,\tau) - g_3`. 

    .. math :: \wp'(z, \tau) =  \sqrt{ 4 [\wp(z,\tau)]^3 - g_2 \wp(z,\tau) - g_3 }.


    See also MathWorld :cite:p:`WolframFun191`, Flint :cite:p:`FlintFun190`.


    See also: https://dlmf.nist.gov/23.2


    

    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.weierstrass_pprime_t(x, tau)))
            fpm:  (0.992425539025143, 26.6634628200187)
            mpm:  (0.9924255390251424904848569744012269422898, 26.66346282001865720765329567001337977704)
        cmath53:  (0.99242553902508, 26.6634628200188)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.weierstrass_pprime_t(x, tau))))
            fpm:  0.992425539025143
            mpm:  0.992425539025142490484856974401226942286628664355608847314699843453258112576362442767381946
            dpm:  0.992425539025142490484856974401226942286628664355608847314699843453258112576362442767381946
            gpm:  0.99242553902514249048485697440122694228662866435560884731469984345325811257636244276738194599
            apm: [0.9924255390251424904848569744012269422866286643556088473146998434532581125763624427674 +/- 6.61e-86]
        cmath53:  0.99242553902508
        sflintc:  0.9924368
        dflintc:  0.992425539025129
        eflintc:  0.99242553902514250071
        qflintc:  0.992425539025142490484856974401215
        oflintc:  0.99242553902514249048485697440122694228662866435560884731469984345325752
        mflintc:  0.992425539025142490484856974401226942286628664355608847314699843453258112576362442767382033
        aflintc: [0.992425539025142490484856974401226942286628664355608847314699843453258112576362442767 +/- 5.42e-85]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.weierstrass_pprime_t(x, tau))))
            fpm:  26.6634628200187
            mpm:  26.6634628200186572076532956700133797770419023533543634138452759890185048373647300952880864
            dpm:  26.6634628200186572076532956700133797770419023533543634138452759890185048373647300952880864
            gpm:  26.663462820018657207653295670013379777041902353354363413845275989018504837364730095288086401
            apm: [26.6634628200186572076532956700133797770419023533543634138452759890185048373647300952881 +/- 6.21e-86]
        cmath53:  26.6634628200188
        sflintc:  26.66344
        dflintc:  26.6634628200187
        eflintc:  26.663462820018657187
        qflintc:  26.6634628200186572076532956700134
        oflintc:  26.663462820018657207653295670013379777041902353354363413845275989018506
        mflintc:  26.663462820018657207653295670013379777041902353354363413845275989018504837364730095288085
        aflintc: [26.663462820018657207653295670013379777041902353354363413845275989018504837364730095288 +/- 2.46e-85]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C06_WeierstrassTau/D02_WeistrassPprimeTauCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C06_WeierstrassTau/D02_Weierstrass_p_prime_t.cs>`__. 










.. _rst_mpm_wpg_inv_by_tau: 

Inverse Weierstrass function `\wp^{-1}(z| \tau)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_p_inv_t(z, tau)


    Computes the inverse of the Weierstrass elliptic function in terms of half-period `\omega_1` and elliptic period ratio `\tau`. It which satisfies `\wp(\wp^{-1}(z, \tau), \tau) = z`. This function is given  by the elliptic integral

    .. math :: \wp^{-1}(z, \tau) = \frac{1}{2} \int_z^{\infty} \frac{\mathrm{d}t}{\sqrt{(t-e_1)(t-e_2)(t-e_3)}}  = R_F(z-e_1,z-e_2,z-e_3).


    See also MathWorld :cite:p:`WolframFun192`, Flint :cite:p:`FlintFun190`.


    See also: https://dlmf.nist.gov/23.2


    

    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.weierstrass_pinv_t(x, tau)))
            fpm:  (0.408458464677131, -0.297575206941329)
            mpm:  (0.4084584646771311633210730690530960731275, -0.2975752069413288186194559922372487678026)
        cmath53:  (0.408458464677103, -0.297575206941308)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.weierstrass_pinv_t(x, tau))))
            fpm:  0.408458464677131
            mpm:  0.408458464677131163321073069053096073127551204694840874360168926360515659585568931558425682
            dpm:  0.408458464677131163321073069053096073127551204694840874360168926360515659585568931558425682
            gpm:  0.40845846467713116332107306905309607312755120469484087436016892636051565958556893155842568201
            apm: [0.40845846467713116332107306905309607312755120469484087436016892636051565958556893155843 +/- 6.50e-87]
        cmath53:  0.408458464677103
        sflintc:  0.4084585
        dflintc:  0.408458464677131
        eflintc:  0.40845846467713116333
        qflintc:  0.408458464677131163321073069053096
        oflintc:  0.40845846467713116332107306905309607312755120469484087436016892636051566
        mflintc:  0.408458464677131163321073069053096073127551204694840874360168926360515659585568931558425683
        aflintc: [0.4084584646771311633210730690530960731275512046948408743601689263605156595855689315584 +/- 3.37e-86]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.weierstrass_pinv_t(x, tau))))
            fpm:  -0.297575206941329
            mpm:  -0.297575206941328818619455992237248767802590833504130544485629345380549132990744265473296515
            dpm:  -0.297575206941328818619455992237248767802590833504130544485629345380549132990744265473296515
            gpm:  -0.29757520694132881861945599223724876780259083350413054448562934538054913299074426547329651502
            apm: [-0.29757520694132881861945599223724876780259083350413054448562934538054913299074426547330 +/- 4.82e-87]
        cmath53:  -0.297575206941308
        sflintc:  -0.2975752
        dflintc:  -0.297575206941329
        eflintc:  -0.29757520694132881862
        qflintc:  -0.297575206941328818619455992237249
        oflintc:  -0.29757520694132881861945599223724876780259083350413054448562934538054913
        mflintc:  -0.297575206941328818619455992237248767802590833504130544485629345380549132990744265473296515
        aflintc: [-0.29757520694132881861945599223724876780259083350413054448562934538054913299074426547330 +/- 8.37e-87]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C06_WeierstrassTau/D03_WeistrassPInvTauCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C06_WeierstrassTau/D03_Weierstrass_p_inv_t.cs>`__. 











.. _rst_mpm_weierstrass_zeta_by_tau: 

Weierstrass Zeta function `\zeta(z, \tau)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_zeta_t(z, tau)


    Computes the Weierstrass zeta function in terms of half-period `\omega_1` and elliptic period ratio `\tau`. 

    We have `\zeta(tz| t \omega, \tau) = t^{-1} \zeta(z| \omega, \tau)`.

    The function can be defined as

    .. math :: \zeta(z| \omega, \tau) = \frac{1}{z} + \sum_{n^2+m^2 \ne 0}  \left[ \frac{1}{z-m-n\tau} + \frac{1}{m+n\tau} + \frac{z}{(m+n\tau)^2} \right]

    and is quasiperiodic with `\zeta(z + 1| \omega, \tau) = \zeta(z| \omega, \tau) + \zeta(1/2| \omega, \tau)` and `\zeta(z + \tau| \omega, \tau) = \zeta(z| \omega, \tau) + \zeta(\tau/2| \omega, \tau)`.

    The function is related to `\wp(z| \omega, \tau)` by `\displaystyle \frac{d \zeta(z| \omega, \tau)}{\mathrm{d}z} = -\wp(z| \omega, \tau)` and `\displaystyle \zeta(z| \omega, \tau) - z^{-1} = \int_0^z \left(\wp(z| \omega, \tau) - z^{-2} \right)`.

    See also MathWorld :cite:p:`WolframFun194`, Flint :cite:p:`FlintFun190`.


    See also: https://dlmf.nist.gov/23.2



    To evaluate the function efficiently, we use the formula

    .. math :: \zeta(z| \omega, \tau) = \frac{\pi z}{3} \frac{\theta_1'''(0,q)}{\theta_1'(0,q)}   + \frac{\theta_1'(\pi z,q)}{\theta_1(\pi z,q)}

    

    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.weierstrass_zeta_t(x, tau)))
            fpm:  (3.98088971569181, -2.42206897334368)
            mpm:  (3.980889715691808342151541496199970266175, -2.422068973343679557790538434887960265993)
        cmath53:  (3.98088971569094, -2.42206897334536)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.weierstrass_zeta_t(x, tau))))
            fpm:  3.98088971569181
            mpm:  3.98088971569180834215154149619997026617514164120314092077263843965481693540841793490425065
            dpm:  3.98088971569180834215154149619997026617514164120314092077263843965481693540841793490425065
            gpm:  3.98088971569180834215154149619997026617514164120314092077263843965481693540841793490425065
            apm: [3.98088971569180834215154149619997026617514164120314092077263843965481693540841793490425 +/- 4.33e-87]
        cmath53:  3.98088971569094
        sflintc:  3.98089
        dflintc:  3.98088971569181
        eflintc:  3.9808897156918083425
        qflintc:  3.98088971569180834215154149619997
        oflintc:  3.9808897156918083421515414961999702661751416412031409207726384396548169
        mflintc:  3.98088971569180834215154149619997026617514164120314092077263843965481693540841793490425117
        aflintc: [3.9808897156918083421515414961999702661751416412031409207726384396548169354084179349043 +/- 5.73e-86]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.weierstrass_zeta_t(x, tau))))
            fpm:  -2.42206897334368
            mpm:  -2.4220689733436795577905384348879602659923578377926217327095984664562795228352572070712683
            dpm:  -2.4220689733436795577905384348879602659923578377926217327095984664562795228352572070712683
            gpm:  -2.4220689733436795577905384348879602659923578377926217327095984664562795228352572070712682999
            apm: [-2.42206897334367955779053843488796026599235783779262173270959846645627952283525720707127 +/- 4.76e-87]
        cmath53:  -2.42206897334536
        sflintc:  -2.422069
        dflintc:  -2.42206897334368
        eflintc:  -2.4220689733436795582
        qflintc:  -2.42206897334367955779053843488796
        oflintc:  -2.4220689733436795577905384348879602659923578377926217327095984664562795
        mflintc:  -2.42206897334367955779053843488796026599235783779262173270959846645627952283525720707126845
        aflintc: [-2.4220689733436795577905384348879602659923578377926217327095984664562795228352572070713 +/- 4.01e-86]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C06_WeierstrassTau/D04_WeistrassZetaTauCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C06_WeierstrassTau/D04_Weierstrass_zeta_t.cs>`__. 








.. _rst_mpm_weierstrass_sigma_by_tau: 

Weierstrass Sigma function `\sigma(z| \tau)`
-------------------------------------------------------------------------------


.. method:: ctx.weierstrass_sigma_t(z, omega, tau)


    Computes the Weierstrass sigma function in terms of half-period `\omega_1` and elliptic period ratio `\tau`. We have `\sigma(tz| t \omega, \tau) = t \sigma(z| \omega, \tau)`.


    See also MathWorld :cite:p:`WolframFun193`, Flint :cite:p:`FlintFun190`.


    See also: https://dlmf.nist.gov/23.2


    The function can be defined as

    .. math :: \sigma(z| \omega, \tau) = z \prod_{n^2+m^2 \ne 0}  \left[ \left(1-\frac{z}{m+n\tau}\right)  \exp\left(\frac{z}{m+n\tau} + \frac{z^2}{2(m+n\tau)^2} \right) \right]

    and is quasiperiodic with `\sigma(z + 1| \omega, \tau) = -e^{2 \zeta(1/2| \omega, \tau) (z+1/2)} \sigma(z| \omega, \tau)` and `\sigma(z + \tau| \omega, \tau) = -e^{2 \zeta(\tau/2| \omega, \tau) (z+\tau/2)} \sigma(z| \omega, \tau)`.



    The function is related to `\zeta(z| \omega, \tau)` by `\displaystyle \frac{d}{\mathrm{d}z} \log \sigma(z| \omega, \tau) = \zeta(z| \omega, \tau)`.


    See also MathWorld :cite:p:`WolframFun193`, Flint :cite:p:`FlintFun190`.


    To evaluate the function efficiently, we use the formula


    .. math :: \sigma(z, \tau) = \exp \left( -\frac{(\pi z)^2}{6}  \frac{\theta_1'''(0,q)}{\theta_1'(0,q)} \right)   \times \frac{\theta_1(\pi z,q)}{\theta_1'(\pi z,q)}



    

    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.weierstrass_sigma_t(x, tau)))
            fpm:  (-58.2289241875752, 186.450409191644)
            mpm:  (-58.22892418757515831369822982307070065278, 186.4504091916438864469475633005725545015)
        cmath53:  (-58.2289241872898, 186.450409191966)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.weierstrass_sigma_t(x, tau))))
            fpm:  -58.2289241875752
            mpm:  -58.228924187575158313698229823070700652788947392932149320847754676264872753603678004134255
            dpm:  -58.228924187575158313698229823070700652788947392932149320847754676264872753603678004134255
            gpm:  -58.228924187575158313698229823070700652788947392932149320847754676264872753603678004134254996
            apm: [-58.228924187575158313698229823070700652788947392932149320847754676264872753603678004134 +/- 6.30e-85]
        cmath53:  -58.2289241872898
        sflintc:  -58.2289
        dflintc:  -58.2289241875752
        eflintc:  -58.228924187575158294
        qflintc:  -58.2289241875751583136982298230707
        oflintc:  -58.228924187575158313698229823070700652788947392932149320847754676264874
        mflintc:  -58.2289241875751583136982298230707006527889473929321493208477546762648727536036780041343585
        aflintc: [-58.228924187575158313698229823070700652788947392932149320847754676264872753603678004134 +/- 6.86e-85]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 1.2+2j;  tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.weierstrass_sigma_t(x, tau))))
            fpm:  186.450409191644
            mpm:  186.45040919164388644694756330057255450146544108080848765958214622288239763490128271881774
            dpm:  186.45040919164388644694756330057255450146544108080848765958214622288239763490128271881774
            gpm:  186.45040919164388644694756330057255450146544108080848765958214622288239763490128271881774001
            apm: [186.450409191643886446947563300572554501465441080808487659582146222882397634901282718818 +/- 4.73e-85]
        cmath53:  186.450409191966
        sflintc:  186.4504
        dflintc:  186.450409191644
        eflintc:  186.45040919164388643
        qflintc:  186.450409191643886446947563300573
        oflintc:  186.4504091916438864469475633005725545014654410808084876595821462228824
        mflintc:  186.450409191643886446947563300572554501465441080808487659582146222882397634901282718817795
        aflintc: [186.450409191643886446947563300572554501465441080808487659582146222882397634901282718818 +/- 5.29e-85]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C06_WeierstrassTau/D05_WeistrassSigmaTauCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C06_WeierstrassTau/D05_Weierstrass_sigma_t.cs>`__. 





