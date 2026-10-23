

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


    In extended precision (32 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.Zero()
        ereal('0.0000000000000000000)


    In double precision (64 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.Zero()
        0.0




Negative zero
-------------------------------------------------------------------------------

.. property:: ctx.negzero

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  `-0`.


    In extended precision (32 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.Zero()
        ereal('0.0000000000000000000)


    In double precision (64 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.Zero()
        0.0




One
-------------------------------------------------------------------------------

.. property:: Cxt.one

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  `1`


    In extended precision (32 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.One()
        ereal('1.0000000000000000000')


    In double precision (64 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.One()
        1.0





Imaginary One
-------------------------------------------------------------------------------

.. property:: ctx.onej

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the imaginary unit.


    In extended precision (32 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.ConstDegree()
        ereal('1.7453292519943295769E-2')


    In double precision (64 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.ConstDegree()
        0.0174532925199433





Positive infinity
-------------------------------------------------------------------------------

.. method:: ctx.inf

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns  `+\infty`


    In extended precision (32 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.PositiveInfinity()
        ereal('+Inf')


    In double precision (64 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.PositiveInfinity()
        +Inf




Negative infinity
-------------------------------------------------------------------------------

.. method:: ctx.neginf

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns the  representation of `-\infty`


    In extended precision (32 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.NegativeInfinity()
        ereal('-Inf')


    In double precision (64 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.NegativeInfinity()
        -Inf






NaN (Not a Number)
-------------------------------------------------------------------------------

.. method:: ctx.nan

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns ``NaN`` (Not a Number).


    In extended precision (32 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.Nan()
        ereal('Nan')


    In double precision (64 bit version of xlcalcnet)

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.Nan()
        Nan






