

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />






|newpage|


Machine constants, general
===============================================================================



Zero, positive zero
-------------------------------------------------------------------------------

.. property:: ctx.zero

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  `+0`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.zero))
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






Negative zero
-------------------------------------------------------------------------------

.. property:: ctx.negzero

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  `-0`.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.negzero))
            fpm:  -0
            mpm:  0.0
            dpm:  0
            ipm: [0.0,
                  0.0]
            gpm:  -0.0
            apm: 0
         math53:  0
          sreal:  0
          dreal:  0
          ereal:  0
          qreal:  0
          oreal:  0
          mreal:  -0
         sflint:  0
         dflint:  0
         eflint:  0
         qflint:  0
         oflint:  0
         mflint:  -0
         aflint:  0




One
-------------------------------------------------------------------------------

.. property:: Cxt.one

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  `1`



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.one))
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





Positive infinity
-------------------------------------------------------------------------------

.. method:: ctx.inf

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  `+\infty`



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.inf))
            fpm:  INF
            mpm:  inf
            dpm:  Infinity
            ipm: [inf,
                  inf]
            gpm:  inf
            apm: [+/- inf]
         math53:  ∞
          sreal:  ∞
          dreal:  ∞
          ereal:  inf
          qreal:  inf
          oreal:  inf
          mreal:  INF
         sflint:  ∞
         dflint:  ∞
         eflint:  inf
         qflint:  inf
         oflint:  inf
         mflint:  INF
         aflint:  inf




Negative infinity
-------------------------------------------------------------------------------

.. method:: ctx.neginf

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the  representation of `-\infty`



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.neginf))
            fpm:  -INF
            mpm:  -inf
            dpm:  -Infinity
            ipm: [-inf,
                  -inf]
            gpm:  -inf
            apm: [+/- inf]
         math53:  -∞
          sreal:  -∞
          dreal:  -∞
          ereal:  -inf
          qreal:  -inf
          oreal:  -inf
          mreal:  -INF
         sflint:  -∞
         dflint:  -∞
         eflint:  -inf
         qflint:  -inf
         oflint:  -inf
         mflint:  -INF
         aflint:  -inf






NaN (Not a Number)
-------------------------------------------------------------------------------

.. method:: ctx.nan

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``NaN`` (Not a Number).



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.nan))
            fpm:  NAN
            mpm:  nan
            dpm:  NaN
            ipm: [nan,
                  nan]
            gpm:  nan
            apm: nan
         math53:  NaN
          sreal:  NaN
          dreal:  NaN
          ereal:  nan
          qreal:  NaN
          oreal:  nan
          mreal:  NAN
         sflint:  NaN
         dflint:  NaN
         eflint:  nan
         qflint:  NaN
         oflint:  nan
         mflint:  NAN
         aflint:  nan






