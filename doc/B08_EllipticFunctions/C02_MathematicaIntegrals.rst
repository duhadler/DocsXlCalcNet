

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Legendre elliptic integrals (elliptic parameter `m`)
===============================================================================

While the Legendre/Bulirsch/Maple style functions have the modulus `k` (or `k', k_c`) as
an argument, the Mathematica style functions (prefixed with ``M`` ) use the parameter
(`m = k^2`) and therefore cover the imaginary modulus functions with `m < 0`.



Legendre complete elliptic integral of the first kind, `K(m)`
-------------------------------------------------------------------------------

.. method:: ctx.m_elliptic_k(m)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the complete elliptic integral of the first kind, `\displaystyle  \mathrm{M\_EllipticK}(m) = \int_0^{\pi/2} \frac{\mathrm{d}t}{\sqrt{1-m \sin^2(t)}}`, with parameter `m \ne 1`.

    See also Wikipedia :cite:p:`WikipediaFun148`, MathWorld :cite:p:`WolframFun148`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun148`, :cite:t:`Ehrhardt2018` (3.2.5.1), Flint :cite:p:`FlintFun148`.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> m = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_k(m)))
            fpm:  0.950714187079869
            mpm:  0.950714187079868563186782597025369087762678867942372170663135075106214263306060180818124363
            dpm:  0.950714187079868563186782597025369087762678867942372170663135075106214263306060180818124363
            gpm:  0.95071418707986856318678259702536908776267886794237217066313507510621426330606018081812436303
            apm: [0.95071418707986856318678259702536908776267886794237217066313507510621426330606018081812436 +/- 4.26e-90]
         math53:  0.950714187079869
         sflint:  0.9507142
         dflint:  0.950714187079869
         eflint:  0.95071418707986856317
         qflint:  0.950714187079868563186782597025369
         oflint:  0.95071418707986856318678259702536908776267886794237217066313507510621426
         mflint:  0.950714187079868563186782597025369087762678867942372170663135075106214263306060180818124365
         aflint: [0.95071418707986856318678259702536908776267886794237217066313507510621426330606018081812436 +/- 9.16e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> m = -5.1+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_k(m)))
            fpm:  (0.932926541517737, 0.090648574571162)
            mpm:  (0.9329265415177372729218770094272884911842, 0.09064857457116197100223151832277238301948)
        cmath53:  (0.932926541517737, 0.090648574571162)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> m = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.m_elliptic_k(m))))
            fpm:  0.932926541517737
            mpm:  0.932926541517737272921877009427288491184200638627491129476332010458399374538437820829666054
            dpm:  0.932926541517737272921877009427288491184200638627491129476332010458399374538437820829666054
            gpm:  0.93292654151773727292187700942728849118420063862749112947633201045839937453843782082966605398
            apm: [0.93292654151773727292187700942728849118420063862749112947633201045839937453843782082966605 +/- 5.67e-90]
        cmath53:  0.932926541517737
        sflintc:  0.9329265
        dflintc:  0.932926541517737
        eflintc:  0.93292654151773727293
        qflintc:  0.932926541517737272921877009427288
        oflintc:  0.93292654151773727292187700942728849118420063862749112947633201045839938
        mflintc:  0.932926541517737272921877009427288491184200638627491129476332010458399374538437820829666056
        aflintc: [0.9329265415177372729218770094272884911842006386274911294763320104583993745384378208296661 +/- 5.14e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> m = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.m_elliptic_k(m))))
            fpm:  0.090648574571162
            mpm:  0.0906485745711619710022315183227723830194776828319962771506364558637474416687832704280258365
            dpm:  0.0906485745711619710022315183227723830194776828319962771506364558637474416687832704280258365
            gpm:  0.090648574571161971002231518322772383019477682831996277150636455863747441668783270428025836503
            apm: [0.090648574571161971002231518322772383019477682831996277150636455863747441668783270428025836 +/- 9.67e-91]
        cmath53:  0.090648574571162
        sflintc:  0.09064858
        dflintc:  0.090648574571162
        eflintc:  0.090648574571161971002
        qflintc:  0.0906485745711619710022315183227724
        oflintc:  0.090648574571161971002231518322772383019477682831996277150636455863747442
        mflintc:  0.0906485745711619710022315183227723830194776828319962771506364558637474416687832704280258366
        aflintc: [0.09064857457116197100223151832277238301947768283199627715063645586374744166878327042802584 +/- 5.59e-90]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D01a_MEllipticKReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D01b_MEllipticKCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C02_MathematicaIntegrals/D01_MEllipticK.cs>`__. 








