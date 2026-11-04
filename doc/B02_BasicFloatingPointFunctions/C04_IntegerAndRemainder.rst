

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|


Integer related functions
===============================================================================


Integral value nearest `x` (rounding to nearest): `\mathrm{nearbyint}(x), \mathrm{rint}(x)`
-------------------------------------------------------------------------------------------------

.. method:: ctx.rint(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the integral value (in floating-point format)  nearest `x`, using the ``rounding-to-nearest`` rounding mode. 

    For the std::rint function:

    * If num is ±∞, it is returned, unmodified.

    * If num is ±0, it is returned, unmodified.

    * If num is NaN, NaN is returned.

    See also: https://en.cppreference.com/w/cpp/numeric/math/nearbyint

    See also: https://en.cppreference.com/w/cpp/numeric/math/rint



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.rint(x)))
            fpm:  -5
            mpm:  -5.0
            dpm:  -5
            ipm: [-5.0,
                  -5.0]
            gpm:  -5.0
            apm: -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
         math53:  -5
          sreal:  -5
          dreal:  -5
          ereal:  -5
          qreal:  -5
          oreal:  -5
          mreal:  -5
         sflint:  -5
         dflint:  -5
         eflint:  -5
         qflint:  -5
         oflint:  -5
         mflint:  -5
         aflint:  -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000






.. method:: ctx.nearbyint(x)

    Is an alias for ``ctx.rint(x)`` in this implementation. The only difference between ``std::rint`` and ``std::nearbyint`` is that ``std::nearbyint`` never raises ``FE_INEXACT``.





32 bit integer nearest `x` (rounding to nearest): `\mathrm{lrint}(x)`
------------------------------------------------------------------------------

.. method:: ctx.lrint(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  an 32 bit signed integer nearest `x`, using the ``rounding-to-nearest`` rounding mode. 

    If the result is outside the range representable by an 32 bit signed integer, a domain error or a range error may occur.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5345346.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + str(ctx.lrint(x)))
            fpm: -5345347
            mpm: -5345347
            dpm: -5345347
            ipm: -5345347
            gpm: -5345347
            apm: -5345347
         math53: -5345347
          sreal: -5345346
          dreal: -5345347
          ereal: -5345347
          qreal: -5345347
          oreal: -5345347
          mreal: -5345347
         sflint: -5345346
         dflint: -5345347
         eflint: -5345347
         qflint: -5345347
         oflint: -5345347
         mflint: -5345347
         aflint: -5345347





64 bit integer nearest `x` (rounding to nearest): `\mathrm{llrint}(x)`
--------------------------------------------------------------------------------

.. method:: ctx.llrint(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  an 64 bit signed integer nearest `x`, using the ``rounding-to-nearest`` rounding mode. 

    If the result is outside the range representable by an 64 bit signed integer, a domain error or a range error may occur.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = '-9223372036854775807.2'; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + str(ctx.llrint(x)))
            fpm: -9223372036854775808
            mpm: -9223372036854775807
            dpm: -9223372036854775807
            ipm: -9223372036854775807
            gpm: -9223372036854775807
            apm: -9223372036854775807
         math53: -9223372036854775808
          sreal: -9223372036854775808
          dreal: -9223372036854775808
          ereal: -9223372036854775807
          qreal: -9223372036854775807
          oreal: -9223372036854775807
          mreal: -9223372036854775807
         sflint: -9223372036854775808
         dflint: -9223372036854775808
         eflint: -9223372036854775807
         qflint: -9223372036854775807
         oflint: -9223372036854775807
         mflint: -9223372036854775807
         aflint: -9223372036854775807








