

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|


Properties of numbers
===============================================================================




Test for signbit
-------------------------------------------------------------------------------

.. method:: ctx.signbit(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if the sign bit of `x` is set.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.signbit(x)))
            fpm:  1
            mpm:  1.0
            dpm:  1
            ipm: [1.0,
                  1.0]
            gpm:  1.0
            apm: 1.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
         math53:  1
          sreal:  1
          dreal:  1
          ereal:  1
          qreal:  1
          oreal:  1
          mreal:  1
         sflint:  1
         dflint:  1
         eflint:  1
         qflint:  1
         oflint:  1
         mflint:  1
         aflint:  1.00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000






Test for a finite number
-------------------------------------------------------------------------------

.. method:: ctx.isfinite(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is neither `+\infty` nor `-\infty` nor ``NaN``.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isfinite(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, True, True, True, True, False]
            mpm:  [False, False, True, True, True, True, False]
            dpm:  [False, False, True, True, True, True, False]
            ipm:  [False, False, True, True, True, True, False]
            gpm:  [False, False, True, True, True, True, False]
            apm:  [False, False, True, True, True, True, False]
         math53:  [False, False, True, True, True, True, False]
          sreal:  [False, False, True, True, True, True, False]
          dreal:  [False, False, True, True, True, True, False]
          ereal:  [False, False, True, True, True, True, False]
          qreal:  [False, False, True, True, True, True, False]
          oreal:  [False, False, True, True, True, True, False]
          mreal:  [False, False, True, True, True, True, False]
         sflint:  [False, False, True, True, True, True, False]
         dflint:  [False, False, True, True, True, True, False]
         eflint:  [False, False, True, True, True, True, False]
         qflint:  [False, False, True, True, True, True, False]
         oflint:  [False, False, True, True, True, True, False]
         mflint:  [False, False, True, True, True, True, False]
         aflint:  [False, False, True, True, True, True, False]







Test for infinity
-------------------------------------------------------------------------------

.. method:: ctx.isinf(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is either `+\infty` or `-\infty`.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isinf(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, True, False, False, False, False, True]
            mpm:  [False, True, False, False, False, False, True]
            dpm:  [False, True, False, False, False, False, True]
            ipm:  [False, True, False, False, False, False, True]
            gpm:  [False, True, False, False, False, False, True]
            apm:  [False, True, False, False, False, False, True]
         math53:  [False, True, False, False, False, False, True]
          sreal:  [False, True, False, False, False, False, True]
          dreal:  [False, True, False, False, False, False, True]
          ereal:  [False, True, False, False, False, False, True]
          qreal:  [False, True, False, False, False, False, True]
          oreal:  [False, True, False, False, False, False, True]
          mreal:  [False, True, False, False, False, False, True]
         sflint:  [False, True, False, False, False, False, True]
         dflint:  [False, True, False, False, False, False, True]
         eflint:  [False, True, False, False, False, False, True]
         qflint:  [False, True, False, False, False, False, True]
         oflint:  [False, True, False, False, False, False, True]
         mflint:  [False, True, False, False, False, False, True]
         aflint:  [False, True, False, False, False, False, True]




Test for positive infinity
-------------------------------------------------------------------------------

.. method:: ctx.isposinf(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is `+\infty`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isposinf(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, False, False, False, False, True]
            mpm:  [False, False, False, False, False, False, True]
            dpm:  [False, False, False, False, False, False, True]
            ipm:  [False, False, False, False, False, False, True]
            gpm:  [False, False, False, False, False, False, True]
            apm:  [False, False, False, False, False, False, True]
         math53:  [False, False, False, False, False, False, True]
          sreal:  [False, False, False, False, False, False, True]
          dreal:  [False, False, False, False, False, False, True]
          ereal:  [False, False, False, False, False, False, True]
          qreal:  [False, False, False, False, False, False, True]
          oreal:  [False, False, False, False, False, False, True]
          mreal:  [False, False, False, False, False, False, True]
         sflint:  [False, False, False, False, False, False, True]
         dflint:  [False, False, False, False, False, False, True]
         eflint:  [False, False, False, False, False, False, True]
         qflint:  [False, False, False, False, False, False, True]
         oflint:  [False, False, False, False, False, False, True]
         mflint:  [False, False, False, False, False, False, True]
         aflint:  [False, False, False, False, False, False, True]





Test for negative infinity
-------------------------------------------------------------------------------

.. method:: ctx.isneginf(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is `-\infty`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isneginf(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, True, False, False, False, False, False]
            mpm:  [False, True, False, False, False, False, False]
            dpm:  [False, True, False, False, False, False, False]
            ipm:  [False, True, False, False, False, False, False]
            gpm:  [False, True, False, False, False, False, False]
            apm:  [False, True, False, False, False, False, False]
         math53:  [False, True, False, False, False, False, False]
          sreal:  [False, True, False, False, False, False, False]
          dreal:  [False, True, False, False, False, False, False]
          ereal:  [False, True, False, False, False, False, False]
          qreal:  [False, True, False, False, False, False, False]
          oreal:  [False, True, False, False, False, False, False]
          mreal:  [False, True, False, False, False, False, False]
         sflint:  [False, True, False, False, False, False, False]
         dflint:  [False, True, False, False, False, False, False]
         eflint:  [False, True, False, False, False, False, False]
         qflint:  [False, True, False, False, False, False, False]
         oflint:  [False, True, False, False, False, False, False]
         mflint:  [False, True, False, False, False, False, False]
         aflint:  [False, True, False, False, False, False, False]




Test for NaN
-------------------------------------------------------------------------------

.. method:: ctx.isnan(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is Nan (Not a number).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isnan(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [True, False, False, False, False, False, False]
            mpm:  [True, False, False, False, False, False, False]
            dpm:  [True, False, False, False, False, False, False]
            ipm:  [True, False, False, False, False, False, False]
            gpm:  [True, False, False, False, False, False, False]
            apm:  [True, False, False, False, False, False, False]
         math53:  [True, False, False, False, False, False, False]
          sreal:  [True, False, False, False, False, False, False]
          dreal:  [True, False, False, False, False, False, False]
          ereal:  [True, False, False, False, False, False, False]
          qreal:  [True, False, False, False, False, False, False]
          oreal:  [True, False, False, False, False, False, False]
          mreal:  [True, False, False, False, False, False, False]
         sflint:  [True, False, False, False, False, False, False]
         dflint:  [True, False, False, False, False, False, False]
         eflint:  [True, False, False, False, False, False, False]
         qflint:  [True, False, False, False, False, False, False]
         oflint:  [True, False, False, False, False, False, False]
         mflint:  [True, False, False, False, False, False, False]
         aflint:  [True, False, False, False, False, False, False]






Test for zero
-------------------------------------------------------------------------------

.. method:: ctx.iszero(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is 0 (+0 or -0).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.iszero(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, False, True, True, False, False]
            mpm:  [False, False, False, True, True, False, False]
            dpm:  [False, False, False, True, True, False, False]
            ipm:  [False, False, False, True, True, False, False]
            gpm:  [False, False, False, True, True, False, False]
            apm:  [False, False, False, True, True, False, False]
         math53:  [False, False, False, True, True, False, False]
          sreal:  [False, False, False, True, True, False, False]
          dreal:  [False, False, False, True, True, False, False]
          ereal:  [False, False, False, True, True, False, False]
          qreal:  [False, False, False, True, True, False, False]
          oreal:  [False, False, False, True, True, False, False]
          mreal:  [False, False, False, True, True, False, False]
         sflint:  [False, False, False, True, True, False, False]
         dflint:  [False, False, False, True, True, False, False]
         eflint:  [False, False, False, True, True, False, False]
         qflint:  [False, False, False, True, True, False, False]
         oflint:  [False, False, False, True, True, False, False]
         mflint:  [False, False, False, True, True, False, False]
         aflint:  [False, False, False, True, True, False, False]





Test for one
-------------------------------------------------------------------------------

.. method:: ctx.isone(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is 1.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 1.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isone(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, False, False, False, True, False, False]
            mpm:  [False, False, False, False, False, True, False, False]
            dpm:  [False, False, False, False, False, True, False, False]
            ipm:  [False, False, False, False, False, True, False, False]
            gpm:  [False, False, False, False, False, True, False, False]
            apm:  [False, False, False, False, False, True, False, False]
         math53:  [False, False, False, False, False, True, False, False]
          sreal:  [False, False, False, False, False, True, False, False]
          dreal:  [False, False, False, False, False, True, False, False]
          ereal:  [False, False, False, False, False, True, False, False]
          qreal:  [False, False, False, False, False, True, False, False]
          oreal:  [False, False, False, False, False, True, False, False]
          mreal:  [False, False, False, False, False, True, False, False]
         sflint:  [False, False, False, False, False, True, False, False]
         dflint:  [False, False, False, False, False, True, False, False]
         eflint:  [False, False, False, False, False, True, False, False]
         qflint:  [False, False, False, False, False, True, False, False]
         oflint:  [False, False, False, False, False, True, False, False]
         mflint:  [False, False, False, False, False, True, False, False]
         aflint:  [False, False, False, False, False, True, False, False]







Test if a number is an integer
-------------------------------------------------------------------------------

.. method:: ctx.isinteger(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is an integer.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 1.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isinteger(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, False, True, True, True, False, False]
            mpm:  [False, False, False, True, True, True, False, False]
            dpm:  [False, False, False, True, True, True, False, False]
            ipm:  [False, False, False, True, True, True, False, False]
            gpm:  [False, False, False, True, True, True, False, False]
            apm:  [False, False, False, True, True, True, False, False]
         math53:  [False, False, False, True, True, True, False, False]
          sreal:  [False, False, False, True, True, True, False, False]
          dreal:  [False, False, False, True, True, True, False, False]
          ereal:  [False, False, False, True, True, True, False, False]
          qreal:  [False, False, False, True, True, True, False, False]
          oreal:  [False, False, False, True, True, True, False, False]
          mreal:  [False, False, False, True, True, True, False, False]
         sflint:  [False, False, False, True, True, True, False, False]
         dflint:  [False, False, False, True, True, True, False, False]
         eflint:  [False, False, False, True, True, True, False, False]
         qflint:  [False, False, False, True, True, True, False, False]
         oflint:  [False, False, False, True, True, True, False, False]
         mflint:  [False, False, False, True, True, True, False, False]
         aflint:  [False, False, False, True, True, True, False, False]





Test if a number is a simple number (not an infinity or NaN)
-------------------------------------------------------------------------------

.. method:: ctx.isnumber(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is an integer.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 1.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isnumber(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, True, True, True, True, True, False]
            mpm:  [False, False, True, True, True, True, True, False]
            dpm:  [False, False, True, True, True, True, True, False]
            ipm:  [False, False, True, True, True, True, True, False]
            gpm:  [False, False, True, True, True, True, True, False]
            apm:  [False, False, True, True, True, True, True, False]
         math53:  [False, False, True, True, True, True, True, False]
          sreal:  [False, False, True, True, True, True, True, False]
          dreal:  [False, False, True, True, True, True, True, False]
          ereal:  [False, False, True, True, True, True, True, False]
          qreal:  [False, False, True, True, True, True, True, False]
          oreal:  [False, False, True, True, True, True, True, False]
          mreal:  [False, False, True, True, True, True, True, False]
         sflint:  [False, False, True, True, True, True, True, False]
         dflint:  [False, False, True, True, True, True, True, False]
         eflint:  [False, False, True, True, True, True, True, False]
         qflint:  [False, False, True, True, True, True, True, False]
         oflint:  [False, False, True, True, True, True, True, False]
         mflint:  [False, False, True, True, True, True, True, False]
         aflint:  [False, False, True, True, True, True, True, False]





Test if a number is a regular number (not zero, an infinity or NaN)
-------------------------------------------------------------------------------

.. method:: ctx.isregular(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is a regular number (not zero, an infinity or NaN).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 1.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isregular(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, True, False, False, True, True, False]
            mpm:  [False, False, True, False, False, True, True, False]
            dpm:  [False, False, True, False, False, True, True, False]
            ipm:  [False, False, True, False, False, True, True, False]
            gpm:  [False, False, True, False, False, True, True, False]
            apm:  [False, False, True, False, False, True, True, False]
         math53:  [False, False, True, False, False, True, True, False]
          sreal:  [False, False, True, False, False, True, True, False]
          dreal:  [False, False, True, False, False, True, True, False]
          ereal:  [False, False, True, False, False, True, True, False]
          qreal:  [False, False, True, False, False, True, True, False]
          oreal:  [False, False, True, False, False, True, True, False]
          mreal:  [False, False, True, False, False, True, True, False]
         sflint:  [False, False, True, False, False, True, True, False]
         dflint:  [False, False, True, False, False, True, True, False]
         eflint:  [False, False, True, False, False, True, True, False]
         qflint:  [False, False, True, False, False, True, True, False]
         oflint:  [False, False, True, False, False, True, True, False]
         mflint:  [False, False, True, False, False, True, True, False]
         aflint:  [False, False, True, False, False, True, True, False]




Test if a number is a normal number (not subnormal, zero, an infinity or NaN)
-------------------------------------------------------------------------------

.. method:: ctx.isnormal(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` is a normal number (not subnormal, zero, an infinity or NaN)


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, -5.1, -0.0, 0.0, 1.0, 8.8, dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.isnormal(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, True, False, False, True, True, False]
            mpm:  [False, False, True, False, False, True, True, False]
            dpm:  [False, False, True, False, False, True, True, False]
            ipm:  [False, False, True, False, False, True, True, False]
            gpm:  [False, False, True, False, False, True, True, False]
            apm:  [False, False, True, False, False, True, True, False]
         math53:  [False, False, True, False, False, True, True, False]
          sreal:  [False, False, True, False, False, True, True, False]
          dreal:  [False, False, True, False, False, True, True, False]
          ereal:  [False, False, True, False, False, True, True, False]
          qreal:  [False, False, True, False, False, True, True, False]
          oreal:  [False, False, True, False, False, True, True, False]
          mreal:  [False, False, True, False, False, True, True, False]
         sflint:  [False, False, True, False, False, True, True, False]
         dflint:  [False, False, True, False, False, True, True, False]
         eflint:  [False, False, True, False, False, True, True, False]
         qflint:  [False, False, True, False, False, True, True, False]
         oflint:  [False, False, True, False, False, True, True, False]
         mflint:  [False, False, True, False, False, True, True, False]
         aflint:  [False, False, True, False, False, True, True, False]








Test if 2 numbers are unordered
-------------------------------------------------------------------------------

.. method:: ctx.isunordered(x, y)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``True`` if `x` and  `y` are unordered.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, '-2147483649', '-2147483648', 0.0, '2147483647', '2147483648', dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.fitsint32(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, False, True, True, True, False, False]
            mpm:  [False, False, False, True, True, True, False, False]
            dpm:  [False, False, False, True, True, True, False, False]
            ipm:  [False, False, False, True, True, True, False, False]
            gpm:  [False, False, False, True, True, True, False, False]
            apm:  [False, False, False, True, True, True, False, False]
         math53:  [False, False, False, True, True, True, False, False]
          sreal:  [False, False, True, True, True, True, True, False]
          dreal:  [False, False, False, True, True, True, False, False]
          ereal:  [False, False, False, True, True, True, False, False]
          qreal:  [False, False, False, True, True, True, False, False]
          oreal:  [False, False, False, True, True, True, False, False]
          mreal:  [False, False, False, True, True, True, False, False]
         sflint:  [False, False, True, True, True, True, True, False]
         dflint:  [False, False, False, True, True, True, False, False]
         eflint:  [False, False, False, True, True, True, False, False]
         qflint:  [False, False, False, True, True, True, False, False]
         oflint:  [False, False, False, True, True, True, False, False]
         mflint:  [False, False, False, True, True, True, False, False]
         aflint:  [False, False, False, True, True, True, False, False]







Test if a number fits in a signed 32 bit integer
-------------------------------------------------------------------------------

.. method:: ctx.fitsint32(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Test if a number fits in a signed 32 bit integer


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, '-2147483649', '-2147483648', 0.0, '2147483647', '2147483648', dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.fitsint32(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, False, True, True, True, False, False]
            mpm:  [False, False, False, True, True, True, False, False]
            dpm:  [False, False, False, True, True, True, False, False]
            ipm:  [False, False, False, True, True, True, False, False]
            gpm:  [False, False, False, True, True, True, False, False]
            apm:  [False, False, False, True, True, True, False, False]
         math53:  [False, False, False, True, True, True, False, False]
          sreal:  [False, False, True, True, True, True, True, False]
          dreal:  [False, False, False, True, True, True, False, False]
          ereal:  [False, False, False, True, True, True, False, False]
          qreal:  [False, False, False, True, True, True, False, False]
          oreal:  [False, False, False, True, True, True, False, False]
          mreal:  [False, False, False, True, True, True, False, False]
         sflint:  [False, False, True, True, True, True, True, False]
         dflint:  [False, False, False, True, True, True, False, False]
         eflint:  [False, False, False, True, True, True, False, False]
         qflint:  [False, False, False, True, True, True, False, False]
         oflint:  [False, False, False, True, True, True, False, False]
         mflint:  [False, False, False, True, True, True, False, False]
         aflint:  [False, False, False, True, True, True, False, False]






Test if a number fits in a signed 64 bit integer
-------------------------------------------------------------------------------

.. method:: ctx.fitsint64(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Test if a number fits in a signed 64 bit integer


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> xlist = [dreal.nan, dreal.neginf, '-9223372036854775809', '-9223372036854775808', \
            0.0, '9223372036854775807', '9223372036854775808', dreal.inf]
        >>> for ctx in gui.ctxlist_real:
        ...     res = []
        ...     for x in xlist: res.append(ctx.fitsint64(x))
        ...     print(ctx.fmtname + ': ', res)
        ...     
        ...     
            fpm:  [False, False, True, True, True, True, True, False]
            mpm:  [False, False, False, True, True, True, False, False]
            dpm:  [False, False, False, True, True, True, False, False]
            ipm:  [False, False, False, True, True, True, False, False]
            gpm:  [False, False, False, True, True, True, False, False]
            apm:  [False, False, False, True, True, True, False, False]
         math53:  [False, False, True, True, True, True, True, False]
          sreal:  [False, False, True, True, True, True, True, False]
          dreal:  [False, False, True, True, True, True, True, False]
          ereal:  [False, False, False, True, True, True, False, False]
          qreal:  [False, False, False, True, True, True, False, False]
          oreal:  [False, False, False, True, True, True, False, False]
          mreal:  [False, False, False, True, True, True, False, False]
         sflint:  [False, False, False, False, True, False, False, False]
         dflint:  [False, False, False, False, True, False, False, False]
         eflint:  [False, False, False, False, True, False, False, False]
         qflint:  [False, False, False, False, True, False, False, False]
         oflint:  [False, False, False, False, True, False, False, False]
         mflint:  [False, False, False, True, True, True, False, False]
         aflint:  [False, False, False, True, True, True, False, False]



