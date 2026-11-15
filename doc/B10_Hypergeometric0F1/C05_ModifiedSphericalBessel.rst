

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Modified spherical Bessel functions
===============================================================================




.. _rst_mpm_bessel_in: 

Modified spherical Bessel function of the first kind, `i_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_in(n, x, scaled=False)

    Returns `i_n(x)`, the modified spherical Bessel function of the first kind. 

    If *scaled* is *True*, then `i_n(x) \cdot \exp(-|\Re(x)|)` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun143`, MathWorld :cite:p:`WolframFun143c`, NIST :cite:p:`DLMFun143`, BoostMath :cite:p:`BoostFun143`, :cite:t:`Ehrhardt2018` (3.1.6.3).

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 

    This function is traditionally defined as `\displaystyle i_n(x) = \sqrt{\tfrac{1}{2}\pi/x} I_{n+\tfrac{1}{2}}(x)`, where `I_n(x)` is a modified Bessel function of the first kind. 

    In XlCalcNet, the definition `\displaystyle i_n(x) = \sqrt{\tfrac{1}{2}\pi} \frac{1}{\sqrt{x}} I_{n+\tfrac{1}{2}}(x)` is used instead, which gives identical results for `\Re(x) \ge 0`, but differs from the "traditional version" along the branch cut of the square root function. This ensures that results for real input and complex input with zero imaginary part are the same. 


    It also ensures that the general definition for complex `n` and complex `x` agrees with the results from the following two Rayleigh-type formulas:


    `\displaystyle i_n(x) = x^n \left(\frac{1}{x}\frac{d}{dx}\right)^n \frac{\sinh(x)}{x}` for integer `n \ge 0` and real or complex `x \ne 0`. Given `i_0(x)` and `i_1(x)`, this Rayleigh-type formula can also be computed recursively as `\displaystyle i_n(x) = \frac{2n-1}{x} i_{n-1}(x) - i_{n-2}(x)` for `n \ge 2`.


    `\displaystyle i_{-n-1}(x) = x^n \left(\frac{1}{x}\frac{d}{dx}\right)^n \frac{\cosh(x)}{x}` for integer `n \ge 0` and real or complex `x \ne 0`. Given `i_0(x)` and `i_1(x)`, this Rayleigh-type formula can also be computed recursively as `\displaystyle i_n(x) = \frac{2n+3}{x} i_{n+1}(x) -  i_{n+2}(x)` for `n \le -1`.

    With `i_0(0) = 1`, `i_n(0) =` NaN for even `n \ne 0`, `i_n(0) = -\infty` for odd `n`, `i_n(-\infty) = i_n(\infty) = 0`, we have the following explicit versions of the Rayleigh-type formulas for `x \ne 0` and `n = -3,-2,-1,0,1,2`:


    .. math:: i_{-3}(x) = \frac{(3 + x^2)\cosh x}{x^3} - \frac{3 \sinh x}{x^2},

    .. math:: i_{-2}(x) = -\frac{\cosh x}{x^2} + \frac{\sinh x}{x},

    .. math:: i_{-1}(x) = \frac{\cosh x}{x},

    .. math:: i_0(x) =  \frac{\sinh x}{x},

    .. math:: i_1(x) = -\frac{\sinh x}{x^2} + \frac{\cosh x}{x},

    .. math:: i_2(x) = \frac{(3 + x^2)\sinh x}{x^3} - \frac{3 \cosh x}{x^2}.



    We also have `i_n(-x) = (-1)^{n} i_{n}(x)` for `x > 0`. Therefore we can calculate `i_n(x)` for any `n \in \mathbb{Z}` and `x \in \mathbb{R}` without resorting to complex functions, using the general definition with `n \ge 0`, always obtaining a real result.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_in(n, x, scaled=False)))
        fpm:  0.0181795206322034
        mpm:  0.0181795206322033890968607961415485548409794641770326031049847877533697124741991231196659823
        dpm:  0.0181795206322033890968607961415485548409794641770326031049847877533697124741991231196659823
        gpm:  0.0181795206322033890968607961415485548409794641770326031049847877533697124741991231196659823
        apm: [0.0181795206322033890968607961415485548409794641770326031049847877533697124741991231196659823 +/- 7.58e-92]
     math53:  0.0181795206322034
      sreal:  0.01817952
      dreal:  0.0181795206322034
      ereal:  0.018179520632203389099
      qreal:  0.0181795206322033890968607961415486
      oreal:  0.018179520632203389096860796141548554840979464177032603104984787753369713
      mreal:  0.0181795206322033890968607961415485548409794641770326031049847877533697124741991231196659823
     sflint:  0.01817952
     dflint:  0.0181795206322034
     eflint:  0.018179520632203389099
     qflint:  0.0181795206322033890968607961415486
     oflint:  0.018179520632203389096860796141548554840979464177032603104984787753369712
     mflint:  0.0181795206322033890968607961415485548409794641770326031049847877533697124741991231196659823
     aflint: [0.018179520632203389096860796141548554840979464177032603104984787753369712474199123119665982 +/- 4.36e-91]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_in(n, x, scaled=False)))
        fpm:  (-0.276988587668791, 0.144011156568703)
        mpm:  (-0.2769885876687905968168557769937428451159, 0.1440111565687033468944386699156567439994)
    cmath53:  (-0.276988587668791, 0.144011156568703)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_bessel_in(n, x, scaled=False))))
        fpm:  -0.276988587668791
        mpm:  -0.276988587668790596816855776993742845115913603603085880177407443620286736043323591707044259
        dpm:  -0.276988587668790596816855776993742845115913603603085880177407443620286736043323591707044259
        gpm:  -0.27698858766879059681685577699374284511591360360308588017740744362028673604332359170704425897
        apm: [-0.2769885876687905968168557769937428451159136036030858801774074436202867360433235917070443 +/- 6.53e-89]
    cmath53:  -0.276988587668791
    sflintc:  -0.2769886
    dflintc:  -0.276988587668791
    eflintc:  -0.27698858766879059685
    qflintc:  -0.276988587668790596816855776993743
    oflintc:  -0.27698858766879059681685577699374284511591360360308588017740744362028674
    mflintc:  -0.276988587668790596816855776993742845115913603603085880177407443620286736043323591707044259
    aflintc: [-0.276988587668790596816855776993742845115913603603085880177407443620286736043323591707044 +/- 3.36e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_bessel_in(n, x, scaled=False))))
        fpm:  0.144011156568703
        mpm:  0.144011156568703346894438669915656743999386235708284695418323844455159630504198435785170196
        dpm:  0.144011156568703346894438669915656743999386235708284695418323844455159630504198435785170196
        gpm:  0.14401115656870334689443866991565674399938623570828469541832384445515963050419843578517019599
        apm: [0.1440111565687033468944386699156567439993862357082846954183238444551596305041984357851702 +/- 2.40e-89]
    cmath53:  0.144011156568703
    sflintc:  0.1440112
    dflintc:  0.144011156568703
    eflintc:  0.14401115656870334688
    qflintc:  0.144011156568703346894438669915657
    oflintc:  0.14401115656870334689443866991565674399938623570828469541832384445515963
    mflintc:  0.144011156568703346894438669915656743999386235708284695418323844455159630504198435785170196
    aflintc: [0.1440111565687033468944386699156567439993862357082846954183238444551596305041984357851702 +/- 6.55e-89]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D01a_SphBesselInReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D01b_SphBesselInCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D01_SphBesselIn.cs>`__. 









|newpage|


.. _rst_mpm_bessel_kn: 

Modified Spherical Bessel function of the second kind, `k_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_kn(n, x, scaled=False)


    Returns `k_n(x)`, the modified spherical Bessel function of the second kind. 

    If *scaled* is *True*, then `k_n(x) \cdot \exp(x)` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun143`, MathWorld :cite:p:`WolframFun143d`, NIST :cite:p:`DLMFun143`, BoostMath :cite:p:`BoostFun143`, :cite:t:`Ehrhardt2018` (3.1.6.5).

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 



    This function is traditionally defined as `\displaystyle k_n(x) = \sqrt{\tfrac{1}{2}\pi/x} K_{n+\tfrac{1}{2}}(x)`, where `K_n(x)` is a modified Bessel function of the first kind. 

    In XlCalcNet, the definition `\displaystyle k_n(x) = \sqrt{\tfrac{1}{2}\pi} \frac{1}{\sqrt{x}} K_{n+\tfrac{1}{2}}(x)` is used instead, which gives identical results for `\Re(x) \ge 0`, but differs from the "traditional version" along the branch cut of the square root function. This ensures that results for real input and complex input with zero imaginary part are the same. 


    It also ensures that the general definition for complex `n` and complex `x` agrees with the results from the following Rayleigh-type formula:


    `\displaystyle k_n(x) = \frac{\pi}{2} (-x)^n \left(\frac{1}{x}\frac{d}{dx}\right)^n \frac{e^{-x}}{x}` for integer `n \ge 0` and real or complex `x \ne 0`. Given `k_0(x)` and `k_1(x)`, this Rayleigh-type formula can also be computed recursively as `\displaystyle k_n(x) = \frac{2n-1}{x} k_{n-1}(x) -  k_{n-2}(x)` for `n \ge 2`.


    With `k_n(0) =` NaN for even `n`, `k_n(0) = +\infty` for odd `n`, `k_n(-\infty) = -\infty`, `k_n(+\infty) = 0`, we have the following explicit versions of the Rayleigh-type formula for `x \ne 0` and `n = 0,1,2`:


    .. math:: k_0(x) = \frac{\pi}{2} \frac{1}{x} e^{-x},

    .. math:: k_1(x) = \frac{\pi}{2} \left( \frac{1}{x^2} + \frac{1}{x} \right) e^{-x},

    .. math:: k_2(x) = \frac{\pi}{2} \left( \frac{3}{x^3} +  \frac{3}{x^2} + \frac{1}{x} \right) e^{-x}.



    We also have `k_{-n}(x) = k_{n}(x)` for `n > 0` and `k_n(-x) = \tfrac{\pi}{2} (i_{n}(x) - i_{-n-1}(x))` for `x > 0`. Therefore we can calculate `k_n(x)` for any `n \in \mathbb{Z}` and `x \in \mathbb{R}` without resorting to complex functions, using the general definition with `n \ge 0`, always obtaining a real result.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_kn(n, x, scaled=False)))
        fpm:  2.60649792875829
        mpm:  2.60649792875829434940081616256432455039634158497301115822478724662076112866833488054835223
        dpm:  2.60649792875829434940081616256432455039634158497301115822478724662076112866833488054835223
        gpm:  2.6064979287582943494008161625643245503963415849730111582247872466207611286683348805483522302
        apm: [2.6064979287582943494008161625643245503963415849730111582247872466207611286683348805483522 +/- 4.02e-89]
     math53:  2.60649792875829
      sreal:  2.606498
      dreal:  2.60649792875829
      ereal:  2.6064979287582943491
      qreal:  2.60649792875829434940081616256432
      oreal:  2.6064979287582943494008161625643245503963415849730111582247872466207611
      mreal:  2.60649792875829434940081616256432455039634158497301115822478724662076112866833488054835223
     sflint:  2.606498
     dflint:  2.60649792875829
     eflint:  2.6064979287582943491
     qflint:  2.60649792875829434940081616256432
     oflint:  2.6064979287582943494008161625643245503963415849730111582247872466207611
     mflint:  2.60649792875829434940081616256432455039634158497301115822478724662076112866833488054835223
     aflint: [2.6064979287582943494008161625643245503963415849730111582247872466207611286683348805483522 +/- 4.79e-89]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_kn(n, x, scaled=False)))
        fpm:  (-0.223371113632498, 0.224464987823346)
        mpm:  (-0.2233711136324982120298467788606189089367, 0.2244649878233460123717533802610726383595)
    cmath53:  (-0.223371113632498, 0.224464987823346)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_bessel_kn(n, x, scaled=False))))
        fpm:  -0.223371113632498
        mpm:  -0.223371113632498212029846778860618908936748312867264060335338986695903028322610686289905967
        dpm:  -0.223371113632498212029846778860618908936748312867264060335338986695903028322610686289905967
        gpm:  -0.223371113632498212029846778860618908936748312867264060335338986695903028322610686289905967
        apm: [-0.2233711136324982120298467788606189089367483128672640603353389866959030283226106862899060 +/- 8.72e-89]
    cmath53:  -0.223371113632498
    sflintc:  -0.2233711
    dflintc:  -0.223371113632498
    eflintc:  -0.22337111363249821201
    qflintc:  -0.223371113632498212029846778860619
    oflintc:  -0.22337111363249821202984677886061890893674831286726406033533898669590303
    mflintc:  -0.223371113632498212029846778860618908936748312867264060335338986695903028322610686289905967
    aflintc: [-0.223371113632498212029846778860618908936748312867264060335338986695903028322610686289906 +/- 2.10e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_bessel_kn(n, x, scaled=False))))
        fpm:  0.224464987823346
        mpm:  0.224464987823346012371753380261072638359484237408201959032845601273315502875889036287093985
        dpm:  0.224464987823346012371753380261072638359484237408201959032845601273315502875889036287093985
        gpm:  0.224464987823346012371753380261072638359484237408201959032845601273315502875889036287093985
        apm: [0.2244649878233460123717533802610726383594842374082019590328456012733155028758890362870940 +/- 5.83e-89]
    cmath53:  0.224464987823346
    sflintc:  0.2244649
    dflintc:  0.224464987823346
    eflintc:  0.22446498782334601233
    qflintc:  0.224464987823346012371753380261072
    oflintc:  0.2244649878233460123717533802610726383594842374082019590328456012733155
    mflintc:  0.224464987823346012371753380261072638359484237408201959032845601273315502875889036287093985
    aflintc: [0.224464987823346012371753380261072638359484237408201959032845601273315502875889036287094 +/- 1.59e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D02a_SphBesselKnReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D02b_SphBesselKnCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D02_SphBesselKn.cs>`__. 