Legendre complete elliptic integral of the second kind, `E(m)`
-------------------------------------------------------------------------------

.. method:: ctx.m_elliptic_e(m)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the complete elliptic integral of the second kind,  `\displaystyle  \mathrm{M\_EllipticEC}(m) = \int_0^{\pi/2} \sqrt{1-m \sin^2(t)} \, \mathrm{d}t`,  with parameter `m \ne 1`. 

    See also Wikipedia :cite:p:`WikipediaFun149`, MathWorld :cite:p:`WolframFun149`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun149`, :cite:t:`Ehrhardt2018` (3.2.5.2), Flint :cite:p:`FlintFun148`.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> m = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_e(m)))
            fpm:  2.84887617240518
            mpm:  2.8488761724051832293549304119615724886745556296796933176525551335527332215223799567485471
            dpm:  2.8488761724051832293549304119615724886745556296796933176525551335527332215223799567485471
            gpm:  2.8488761724051832293549304119615724886745556296796933176525551335527332215223799567485471002
            apm: [2.8488761724051832293549304119615724886745556296796933176525551335527332215223799567485471 +/- 4.97e-89]
         math53:  2.84887617240518
         sflint:  2.848876
         dflint:  2.84887617240518
         eflint:  2.8488761724051832294
         qflint:  2.84887617240518322935493041196157
         oflint:  2.8488761724051832293549304119615724886745556296796933176525551335527332
         mflint:  2.84887617240518322935493041196157248867455562967969331765255513355273322152237995674854709
         aflint: [2.848876172405183229354930411961572488674555629679693317652555133552733221522379956748547 +/- 2.43e-88]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> m = -5.1+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_e(m)))
            fpm:  (2.87531976422923, -0.368250870477359)
            mpm:  (2.875319764229230843159805851338373303672, -0.3682508704773587959303088256204950491917)
        cmath53:  (2.87531976422909, -0.368250870477372)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> m = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.m_elliptic_e(m))))
            fpm:  2.87531976422923
            mpm:  2.87531976422923084315980585133837330367235640089848634582875066909081166900049165608416053
            dpm:  2.87531976422923084315980585133837330367235640089848634582875066909081166900049165608416053
            gpm:  2.87531976422923084315980585133837330367235640089848634582875066909081166900049165608416053
            apm: [2.875319764229230843159805851338373303672356400898486345828750669090811669000491656084161 +/- 5.87e-88]
        cmath53:  2.87531976422909
        sflintc:  2.87532
        dflintc:  2.87531976422923
        eflintc:  2.8753197642292308432
        qflintc:  2.87531976422923084315980585133837
        oflintc:  2.8753197642292308431598058513383733036723564008984863458287506690908117
        mflintc:  2.87531976422923084315980585133837330367235640089848634582875066909081166900049165608416052
        aflintc: [2.875319764229230843159805851338373303672356400898486345828750669090811669000491656084161 +/- 8.39e-88]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> m = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.m_elliptic_e(m))))
            fpm:  -0.368250870477359
            mpm:  -0.368250870477358795930308825620495049191659418883867234130477851430199988279551665744024943
            dpm:  -0.368250870477358795930308825620495049191659418883867234130477851430199988279551665744024943
            gpm:  -0.368250870477358795930308825620495049191659418883867234130477851430199988279551665744024943
            apm: [-0.368250870477358795930308825620495049191659418883867234130477851430199988279551665744025 +/- 1.65e-88]
        cmath53:  -0.368250870477372
        sflintc:  -0.3682509
        dflintc:  -0.368250870477359
        eflintc:  -0.36825087047735879594
        qflintc:  -0.368250870477358795930308825620495
        oflintc:  -0.36825087047735879593030882562049504919165941888386723413047785143019999
        mflintc:  -0.368250870477358795930308825620495049191659418883867234130477851430199988279551665744024942
        aflintc: [-0.368250870477358795930308825620495049191659418883867234130477851430199988279551665744025 +/- 4.03e-88]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D02a_MEllipticEReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D02b_MEllipticECplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C02_MathematicaIntegrals/D02_MEllipticE.cs>`__. 







