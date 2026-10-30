

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />



Complex components
===============================================================================




Absolute value of a real or complex number
----------------------------------------------

.. method:: ctx.abs(x)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxcpp`` or ``ctxflint``.

    Returns the absolute value of `x`, `|x|`. 



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.abs(x)))
            fpm:  5.1
            mpm:  5.1
            dpm:  5.1
            ipm: [5.0999999999999999999999999999999999999999999999999999999999999999999999999999999999999999992145,
                  5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001964]
            gpm:  5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002
            apm: [5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.77e-90]
         math53:  5.1
          sreal:  5.1
          dreal:  5.1
          ereal:  5.0999999999999999999
          qreal:  5.1
          oreal:  5.1
          mreal:  5.1
         sflint:  5.1
         dflint:  5.1
         eflint:  5.0999999999999999999
         qflint:  5.1
         oflint:  5.1
         mflint:  5.1
         aflint: [5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.58e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.abs(x)))
            fpm:  5.47813836992094
            mpm:  5.4781383699209351022648364340189282337545849763702
        cmath53:  5.47813836992093
          qcplx:  5.47813836992093510226483643401893



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.abs(x))))
            fpm:  5.47813836992094
            mpm:  5.47813836992093510226483643401892823375458497637021084486761170937337176722073409530758203
            dpm:  5.47813836992093510226483643401892823375458497637021084486761170937337176722073409530758203
            ipm: [5.4781383699209351022648364340189282337545849763702108448676117093733717672207340953075820327435,
                  5.4781383699209351022648364340189282337545849763702108448676117093733717672207340953075820347071]
            gpm:  5.4781383699209351022648364340189282337545849763702108448676117093733717672207340953075820347
            apm: [5.47813836992093510226483643401892823375458497637021084486761170937337176722073409530758203 +/- 4.67e-90]
        cmath53:  5.47813836992093
          scplx:  5.478138
          dcplx:  5.47813836992093
          ecplx:  5.4781383699209351022
          qcplx:  5.47813836992093510226483643401893
          ocplx:  5.4781383699209351022648364340189282337545849763702108448676117093733718
          mcplx:  5.47813836992093510226483643401892823375458497637021084486761170937337176722073409530758203
        sflintc:  5.478138
        dflintc:  5.47813836992093
        eflintc:  5.4781383699209351022
        qflintc:  5.47813836992093510226483643401893
        oflintc:  5.4781383699209351022648364340189282337545849763702108448676117093733718
        mflintc:  5.47813836992093510226483643401892823375458497637021084486761170937337176722073409530758203
        aflintc: [5.47813836992093510226483643401892823375458497637021084486761170937337176722073409530758203 +/- 6.52e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.abs(x))))
            fpm:  0
            mpm:  0.0
            dpm:  0
            ipm: [0.0,
                  0.0]
            gpm:  0.0
            apm: 0
        cmath53:  0
          scplx:  0
          dcplx:  0
          ecplx:  0
          qcplx:  0
          ocplx:  0
          mcplx:  0
        sflintc:  0
        dflintc:  0
        eflintc:  0
        qflintc:  0
        oflintc:  0
        mflintc:  0
        aflintc:  0






.. method:: ctx.fabs(x)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxcpp``. This is an alias of ``ctx.abs(x)``.




Sign of a real or complex number
----------------------------------------------