|newpage|


First derivative of the modified spherical Bessel function of the first kind, `i'_n(x)`
------------------------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_in_prime(n, x, scaled=False)

    Returns `i'_n(x)`, the first derivative (with respect to `x`) of `i_n(x)`, the modified spherical Bessel function of the first kind. 

    If *scaled* is *True*, then `i'_n(x) \cdot \exp(-|\Re(x)|)` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun143`, MathWorld :cite:p:`WolframFun143c`, NIST :cite:p:`DLMFun143`, BoostMath :cite:p:`BoostFun143`, :cite:t:`Ehrhardt2018` (3.1.6.3).

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 


    In all cases, the function is calculated as 

    `\displaystyle i'_n(x) = \frac{n i_{n-1}(x) + (n+1)i_{n+1}(x)}{2n+1}` for `|2n+1|>0.1` and `\displaystyle i'_n(x) = i_{n-1}(x) - \frac{n+1}{x} i_{n}(x)` otherwise.


    For `n \in \mathbb{Z}` and `x \in \mathbb{R}` the function is real-valued with  `i'_1(0) = 1/3`, `i'_n(0) = 0` for `n \ge 0` and `n \ne 1`, `i'_{-n}(0) = -\infty` for odd `n>0` and `i'_{-n}(0) =` NaN for even `n>0`. We also have `i_n(-\infty) = 0` and `y_n(\infty) = 0`.






An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_in_prime(n, x, scaled=False)))
        fpm:  0.0373090296802504
        mpm:  0.0373090296802503806918165793306427795723224404075867287695089593674139937767695250587488545
        dpm:  0.0373090296802503806918165793306427795723224404075867287695089593674139937767695250587488545
        gpm:  0.037309029680250380691816579330642779572322440407586728769508959367413993776769525058748854502
        apm: [0.037309029680250380691816579330642779572322440407586728769508959367413993776769525058748855 +/- 6.44e-91]
     math53:  0.0373090296802504
      sreal:  0.03730903
      dreal:  0.0373090296802504
      ereal:  0.037309029680250380696
      qreal:  0.0373090296802503806918165793306428
      oreal:  0.037309029680250380691816579330642779572322440407586728769508959367413994
      mreal:  0.0373090296802503806918165793306427795723224404075867287695089593674139937767695250587488546
     sflint:  0.03730903
     dflint:  0.0373090296802504
     eflint:  0.037309029680250380696
     qflint:  0.0373090296802503806918165793306428
     oflint:  0.037309029680250380691816579330642779572322440407586728769508959367413994
     mflint:  0.0373090296802503806918165793306427795723224404075867287695089593674139937767695250587488546
     aflint: [0.037309029680250380691816579330642779572322440407586728769508959367413993776769525058748854 +/- 8.60e-91]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_in_prime(n, x, scaled=False)))
        fpm:  (-0.0527232113837451, -0.222538576886009)
        mpm:  (-0.05272321138374513763150810324192190409665, -0.2225385768860093735951307906663297089584)
    cmath53:  (-0.0527232113837454, -0.222538576886009)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_bessel_in_prime(n, x, scaled=False))))
        fpm:  -0.0527232113837451
        mpm:  -0.052723211383745137631508103241921904096649854415882412168467412633635651168700894081649277
        dpm:  -0.052723211383745137631508103241921904096649854415882412168467412633635651168700894081649277
        gpm:  -0.052723211383745137631508103241921904096649854415882412168467412633635651168700894081649276998
        apm: [-0.0527232113837451376315081032419219040966498544158824121684674126336356511687008940816493 +/- 6.14e-89]
    cmath53:  -0.0527232113837454
    sflintc:  -0.05272321
    dflintc:  -0.0527232113837451
    eflintc:  -0.052723211383745137629
    qflintc:  -0.0527232113837451376315081032419219
    oflintc:  -0.052723211383745137631508103241921904096649854415882412168467412633635651
    mflintc:  -0.052723211383745137631508103241921904096649854415882412168467412633635651168700894081649277
    aflintc: [-0.052723211383745137631508103241921904096649854415882412168467412633635651168700894081649 +/- 3.95e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_bessel_in_prime(n, x, scaled=False))))
        fpm:  -0.222538576886009
        mpm:  -0.222538576886009373595130790666329708958439079365061107173535204475273987255141071327450233
        dpm:  -0.222538576886009373595130790666329708958439079365061107173535204475273987255141071327450233
        gpm:  -0.22253857688600937359513079066632970895843907936506110717353520447527398725514107132745023299
        apm: [-0.2225385768860093735951307906663297089584390793650611071735352044752739872551410713274502 +/- 6.89e-89]
    cmath53:  -0.222538576886009
    sflintc:  -0.2225385
    dflintc:  -0.222538576886009
    eflintc:  -0.22253857688600937354
    qflintc:  -0.22253857688600937359513079066633
    oflintc:  -0.22253857688600937359513079066632970895843907936506110717353520447527399
    mflintc:  -0.222538576886009373595130790666329708958439079365061107173535204475273987255141071327450232
    aflintc: [-0.222538576886009373595130790666329708958439079365061107173535204475273987255141071327450 +/- 3.47e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D03a_SphBesselInRealPrime.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D03b_SphBesselInCplxPrime.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D03_SphBesselInPrime.cs>`__. 