Legendre complete elliptic integral of the third kind, `\Pi(n, m)`
-----------------------------------------------------------------------------------------------

.. method:: ctx.m_elliptic_pi(n, m)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the complete elliptic integral of the third kind ,  `\displaystyle  \mathrm{M\_EllipticPiC}(n, m) = \int_0^{\pi/2} \frac{\mathrm{d}t}{(1-n \sin^2(t)) \sqrt{1-m \sin^2(t)}}`, with characteristic `n \ne 1` and parameter `m \ne 1`. 

    See also Wikipedia :cite:p:`WikipediaFun150`, MathWorld :cite:p:`WolframFun150`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun150`, :cite:t:`Ehrhardt2018` (3.2.5.3), Flint :cite:p:`FlintFun151`.


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.75; m = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_pi(n, m)))
            fpm:  3.93061484589535
            mpm:  3.93061484589535091387575176606230235110410422764021439109586406082747681263431269200455237
            dpm:  3.93061484589535091387575176606230235110410422764021439109586406082747681263431269200455237
            gpm:  3.9306148458953509138757517660623023511041042276402143910958640608274768126343126920045523698
            apm: [3.93061484589535091387575176606230235110410422764021439109586406082747681263431269200455237 +/- 2.87e-90]
         math53:  3.93061484589535
         sflint:  3.930615
         dflint:  3.93061484589535
         eflint:  3.9306148458953509138
         qflint:  3.9306148458953509138757517660623
         oflint:  3.9306148458953509138757517660623023511041042276402143910958640608274768
         mflint:  3.93061484589535091387575176606230235110410422764021439109586406082747681263431269200455237
         aflint: [3.93061484589535091387575176606230235110410422764021439109586406082747681263431269200455237 +/- 6.07e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.75+2j;  m = 0.5+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_pi(n, m)))
            fpm:  (0.499097246595171, 0.705231094798092)
            mpm:  (0.4990972465951706312298307615445249766389, 0.7052310947980915876902594934850785039421)
        cmath53:  (0.499097250800956, 0.705231090070493)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.75+2j;  m = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.m_elliptic_pi(n, m))))
            fpm:  0.499097246595171
            mpm:  0.499097246595170631229830761544524976638912820453304705274709914144790976919364713867037308
            dpm:  0.499097246595170631229830761544524976638912820453304705274709914144790976919364713867037308
            gpm:  0.499097246595170631229830761544524976638912820453304705274709914144790976919364713867037308
            apm: [0.49909724659517063122983076154452497663891282045330470527470991414479097691936471386703731 +/- 2.34e-90]
        cmath53:  0.499097250800956
        sflintc:  0.4990973
        dflintc:  0.499097246595171
        eflintc:  0.49909724659517063123
        qflintc:  0.499097246595170631229830761544525
        oflintc:  0.49909724659517063122983076154452497663891282045330470527470991414479098
        mflintc:  0.499097246595170631229830761544524976638912820453304705274709914144790976919364713867037309
        aflintc: [0.49909724659517063122983076154452497663891282045330470527470991414479097691936471386703731 +/- 4.07e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.75+2j;  m = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.m_elliptic_pi(n, m))))
            fpm:  0.705231094798092
            mpm:  0.705231094798091587690259493485078503942117066858510903046413440050183664020809730997046859
            dpm:  0.705231094798091587690259493485078503942117066858510903046413440050183664020809730997046859
            gpm:  0.70523109479809158769025949348507850394211706685851090304641344005018366402080973099704685902
            apm: [0.705231094798091587690259493485078503942117066858510903046413440050183664020809730997046859 +/- 6.50e-91]
        cmath53:  0.705231090070493
        sflintc:  0.7052311
        dflintc:  0.705231094798092
        eflintc:  0.7052310947980915877
        qflintc:  0.705231094798091587690259493485078
        oflintc:  0.70523109479809158769025949348507850394211706685851090304641344005018366
        mflintc:  0.705231094798091587690259493485078503942117066858510903046413440050183664020809730997046858
        aflintc: [0.70523109479809158769025949348507850394211706685851090304641344005018366402080973099704686 +/- 3.41e-90]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D03a_MellipticPiReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D03b_MellipticPiCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C02_MathematicaIntegrals/D03_MEllipticPi.cs>`__. 