.. method:: ctx.sign(x)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxcpp``.

    Returns the sign of `x`, defined as `\mathrm{sign}(x) = x / |x|`
    (with the special case `\mathrm{sign}(0) = 0`):


    See also: https://en.wikipedia.org/wiki/Sign_function



    Note that the sign function is also defined for complex numbers,
    for which it gives the projection onto the unit circle:



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sign(x)))
            fpm:  -1
            mpm:  -1.0
            dpm:  -1
            ipm: [-1.0,
                  -1.0]
            gpm:  -1.0
            apm: [-1.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 3.86e-91]
         math53:  -1
          sreal:  -1
          dreal:  -1
          ereal:  -1
          qreal:  -1
          oreal:  -1
          mreal:  -1
         sflint:  -1
         dflint:  -1
         eflint:  -1
         qflint:  -1
         oflint:  -1
         mflint:  -1
         aflint:  -1.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sign(x)))
            fpm:  (-0.930973198487063, 0.365087528818456)
            mpm:  (-0.9309731984870632796251471447349728088020121086134, 0.36508752881845618808829299793528345443216161122094)
        cmath53:  (-0.930973198487063, 0.365087528818456)
          qcplx:  (-0.930973198487063279625147144734973, 0.365087528818456188088292997935283)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sign(x))))
            fpm:  -0.930973198487063
            mpm:  -0.930973198487063279625147144734972808802012108613398044279400856974481706525349679642408143
            dpm:  -0.930973198487063279625147144734972808802012108613398044279400856974481706525349679642408144
            ipm: [-0.93097319848706327962514714473497280880201210861339804427940085697448170652534967964240814371239,
                  -0.93097319848706327962514714473497280880201210861339804427940085697448170652534967964240814248511]
            gpm:  -0.93097319848706327962514714473497280880201210861339804427940085697448170652534967964240814298
            apm: [-0.930973198487063279625147144734972808802012108613398044279400856974481706525349679642408143 +/- 7.27e-91]
        cmath53:  -0.930973198487063
          scplx:  -0.9309732
          dcplx:  -0.930973198487063
          ecplx:  -0.93097319848706327962
          qcplx:  -0.930973198487063279625147144734973
          ocplx:  -0.9309731984870632796251471447349728088020121086133980442794008569744817
          mcplx:  -0.930973198487063279625147144734972808802012108613398044279400856974481706525349679642408143
        sflintc:  -0.9309732
        dflintc:  -0.930973198487063
        eflintc:  -0.93097319848706327962
        qflintc:  -0.930973198487063279625147144734973
        oflintc:  -0.9309731984870632796251471447349728088020121086133980442794008569744817
        mflintc:  -0.930973198487063279625147144734972808802012108613398044279400856974481706525349679642408143
        aflintc: [-0.93097319848706327962514714473497280880201210861339804427940085697448170652534967964240814 +/- 4.67e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.sign(x))))
            fpm:  0.365087528818456
            mpm:  0.365087528818456188088292997935283454432161611220940409521333669401757531970725364565650252
            dpm:  0.365087528818456188088292997935283454432161611220940409521333669401757531970725364565650253
            ipm: [0.36508752881845618808829299793528345443216161122094040952133366940175753197072536456565025196698,
                  0.36508752881845618808829299793528345443216161122094040952133366940175753197072536456565025245789]
            gpm:  0.36508752881845618808829299793528345443216161122094040952133366940175753197072536456565025215
            apm: [0.365087528818456188088292997935283454432161611220940409521333669401757531970725364565650252 +/- 4.64e-91]
        cmath53:  0.365087528818456
          scplx:  0.3650875
          dcplx:  0.365087528818456
          ecplx:  0.36508752881845618811
          qcplx:  0.365087528818456188088292997935283
          ocplx:  0.36508752881845618808829299793528345443216161122094040952133366940175753
          mcplx:  0.365087528818456188088292997935283454432161611220940409521333669401757531970725364565650252
        sflintc:  0.3650875
        dflintc:  0.365087528818456
        eflintc:  0.36508752881845618811
        qflintc:  0.365087528818456188088292997935283
        oflintc:  0.36508752881845618808829299793528345443216161122094040952133366940175753
        mflintc:  0.365087528818456188088292997935283454432161611220940409521333669401757531970725364565650252
        aflintc: [0.365087528818456188088292997935283454432161611220940409521333669401757531970725364565650252 +/- 8.98e-91]









Real part of a real or complex number
----------------------------------------------

