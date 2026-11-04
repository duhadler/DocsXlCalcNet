

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|


Floating point functions for real numbers
==========================================================================================





Efficient computation of `|x| \cdot \mathrm{sign}(y): \mathrm{copysign}(x, y)`
-------------------------------------------------------------------------------

.. method:: ctx.copysign(mag, sgn)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  `|x| \cdot \mathrm{sign}(y)`.

    See also: https://en.cppreference.com/w/cpp/numeric/math/copysign


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> y = 1.0
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.copysign(x, y)))
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






Decomposition of `x` as `x = m \cdot 2^e; 0.5<m<1: \mathrm{frexp}(x)`
----------------------------------------------------------------------------------------------------

.. method:: ctx.frexp(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``. See also  Mpmath :cite:p:`MpmathFun933`.


    Returns (as a tuple) the mantissa `m` and exponent `e` of `x` with `x = m \cdot 2^e, 0.5 < m < 1`.

    If `x` is 0, `\pm \infty` or NaN, returns `m=x, e=0`.

    See also: https://en.cppreference.com/w/cpp/numeric/math/frexp

    See also: https://en.cppreference.com/w/cpp/numeric/math/ilogb

    See also: https://en.cppreference.com/w/cpp/numeric/math/logb


    Ilogb: Returns base 2 exponent of x. For finite x ilogb = floor(log2(`|x|`)),
    otherwise -MaxLongint for x = 0 or MaxLongint if x = +-INF or Nan.

    Extracts the value of the unbiased exponent from the floating-point argument num, and returns it as a signed integer value. The value of the exponent returned by ``std::ilogb`` is always 1 less than the exponent returned by ``std::frexp`` because of the different normalization requirements: for the exponent `e` returned by ``std::ilogb``,  `|num*2^{-e}|` is between  1 and 2, but for the exponent e returned by std::frexp,   `|num*2^{-e}|` is between 0.5 and 1.

    If the implementation supports IEEE floating-point arithmetic (IEC 60559),

    * If num is `\pm 0`, `-\inf` is returned and FE_DIVBYZERO is raised.

    * If num is `\pm \inf`, `+\inf` is returned.

    * If num is NaN, NaN is returned.

    In all other cases, the result is exact (FE_INEXACT is never raised) and the current rounding mode is ignored.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(30)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ', ctx.frexp(x))
            fpm:  (-0.6375, 3)
            mpm:  (mpf('-0.637500000000000000000000000000039'), 3)
            dpm:  (Decimal('-0.6375'), 3)
            ipm:  (mpi('-0.637500000000000000000000000000039', '-0.637499999999999999999999999999941'), 3)
            gpm:  (mpfr('-0.637500000000000000000000000000039',103), 3)
            apm:  ([-0.637500000000000000000000000000 +/- 1.58e-31], 3)
         math53:  (-0.6375, 3)
          sreal:  (-0.6375, 3)
          dreal:  (-0.6375, 3)
          ereal:  (-0.63749999999999999999, 3)
          qreal:  (-0.6375, 3)
          oreal:  (-0.6375, 3)
          mreal:  (-0.6375, 3)
         sflint:  (-0.6375, 3)
         dflint:  (-0.6375, 3)
         eflint:  (-0.63749999999999999999, 3)
         qflint:  (-0.6375, 3)
         oflint:  (-0.6375, 3)
         mflint:  (-0.6375, 3)
         aflint:  ([-0.637500000000000000000000000000 +/- 9.47e-31], 3)






Integral value `e`, from the decomposition of `x` as `x = m \cdot 2^e; 1<m<2: \mathrm{logb}(x)`
----------------------------------------------------------------------------------------------------

.. method:: ctx.logb(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.


    Returns (as a tuple) the mantissa `m` and exponent `e` of `x` with `x = m \cdot 2^e, 0.5 < m < 1`.

    If `x` is 0, `\pm \infty` or NaN, returns `m=x, e=0`.

    See also: https://en.cppreference.com/w/cpp/numeric/math/frexp

    See also: https://en.cppreference.com/w/cpp/numeric/math/ilogb

    See also: https://en.cppreference.com/w/cpp/numeric/math/logb


    Logb: Returns base 2 exponent of x. For finite x logb = floor(log2(`|x|`)),
    otherwise -MaxLongint for x = 0 or MaxLongint if x = +-INF or Nan.

    Extracts the value of the unbiased exponent from the floating-point argument num, and returns it as a signed integer value. The value of the exponent returned by ``std::ilogb`` is always 1 less than the exponent returned by ``std::frexp`` because of the different normalization requirements: for the exponent `e` returned by ``std::ilogb``,  `|num*2^{-e}|` is between  1 and 2, but for the exponent e returned by std::frexp,   `|num*2^{-e}|` is between 0.5 and 1.

    If the implementation supports IEEE floating-point arithmetic (IEC 60559),

    * If num is `\pm 0`, `-\inf` is returned and FE_DIVBYZERO is raised.

    * If num is `\pm \inf`, `+\inf` is returned.

    * If num is NaN, NaN is returned.

    In all other cases, the result is exact (FE_INEXACT is never raised) and the current rounding mode is ignored.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(30)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.logb(x)))
            fpm:  2
            mpm:  2.0
            dpm:  2
            ipm: [2.0,
                  2.0]
            gpm:  2.0
            apm: 2.00000000000000000000000000000
         math53:  2
          sreal:  2
          dreal:  2
          ereal:  2
          qreal:  2
          oreal:  2
          mreal:  2
         sflint:  2
         dflint:  2
         eflint:  2
         qflint:  2
         oflint:  2
         mflint:  2
         aflint:  2.00000000000000000000000000000