Legendre incomplete elliptic integral of the first kind, `F(\phi, m)`
-------------------------------------------------------------------------------------------

.. method:: ctx.m_elliptic_f(phi, m)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the complete elliptic integral of the first kind,  `\displaystyle  \mathrm{M\_EllipticF}(\phi,m) = \int_0^{\phi} \frac{\mathrm{d}t}{\sqrt{1-m \sin^2(t)}}`, with parameter `m \sin^2(\phi) \le 1`. 

    See also Wikipedia :cite:p:`WikipediaFun151`, MathWorld :cite:p:`WolframFun151`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun148`, :cite:t:`Ehrhardt2018` (3.2.5.4).


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75; m = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_f(phi, m)))
            fpm:  0.785381841639308
            mpm:  0.785381841639308415040695231202441817572888604673497268030236048704844121866911955427766389
            dpm:  0.785381841639308415040695231202441817572888604673497268030236048704844121866911955427766389
            gpm:  0.78538184163930841504069523120244181757288860467349726803023604870484412186691195542776638904
            apm: [0.785381841639308415040695231202441817572888604673497268030236048704844121866911955427766389 +/- 8.67e-91]
         math53:  0.785381841639308
         sflint:  0.7853819
         dflint:  0.785381841639308
         eflint:  0.78538184163930841505
         qflint:  0.785381841639308415040695231202442
         oflint:  0.78538184163930841504069523120244181757288860467349726803023604870484412
         mflint:  0.785381841639308415040695231202441817572888604673497268030236048704844121866911955427766388
         aflint: [0.78538184163930841504069523120244181757288860467349726803023604870484412186691195542776639 +/- 3.65e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  m = 0.5+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_f(phi, m)))
            fpm:  (0.490302892126893, 1.06285354403954)
            mpm:  (0.4903028921268929204706769914013676242743, 1.062853544039536018224634256323298294282)
        cmath53:  (0.490302892126848, 1.06285354403944)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  m = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.m_elliptic_f(phi, m))))
            fpm:  0.490302892126893
            mpm:  0.490302892126892920470676991401367624274322695618689794953856273356996553395086525496410131
            dpm:  0.490302892126892920470676991401367624274322695618689794953856273356996553395086525496410131
            gpm:  0.49030289212689292047067699140136762427432269561868979495385627335699655339508652549641013099
            apm: [0.490302892126892920470676991401367624274322695618689794953856273356996553395086525496410 +/- 2.94e-88]
        cmath53:  0.490302892126848
        sflintc:  0.4903029
        dflintc:  0.490302892126893
        eflintc:  0.49030289212689292047
        qflintc:  0.490302892126892920470676991401368
        oflintc:  0.49030289212689292047067699140136762427432269561868979495385627335699655
        mflintc:  0.490302892126892920470676991401367624274322695618689794953856273356996553395086525496410131
        aflintc: [0.490302892126892920470676991401367624274322695618689794953856273356996553395086525496410 +/- 5.43e-88]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  m = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.m_elliptic_f(phi, m))))
            fpm:  1.06285354403954
            mpm:  1.06285354403953601822463425632329829428239783567815484595339204566387454668448905636004014
            dpm:  1.06285354403953601822463425632329829428239783567815484595339204566387454668448905636004014
            gpm:  1.06285354403953601822463425632329829428239783567815484595339204566387454668448905636004014
            apm: [1.062853544039536018224634256323298294282397835678154845953392045663874546684489056360040 +/- 3.08e-88]
        cmath53:  1.06285354403944
        sflintc:  1.062854
        dflintc:  1.06285354403954
        eflintc:  1.0628535440395360182
        qflintc:  1.0628535440395360182246342563233
        oflintc:  1.0628535440395360182246342563232982942823978356781548459533920456638745
        mflintc:  1.06285354403953601822463425632329829428239783567815484595339204566387454668448905636004014
        aflintc: [1.062853544039536018224634256323298294282397835678154845953392045663874546684489056360040 +/- 5.60e-88]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D04a_MellipticFReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D04b_MellipticFCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C02_MathematicaIntegrals/D04_MEllipticF.cs>`__. 








