

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />






|newpage|

Carlson symmetric elliptic integrals
===============================================================================




Carlson symmetric elliptic integral of the first kind, `R_F(x,y,z)`
---------------------------------------------------------------------------------------

.. method:: ctx.elliptic_rf(x, y, z)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the Carlson symmetric elliptic integral of the first kind, `R_F(x,y,z)`, which is defined for `x,y,z \notin (-\infty,0)`, and with at most one of `x,y,z` being zero. See also Wikipedia :cite:p:`WikipediaFun154`, NIST :cite:p:`DLMFun154`, BoostMath :cite:p:`BoostFun154`, :cite:t:`Ehrhardt2018` (3.2.2.2), Flint :cite:p:`FlintFun154`, Mpmath :cite:p:`MpmathFun154a`. 


    .. math ::  R_F(x,y,z) = \frac{1}{2}  \int_0^{\infty} \frac{\mathrm{d}t}{\sqrt{(t+x)(t+y)(t+z)}}



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; y = 2.7; z = 1.3; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rf(x, y, z)))
            fpm:  0.599561454504973
            mpm:  0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068
            dpm:  0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068
            gpm:  0.59956145450497343449459138684638691543188576109180397027471341101262689154588763504617406794
            apm: ([0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068 +/- 3.59e-91], 0)
         math53:  0.599561454504973
          sreal:  0.5995615
          dreal:  0.599561454504973
          ereal:  0.59956145450497343446
          qreal:  0.599561454504973434494591386846387
          oreal:  0.59956145450497343449459138684638691543188576109180397027471341101262689
          mreal:  0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068
         sflint:  0.5995615
         dflint:  0.599561454504973
         eflint:  0.59956145450497343451
         qflint:  0.599561454504973434494591386846387
         oflint:  0.59956145450497343449459138684638691543188576109180397027471341101262689
         mflint:  0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068
         aflint: [0.59956145450497343449459138684638691543188576109180397027471341101262689154588763504617407 +/- 2.98e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; z = 1.3+2j;  gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rf(x, y, z)))
            fpm:  (0.406346809053485, -0.408712185367039)
            mpm:  (0.4063468090534854068789456061473383254573, -0.408712185367038816093937231856418037956)
        cmath53:  (0.406346809053458, -0.408712185367011)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; z = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_rf(x, y, z))))
            fpm:  0.406346809053485
            mpm:  0.406346809053485406878945606147338325457278110986679449892518286213613251646468792703839987
            dpm:  0.406346809053485406878945606147338325457278110986679449892518286213613251646468792703839987
            gpm:  0.40634680905348540687894560614733832545727811098667944989251828621361325164646879270383998698
            apm: [0.4063468090534854068789456061473383254572781109866794498925182862136132516464687927038400 +/- 4.38e-89]
        cmath53:  0.406346809053458
        sflintc:  0.4063468
        dflintc:  0.406346809053485
        eflintc:  0.40634680905348540689
        qflintc:  0.406346809053485406878945606147338
        oflintc:  0.40634680905348540687894560614733832545727811098667944989251828621361325
        mflintc:  0.406346809053485406878945606147338325457278110986679449892518286213613251646468792703839987
        aflintc: [0.4063468090534854068789456061473383254572781109866794498925182862136132516464687927038400 +/- 4.30e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; z = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_rf(x, y, z))))
            fpm:  -0.408712185367039
            mpm:  -0.408712185367038816093937231856418037956038354807874415662832443483714984086729335531856168
            dpm:  -0.408712185367038816093937231856418037956038354807874415662832443483714984086729335531856168
            gpm:  -0.408712185367038816093937231856418037956038354807874415662832443483714984086729335531856168
            apm: [-0.4087121853670388160939372318564180379560383548078744156628324434837149840867293355318562 +/- 7.42e-89]
        cmath53:  -0.408712185367011
        sflintc:  -0.4087122
        dflintc:  -0.408712185367039
        eflintc:  -0.4087121853670388161
        qflintc:  -0.408712185367038816093937231856418
        oflintc:  -0.40871218536703881609393723185641803795603835480787441566283244348371498
        mflintc:  -0.408712185367038816093937231856418037956038354807874415662832443483714984086729335531856167
        aflintc: [-0.4087121853670388160939372318564180379560383548078744156628324434837149840867293355318562 +/- 7.32e-89]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D01a_CarlsonRfReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D01b_CarlsonRfCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C01_CarlsonIntegrals/D01_CarlsonRf.cs>`__. 









Carlson completely symmetric elliptic integral of the second kind, `R_G(x,y,z)`
------------------------------------------------------------------------------------------------------

.. method:: ctx.elliptic_rg(x, y, z)

    where ``ctx`` is ``math53`` or ``ctxflint``.

    Returns the Carlson completely symmetric elliptic integral of the second kind, `R_G(x,y,z)`.  See also Wikipedia :cite:p:`WikipediaFun154`, NIST :cite:p:`DLMFun154`, BoostMath :cite:p:`BoostFun154`, :cite:t:`Ehrhardt2018` (3.2.2.4), Flint :cite:p:`FlintFun154`, Mpmath :cite:p:`MpmathFun154e`. 


    .. math ::  R_G(x,y,z) = \frac{1}{4} \int_0^{\infty}  \frac{t}{\sqrt{(t+x)(t+y)(t+z)}} \left( \frac{x}{t+x} + \frac{y}{t+y} + \frac{z}{t+z}\right) \mathrm{d}t.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; y = 2.7; z = 1.3; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rg(x, y, z)))
            fpm:  1.71771940872781
            mpm:  1.71771940872780544839820593594931907935890946673516328517839445821854284968464536517939035
            dpm:  1.71771940872780544839820593594931907935890946673516328517839445821854284968464536517939035
            gpm:  1.71771940872780544839820593594931907935890946673516328517839445821854284968464536517939035
            apm: ([1.71771940872780544839820593594931907935890946673516328517839445821854284968464536517939035 +/- 1.45e-90], 0)
         math53:  1.71771940872781
          sreal:  1.717719
          dreal:  1.71771940872781
          ereal:  1.7177194087278054484
          qreal:  1.71771940872780544839820593594932
          oreal:  1.7177194087278054483982059359493190793589094667351632851783944582185428
          mreal:  1.71771940872780544839820593594931907935890946673516328517839445821854284968464536517939035
         sflint:  1.717719
         dflint:  1.71771940872781
         eflint:  1.7177194087278054484
         qflint:  1.71771940872780544839820593594932
         oflint:  1.7177194087278054483982059359493190793589094667351632851783944582185429
         mflint:  1.71771940872780544839820593594931907935890946673516328517839445821854284968464536517939035
         aflint: [1.71771940872780544839820593594931907935890946673516328517839445821854284968464536517939035 +/- 2.29e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; z = 1.3+2j;  gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rg(x, y, z)))
            fpm:  (1.03495931235596, 1.15500266588851)
            mpm:  (1.034959312355955821133775253751604723113, 1.155002665888506178430005795902737975844)
        cmath53:  (1.03495931235591, 1.1550026658885)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; z = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_rg(x, y, z))))
            fpm:  1.03495931235596
            mpm:  1.03495931235595582113377525375160472311339314831930910465178079797659303701958487738158822
            dpm:  1.03495931235595582113377525375160472311339314831930910465178079797659303701958487738158822
            gpm:  1.0349593123559558211337752537516047231133931483193091046517807979765930370195848773815882199
            apm: [1.034959312355955821133775253751604723113393148319309104651780797976593037019584877381588 +/- 3.77e-88]
        cmath53:  1.03495931235591
        sflintc:  1.034959
        dflintc:  1.03495931235596
        eflintc:  1.0349593123559558211
        qflintc:  1.0349593123559558211337752537516
        oflintc:  1.034959312355955821133775253751604723113393148319309104651780797976593
        mflintc:  1.03495931235595582113377525375160472311339314831930910465178079797659303701958487738158822
        aflintc: [1.034959312355955821133775253751604723113393148319309104651780797976593037019584877381588 +/- 3.73e-88]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; z = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_rg(x, y, z))))
            fpm:  1.15500266588851
            mpm:  1.1550026658885061784300057959027379758439420285395762033572812154820776227314424983821642
            dpm:  1.1550026658885061784300057959027379758439420285395762033572812154820776227314424983821642
            gpm:  1.1550026658885061784300057959027379758439420285395762033572812154820776227314424983821642
            apm: [1.155002665888506178430005795902737975843942028539576203357281215482077622731442498382164 +/- 3.44e-88]
        cmath53:  1.1550026658885
        sflintc:  1.155003
        dflintc:  1.15500266588851
        eflintc:  1.1550026658885061784
        qflintc:  1.15500266588850617843000579590274
        oflintc:  1.1550026658885061784300057959027379758439420285395762033572812154820776
        mflintc:  1.1550026658885061784300057959027379758439420285395762033572812154820776227314424983821642
        aflintc: [1.155002665888506178430005795902737975843942028539576203357281215482077622731442498382164 +/- 3.39e-88]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D02a_CarlsonRgReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D02b_CarlsonRgCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C01_CarlsonIntegrals/D02_CarlsonRg.cs>`__. 









