

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />



   

|newpage|

Modular forms, in terms of half-period `\omega_1` and elliptic period ratio `\tau`
=======================================================================================================




.. _rst_mpm_dedekind_eta: 

Dedekind eta function `\eta(\tau)`
-------------------------------------------------------------------------------


.. method:: ctx.dedekind_eta(tau) 



    Returns Dedekind `\eta` in terms of elliptic period ratio `\tau`. . See also Flint :cite:p:`FlintFun270`, MathWorld :cite:p:`WolframFun270`, Mathworld, equation 20:

    .. math :: \eta(\tau) = \frac{\theta_2(\pi/6, \bar{q}^{1/6})}{\sqrt{3}}, \quad \text{where }  \bar{q} = q^2 = e^{2 i \pi \tau}.

    See also: https://dlmf.nist.gov/23.15#ii


    Returns the Dedekind eta function `\eta(ix)` for `x \ge 0`, with `\eta(x) = q^{1/24}(q)_{\infty}`, and `(q)_{\infty}` is is the q-Pochhammer Euler function.

    See also: MathWorld :cite:p:`WolframFun270`, :cite:t:`Ehrhardt2018` (3.2.17.10).




    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.dedekind_eta(tau)))
            fpm:  (0.729844359380083, 0.0188831925200341)
            mpm:  (0.7298443593800830054556820795289039369486, 0.01888319252003409970439576558626442052808)
        cmath53:  (0.729844359380083, 0.0188831925200341)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.dedekind_eta(tau))))
            fpm:  0.729844359380083
            mpm:  0.729844359380083005455682079528903936948641546143867465563109628101519787122062963401378976
            dpm:  0.729844359380083005455682079528903936948641546143867465563109628101519787122062963401378976
            gpm:  0.72984435938008300545568207952890393694864154614386746556310962810151978712206296340137897604
            apm: [0.729844359380083005455682079528903936948641546143867465563109628101519787122062963401378975 +/- 8.79e-91]
        cmath53:  0.729844359380083
        sflintc:  0.7298443
        dflintc:  0.729844359380083
        eflintc:  0.72984435938008300547
        qflintc:  0.729844359380083005455682079528904
        oflintc:  0.72984435938008300545568207952890393694864154614386746556310962810151979
        mflintc:  0.729844359380083005455682079528903936948641546143867465563109628101519787122062963401378975
        aflintc: [0.72984435938008300545568207952890393694864154614386746556310962810151978712206296340137897 +/- 7.62e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.dedekind_eta(tau))))
            fpm:  0.0188831925200341
            mpm:  0.0188831925200340997043957655862644205280802309567528511826273646480956172076659498852120977
            dpm:  0.0188831925200340997043957655862644205280802309567528511826273646480956172076659498852120977
            gpm:  0.018883192520034099704395765586264420528080230956752851182627364648095617207665949885212097701
            apm: [0.0188831925200340997043957655862644205280802309567528511826273646480956172076659498852120976 +/- 7.86e-92]
        cmath53:  0.0188831925200341
        sflintc:  0.01888319
        dflintc:  0.0188831925200341
        eflintc:  0.018883192520034099705
        qflintc:  0.0188831925200340997043957655862644
        oflintc:  0.018883192520034099704395765586264420528080230956752851182627364648095617
        mflintc:  0.0188831925200340997043957655862644205280802309567528511826273646480956172076659498852120976
        aflintc: [0.018883192520034099704395765586264420528080230956752851182627364648095617207665949885212098 +/- 5.20e-91]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C07_ModularFormsTau/D01_DedekindEtaCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C07_ModularFormsTau/D01_Dedekind_eta.cs>`__. 










.. _rst_mpm_modular_lambda_by_tau: 

Elliptic modular lambda function `\lambda(\tau)` (also DAMath)
-------------------------------------------------------------------------------


.. method:: ctx.ctx.elliptic_modular_lambda(tau) 


    Computes the lambda function `\lambda(\tau) = \theta_2^4(0,\tau) / \theta_3^4(0,\tau)` in terms of elliptic period ratio `\tau`. It is invariant under modular transformations `(a, b; c, d)` where `a, d` are odd and `b, c` are even.

    See also MathWorld :cite:p:`WolframFun195`, Flint :cite:p:`FlintFun195`.

    See also: https://dlmf.nist.gov/23.15#ii


    Returns the elliptic modular function `\lambda(\tau), \tau = iy,  y \ge 0`, `\displaystyle \lambda(\tau) = \frac{\theta_2^4(0,q)}{\theta_e^4(0,q)}, q = e^{i \pi \tau} = e^{-\pi y}`.


    See also: MathWorld :cite:p:`WolframFun195`, :cite:t:`Ehrhardt2018` (3.2.17.11).





    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.modular_lambda(tau)))
            fpm:  (0.300577711578404, 0.0802212287569385)
            mpm:  (0.300577711578404340028281738687470371203, 0.08022122875693849474806003837603901081353)
        cmath53:  (0.300577711578405, 0.0802212287569385)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.modular_lambda(tau))))
            fpm:  0.300577711578404
            mpm:  0.300577711578404340028281738687470371202958619984498518690738995316323687845851051645508437
            dpm:  0.300577711578404340028281738687470371202958619984498518690738995316323687845851051645508437
            gpm:  0.30057771157840434002828173868747037120295861998449851869073899531632368784585105164550843702
            apm: [0.30057771157840434002828173868747037120295861998449851869073899531632368784585105164550844 +/- 7.26e-90]
        cmath53:  0.300577711578405
        sflintc:  0.3005777
        dflintc:  0.300577711578404
        eflintc:  0.30057771157840433999
        qflintc:  0.30057771157840434002828173868747
        oflintc:  0.30057771157840434002828173868747037120295861998449851869073899531632369
        mflintc:  0.300577711578404340028281738687470371202958619984498518690738995316323687845851051645508432
        aflintc: [0.3005777115784043400282817386874703712029586199844985186907389953163236878458510516455084 +/- 4.59e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.modular_lambda(tau))))
            fpm:  0.0802212287569385
            mpm:  0.080221228756938494748060038376039010813534623673125852569879858290876176842297854192494793
            dpm:  0.080221228756938494748060038376039010813534623673125852569879858290876176842297854192494793
            gpm:  0.080221228756938494748060038376039010813534623673125852569879858290876176842297854192494792996
            apm: [0.08022122875693849474806003837603901081353462367312585256987985829087617684229785419249479 +/- 4.30e-90]
        cmath53:  0.0802212287569385
        sflintc:  0.08022122
        dflintc:  0.0802212287569385
        eflintc:  0.080221228756938494741
        qflintc:  0.080221228756938494748060038376039
        oflintc:  0.080221228756938494748060038376039010813534623673125852569879858290876177
        mflintc:  0.0802212287569384947480600383760390108135346236731258525698798582908761768422978541924947918
        aflintc: [0.08022122875693849474806003837603901081353462367312585256987985829087617684229785419249479 +/- 7.07e-90]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C07_ModularFormsTau/D02_ModularLambdaCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C07_ModularFormsTau/D02_Modular_lambda.cs>`__. 