|newpage|


First derivative of the modified spherical Bessel function of the second kind, `k'_n(x)`
-------------------------------------------------------------------------------------------------

.. method:: ctx.sph_bessel_kn_prime(n, x, scaled=False)

    Returns `k'_n(x)`, the first derivative (with respect to `x`) of `k_n(x)`, the modified spherical Bessel function of the second kind.  

    If *scaled* is *True*, then `K_{\nu}(x) \cdot \exp(x)` is returned.

    See also  Wikipedia :cite:p:`WikipediaFun143`, MathWorld :cite:p:`WolframFun143d`, NIST :cite:p:`DLMFun143`, BoostMath :cite:p:`BoostFun143`, :cite:t:`Ehrhardt2018` (3.1.6.5).

    Here `n` and `x` are, in general, complex numbers. However, if ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `n \in \mathbb{Z}` and `x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `n \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `n, x \in \mathbb{C}` is accepted. 


    In all cases, the function is calculated as 

    `\displaystyle k'_n(x) = -\frac{n k_{n-1}(x) + (n+1)k_{n+1}(x)}{2n+1}` for `|2n+1|>0.1` and `\displaystyle k'_n(x) = k_{n-1}(x) - \frac{n+1}{x} k_{n}(x)` otherwise.

    For `n \in \mathbb{Z}` and `x \in \mathbb{R}` the function is real-valued with `k'_{n}(0) = -\infty` for even `n>0` and odd `n<0` and `k'_{n}(0) =` NaN for odd `n>0` and even `n<0`. We also have `k_n(-\infty) = 0` and `y_n(\infty) = 0`.





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_kn_prime(n, x, scaled=False)))
        fpm:  -6.5032979123119
        mpm:  -6.50329791231190087945860036626771835642271406088927210094299129102645360480451567953873388
        dpm:  -6.50329791231190087945860036626771835642271406088927210094299129102645360480451567953873388
        gpm:  -6.5032979123119008794586003662677183564227140608892721009429912910264536048045156795387338803
        apm: [-6.5032979123119008794586003662677183564227140608892721009429912910264536048045156795387339 +/- 5.11e-89]
     math53:  -6.5032979123119
      sreal:  -6.503297
      dreal:  -6.50329791231189
      ereal:  -6.5032979123119008789
      qreal:  -6.50329791231190087945860036626772
      oreal:  -6.5032979123119008794586003662677183564227140608892721009429912910264534
      mreal:  -6.50329791231190087945860036626771835642271406088927210094299129102645360480451567953873387
     sflint:  -6.503297
     dflint:  -6.5032979123119
     eflint:  -6.5032979123119008789
     qflint:  -6.50329791231190087945860036626772
     oflint:  -6.5032979123119008794586003662677183564227140608892721009429912910264536
     mflint:  -6.50329791231190087945860036626771835642271406088927210094299129102645360480451567953873387
     aflint: [-6.503297912311900879458600366267718356422714060889272100942991291026453604804515679538734 +/- 1.95e-88]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sph_bessel_kn_prime(n, x, scaled=False)))
        fpm:  (0.192416184397702, -0.517195536499724)
        mpm:  (0.1924161843977021824790795227952281325406, -0.5171955364997235543741233079526138661157)
    cmath53:  (0.192416184397702, -0.517195536499723)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sph_bessel_kn_prime(n, x, scaled=False))))
        fpm:  0.192416184397702
        mpm:  0.192416184397702182479079522795228132540640260775791700888558137185369276306046236523106842
        dpm:  0.192416184397702182479079522795228132540640260775791700888558137185369276306046236523106842
        gpm:  0.19241618439770218247907952279522813254064026077579170088855813718536927630604623652310684199
        apm: [0.192416184397702182479079522795228132540640260775791700888558137185369276306046236523107 +/- 2.43e-88]
    cmath53:  0.192416184397702
    sflintc:  0.1924162
    dflintc:  0.192416184397702
    eflintc:  0.19241618439770218249
    qflintc:  0.192416184397702182479079522795228
    oflintc:  0.19241618439770218247907952279522813254064026077579170088855813718536928
    mflintc:  0.192416184397702182479079522795228132540640260775791700888558137185369276306046236523106842
    aflintc: [0.192416184397702182479079522795228132540640260775791700888558137185369276306046236523107 +/- 4.37e-88]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.sph_bessel_kn_prime(n, x, scaled=False))))
        fpm:  -0.517195536499724
        mpm:  -0.517195536499723554374123307952613866115729939087862214986628012079504700328411029023361957
        dpm:  -0.517195536499723554374123307952613866115729939087862214986628012079504700328411029023361957
        gpm:  -0.51719553649972355437412330795261386611572993908786221498662801207950470032841102902336195703
        apm: [-0.517195536499723554374123307952613866115729939087862214986628012079504700328411029023362 +/- 1.27e-88]
    cmath53:  -0.517195536499723
    sflintc:  -0.5171954
    dflintc:  -0.517195536499724
    eflintc:  -0.51719553649972355429
    qflintc:  -0.517195536499723554374123307952614
    oflintc:  -0.5171955364997235543741233079526138661157299390878622149866280120795047
    mflintc:  -0.517195536499723554374123307952613866115729939087862214986628012079504700328411029023361956
    aflintc: [-0.517195536499723554374123307952613866115729939087862214986628012079504700328411029023362 +/- 3.18e-88]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D04a_SphBesselKnRealPrime.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D04b_SphBesselKnCplxPrime.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D04_SphBesselKnPrime.cs>`__. 









|newpage|

Bessel polynomials `y_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.besselpoly(n,x)

    Returns `y_n(x)`, the Bessel polynomial of order `n`.

    For `n \in \mathbb{Z}` and `x \in \mathbb{R}` the function can be defined in terms of the modified spherical Bessel function of the second kind, `k_n(x)`:

    .. math :: y_{n}(x) = 2{\pi}^{-1} x^{-1} e^{1/x} k_{n}\left(x^{-1}\right), \quad n \ge 0, 

    and `y_{-n}(x) =  y_{n-1}(x)` for negative order.

    The Bessel polynomial may also be defined by a recursion formula:

    .. math::
       :nowrap:

       \begin{eqnarray}
        y_0 (x) & = & 1 \\
        y_1 (x) & = & x + 1 \nonumber \\ 
        y_n (x)& = & (2n - 1) x y_{n-1}(x) + y_{n-2}(x).  \nonumber
       \end{eqnarray}




    The function can be generalized to arbitrary complex `n` and `x` by expressing it in  terms of Tricomi's confluent hypergeometric function, `U(a,b;x)`:

    .. math :: y_{n}(x) = 2^{n+1} \left( \frac{1}{x} \right)^{n+1} U\left(n+1, 2n+2; \frac{2}{x}\right), x \ne 0

    and the limit (if it exists) for `x = 0`.


    See also   :cite:t:`Ehrhardt2018` (3.7.19).

    See also: https://en.wikipedia.org/wiki/Bessel_polynomials

    See also: https://dlmf.nist.gov/18.34

    See also: https://mathworld.wolfram.com/BesselPolynomial.html





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.besselpoly(n, x)))
        fpm:  194892.15565
        mpm:  194892.15565
        dpm:  194892.15565
        gpm:  194892.15565000000000000000000000000000000000000000000000000000000000000000000000000000000002
        apm: [194892.15565000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 2.47e-84]
     math53:  194892.15565
      sreal:  194892.2
      dreal:  194892.15565
      ereal:  194892.15565000000001
      qreal:  194892.15565
      oreal:  194892.15565000000000000000000000000000000000000000000000000000000000065
      mreal:  194892.15565
     sflint:  194892.2
     dflint:  194892.15565
     eflint:  194892.15565000000001
     qflint:  194892.15565
     oflint:  194892.15565
     mflint:  194892.15565
     aflint: [194892.15565000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 3.49e-84]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.besselpoly(n, x)))
        fpm:  (-18080.8447396735, 15195.6438497887)
        mpm:  (-18080.84473967350077094662760600256875237, 15195.64384978870116724371092084173711506)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.besselpoly(n, x))))
        fpm:  -18080.8447396735
        mpm:  -18080.8447396735007709466276060025687523724791513155602737274364750975903286702986862471842
        dpm:  -18080.8447396735007709466276060025687523724791513155602737274364750975903286702986862471842
        gpm:  -18080.844739673500770946627606002568752372479151315560273727436475097590328670298686247184201
        apm: [-18080.84473967350077094662760600256875237247915131556027372743647509759032867029868624718 +/- 6.45e-84]
    cmath53:  NaN
    sflintc:  -18080.84
    dflintc:  -18080.8447396735
    eflintc:  -18080.844739673500765
    qflintc:  -18080.8447396735007709466276060025
    oflintc:  -18080.84473967350077094662760600256875237247915131556027372743647509759
    mflintc:  -18080.8447396735007709466276060025687523724791513155602737274364750975903286702986862471841
    aflintc: [-18080.8447396735007709466276060025687523724791513155602737274364750975903286702986862472 +/- 2.25e-83]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.besselpoly(n, x))))
        fpm:  15195.6438497887
        mpm:  15195.6438497887011672437109208417371150647811095001683415231154254378549005113652833198193
        dpm:  15195.6438497887011672437109208417371150647811095001683415231154254378549005113652833198193
        gpm:  15195.643849788701167243710920841737115064781109500168341523115425437854900511365283319819301
        apm: [15195.64384978870116724371092084173711506478110950016834152311542543785490051136528331982 +/- 2.38e-84]
    cmath53:  NaN
    sflintc:  15195.64
    dflintc:  15195.6438497887
    eflintc:  15195.643849788701165
    qflintc:  15195.6438497887011672437109208417
    oflintc:  15195.643849788701167243710920841737115064781109500168341523115425437855
    mflintc:  15195.6438497887011672437109208417371150647811095001683415231154254378549005113652833198193
    aflintc: [15195.64384978870116724371092084173711506478110950016834152311542543785490051136528331982 +/- 5.24e-84]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D05a_BesselPolynomialsReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D05b_BesselPolynomialsCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D05_BesselPolynomials.cs>`__. 






        


|newpage|

Reverse Bessel polynomials `\theta_n(x)`
-------------------------------------------------------------------------------

.. method:: ctx.besseltheta(n,x)

    Returns `\theta_n(x)`, the reverse Bessel polynomial of order `n`.

    For `n \in \mathbb{Z}` and `x \in \mathbb{R}` the function can be defined in terms of the modified spherical Bessel function of the second kind, `k_n(x)`:

    .. math :: \theta_{n}(x) = 2{\pi}^{-1} x^{n+1} e^x k_{n}(x), \quad n \ge 0, 

    and `\theta_{-n}(x) = x^{-n} y_{n-1}(1/x)` for negative order, where `y_n(x)` is the Bessel polynomial.

    The reverse Bessel polynomial may also be defined by a recursion formula:

    .. math::
       :nowrap:

       \begin{eqnarray}
        \theta_0 (x) & = & 1 \\
        \theta_1 (x) & = & x + 1 \nonumber \\ 
        \theta_n (x)& = & (2n - 1) \theta_{n-1}(x) + x^2 \theta_{n-2}(x).  \nonumber
       \end{eqnarray}



    The function can be generalized to arbitrary complex `n` and `x` by expressing it in  terms of Tricomi's confluent hypergeometric function, `U(a,b;x)`:

    .. math :: \theta_{n}(x) = 2^{n+1} x^{2n+1} U\left(n+1, 2n+2, 2x \right), x \ne 0

    and the limit (if it exists) for `x = 0`.



    See also: https://en.wikipedia.org/wiki/Bessel_polynomials

    See also: https://dlmf.nist.gov/18.34





An example with real input:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = 5; x = 2.7; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.besseltheta(n, x)))
        fpm:  9565.66557
        mpm:  9565.66557
        dpm:  9565.66557
        gpm:  9565.6655699999999999999999999999999999999999999999999999999999999999999999999999999999999998
        apm: [9565.665570000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 9.86e-86]
     math53:  9565.66557
      sreal:  9565.665
      dreal:  9565.66557
      ereal:  9565.6655700000000007
      qreal:  9565.66557
      oreal:  9565.6655699999999999999999999999999999999999999999999999999999999999999
      mreal:  9565.66557
     sflint:  9565.666
     dflint:  9565.66557
     eflint:  9565.6655700000000007
     qflint:  9565.66557
     oflint:  9565.66557
     mflint:  9565.66557
     aflint: [9565.665570000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 2.54e-85]



An example with complex input, using C\#-style formatting for complex numbers for the result 

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(40)
    >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.besseltheta(n, x)))
        fpm:  (-0.00350662647022136, 0.0205506678930004)
        mpm:  (-0.003506626470221362429823061054550891684568, 0.02055066789300040898769985471173826668149)



An example with the same complex input as above, showing only the real part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.besseltheta(n, x))))
        fpm:  -0.00350662647022136
        mpm:  -0.0035066264702213624298230610545508916845673406092448933712585462861777348304305622089450032
        dpm:  -0.0035066264702213624298230610545508916845673406092448933712585462861777348304305622089450032
        gpm:  -0.0035066264702213624298230610545508916845673406092448933712585462861777348304305622089450031999
        apm: [-0.00350662647022136242982306105455089168456734060924489337125854628617773483043056220894500 +/- 7.01e-90]
    cmath53:  NaN
    sflintc:  -0.00350663
    dflintc:  -0.00350662647022136
    eflintc:  -0.003506626470221362433
    qflintc:  -0.0035066264702213624298230610545509
    oflintc:  -0.0035066264702213624298230610545508916845673406092448933712585462861777348
    mflintc:  -0.00350662647022136242982306105455089168456734060924489337125854628617773483043056220894500324
    aflintc: [-0.00350662647022136242982306105455089168456734060924489337125854628617773483043056220894500 +/- 6.93e-90]


An example with the same complex input as above, showing only the imaginary part of the result:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> n = -5.1;  x = 2.7+2j; gui.setdps(90)
    >>> for ctx in gui.ctxlist_noboost_cplx: 
    ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.besseltheta(n, x))))
        fpm:  0.0205506678930004
        mpm:  0.0205506678930004089876998547117382666814921435375181969651990879035735730439882632838685818
        dpm:  0.0205506678930004089876998547117382666814921435375181969651990879035735730439882632838685818
        gpm:  0.020550667893000408987699854711738266681492143537518196965199087903573573043988263283868581801
        apm: [0.02055066789300040898769985471173826668149214353751819696519908790357357304398826328386858 +/- 6.36e-90]
    cmath53:  NaN
    sflintc:  0.02055067
    dflintc:  0.0205506678930004
    eflintc:  0.020550667893000408985
    qflintc:  0.0205506678930004089876998547117383
    oflintc:  0.020550667893000408987699854711738266681492143537518196965199087903573573
    mflintc:  0.0205506678930004089876998547117382666814921435375181969651990879035735730439882632838685818
    aflintc: [0.02055066789300040898769985471173826668149214353751819696519908790357357304398826328386858 +/- 6.14e-90]


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D06a_ReverseBesselPolyReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D05b_BesselPolynomialsCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C05_ModifiedSphericalBessel/D06b_ReverseBesselPolyCplx.py>`__. 








