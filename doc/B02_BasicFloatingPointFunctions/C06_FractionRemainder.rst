

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|


Fraction and remainder related functions
===============================================================================



Integral and fractional part of a floating point number: `\mathrm{modf}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.modf(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns (as a tuple) frac(`x`) and trunc(`x`) in ip, `|x| <` MaxLongint

    Decomposes given floating point value num into integral and fractional parts, each having the same type and sign as num. The integral part (in floating-point format) is stored in the object pointed to by iptr.

    If the implementation supports IEEE floating-point arithmetic (IEC 60559),

    * If num is `\pm 0`, `\pm 0` is returned, and `\pm 0` is stored in ``*iptr``.

    * If num is `\pm \inf`, `\pm 0` is returned, and `\pm \inf` is stored in ``*iptr``.

    * If num is NaN, NaN is returned, and NaN is stored in ``*iptr``.

    The returned value is exact, the current rounding mode is ignored.



    See also: https://en.cppreference.com/w/cpp/numeric/math/modf


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(30)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ', ctx.modf(x))
            fpm:  (-5.0, -0.09999999999999964)
            mpm:  (mpf('-5.0'), mpf('-0.100000000000000000000000000000316'))
            dpm:  (Decimal('-5'), Decimal('-0.1'))
            ipm:  (mpi('-5.0', '-5.0'), mpi('-0.100000000000000000000000000000316', '-0.0999999999999999999999999999995267'))
            gpm:  (mpfr('-5.0',103), mpfr('-0.100000000000000000000000000000316',103))
            apm:  (-5.00000000000000000000000000000, [-0.1000000000000000000000000000 +/- 1.30e-30])
         math53:  (-5, -0.0999999999999996)
          sreal:  (-5, -0.0999999)
          dreal:  (-5, -0.0999999999999996)
          ereal:  (-5, -0.099999999999999999913)
          qreal:  (-5, -0.0999999999999999999999999999999997)
          oreal:  (-5, -0.099999999999999999999999999999999999999999999999999999999999999999999986)
          mreal:  (-5, -0.0999999999999999999999999999987)
         sflint:  (-5, -0.0999999)
         dflint:  (-5, -0.0999999999999996)
         eflint:  (-5, -0.099999999999999999913)
         qflint:  (-5, -0.0999999999999999999999999999999997)
         oflint:  (-5, -0.099999999999999999999999999999999999999999999999999999999999999999999986)
         mflint:  (-5, -0.0999999999999999999999999999987)
         aflint:  ( -5.00000000000000000000000000000, [-0.1000000000000000000000000000 +/- 2.53e-30])








.. _rst_mpm_fmod: 

Floating point remainder: `\mathrm{fmod}(x, y)`
-------------------------------------------------------------------------------

.. method:: ctx.fmod(x, y)


    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the floating-point remainder of the division operation ``x / y`` calculated by this function is exactly the value ``x - rem * y``, where ``rem`` is ``x / y`` with its fractional part truncated.

    The returned value has the same sign as x and is less than y in magnitude.

    If the implementation supports IEEE floating-point arithmetic (IEC 60559),

    * If x is `\pm 0` and y is not zero, `\pm 0` is returned.

    * If x is `\pm \inf` and y is not NaN, NaN is returned and FE_INVALID is raised.

    * If y is `\pm 0` and x is not NaN, NaN is returned and FE_INVALID is raised.

    * If y is `\pm \inf` and x is finite, x is returned.

    * If either argument is NaN, NaN is returned.


    See also: https://en.cppreference.com/w/cpp/numeric/math/fmod


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 7.5; y = 2.1; gui.setdps(30)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.fmod(x, y)))
            fpm:  1.2
            mpm:  1.2
            dpm:  1.2
            ipm: [1.1999999999999999999999999999990534,
                  1.2000000000000000000000000000002367]
            gpm:  1.20000000000000000000000000000024
            apm: [1.20000000000000000000000000000 +/- 2.61e-30]
         math53:  1.2
          sreal:  1.2
          dreal:  1.2
          ereal:  1.2000000000000000003
          qreal:  1.2
          oreal:  1.2
          mreal:  1.2
         sflint:  1.2
         dflint:  1.2
         eflint:  1.2000000000000000003
         qflint:  1.2
         oflint:  1.2
         mflint:  1.2
         aflint: [1.20000000000000000000000000000 +/- 7.58e-30]







IEEE floating point remainder: `\mathrm{remainder}(x, y)`
-------------------------------------------------------------------------------

.. method:: ctx.remainder(x, y)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the IEEE754 remainder x REM y = x - rmNearest(x/y)*y.

    The IEEE floating-point remainder of the division operation ``x / y`` calculated by this function is exactly the value ``x - quo * y``, where the value ``quo`` is the integral value nearest the exact value ``x / y``. When ``|quo - x / y| = 0.5``, the value ``quo`` is chosen to be even.

    In contrast to std::fmod, the returned value is not guaranteed to have the same sign as x.

    If the returned value is zero, it will have the same sign as x.

    If the implementation supports IEEE floating-point arithmetic (IEC 60559),

    * The current rounding mode has no effect.

    * FE_INEXACT is never raised, the result is always exact.

    * If x is `\pm \inf` and y is not NaN, NaN is returned and FE_INVALID is raised.

    * If y is `\pm 0` and x is not NaN, NaN is returned and FE_INVALID is raised.

    * If either argument is NaN, NaN is returned.



    See also: https://en.cppreference.com/w/cpp/numeric/math/remainder


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 7.5; y = 2.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.remainder(x, y)))
            fpm:  -0.9
            mpm:  -0.900000000000000000000000000000000000000000000000000000000000000000000000000000000000000001
            dpm:  -0.9
            ipm: [-0.90000000000000000000000000000000000000000000000000000000000000000000000000000000000000000078545,
                  -0.89999999999999999999999999999999999999999999999999999999999999999999999999999999999999999882182]
            gpm:  -0.90000000000000000000000000000000000000000000000000000000000000000000000000000000000000000079
            apm: [-0.90000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 3.15e-90]
         math53:  -0.9
          sreal:  -0.8999996
          dreal:  -0.9
          ereal:  -0.89999999999999999965
          qreal:  -0.9
          oreal:  -0.90000000000000000000000000000000000000000000000000000000000000000000001
          mreal:  -0.899999999999999999999999999999999999999999999999999999999999999999999999999999999999999997
         sflint:  -0.8999996
         dflint:  -0.9
         eflint:  -0.89999999999999999965
         qflint:  -0.9
         oflint:  -0.90000000000000000000000000000000000000000000000000000000000000000000001
         mflint:  -0.899999999999999999999999999999999999999999999999999999999999999999999999999999999999999997
         aflint: [-0.90000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 6.29e-90]






IEEE floating point remainder and part of quotient: `\mathrm{remquo}(x, y)`
-------------------------------------------------------------------------------

.. method:: ctx.remquo(x, y)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the IEEE floating point remainder and part of the quotient.

    Computes the floating-point remainder of the division operation `x / y` as the ``std::remainder`` function does. Additionally, the sign and at least three of the last bits of `x / y` will be stored in quo, sufficient to determine the octant of the result within a period. Formally, stores a value whose sign is the sign of `x / y` and whose magnitude is congruent modulo `2^n` to the magnitude of the integral quotient of `x / y`, where `n` is an implementation-defined integer greater than or equal to 3.

    If the implementation supports IEEE floating-point arithmetic (IEC 60559),

    The current rounding mode has no effect.

    FE_INEXACT is never raised.

    If x is `\pm \inf` and y is not NaN, NaN is returned and FE_INVALID is raised.

    If y is `\pm 0` and x is not NaN, NaN is returned and FE_INVALID is raised.

    If either x or y is NaN, NaN is returned.


    See also: https://en.cppreference.com/w/cpp/numeric/math/remquo


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = '7.5'; y = '2.1'; gui.setdps(30)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ', ctx.remquo(x, y))
            fpm:  (-0.9000000000000004, 4)
            mpm:  (mpf('-0.899999999999999999999999999999684'), 4)
            dpm:  (Decimal('-0.9'), 4)
            ipm:  (mpi('-0.900000000000000000000000000001262', '-0.899999999999999999999999999999684'), 4)
            gpm:  (mpfr('-0.899999999999999999999999999999684',103), 4)
            apm:  ([-0.90000000000000000000000000000 +/- 1.90e-30], 4)
         math53:  (-0.9, 4)
          sreal:  (-0.8999996, 4)
          dreal:  (-0.9, 4)
          ereal:  (-0.89999999999999999965, 4)
          qreal:  (-0.9, 4)
          oreal:  (-0.90000000000000000000000000000000000000000000000000000000000000000000001, 4)
          mreal:  (-0.899999999999999999999999999995, 4)
         sflint:  (-0.8999996, 4)
         dflint:  (-0.9, 4)
         eflint:  (-0.89999999999999999965, 4)
         qflint:  (-0.9, 4)
         oflint:  (-0.90000000000000000000000000000000000000000000000000000000000000000000001, 4)
         mflint:  (-0.899999999999999999999999999995, 4)
         aflint:  ([-0.9000000000000000000000000000 +/- 1.02e-29], 4)






Fractional part of a floating point number: `\mathrm{frac}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.frac(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the fractional part of `x`, that is, `\mathrm{frac}(x) = x - floor(x)`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.frac(x)))
            fpm:  0.9
            mpm:  0.9
            dpm:  0.9
            ipm: [0.89999999999999999999999999999999999999999999999999999999999999999999999999999999999999999980364,
                  0.90000000000000000000000000000000000000000000000000000000000000000000000000000000000000000078545]
            gpm:  0.8999999999999999999999999999999999999999999999999999999999999999999999999999999999999999998
            apm: [0.90000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.77e-90]
         math53:  0.9
          sreal:  0.9000001
          dreal:  0.9
          ereal:  0.90000000000000000009
          qreal:  0.9
          oreal:  0.90000000000000000000000000000000000000000000000000000000000000000000001
          mreal:  0.900000000000000000000000000000000000000000000000000000000000000000000000000000000000000001
         sflint:  0.9000001
         dflint:  0.9
         eflint:  0.90000000000000000009
         qflint:  0.9
         oflint:  0.90000000000000000000000000000000000000000000000000000000000000000000001
         mflint:  0.900000000000000000000000000000000000000000000000000000000000000000000000000000000000000001
         aflint: [0.90000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.58e-90]