Carlson symmetric elliptic integral of the third kind, `R_J(x,y,z,p)`
---------------------------------------------------------------------------------------------

.. method:: ctx.elliptic_rj(x, y, z, p)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the Carlson symmetric elliptic integral of the third kind, `R_J(x,y,z,p)`, with `x, y, z \ge 0`, at most one may be zero and `p \ne 0`. See also Wikipedia :cite:p:`WikipediaFun154`, NIST :cite:p:`DLMFun154`, BoostMath :cite:p:`BoostFun154`, :cite:t:`Ehrhardt2018` (3.2.2.5), Flint :cite:p:`FlintFun154`, Mpmath :cite:p:`MpmathFun154c`. 


    .. math ::  R_J(x,y,z,p) = \frac{3}{2}  \int_0^{\infty} \frac{\mathrm{d}t}{(t+p)\sqrt{(t+x)(t+y)(t+z)}}.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; y = 2.7; z = 1.3; p = 6.4; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rj(x, y, z, p)))
            fpm:  0.127423787191668
            mpm:  0.127423787191668222903646534510955430327295706344281528842778153775872583638180051189580668
            dpm:  0.127423787191668222903646534510955430327295706344281528842778153775872583638180051189580668
            gpm:  0.127423787191668222903646534510955430327295706344281528842778153775872583638180051189580668
            apm: ([0.127423787191668222903646534510955430327295706344281528842778153775872583638180051189580668 +/- 4.66e-91], 0)
         math53:  0.127423787191668
          sreal:  0.1274238
          dreal:  0.127423787191668
          ereal:  0.12742378719166822289
          qreal:  0.127423787191668222903646534510955
          oreal:  0.12742378719166822290364653451095543032729570634428152884277815377587258
          mreal:  0.127423787191668222903646534510955430327295706344281528842778153775872583638180051189580668
         sflint:  0.1274238
         dflint:  0.127423787191668
         eflint:  0.12742378719166822291
         qflint:  0.127423787191668222903646534510955
         oflint:  0.12742378719166822290364653451095543032729570634428152884277815377587258
         mflint:  0.127423787191668222903646534510955430327295706344281528842778153775872583638180051189580668
         aflint: [0.127423787191668222903646534510955430327295706344281528842778153775872583638180051189580668 +/- 5.86e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1+2j;  y = 2.7+2j; z = 1.3+2j; p = 6.4+2j;  gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rj(x, y, z, p)))
            fpm:  (0.0744060403350267, -0.0675655379365139)
            mpm:  (0.07440604033502674339417304654965556875533, -0.06756553793651386967546330619794024298378)
        cmath53:  (0.0744060390508556, -0.0675655361339475)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1+2j;  y = 2.7+2j; z = 1.3+2j; p = 6.4+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_rj(x, y, z, p))))
            fpm:  0.0744060403350267
            mpm:  0.0744060403350267433941730465496555687553352918016766141924910569924297002569533506124598363
            dpm:  0.0744060403350267433941730465496555687553352918016766141924910569924297002569533506124598363
            gpm:  0.074406040335026743394173046549655568755335291801676614192491056992429700256953350612459836297
            apm: [0.0744060403350267433941730465496555687553352918016766141924910569924297002569533506124598363 +/- 5.70e-92]
        cmath53:  0.0744060390508556
        sflintc:  0.07440604
        dflintc:  0.0744060403350267
        eflintc:  0.074406040335026743392
        qflintc:  0.0744060403350267433941730465496556
        oflintc:  0.0744060403350267433941730465496555687553352918016766141924910569924297
        mflintc:  0.0744060403350267433941730465496555687553352918016766141924910569924297002569533506124598362
        aflintc: [0.074406040335026743394173046549655568755335291801676614192491056992429700256953350612459836 +/- 3.34e-91]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x =5.1+2j;  y = 2.7+2j; z = 1.3+2j; p = 6.4+2j;  gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_rj(x, y, z, p))))
            fpm:  -0.0675655379365139
            mpm:  -0.0675655379365138696754633061979402429837776734682841357675547380010944271350023323418584808
            dpm:  -0.0675655379365138696754633061979402429837776734682841357675547380010944271350023323418584808
            gpm:  -0.067565537936513869675463306197940242983777673468284135767554738001094427135002332341858480805
            apm: [-0.0675655379365138696754633061979402429837776734682841357675547380010944271350023323418584808 +/- 6.18e-92]
        cmath53:  -0.0675655361339475
        sflintc:  -0.06756554
        dflintc:  -0.0675655379365139
        eflintc:  -0.067565537936513869677
        qflintc:  -0.0675655379365138696754633061979402
        oflintc:  -0.067565537936513869675463306197940242983777673468284135767554738001094427
        mflintc:  -0.0675655379365138696754633061979402429837776734682841357675547380010944271350023323418584808
        aflintc: [-0.067565537936513869675463306197940242983777673468284135767554738001094427135002332341858481 +/- 3.10e-91]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D03a_CarlsonRjReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D03b_CarlsonRjCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C01_CarlsonIntegrals/D03_CarlsonRj.cs>`__. 








Carlson symmetric elliptic integral of the second kind, `R_D(x,y,z)`
----------------------------------------------------------------------------------------------

.. method:: ctx.elliptic_rd(x, y, z)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the Carlson symmetric elliptic integral of the second kind,  `R_D(x,y,z) = R_J(x,y,z,z)`, with `z > 0, x, y \ge 0`, at most one of `x, y` may be zero. See also Wikipedia :cite:p:`WikipediaFun154`, NIST :cite:p:`DLMFun154`, BoostMath :cite:p:`BoostFun154`, :cite:t:`Ehrhardt2018` (3.2.2.3), Flint :cite:p:`FlintFun154`, Mpmath :cite:p:`MpmathFun154d`. 



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; y = 2.7; z = 1.3; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rd(x, y, z)))
            fpm:  0.599561454504973
            mpm:  0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068
            dpm:  0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068
            gpm:  0.59956145450497343449459138684638691543188576109180397027471341101262689154588763504617406794
            apm: ([0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068 +/- 3.59e-91], 0)
         math53:  0.599561454504973
          sreal:  0.5995615
          dreal:  0.599561454504973
          ereal:  0.59956145450497343446
          qreal:  0.599561454504973434494591386846387
          oreal:  0.59956145450497343449459138684638691543188576109180397027471341101262689
          mreal:  0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068
         sflint:  0.5995615
         dflint:  0.599561454504973
         eflint:  0.59956145450497343451
         qflint:  0.599561454504973434494591386846387
         oflint:  0.59956145450497343449459138684638691543188576109180397027471341101262689
         mflint:  0.599561454504973434494591386846386915431885761091803970274713411012626891545887635046174068
         aflint: [0.59956145450497343449459138684638691543188576109180397027471341101262689154588763504617407 +/- 2.98e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; z = 1.3+2j;  gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rd(x, y, z)))
            fpm:  (-0.0897631544562476, -0.189488727804841)
            mpm:  (-0.08976315445624765201454616660232400355089, -0.1894887278048410590590189055902419509779)
        cmath53:  (-0.0897631544562477, -0.189488727804841)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; z = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_rd(x, y, z))))
            fpm:  -0.0897631544562476
            mpm:  -0.0897631544562476520145461666023240035508865767548961753841709174170226499432591346556986443
            dpm:  -0.0897631544562476520145461666023240035508865767548961753841709174170226499432591346556986443
            gpm:  -0.089763154456247652014546166602324003550886576754896175384170917417022649943259134655698644303
            apm: [-0.089763154456247652014546166602324003550886576754896175384170917417022649943259134655698644 +/- 4.23e-91]
        cmath53:  -0.0897631544562477
        sflintc:  -0.08976316
        dflintc:  -0.0897631544562476
        eflintc:  -0.089763154456247652019
        qflintc:  -0.089763154456247652014546166602324
        oflintc:  -0.089763154456247652014546166602324003550886576754896175384170917417022649
        mflintc:  -0.0897631544562476520145461666023240035508865767548961753841709174170226499432591346556986443
        aflintc: [-0.089763154456247652014546166602324003550886576754896175384170917417022649943259134655698644 +/- 4.75e-91]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; z = 1.3+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_rd(x, y, z))))
            fpm:  -0.189488727804841
            mpm:  -0.189488727804841059059018905590241950977941195215932987790330699278670562283113704184277324
            dpm:  -0.189488727804841059059018905590241950977941195215932987790330699278670562283113704184277324
            gpm:  -0.18948872780484105905901890559024195097794119521593298779033069927867056228311370418427732401
            apm: [-0.189488727804841059059018905590241950977941195215932987790330699278670562283113704184277324 +/- 3.47e-91]
        cmath53:  -0.189488727804841
        sflintc:  -0.1894887
        dflintc:  -0.189488727804841
        eflintc:  -0.18948872780484105906
        qflintc:  -0.189488727804841059059018905590242
        oflintc:  -0.18948872780484105905901890559024195097794119521593298779033069927867056
        mflintc:  -0.189488727804841059059018905590241950977941195215932987790330699278670562283113704184277324
        aflintc: [-0.189488727804841059059018905590241950977941195215932987790330699278670562283113704184277324 +/- 3.53e-91]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D04a_CarlsonRdReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D04b_CarlsonRdCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C01_CarlsonIntegrals/D04_CarlsonRd.cs>`__. 