.. method:: ctx.real(x)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxcpp``.

    Returns the real part of `x`, `\Re(x)`.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.real(x)))
            fpm:  -5.1
            mpm:  -5.1
            dpm:  -5.1
            ipm: [-5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001964,
                  -5.0999999999999999999999999999999999999999999999999999999999999999999999999999999999999999992145]
            gpm:  -5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002
            apm: [-5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.77e-90]
         math53:  -5.1
          sreal:  -5.1
          dreal:  -5.1
          ereal:  -5.0999999999999999999
          qreal:  -5.1
          oreal:  -5.1
          mreal:  -5.1
         sflint:  -5.1
         dflint:  -5.1
         eflint:  -5.0999999999999999999
         qflint:  -5.1
         oflint:  -5.1
         mflint:  -5.1
         aflint: [-5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.58e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.real(x)))
            fpm:  -5.1
            mpm:  -5.1
        cmath53:  -5.1
          qcplx:  -5.1



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.real(x))))
            fpm:  -5.1
            mpm:  -5.1
            dpm:  -5.1
            ipm: [-5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001964,
                  -5.0999999999999999999999999999999999999999999999999999999999999999999999999999999999999999992145]
            gpm:  -5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002
            apm: [-5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.77e-90]
        cmath53:  -5.1
          scplx:  -5.1
          dcplx:  -5.1
          ecplx:  -5.0999999999999999999
          qcplx:  -5.1
          ocplx:  -5.1
          mcplx:  -5.1
        sflintc:  -5.1
        dflintc:  -5.1
        eflintc:  -5.0999999999999999999
        qflintc:  -5.1
        oflintc:  -5.1
        mflintc:  -5.1
        aflintc: [-5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.58e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.real(x))))
            fpm:  0
            mpm:  0.0
            dpm:  0
            ipm: [0.0,
                  0.0]
            gpm:  0.0
            apm: 0
        cmath53:  0
          scplx:  0
          dcplx:  0
          ecplx:  0
          qcplx:  0
          ocplx:  0
          mcplx:  0
        sflintc:  0
        dflintc:  0
        eflintc:  0
        qflintc:  0
        oflintc:  0
        mflintc:  0
        aflintc:  0









Imaginary part of a real or complex number
----------------------------------------------

.. method:: ctx.imag(x)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxcpp``.

    Returns the imaginary part of `x`, `\Im(x)`.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.imag(x)))
            fpm:  0
            mpm:  0.0
            dpm:  0
            ipm: [0.0,
                  0.0]
            gpm:  0.0
            apm: 0
         math53:  0
          sreal:  0
          dreal:  0
          ereal:  0
          qreal:  0
          oreal:  0
          mreal:  0
         sflint:  0
         dflint:  0
         eflint:  0
         qflint:  0
         oflint:  0
         mflint:  0
         aflint:  0



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.imag(x)))
            fpm:  2
            mpm:  2.0
        cmath53:  2
          qcplx:  2



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.imag(x))))
            fpm:  2
            mpm:  2.0
            dpm:  2.0
            ipm: [2.0,
                  2.0]
            gpm:  2.0
            apm: 2.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
        cmath53:  2
          scplx:  2
          dcplx:  2
          ecplx:  2
          qcplx:  2
          ocplx:  2
          mcplx:  2
        sflintc:  2
        dflintc:  2
        eflintc:  2
        qflintc:  2
        oflintc:  2
        mflintc:  2
        aflintc:  2.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.imag(x))))
            fpm:  0
            mpm:  0.0
            dpm:  0
            ipm: [0.0,
                  0.0]
            gpm:  0.0
            apm: 0
        cmath53:  0
          scplx:  0
          dcplx:  0
          ecplx:  0
          qcplx:  0
          ocplx:  0
          mcplx:  0
        sflintc:  0
        dflintc:  0
        eflintc:  0
        qflintc:  0
        oflintc:  0
        mflintc:  0
        aflintc:  0









Phase (or argument) of a real or complex number
----------------------------------------------------------