Fractional part of a floating point number (symmetric function): `\mathrm{fractionalpart}(x)`
------------------------------------------------------------------------------------------------

.. method:: ctx.fractionalpart(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the fractional part of x as a symmetric function: 

    `\mathrm{fractionalpart}(x) = \mathrm{frac}(x)` for `x \geq 0` and `\mathrm{fractionalpart}(x) = -\mathrm{frac}(-x)` for `x < 0`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.fractionalpart(x)))
            fpm:  -0.0999999999999996
            mpm:  -0.1
            dpm:  -0.1
            ipm: [-0.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000019636,
                  -0.099999999999999999999999999999999999999999999999999999999999999999999999999999999999999999214545]
            gpm:  -0.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002
            apm: [-0.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.81e-90]
         math53:  -0.0999999999999996
          sreal:  -0.0999999
          dreal:  -0.0999999999999996
          ereal:  -0.099999999999999999913
          qreal:  -0.0999999999999999999999999999999997
          oreal:  -0.099999999999999999999999999999999999999999999999999999999999999999999986
          mreal:  -0.0999999999999999999999999999999999999999999999999999999999999999999999999999999999999999992
         sflint:  -0.0999999
         dflint:  -0.0999999999999996
         eflint:  -0.099999999999999999913
         qflint:  -0.0999999999999999999999999999999997
         oflint:  -0.099999999999999999999999999999999999999999999999999999999999999999999986
         mflint:  -0.0999999999999999999999999999999999999999999999999999999999999999999999999999999999999999992
         aflint: [-0.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.58e-90]