.. _rst_mpm_modular_delta_by_tau: 

Elliptic modular delta function `\Delta(\omega, \tau)`
-------------------------------------------------------------------------------


.. method:: ctx.ctx.elliptic_modular_delta(omega, tau) 


    Computes the modular discriminant `\Delta(\tau) = \eta(\tau)^{24}` in terms of half-period `\omega_1` and elliptic period ratio `\tau`.  It transforms as

    .. math ::  \Delta\left(\frac{a\tau+b}{c\tau+d}\right) = (c\tau+d)^{12} \Delta(\tau).

    The modular discriminant is sometimes defined with an extra factor `(2\pi)^{12}`, which we omit in this implementation.

    We have `\Delta(t \omega, \tau) = t^{-12} \Delta(\omega, \tau)`.



    .. math ::  \Delta =g_{2}^{3}-27g_{3}^{2} = 4096\pi ^{12}\eta (\tau )^{24}

    for Weierstrass invariants `g_2, g_3`, and Dedekind eta function `\eta(\tau)`. 


    See also Wikipedia :cite:p:`WikipediaFun195a`, MathWorld :cite:p:`WolframFun195a`, Flint :cite:p:`FlintFun195`.

    See also: https://dlmf.nist.gov/23.3#i



    Computes the modular discriminant `\Delta(\tau) = \eta(\tau)^{24}` in terms of elliptic period ratio `\tau`.  It transforms as

    .. math ::  \Delta(g_2, g_3) = g_2^3 - 27 g_3^2 = \Delta(e_1, e_2, e_3) = 16(e_2-e_3)^2(e_3-e_1)^2(e_1-e_2)^2.


    See also Wikipedia :cite:p:`WikipediaFun195a`, MathWorld :cite:p:`WolframFun195a`, Flint :cite:p:`FlintFun195`.


    

    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.modular_delta(tau)))
            fpm:  (0.00042787946743128, 0.000305991294074904)
            mpm:  (0.0004278794674312799665251403416925907599738, 0.0003059912940749042846053724625759338221924)
        cmath53:  (0.000427879467431282, 0.000305991294074906)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.modular_delta(tau))))
            fpm:  0.00042787946743128
            mpm:  0.000427879467431279966525140341692590759973793001788905022564351626292739292314368289012572583
            dpm:  0.000427879467431279966525140341692590759973793001788905022564351626292739292314368289012572583
            gpm:  0.00042787946743127996652514034169259075997379300178890502256435162629273929231436828901257258302
            apm: [0.0004278794674312799665251403416925907599737930017889050225643516262927392923143682890125726 +/- 3.47e-92]
        cmath53:  0.000427879467431282
        sflintc:  0.0004278793
        dflintc:  0.00042787946743128
        eflintc:  0.00042787946743127996641
        qflintc:  0.000427879467431279966525140341692591
        oflintc:  0.0004278794674312799665251403416925907599737930017889050225643516262927393
        mflintc:  0.000427879467431279966525140341692590759973793001788905022564351626292739292314368289012572562
        aflintc: [0.0004278794674312799665251403416925907599737930017889050225643516262927392923143682890125726 +/- 8.95e-92]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.modular_delta(tau))))
            fpm:  0.000305991294074904
            mpm:  0.000305991294074904284605372462575933822192369703989832519495247154668902964985370762146354576
            dpm:  0.000305991294074904284605372462575933822192369703989832519495247154668902964985370762146354576
            gpm:  0.00030599129407490428460537246257593382219236970398983251949524715466890296498537076214635457602
            apm: [0.0003059912940749042846053724625759338221923697039898325194952471546689029649853707621463546 +/- 3.62e-92]
        cmath53:  0.000305991294074906
        sflintc:  0.0003059912
        dflintc:  0.000305991294074904
        eflintc:  0.00030599129407490428451
        qflintc:  0.000305991294074904284605372462575934
        oflintc:  0.00030599129407490428460537246257593382219236970398983251949524715466890297
        mflintc:  0.00030599129407490428460537246257593382219236970398983251949524715466890296498537076214635456
        aflintc: [0.0003059912940749042846053724625759338221923697039898325194952471546689029649853707621463546 +/- 7.22e-92]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C07_ModularFormsTau/D03_ModularDeltaCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C07_ModularFormsTau/D03_Modular_delta.cs>`__. 









.. _rst_mpm_kleinj_by_tau: 

Klein j-invariant `j(\tau )` (also DAMath)
-------------------------------------------------------------------------------


.. method:: ctx.klein_j(tau)


    Returns the Klein `j`-invariant in terms of elliptic period ratio `\tau`. See also Wikipedia :cite:p:`WikipediaFun1006`, MathWorld :cite:p:`WolframFun1006`, NIST :cite:p:`DLMFun155`, Flint :cite:p:`FlintFun195`, Mpmath :cite:p:`MpmathFun1006`.

    See also: https://dlmf.nist.gov/23.15#ii


    Computes Klein's `j`-invariant `j(\tau)` given `\tau` in the upper half-plane. The function is normalized so that `j(i) = 1728`. We first move `\tau` to the fundamental domain, which does not change the value of the function. Then we use the formula

    .. math ::  j(\tau ) = 1728{\frac {g_{2}^{3}}{g_{2}^{3}-27g_{3}^{2}}} = 32 (\theta_2^8+\theta_3^8+\theta_4^8)^3 / (\theta_2 \theta_3 \theta_4)^8


    where `\theta_i = \theta_i(0,\tau)`.



    Returns the Klein j-invariant `J(\tau), \tau = iy,  y \ge 0`, `\displaystyle J(\tau) = \frac{\left(\theta_2^8(q)+\theta_3^8(q)+\theta_4^8(q)\right)^3}{54 (\theta'_1)^8(q)}, q = e^{i \pi \tau} = e^{-\pi y}`.

    See also: Wikipedia :cite:p:`WikipediaFun1006`, MathWorld :cite:p:`WolframFun1006`, :cite:t:`Ehrhardt2018` (3.2.17.12).


    Returns the Klein j-invariant in terms of elliptic period ratio `\tau`. See also Wikipedia :cite:p:`WikipediaFun1006`, MathWorld :cite:p:`WolframFun1006`, NIST :cite:p:`DLMFun155`, Flint :cite:p:`FlintFun195`.


    .. math ::  j(g_1, g_2) = 1728{\frac {g_{2}^{3}}{g_{2}^{3}-27g_{3}^{2}}}


    

    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.klein_j(tau)))
            fpm:  (2352.65426118271, -1038.50945324977)
            mpm:  (2352.654261182714612483685954244309154515, -1038.509453249774101440766187794980665174)
        cmath53:  (2352.65426118271, -1038.50945324977)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.klein_j(tau))))
            fpm:  2352.65426118271
            mpm:  2352.65426118271461248368595424430915451453758321480677618371489055091853169740920064300255
            dpm:  2352.65426118271461248368595424430915451453758321480677618371489055091853169740920064300255
            gpm:  2352.6542611827146124836859542443091545145375832148067761837148905509185316974092006430025498
            apm: [2352.654261182714612483685954244309154514537583214806776183714890550918531697409200643003 +/- 6.20e-85]
        cmath53:  2352.65426118271
        sflintc:  2352.655
        dflintc:  2352.65426118271
        eflintc:  2352.6542611827146128
        qflintc:  2352.65426118271461248368595424431
        oflintc:  2352.6542611827146124836859542443091545145375832148067761837148905509185
        mflintc:  2352.65426118271461248368595424430915451453758321480677618371489055091853169740920064300259
        aflintc: [2352.65426118271461248368595424430915451453758321480677618371489055091853169740920064300 +/- 3.22e-84]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> tau = 0.1+1.2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.klein_j(tau))))
            fpm:  -1038.50945324977
            mpm:  -1038.50945324977410144076618779498066517374835594342658256261154196725501879517272357022604
            dpm:  -1038.50945324977410144076618779498066517374835594342658256261154196725501879517272357022604
            gpm:  -1038.5094532497741014407661877949806651737483559434265825626115419672550187951727235702260401
            apm: [-1038.509453249774101440766187794980665173748355943426582562611541967255018795172723570226 +/- 2.20e-85]
        cmath53:  -1038.50945324977
        sflintc:  -1038.51
        dflintc:  -1038.50945324977
        eflintc:  -1038.5094532497741018
        qflintc:  -1038.50945324977410144076618779498
        oflintc:  -1038.509453249774101440766187794980665173748355943426582562611541967255
        mflintc:  -1038.50945324977410144076618779498066517374835594342658256261154196725501879517272357022607
        aflintc: [-1038.509453249774101440766187794980665173748355943426582562611541967255018795172723570226 +/- 6.88e-85]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C07_ModularFormsTau/D04_KleinJCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C07_ModularFormsTau/D04_Klein_j.cs>`__. 