Smallest integral value not less than `x: \mathrm{ceil}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.ceil(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the smallest integer `> x; |x| \le` MaxLongint.

    See also: https://en.cppreference.com/w/cpp/numeric/math/ceil


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.ceil(x)))
            fpm:  -5
            mpm:  -5.0
            dpm:  -5
            ipm: [-5.0,
                  -5.0]
            gpm:  -5.0
            apm: -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
         math53:  -5
          sreal:  -5
          dreal:  -5
          ereal:  -5
          qreal:  -5
          oreal:  -5
          mreal:  -5
         sflint:  -5
         dflint:  -5
         eflint:  -5
         qflint:  -5
         oflint:  -5
         mflint:  -5
         aflint:  -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000





Largest integral value not greater than `x: \mathrm{floor}(x)`
----------------------------------------------------------------------------------------------

.. method:: ctx.floor(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the largest integer `< x; |x| \le` MaxLongint.

    See also: https://en.cppreference.com/w/cpp/numeric/math/floor


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.floor(x)))
            fpm:  -5
            mpm:  -5.0
            dpm:  -5
            ipm: [-5.0,
                  -5.0]
            gpm:  -5.0
            apm: -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
         math53:  -5
          sreal:  -5
          dreal:  -5
          ereal:  -5
          qreal:  -5
          oreal:  -5
          mreal:  -5
         sflint:  -5
         dflint:  -5
         eflint:  -5
         qflint:  -5
         oflint:  -5
         mflint:  -5
         aflint:  -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000






Nearest integral value not greater in magnitude than `x: \mathrm{trunc}(x)`
-------------------------------------------------------------------------------------------------

.. method:: ctx.trunc(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the truncated value of `x`.


    See also: https://en.cppreference.com/w/cpp/numeric/math/trunc


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.trunc(x)))
            fpm:  -5
            mpm:  -5.0
            dpm:  -5
            ipm: [-5.0,
                  -5.0]
            gpm:  -5.0
            apm: -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
         math53:  -5
          sreal:  -5
          dreal:  -5
          ereal:  -5
          qreal:  -5
          oreal:  -5
          mreal:  -5
         sflint:  -5
         dflint:  -5
         eflint:  -5
         qflint:  -5
         oflint:  -5
         mflint:  -5
         aflint:  -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000







Nearest integral value, rounding halfway cases away from zero: `\mathrm{round}(x)`
----------------------------------------------------------------------------------------

.. method:: ctx.round(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Computes the nearest integer  (in floating-point format), rounding halfway cases away from zero, regardless of the current rounding mode.


    See also: https://en.cppreference.com/w/cpp/numeric/math/round


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.round(x)))
            fpm:  -5
            mpm:  -5.0
            dpm:  -5
            ipm: [-5.0,
                  -5.0]
            gpm:  -5.0
            apm: -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
         math53:  -5
          sreal:  -5
          dreal:  -5
          ereal:  -5
          qreal:  -5
          oreal:  -5
          mreal:  -5
         sflint:  -5
         dflint:  -5
         eflint:  -5
         qflint:  -5
         oflint:  -5
         mflint:  -5
         aflint:  -5.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000





Nearest 32 bit integer, rounding halfway cases away from zero: `\mathrm{lround}(x)`
------------------------------------------------------------------------------------------

.. method:: ctx.lround(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the nearest 32 bit signed integer, rounding halfway cases away from zero.


    See also: https://en.cppreference.com/w/cpp/numeric/math/round


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5345346.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + str(ctx.lround(x)))
            fpm: -5345347
            mpm: -5345347
            dpm: -5345347
            ipm: -5345347
            gpm: -5345347
            apm: -5345347
         math53: -5345347
          sreal: -5345347
          dreal: -5345347
          ereal: -5345347
          qreal: -5345347
          oreal: -5345347
          mreal: -5345347
         sflint: -5345347
         dflint: -5345347
         eflint: -5345347
         qflint: -5345347
         oflint: -5345347
         mflint: -5345347
         aflint: -5345347






Nearest 64 bit integer, rounding halfway cases away from zero: `\mathrm{llround}(x)`
------------------------------------------------------------------------------------------

.. method:: ctx.llround(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the nearest 64 bit signed integer, rounding halfway cases away from zero.



    See also: https://en.cppreference.com/w/cpp/numeric/math/round


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = '-9223372036854775807.2'; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + str(ctx.llround(x)))
            fpm: -9223372036854775808
            mpm: -9223372036854775807
            dpm: -9223372036854775807
            ipm: -9223372036854775807
            gpm: -9223372036854775807
            apm: -9223372036854775807
         math53: -9223372036854775808
          sreal: -9223372036854775808
          dreal: -9223372036854775808
          ereal: -9223372036854775807
          qreal: -9223372036854775807
          oreal: -9223372036854775807
          mreal: -9223372036854775807
         sflint: -9223372036854775808
         dflint: -9223372036854775808
         eflint: -9223372036854775807
         qflint: -9223372036854775807
         oflint: -9223372036854775807
         mflint: -9223372036854775807
         aflint: -9223372036854775807