.. method:: ctx.phase(x)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxcpp``.


    Computes the complex argument (phase) of `x`, defined as the signed angle between the positive real axis and `x` in the complex plane: The angle is defined to satisfy `-\pi < \arg(x) \le \pi` and with the sign convention that a nonnegative imaginary part results in a nonnegative argument.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.phase(x)))
            fpm:  0
            mpm:  3.14159265358979323846264338327950288419716939937510582097494459230781640628620899862803483
            dpm:  3.14159265358979323846264338327950288419716939937510582097494459230781640628620899862803483
            ipm: [3.1415926535897932384626433832795028841971693993751058209749445923078164062862089986280348253398,
                  3.1415926535897932384626433832795028841971693993751058209749445923078164062862089986280348258307]
            gpm:  3.1415926535897932384626433832795028841971693993751058209749445923078164062862089986280348253
            apm: [3.14159265358979323846264338327950288419716939937510582097494459230781640628620899862803483 +/- 4.91e-90]
         math53:  3.14159265358979
          sreal:  3.141593
          dreal:  3.14159265358979
          ereal:  3.1415926535897932385
          qreal:  3.1415926535897932384626433832795
          oreal:  3.1415926535897932384626433832795028841971693993751058209749445923078164
          mreal:  3.14159265358979323846264338327950288419716939937510582097494459230781640628620899862803482
         sflint:  3.141593
         dflint:  3.14159265358979
         eflint:  3.1415926535897932385
         qflint:  3.1415926535897932384626433832795
         oflint:  3.1415926535897932384626433832795028841971693993751058209749445923078164
         mflint:  3.14159265358979323846264338327950288419716939937510582097494459230781640628620899862803482
         aflint: [3.14159265358979323846264338327950288419716939937510582097494459230781640628620899862803482 +/- 5.84e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53, qcplx]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.phase(x)))
            fpm:  2.76786583362424
            mpm:  2.7678658336242397790155820717594347757896731382865
        cmath53:  2.76786583362424
          qcplx:  2.76786583362423977901558207175943



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.phase(x))))
            fpm:  2.76786583362424
            mpm:  2.76786583362423977901558207175943477578967313828649465952475940574898154799554287886905002
            dpm:  2.76786583362423977901558207175943477578967313828649465952475940574898154799554287886905002
            ipm: [2.7678658336242397790155820717594347757896731382864946595247594057489815479955428788690500219374,
                  2.7678658336242397790155820717594347757896731382864946595247594057489815479955428788690500224283]
            gpm:  2.7678658336242397790155820717594347757896731382864946595247594057489815479955428788690500219
            apm: [2.76786583362423977901558207175943477578967313828649465952475940574898154799554287886905002 +/- 2.38e-90]
        cmath53:  2.76786583362424
          scplx:  2.767866
          dcplx:  2.76786583362424
          ecplx:  2.767865833624239779
          qcplx:  2.76786583362423977901558207175943
          ocplx:  2.7678658336242397790155820717594347757896731382864946595247594057489815
          mcplx:  2.76786583362423977901558207175943477578967313828649465952475940574898154799554287886905002
        sflintc:  2.767866
        dflintc:  2.76786583362424
        eflintc:  2.767865833624239779
        qflintc:  2.76786583362423977901558207175943
        oflintc:  2.7678658336242397790155820717594347757896731382864946595247594057489815
        mflintc:  2.76786583362423977901558207175943477578967313828649465952475940574898154799554287886905002
        aflintc: [2.76786583362423977901558207175943477578967313828649465952475940574898154799554287886905002 +/- 2.98e-90]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.phase(x))))
            fpm:  0
            mpm:  0.0
            dpm:  0
            ipm: [0.0,
                  0.0]
            gpm:  0.0
            apm: 0
        cmath53:  0
          scplx:  0
          dcplx:  0
          ecplx:  0
          qcplx:  0
          ocplx:  0
          mcplx:  0
        sflintc:  0
        dflintc:  0
        eflintc:  0
        qflintc:  0
        oflintc:  0
        mflintc:  0
        aflintc:  0










Conjugate of a real or complex number
----------------------------------------------------------

.. method:: ctx.conj(x)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxcpp``.

    Returns the complex conjugate of `x`, `\overline{x}`. 



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; dps = 90
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.conj(x)))
            fpm:  -5.1
            mpm:  -5.1
            dpm:  -5.1
            ipm: [-5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001964,
                  -5.0999999999999999999999999999999999999999999999999999999999999999999999999999999999999999992145]
            gpm:  -5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002
            apm: [-5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.77e-90]
         math53:  -5.1
          sreal:  -5.1
          dreal:  -5.1
          ereal:  -5.0999999999999999999
          qreal:  -5.1
          oreal:  -5.1
          mreal:  -5.1
         sflint:  -5.1
         dflint:  -5.1
         eflint:  -5.0999999999999999999
         qflint:  -5.1
         oflint:  -5.1
         mflint:  -5.1
         aflint: [-5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.58e-90]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(50)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.conj(x))))
            fpm:  (-5.1, -2)
            mpm:  (-5.1, -2.0)
        cmath53:  (-5.1, -2)
          qcplx:  (-5.1, -2)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.conj(x))))
            fpm:  -5.1
            mpm:  -5.1
            dpm:  -5.1
            ipm: [-5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001964,
                  -5.0999999999999999999999999999999999999999999999999999999999999999999999999999999999999999992145]
            gpm:  -5.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002
            apm: [-5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.77e-90]
        cmath53:  -5.1
          scplx:  -5.1
          dcplx:  -5.1
          ecplx:  -5.0999999999999999999
          qcplx:  -5.1
          ocplx:  -5.1
          mcplx:  -5.1
        sflintc:  -5.1
        dflintc:  -5.1
        eflintc:  -5.0999999999999999999
        qflintc:  -5.1
        oflintc:  -5.1
        mflintc:  -5.1
        aflintc: [-5.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.58e-90]

    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.conj(x))))
            fpm:  -2
            mpm:  -2.0
            dpm:  -2.0
            ipm: [-2.0,
                  -2.0]
            gpm:  -2.0
            apm: -2.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
        cmath53:  -2
          scplx:  -2
          dcplx:  -2
          ecplx:  -2
          qcplx:  -2
          ocplx:  -2
          mcplx:  -2
        sflintc:  -2
        dflintc:  -2
        eflintc:  -2
        qflintc:  -2
        oflintc:  -2
        mflintc:  -2
        aflintc:  -2.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000