Legendre incomplete elliptic integral of the second kind, `E(\phi, m)`
------------------------------------------------------------------------------------

.. method:: ctx.m_elliptic_e_inc(phi,m)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the complete elliptic integral of the second kind,  `\displaystyle  \mathrm{M\_EllipticE}(\phi,m) = \int_0^{\phi} \sqrt{1-m \sin^2(t)} \, \mathrm{d}t` with parameter `m \sin^2(\phi) \le 1`. 

    See also Wikipedia :cite:p:`WikipediaFun152`, MathWorld :cite:p:`WolframFun152`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun149`, :cite:t:`Ehrhardt2018` (3.2.5.5), Flint :cite:p:`FlintFun151`.


    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75; m = 0.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_e_inc(phi, m)))
            fpm:  0.717350716077167
            mpm:  0.717350716077166616604159258951610241356761760118313981468098652115868353997171404405303682
            dpm:  0.717350716077166616604159258951610241356761760118313981468098652115868353997171404405303682
            gpm:  0.717350716077166616604159258951610241356761760118313981468098652115868353997171404405303682
            apm: [0.717350716077166616604159258951610241356761760118313981468098652115868353997171404405303682 +/- 7.81e-91]
         math53:  0.717350716077167
         sflint:  0.7173507
         dflint:  0.717350716077167
         eflint:  0.71735071607716661659
         qflint:  0.71735071607716661660415925895161
         oflint:  0.71735071607716661660415925895161024135676176011831398146809865211586835
         mflint:  0.717350716077166616604159258951610241356761760118313981468098652115868353997171404405303681
         aflint: [0.71735071607716661660415925895161024135676176011831398146809865211586835399717140440530368 +/- 3.92e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> pphi = 0.75+2j;  m = 0.5+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_e_inc(phi, m)))
            fpm:  (1.5837638485753, 4.83404671559569)
            mpm:  (1.583763848575302697875448499717636585461, 4.834046715595690036838024223269293844158)
        cmath53:  (1.58376384857526, 4.83404671559559)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  m = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.m_elliptic_e_inc(phi, m))))
            fpm:  1.5837638485753
            mpm:  1.5837638485753026978754484997176365854611321614757796005185200313188425055347715412609672
            dpm:  1.5837638485753026978754484997176365854611321614757796005185200313188425055347715412609672
            gpm:  1.5837638485753026978754484997176365854611321614757796005185200313188425055347715412609672001
            apm: [1.583763848575302697875448499717636585461132161475779600518520031318842505534771541260967 +/- 3.98e-88]
        cmath53:  1.58376384857526
        sflintc:  1.583764
        dflintc:  1.5837638485753
        eflintc:  1.5837638485753026979
        qflintc:  1.58376384857530269787544849971764
        oflintc:  1.5837638485753026978754484997176365854611321614757796005185200313188425
        mflintc:  1.58376384857530269787544849971763658546113216147577960051852003131884250553477154126096719
        aflintc: [1.583763848575302697875448499717636585461132161475779600518520031318842505534771541260967 +/- 7.61e-88]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> phi = 0.75+2j;  m = 0.5+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.m_elliptic_e_inc(phi, m))))
            fpm:  4.83404671559569
            mpm:  4.83404671559569003683802422326929384415787150050620858422108749059480481429339005257076335
            dpm:  4.83404671559569003683802422326929384415787150050620858422108749059480481429339005257076335
            gpm:  4.8340467155956900368380242232692938441578715005062085842210874905948048142933900525707633501
            apm: [4.834046715595690036838024223269293844157871500506208584221087490594804814293390052570763 +/- 5.55e-88]
        cmath53:  4.83404671559559
        sflintc:  4.834047
        dflintc:  4.83404671559569
        eflintc:  4.8340467155956900369
        qflintc:  4.83404671559569003683802422326929
        oflintc:  4.8340467155956900368380242232692938441578715005062085842210874905948048
        mflintc:  4.83404671559569003683802422326929384415787150050620858422108749059480481429339005257076334
        aflintc: [4.834046715595690036838024223269293844157871500506208584221087490594804814293390052570763 +/- 9.16e-88]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D05a_MellipticEIncReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C02_MathematicaIntegrals/D05b_MellipticEIncCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C02_MathematicaIntegrals/D05_MEllipticEInc.cs>`__. 








