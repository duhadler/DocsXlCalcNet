



.. |newpage| raw:: latex

   \newpage


.. |begin_flushleft| raw:: latex

   \begin{flushleft}


.. |end_flushleft| raw:: latex

   \end{flushleft}


.. |vspace| raw:: html

   <br />






|newpage|



.. _rst_py_groups_of_contexts: 

Mathematical functions based on Mpmath, Gmpy2 and Python-Flint (only Python)
==============================================================================


Overview
---------------------------------------------

Contexts
.....................

The following group of contexts are available in Python only:

* Context group ``ctx_pm``:  this context group includes ``fpm`` (see :ref:`fpm <rst_mpm_def>`), ``mpm`` (see :ref:`mpm <rst_fpm_def>`), ``dpm`` (see :ref:`dpm <rst_fpm_def>`), ``ipm`` (see :ref:`ipm <rst_ipm_def>`), ``gpm`` (see :ref:`gpm <rst_gpm_def>`), ``apm`` (see :ref:`apm <rst_apm_def>`). The ``gpm`` context is only available if Gmpy2 is installed, and the ``apm`` context is only available if Python-FLINT is installed.


XlCalcNet provides the following contexts from mpmath:

* Double-precision binary floating point arithmetic using Python's builtin ``float`` and ``complex`` types (``fp``)
* Arbitrary-precision binary floating point arithmetic (``mp``)
* Arbitrary-precision binary interval arithmetic (``iv``)

and in addition

* Arbitrary-precision decimal arithmetic (``dp``)
* Arbitrary-precision binary floating point arithmetic based on gmpy2 (``gp``): requires gmpy2
* Arbitrary-precision ball arithmetic based on ARB (``ap``): requires xlcalcnet libraries

The implementation of contexts in xlcalcnet extents and sometimes modifies the features of the contexts provided by mpmath; in this manual, changes to features already existing in mpmath  will be pointed out explicitly. 

By and large, xlcalcnet tries to be compatible with mpmath conventions as much as possible. The main difference is that in xlcalcnet the context must always explicitly be stated, whereas in mpmath the ``mp`` context is assumed as the default if the context is missing. In mpmath, we can write:


.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> sqrt(2)
    mpf('1.4142135623730951')


This does not work in xlcalcnet, where also the ``mp`` context has to be given explicitly:

.. code-block:: pycon

    >>> from xlcalcnet import mp
    >>> mp.sqrt(2)
    mpf('1.4142135623730951')



The need to import xlcalcnet and mpmath into the same module should rarely arise (importing them separately in different modules of the same project is of course fine). If both are imported, care should be taken that the imported components do not shadow each other, e.g.:


.. code-block:: pycon

    >>> from xlcalcnet import mp
    >>> from xlcalcnet.mpmath import mp as mpm   # importing the mpmath version of xlcalcnet

    >>> mp.sqrt(2) # calling xlcalcnet
    mpf('1.4142135623730951')
    >>> mpm.sqrt(2) # calling mpmath
    mpf('1.4142135623730951')




Conversion of sclars
........................

This function converts scalars into each other

.. method:: ctx.t(x, strings=True)

    where ``ctx`` is ``fpm``, ``mpm``, ``ipm``, ``dec``, ``gmp`` or ``apm``.


    Converts *x* to an ``ctx.mpf`` or ``ctx.mpc``. If *x* is of type ``ctx.mpf``, ``ctx.mpc``, ``int``, ``float``, ``complex``, the conversion will be performed losslessly, except in the following cases:

    *    conversion of a double to a decimal: cutoff at 14 digits

    *    conversion of an int to a mpfr: cutoff at current precision


    If *x* is a string, the result will be rounded to the present working precision. Strings representing fractions or complex numbers are permitted.


    .. code-block:: python

        >>> from xlcalcnet import fpm, mpm, ipm, dec, gmp, apm; ctxall = [fpm, mpm, ipm, dec, gmp, apm]
        >>> for ctx in ctxall: 
        >>> .... print(ctx.name)
        >>> .... ctx.dps = 10; print([ctx.t(3.5), ctx.t(2+3j)])
        >>> .... ctx.dps = 10; print([ctx.t('3.1'), ctx.t('3.1 + 4.6j')])
        fpm
        [3.5, (2+3j)]
        [3.1, (3.1+4.6j)]

        mpm
        [mpf('3.5'), mpc(real='2.0', imag='3.0')]
        [mpf('3.100000000006'), mpc(real='3.100000000006', imag='4.599999999977')]

        ipm
        [mpi('3.5', '3.5'), iv.mpc(mpi('2.0', '2.0'), mpi('3.0', '3.0'))]
        [mpi('3.099999999977', '3.100000000006'), 
        iv.mpc(mpi('3.099999999977', '3.100000000006'), mpi('4.599999999977', '4.600000000035'))]

        dec
        :cite:t:`Decimal('3.5'), DecCplx('2 + 3.0j')]
        :cite:t:`Decimal('3.1'), DecCplx('3.1 + 4.6j')]

        gmp
        [mpfr('3.5',37), mpc('2.0+3.0j',(37,37))]
        [mpfr('3.100000000006',37), mpc('3.100000000006+4.599999999977j',(37,37))]

        apm
        [arb('3.50'), acb('2.00 + 3.00j')]
        [arb('[3.09999999998 +/- 3.24e-11]'), 
        acb('[3.09999999998 +/- 3.24e-11] + [4.59999999998 +/- 6.15e-11]j')]