Polar representation of a real or complex number
----------------------------------------------------------

.. method:: ctx.polar(z)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxcpp``.

    Returns the polar representation of the complex number `z` as a pair `(r, \phi)` such that `z = r e^{i \phi}`:
    
    See also  Mpmath :cite:p:`MpmathFun918`.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> -5.1; gui.setdps(35)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ', ctx.polar(x))
        fpm:  (5.1, 3.141592653589793)
        mpm:  (mpf('5.0999999999999999999999999999999999988'), mpf('3.1415926535897932384626433832795028847'))
        dpm:  (Decimal('5.1'), Decimal('3.1415926535897932384626433832795029'))
        ipm:  (mpi('5.0999999999999999999999999999999999988', '5.1000000000000000000000000000000000048'), mpi('3.1415926535897932384626433832795028817', '3.1415926535897932384626433832795028847'))
        gpm:  (5.1, mpfr('3.1415926535897932384626433832795028847',120))
        apm:  ([5.1000000000000000000000000000000000 +/- 7.23e-36], [3.1415926535897932384626433832795029 +/- 1.68e-35])
     math53:  (5.1, 3.14159265358979)
      sreal:  (5.1, 3.141593)
      dreal:  (5.1, 3.14159265358979)
      ereal:  (5.0999999999999999999, 3.1415926535897932385)
      qreal:  (5.1, 3.1415926535897932384626433832795)
      oreal:  (5.1, 3.1415926535897932384626433832795028841971693993751058209749445923078164)
      mreal:  (5.1, 3.1415926535897932384626433832795029)
     sflint:  (5.1, 3.141593)
     dflint:  (5.1, 3.14159265358979)
     eflint:  (5.0999999999999999999, 3.1415926535897932385)
     qflint:  (5.1, 3.1415926535897932384626433832795)
     oflint:  (5.1, 3.1415926535897932384626433832795028841971693993751058209749445923078164)
     mflint:  (5.1, 3.1415926535897932384626433832795029)
     aflint:  ([5.1000000000000000000000000000000000 +/- 3.86e-35], [3.1415926535897932384626433832795029 +/- 1.83e-35])



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(35)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ',  ctx.polar(x))
            fpm:  (5.478138369920935, 2.76786583362424)
            mpm:  (mpf('5.4781383699209351022648364340189282348'), mpf('2.7678658336242397790155820717594347745'))
        cmath53:  (5.47813836992093, 2.76786583362424)
          qcplx:  (5.47813836992093510226483643401893, 2.76786583362423977901558207175943)



    An example with the same complex input as above, showing the result for all numerical data types:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j; gui.setdps(40)
        >>> for ctx in gui.ctxlist_cplx: print(ctx.fmtname + ': ',  ctx.polar(x))
            fpm:  (5.478138369920935, 2.76786583362424)
            mpm:  (mpf('5.4781383699209351022648364340189282348'), mpf('2.7678658336242397790155820717594347745'))
            dpm:  (Decimal('5.4781383699209347715167147478545767'), Decimal('2.7678658336242397553387165016128094'))
            ipm:  (mpi('5.4781383699209351022648364340189282288', '5.4781383699209351022648364340189282409'), mpi('2.7678658336242397790155820717594347745', '2.7678658336242397790155820717594347775'))
            gpm:  (5.478138369920935, mpfr('2.7678658336242397790155820717594347745',120))
            apm:  ([5.4781383699209351022648364340189282 +/- 4.06e-35], [2.7678658336242397790155820717594348 +/- 3.13e-35])
        cmath53:  (5.47813836992093, 2.76786583362424)
          scplx:  (5.478138, 2.767866)
          dcplx:  (5.47813836992093, 2.76786583362424)
          ecplx:  (5.4781383699209351022, 2.767865833624239779)
          qcplx:  (5.47813836992093510226483643401893, 2.76786583362423977901558207175943)
          ocplx:  (5.4781383699209351022648364340189282337545849763702108448676117093733718, 2.7678658336242397790155820717594347757896731382864946595247594057489815)
          mcplx:  (5.4781383699209351022648364340189282, 2.7678658336242397790155820717594348)
        sflintc:  (5.478138, 2.767866)
        dflintc:  (5.47813836992093, 2.76786583362424)
        eflintc:  (5.4781383699209351022, 2.767865833624239779)
        qflintc:  (5.47813836992093510226483643401893, 2.76786583362423977901558207175943)
        oflintc:  (5.4781383699209351022648364340189282337545849763702108448676117093733718, 2.7678658336242397790155820717594347757896731382864946595247594057489815)
        mflintc:  (5.4781383699209351022648364340189282, 2.7678658336242397790155820717594348)
        aflintc:  ([5.4781383699209351022648364340189282 +/- 7.45e-35], [2.7678658336242397790155820717594348 +/- 8.11e-35])