Legendre incomplete elliptic integral of the third kind, `\Pi(n,\phi, m)`
-----------------------------------------------------------------------------------------------

.. method:: ctx.m_elliptic_pi_inc(n, phi, m)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the complete elliptic integral of the third kind,  `\displaystyle  \mathrm{M\_EllipticPi}(n, \phi, m) = \int_0^{\phi} \frac{\mathrm{d}t}{(1-n \sin^2(t)) \sqrt{1-m \sin^2(t)}}` with characteristic `n \ne 1` and parameter `m \ne 1`. 

    See also Wikipedia :cite:p:`WikipediaFun153`, MathWorld :cite:p:`WolframFun153`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun150`, :cite:t:`Ehrhardt2018` (3.2.5.6), Flint :cite:p:`FlintFun151`.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = 0.55; phi = 0.18; m = 0.01; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_pi_inc(n, phi, m)))
            fpm:  0.181083455890139
            mpm:  0.181083455890138516332755827884800961120683222666935519365873089823436502404149761333412014
            dpm:  0.181083455890138516332755827884800961120683222666935519365873089823436502404149761333412014
            gpm:  0.18108345589013851633275582788480096112068322266693551936587308982343650240414976133341201401
            apm: [0.181083455890138516332755827884800961120683222666935519365873089823436502404149761333412014 +/- 2.47e-91]
         math53:  0.181083455890138
         sflint:  0.1810835
         dflint:  0.181083455890139
         eflint:  0.18108345589013851634
         qflint:  0.181083455890138516332755827884801
         oflint:  0.1810834558901385163327558278848009611206832226669355193658730898234365
         mflint:  0.181083455890138516332755827884800961120683222666935519365873089823436502404149761333412014
         aflint: [0.181083455890138516332755827884800961120683222666935519365873089823436502404149761333412014 +/- 8.12e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = -5.1+2j;  phi = 2.7+2j; m = 1.3+2j;  gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.m_elliptic_pi_inc(n, phi, m)))
            fpm:  (0.322004007340083, 0.751422520797896)
            mpm:  (0.3220040073400829546054227879987298519782, 0.7514225207978954342344887938985768416085)
        cmath53:  (0.322004003941805, 0.751422522223148)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> n = -5.1+2j;  phi = 2.7+2j; m = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.m_elliptic_pi_inc(n, phi, m))))
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
        >>> n = -5.1+2j;  phi = 2.7+2j; m = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.m_elliptic_pi_inc(n, phi, m))))
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






