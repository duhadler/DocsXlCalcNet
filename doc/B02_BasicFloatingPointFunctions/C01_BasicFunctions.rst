

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />








General real functions
===============================================================================





Fused multiplication and addition: `\mathrm{fma}(x, y, z)`
-------------------------------------------------------------------------------

.. method:: ctx.fma(x, y, z)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.


    If successful, returns the value of x * y + z as if calculated to infinite precision and rounded once to fit the result type (or, alternatively, calculated as a single ternary floating-point operation).


    See also: https://en.cppreference.com/w/cpp/numeric/math/fma

    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; y = 2.7;  z = 3.5; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.fma(x, y, z)))
            fpm:  17.27
            mpm:  17.27
            dpm:  17.27
            ipm: [17.269999999999999999999999999999999999999999999999999999999999999999999999999999999999999998272,
                  17.270000000000000000000000000000000000000000000000000000000000000000000000000000000000000002199]
            gpm:  17.269999999999999999999999999999999999999999999999999999999999999999999999999999999999999998
            apm: [17.2700000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 5.66e-90]
         math53:  17.27
          sreal:  17.27
          dreal:  17.27
          ereal:  17.27
          qreal:  17.27
          oreal:  17.27
          mreal:  17.27
         sflint:  17.27
         dflint:  17.27
         eflint:  17.27
         qflint:  17.27
         oflint:  17.27
         mflint:  17.27
         aflint: [17.2700000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 2.56e-89]














Maximum of two floating point numbers: `\mathrm{fmax}(x, y)`
-------------------------------------------------------------------------------

.. method:: ctx.fmax(x, e)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the maximum of two floating point numbers; `x,y \ne` NAN.

    Returns the larger of two floating point arguments, treating NaNs as missing data (between a NaN and a numeric value, the numeric value is chosen). Only if both arguments are NaN, NaN is returned.

    This function is not required to be sensitive to the sign of zero, although some implementations additionally enforce that if one argument is +0 and the other is -0, then +0 is returned.

    See also: https://en.cppreference.com/w/cpp/numeric/math/fmax

    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; y = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.fmax(x, y)))
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






Minimum of two floating point numbers: `\mathrm{fmin}(x, y)`
-------------------------------------------------------------------------------

.. method:: ctx.fmin(x, y)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the minimum of two floating point numbers; `x,y \ne` NAN.

    Returns the smaller of two floating point arguments, treating NaNs as missing data (between a NaN and a numeric value, the numeric value is chosen). Only if both arguments are NaN, NaN is returned.

    This function is not required to be sensitive to the sign of zero, although some implementations additionally enforce that if one argument is +0 and the other is -0, then -0 is returned.


    See also: https://en.cppreference.com/w/cpp/numeric/math/fmin

    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; y = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.fmin(x, y)))
            fpm:  2.7
            mpm:  2.7
            dpm:  2.7
            ipm: [2.6999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999018,
                  2.7000000000000000000000000000000000000000000000000000000000000000000000000000000000000000003927]
            gpm:  2.6999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999
            apm: [2.70000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 5.90e-91]
         math53:  2.7
          sreal:  5.1
          dreal:  2.7
          ereal:  2.7
          qreal:  2.7
          oreal:  2.7
          mreal:  2.7
         sflint:  5.1
         dflint:  2.7
         eflint:  2.7
         qflint:  2.7
         oflint:  2.7
         mflint:  2.7
         aflint: [2.70000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 7.88e-91]