Rectangular coordinates calculated from the polar representation of a real or complex number
----------------------------------------------------------------------------------------------------

.. method:: ctx.rect(r, phi)

    where ``ctx`` is ``math53``, ``mathc53`` or ``ctxcpp``.

    Returns the complex number represented by polar coordinates `(r, \phi)`, where `r` and `\phi` are real numbers. The result is always a complex number.

    See also  Mpmath :cite:p:`MpmathFun919`.



    An example:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> r = 5.1; phi = 3.1; gui.setdps(40)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.cplxctx.fmt(ctx.rect(r, phi)))
            fpm:  (-5.09558926639373, 0.212061378409781)
            mpm:  (-5.095589266393725268911117878161477940467, 0.2120613784097819538929611851430328128286)
            dpm:  (-5.095589266393725268911117878161477940467, 0.2120613784097819538929611851430328128286)
            ipm: ([-5.09558926639372493278184033907709493069968525, -5.09558926639372493278184033907709493069968525], [0.212061378409781486541300158459371296141849461, 0.212061378409781486541300158459371296141849461])
            gpm:  (-5.09558926639372526891111787816147794046687, 0.212061378409781953892961185143032812828623)
            apm: ([-5.095589266393725268911117878161477940467 +/- 4.78e-40], [0.212061378409781953892961185143032812829 +/- 6.28e-40])
         math53:  (-5.09558926639373, 0.212061378409781)
          sreal:  (-5.095589, 0.2120619)
          dreal:  (-5.09558926639373, 0.212061378409781)
          ereal:  (-5.0955892663937252685, 0.2120613784097819543)
          qreal:  (-5.09558926639372526891111787816148, 0.212061378409781953892961185143032)
          oreal:  (-5.0955892663937252689111178781614779404668725167345079920780515110023443, 0.21206137840978195389296118514303281282852845711541442830484590390601119)
          mreal:  (-5.095589266393725268911117878161477940467, 0.2120613784097819538929611851430328128281)
         sflint:  (-5.095589, 0.2120619)
         dflint:  (-5.09558926639373, 0.212061378409781)
         eflint:  (-5.0955892663937252685, 0.21206137840978195434)
         qflint:  (-5.09558926639372526891111787816148, 0.212061378409781953892961185143032)
         oflint:  (-5.0955892663937252689111178781614779404668725167345079920780515110023443, 0.21206137840978195389296118514303281282852845711541442830484590390601119)
         mflint:  (-5.095589266393725268911117878161477940467, 0.2120613784097819538929611851430328128281)
         aflint: ([-5.09558926639372526891111787816147794047 +/- 5.67e-39], [0.212061378409781953892961185143032812828 +/- 5.58e-40])