Carlson degenerate symmetric elliptic integral of the first kind, `R_C(x,y)`
-------------------------------------------------------------------------------------------------

.. method:: ctx.elliptic_rc(x, y)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the Carlson degenerate symmetric elliptic integral of the first kind, `R_C(x,y) = R_F(x,y,y)`, for `x \ge 0, y \ne 0`. See also Wikipedia :cite:p:`WikipediaFun154`, NIST :cite:p:`DLMFun154`, BoostMath :cite:p:`BoostFun154`, :cite:t:`Ehrhardt2018` (3.2.2.1), Flint :cite:p:`FlintFun154`, Mpmath :cite:p:`MpmathFun154b`. 

    

    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; y = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rc(x, y)))
            fpm:  0.542443519049021
            mpm:  0.542443519049021108409527120866871792671754914444348783296968413054823744075195913976739639
            dpm:  0.542443519049021108409527120866871792671754914444348783296968413054823744075195913976739639
            gpm:  0.54244351904902110840952712086687179267175491444434878329696841305482374407519591397673963904
            apm: ([0.542443519049021108409527120866871792671754914444348783296968413054823744075195913976739639 +/- 2.17e-91], 0)
         math53:  0.542443519049021
          sreal:  0.5424435
          dreal:  0.542443519049021
          ereal:  0.54244351904902110843
          qreal:  0.542443519049021108409527120866872
          oreal:  0.54244351904902110840952712086687179267175491444434878329696841305482375
          mreal:  0.542443519049021108409527120866871792671754914444348783296968413054823744075195913976739639
         sflint:  0.5424435
         dflint:  0.542443519049021
         eflint:  0.54244351904902110843
         qflint:  0.542443519049021108409527120866872
         oflint:  0.54244351904902110840952712086687179267175491444434878329696841305482375
         mflint:  0.542443519049021108409527120866871792671754914444348783296968413054823744075195913976739639
         aflint: [0.542443519049021108409527120866871792671754914444348783296968413054823744075195913976739639 +/- 8.57e-91]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.elliptic_rc(x, y)))
            fpm:  (0.417798027687995, -0.367169982876417)
            mpm:  (0.4177980276879945255418376972076627836295, -0.3671699828764167234833982842431826724982)
        cmath53:  (0.417798027687965, -0.367169982876391)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.elliptic_rc(x, y)))
            fpm:  0.417798027687995
            mpm:  0.417798027687994525541837697207662783629500814728973091422832214781669576212930915073489918
            dpm:  0.417798027687994525541837697207662783629500814728973091422832214781669576212930915073489918
            gpm:  0.417798027687994525541837697207662783629500814728973091422832214781669576212930915073489918
            apm: [0.4177980276879945255418376972076627836295008147289730914228322147816695762129309150734899 +/- 5.41e-89]
        cmath53:  0.417798027687965
        sflintc:  0.417798
        dflintc:  0.417798027687995
        eflintc:  0.41779802768799452554
        qflintc:  0.417798027687994525541837697207663
        oflintc:  0.41779802768799452554183769720766278362950081472897309142283221478166958
        mflintc:  0.417798027687994525541837697207662783629500814728973091422832214781669576212930915073489918
        aflintc: [0.4177980276879945255418376972076627836295008147289730914228322147816695762129309150734899 +/- 4.72e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  y = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.elliptic_rc(x, y)))
            fpm:  -0.367169982876417
            mpm:  -0.367169982876416723483398284243182672498177756840318404994045886721110715493177774023216226
            dpm:  -0.367169982876416723483398284243182672498177756840318404994045886721110715493177774023216226
            gpm:  -0.36716998287641672348339828424318267249817775684031840499404588672111071549317777402321622602
            apm: [-0.3671699828764167234833982842431826724981777568403184049940458867211107154931777740232162 +/- 5.04e-89]
        cmath53:  -0.367169982876391
        sflintc:  -0.36717
        dflintc:  -0.367169982876417
        eflintc:  -0.36716998287641672348
        qflintc:  -0.367169982876416723483398284243183
        oflintc:  -0.36716998287641672348339828424318267249817775684031840499404588672111072
        mflintc:  -0.367169982876416723483398284243182672498177756840318404994045886721110715493177774023216226
        aflintc: [-0.3671699828764167234833982842431826724981777568403184049940458867211107154931777740232162 +/- 4.58e-89]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D05a_CarlsonRcReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B08_EllipticFunctions/C01_CarlsonIntegrals/D05b_CarlsonRcCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B08_EllipticFunctions/C01_CarlsonIntegrals/D05_CarlsonRc.cs>`__. 