Precision in bits and digits
......................................


``ctx.prec`` holds the current precision (in bits):

The default precision (in bits) for all contexts after starting xlcalcnet is ``ctx.prec = 53``.

.. code-block:: pycon

    >>> fp.prec, mp.prec, iv.prec, dp.prec, gp.prec, ap.prec
    (53, 53, 53, 53, 53, 53)




``ctx.dps`` holds the current decimal precision (in digits):

The default decimal precision (in digits) for all contexts after starting xlcalcnet is ``ctx.dps = 15``.

.. code-block:: pycon

    >>> fp.dps, mp.dps, iv.dps, dp.dps, gp.dps, ap.dps
    (15, 15, 15, 15, 15, 15)




Like mpmath, xlcalcnet expects every devision of a *normal* number by zero to raise a ``DivisionByZero``, and not to return ``+inf`` or ``-inf``. This is the default behaviour for the ``fp``, ``mp``, ``iv`` and ``dp`` contexts anyway, and has been changed to follow this convention for the ``gp`` and ``ap`` context.

A number of algorithms use this exception to trigger a temporary increase of precision.




|newpage|


.. _rst_fpm_def: 

Double-precision arithmetic: ``fpm``
---------------------------------------------


The Python module ``fpm`` provides support for real and complex floating point numbers in double precision (see https://en.wikipedia.org/wiki/Double-precision_floating-point_format). The corresponding real and complex data types, ``float`` and ``complex``, are implemented in hardware (and are therefore quite fast).


Note: automatic conversion from ``Double`` in .Net Framework to ``float``

Note: no conversion from  ``Complex`` in .Net Framework to ``complex`` in Python. Explain workarounds.





Examples for ``fpm``, real input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02a_FpmReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D02a_FpmReal.py>`__.





Examples for ``fpm``, complex input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02b_FpmCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D02b_FpmCplx.py>`__.





Implementation in Python
........................................................

The Python source code for this module can be found here: `ctx_fpm.py <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ctx_fpm.py>`__.















|newpage|


.. _rst_mpm_def: 

Binary floating-point with arbitrary-precision and exponent: ``mpm``
-------------------------------------------------------------------------------------


The Python module ``mpm`` provides support for real and complex floating point numbers  with arbitrary-precision and exponent. The corresponding real and complex data types, ``float`` and ``complex``, are implemented in software.





Examples for ``mpm``, real input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03a_MpmReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D03a_MpmReal.py>`__.





Examples for ``mpm``, complex input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03b_MpmCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D03b_MpmCplx.py>`__.





Implementation in Python
........................................................

The Python source code for this module can be found here: `ctx_mpm.py <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ctx_mpm.py>`__.









|newpage|


.. _rst_ipm_def: 

Interval arithmetic with arbitrary-precision and exponent:``ipm``
--------------------------------------------------------------------------------------


The Python module ``ipm`` provides support for real and complex intervals  with arbitrary-precision and exponent. The corresponding real and complex data types, ``float`` and ``complex``, are implemented in software.





Examples for ``ipm``, real input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04a_IpmReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D04a_IpmReal.py>`__.





Examples for ``ipm``, complex input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04b_IpmCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D04b_IpmCplx.py>`__.





Implementation in Python
........................................................

The Python source code for this module can be found here: `ctx_ipm.py <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ctx_ipm.py>`__.






|newpage|


.. _rst_dpm_def: 

Decimal floating-point in arbitrary-precision with limited exponent: ``dpm``
---------------------------------------------------------------------------------


The Python module ``dpm`` provides support for real and complex decimal floating-point in arbitrary-precision with limited exponent. The corresponding real and complex data types, ``float`` and ``complex``, are implemented in software.



Additional contexts are used in xlcalcnet to implement its functions for the mpmath data types, and the Decimal data type, which is part of Python. 


Both real numbers (mpf) and complex numbers (mpc) are implemented. 


In CPython, the ``decimal`` module provides support for fast correctly-rounded decimal floating point arithmetic. See https://docs.python.org/3/library/decimal.html for a decription of the ``Decimal`` data type.

The ``decimal`` module includes only a few transcendental functions: sqrt, log, exp.

The ``dec`` context gives access to many more:





Examples for ``dpm``, real input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04a_IpmReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D05a_DpmReal.py>`__.





Examples for ``dpm``, complex input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05b_DpmCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D05b_DpmCplx.py>`__.





Implementation in Python
........................................................

The Python source code for this module can be found here: `ctx_dpm.py <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ctx_dpm.py>`__.






|newpage|


.. _rst_qpm_def: 

Rational numbers: ``qpm``
---------------------------------------------------------------------------------


The ``qpm`` data type is mostly useful in the context of linear algebra, where it can provide exact results.

Only real numbers (mpf) are implemented. 

The internal representation dependes on what else is installed on the system:

If ``apm`` is available, the ``fmpq`` data type is used; otherwise, if ``gpm`` is available, the ``mpq`` data type is used; otherwise, Python's built in ``Fraction`` data type is used.



In CPython, the ``fractions`` module provides support for rational number arithmetic. See https://docs.python.org/3/library/fractions.html for a decription of the ``Fraction`` data type.





Examples for ``qpm``, real input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06a_QpmReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D06a_QpmReal.py>`__.






Implementation in Python
........................................................

The Python source code for this module can be found here: `ctx_dpm.py <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ctx_qpm.py>`__.









.. _rst_gpm_def: 

Binary floating-point in arbitrary-precision with limited exponent: ``gpm``
--------------------------------------------------------------------------------------

The Python module ``gpm`` provides support for real and complex Binary floating-point in arbitrary-precision with limited exponent. The corresponding real and complex data types, ``float`` and ``complex``, are implemented in software.


gmpy2 is a C-coded Python extension module that supports multiple-precision arithmetic. 

https://gmpy2.readthedocs.io/en/latest/



Examples for ``gpm``, real input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07a_GpmReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D07a_GpmReal.py>`__.





Examples for ``gpm``, complex input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07b_GpmCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D07b_GpmCplx.py>`__.





Implementation in Python
........................................................

The Python source code for this module can be found here: `ctx_gpm.py <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ctx_gpm.py>`__.












|newpage|


.. _rst_apm_def: 

Binary balls in arbitrary-precision and with arbitrary exponent: ``apm``
-------------------------------------------------------------------------------------

The Python module ``apm`` provides support for real and complex binary balls in arbitrary-precision and with arbitrary exponent. The corresponding real and complex data types, ``float`` and ``complex``, are implemented in software.



pythonflint is a C-coded Python extension module that supports multiple-precision arithmetic. 

https://python-flint.readthedocs.io/en/latest/




Examples for ``apm``, real input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D08a_ApmReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D08a_ApmReal.py>`__.





Examples for ``apm``, complex input
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import math53
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_math53()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = math53.t(i)
        print('x = math53.t(i):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)

        x = math53.t(5.7)
        print('x = math53T(5.7):', x)
        x0 = math53.t(2329456398453948563945639364827346)
        print('x0 = math53T(2329456398453948563945639364827346', x0)
        x1 = math53.t("2329456398453948563945639364827346")
        print('x1 = math53.t("2329456398453948563945639364827346"):', x1)
        x = math53.t("5.5")
        print('x = math53T("5.5"):', x)

        print()
        x = math53.t(55)
        print('x = math53.t(5):', x)
        y = math53.exp(x)
        print('y = math53.exp(x):', y)

        z = math53.exp(5.5)
        print('z = math53.exp(5.5):', z)
        z = math53.exp(5)
        print('z = math53.exp(5):', z)
        z = math53.exp("5.5")
        print('z = math53.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = math53.exp(dec)
        print('z = math53.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = math53.exp(frac)
        print('z = math53.exp(frac):', z)

        print()
        x = math53.t(5.5)
        print('x = math53.t(55):', x)
        y = math53.t(3.3)
        print('y = math53.t(33):', y)
        z = math53.pow(x, y)
        print('z = math53.pow(x, y):        ', z)
        z = math53.pow(5.5, 3.3)
        print('z = math53.pow(5.5, 3.3):    ', z)
        z = math53.pow("5.5", "3.3")
        print('z = math53.pow("5.5", "3.3"):', z)
        z = math53.pow(5, 3)
        print('z = math53.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_math53():
        print()
        print('<H1 Title="Arithmetic operators with math53">')

        x = math53.t(5.0)
        y = math53.t(2.5)
        print('x: ', x)
        print('y: ', y)

        res = x + y
        print('res = x + y:', res)
        res = y + x
        print('res = y + x:', res)

        res = x - y
        print('res = x - y:', res)
        res = y - x
        print('res = y - x:', res)

        res = x * y
        print('res = x * y:', res)
        res = y * x
        print('res = y * x:', res)

        res = x / y
        print('res = x / y:', res)
        res = y / x
        print('res = y / x:', res)
        print('</H1>')



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D08b_ApmCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C05_ContextsMpmath/D08b_ApmCplx.py>`__.





Implementation in Python
........................................................

The Python source code for this module can be found here: `ctx_apm.py <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ctx_apm.py>`__.