32 bit integer `e`, from the decomposition of `x` as `x = m \cdot 2^e; 1<m<2: \mathrm{ilogb}(x)`
----------------------------------------------------------------------------------------------------

.. method:: ctx.ilogb(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.


    Returns (as a tuple) the mantissa `m` and exponent `e` of `x` with `x = m \cdot 2^e, 0.5 < m < 1`.

    If `x` is 0, `\pm \infty` or NaN, returns `m=x, e=0`.

    See also: https://en.cppreference.com/w/cpp/numeric/math/frexp

    See also: https://en.cppreference.com/w/cpp/numeric/math/ilogb

    See also: https://en.cppreference.com/w/cpp/numeric/math/logb


    Ilogb: Returns base 2 exponent of x. For finite x ilogb = floor(log2(`|x|`)),
    otherwise -MaxLongint for x = 0 or MaxLongint if x = +-INF or Nan.

    Extracts the value of the unbiased exponent from the floating-point argument num, and returns it as a signed integer value. The value of the exponent returned by ``std::ilogb`` is always 1 less than the exponent returned by ``std::frexp`` because of the different normalization requirements: for the exponent `e` returned by ``std::ilogb``,  `|num*2^{-e}|` is between  1 and 2, but for the exponent e returned by std::frexp,   `|num*2^{-e}|` is between 0.5 and 1.

    If the implementation supports IEEE floating-point arithmetic (IEC 60559),

    * If num is `\pm 0`, `-\inf` is returned and FE_DIVBYZERO is raised.

    * If num is `\pm \inf`, `+\inf` is returned.

    * If num is NaN, NaN is returned.

    In all other cases, the result is exact (FE_INEXACT is never raised) and the current rounding mode is ignored.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(30)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ', ctx.ilogb(x))
            fpm:  2
            mpm:  2
            dpm:  2
            ipm:  2
            gpm:  2
            apm:  2
         math53:  2
          sreal:  2
          dreal:  2
          ereal:  2
          qreal:  2
          oreal:  2
          mreal:  2
         sflint:  2
         dflint:  2
         eflint:  2
         qflint:  2
         oflint:  2
         mflint:  2
         aflint:  2








Efficient computation of `x \cdot 2^e: \mathrm{ldexp}(x,e), \mathrm{scalbn}(x,e), \mathrm{scalbln}(x,e)`
-------------------------------------------------------------------------------------------------------------


.. method:: ctx.ldexp(x, e)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``. See also  Mpmath :cite:p:`MpmathFun932`.



    Returns `x \cdot 2^e`


    On binary systems (where ``FLT_RADIX`` is 2), ``std::scalbn`` is equivalent to std::ldexp.

    Although ``std::scalbn`` and ``std::scalbln`` are specified to perform the operation efficiently, on many implementations they are less efficient than multiplication or division by a power of two using arithmetic operators.

    The function name stands for "new scalb", where scalb was an older non-standard function whose second argument had floating-point type.

    The ``std::scalbln`` function is provided because the factor required to scale from the smallest positive floating-point value to the largest finite one may be greater than 32767, the standard-guaranteed INT_MAX. In particular, for the 80-bit long double, the factor is 32828.


    See also: https://en.cppreference.com/w/cpp/numeric/math/ldexp

    See also: https://en.cppreference.com/w/cpp/numeric/math/scalbn



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> e = 10
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.ldexp(x, e)))
            fpm:  -5222.4
            mpm:  -5222.4
            dpm:  -5222.4
            ipm: [-5222.4000000000000000000000000000000000000000000000000000000000000000000000000000000000000002011,
                  -5222.3999999999999999999999999999999999999999999999999999999999999999999999999999999999999991957]
            gpm:  -5222.4000000000000000000000000000000000000000000000000000000000000000000000000000000000000002
            apm: [-5222.40000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.81e-87]
         math53:  -5222.4
          sreal:  -5222.4
          dreal:  -5222.4
          ereal:  -5222.3999999999999999
          qreal:  -5222.4
          oreal:  -5222.4
          mreal:  -5222.4
         sflint:  -5222.4
         dflint:  -5222.4
         eflint:  -5222.3999999999999999
         qflint:  -5222.4
         oflint:  -5222.4
         mflint:  -5222.4
         aflint: [-5222.40000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.61e-87]



.. method:: ctx.scalbn(x, e)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``. This is an alias of ``ctx.ldexp``.


.. method:: ctx.scalbln(x, e)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``. This is an alias of ``ctx.ldexp``.




Positive difference between `x` and `y`: `\mathrm{fdim}(x, y)`
-------------------------------------------------------------------------------

.. method:: ctx.fdim(x, y)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the positive difference between x and y, that is, if `x > y`, returns `x - y`, otherwise (i.e. if `x \le y`) returns +0.

    See also: https://en.cppreference.com/w/cpp/numeric/math/fdim



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; gui.setdps(90)
        >>> y = 1.0
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.fdim(x, y)))
            fpm:  4.1
            mpm:  4.1
            dpm:  4.1
            ipm: [4.0999999999999999999999999999999999999999999999999999999999999999999999999999999999999999992145,
                  4.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001964]
            gpm:  4.1000000000000000000000000000000000000000000000000000000000000000000000000000000000000000002
            apm: [4.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.77e-90]
         math53:  4.1
          sreal:  4.1
          dreal:  4.1
          ereal:  4.0999999999999999999
          qreal:  4.1
          oreal:  4.1
          mreal:  4.1
         sflint:  4.1
         dflint:  4.1
         eflint:  4.0999999999999999999
         qflint:  4.1
         oflint:  4.1
         mflint:  4.1
         aflint: [4.10000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 +/- 1.58e-90]


