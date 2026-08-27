



.. |newpage| raw:: latex

   \newpage


.. |begin_flushleft| raw:: latex

   \begin{flushleft}


.. |end_flushleft| raw:: latex

   \end{flushleft}


.. |vspace| raw:: html

   <br />






|newpage|



.. _rst_net_groups_of_contexts: 

Mathematical functions in fixed precision (C\#, can be called from Python)
=====================================================================================


C\# based context groups
------------------------------------------------------------------------------------------

Various additional numerical contexts support C\# and Python. It is convenient to divide them into groups to make referencing them per function description more efficient.

The following groups of contexts are available:



Context group ``ctx53``
........................................................

This context group includes ``math53`` and ``cmath53`` (see :ref:`math53/cmath53 <rst_math53_def>`). Almost all functions are from the DAMath library, with a few functions from Boost Math, Scipy, Julia and other libraries available on Github.



Context group ``ctxcpp``
........................................................

This context group includes contexts which contain functions of the C++ standard library, the Eigen library, and functions which can easily be derived from them. They include contexts in fixed precision: ``sreal`` and ``scplx`` (see :ref:`sreal/scplx <rst_sreal_def>`), ``dreal`` and ``dcplx`` (see :ref:`dreal/dcplx <rst_dreal_def>`),  ``ereal`` and ``ecplx`` (see :ref:`ereal/ecplx <rst_ereal_def>`), ``qreal`` and ``qcplx`` (see :ref:`qreal/cplx <rst_qreal_def>`), ``oreal`` and ``ocplx`` (see :ref:`oreal/ocplx <rst_oreal_def>`), ; and contexts in arbitrary precision, which are part of XlCalcNet2 (which hence needs to be installed): ``mreal`` and ``mcplx`` (see :ref:`mreal/mcplx <rst_mreal_def>`).


Context group ``ctxboost``
........................................................

This context group includes contexts which contain functions of the the Boost Math/Multiprecision/Odeint libraries, and functions which can easily be derived from them. They include contexts in fixed precision: ``sreal`` (see :ref:`sreal <rst_sreal_def>`), ``dreal`` (see :ref:`dreal <rst_dreal_def>`),  ``ereal`` (see :ref:`ereal <rst_ereal_def>`), ``qreal`` (see :ref:`qreal <rst_qreal_def>`), ``oreal`` (see :ref:`oreal <rst_oreal_def>`), ; and one context in arbitrary precision, which is part of XlCalcNet2 (which hence needs to be installed): ``mreal`` (see :ref:`mreal <rst_mreal_def>`).


Context group ``ctxflint``
........................................................

This context group includes contexts which contain functions of the Flint 3.4 library, the Eigen library, and functions which can easily be derived from them. These are contexts in fixed and in arbitrary precision, which are part of XlCalcNet2 (which hence needs to be installed). They include ``sflint`` and ``sflintc`` (see :ref:`sflint/sflintc <rst_srealflint_def>`), ``dflint`` and ``dflintc`` (see :ref:`dflint/dflintc <rst_drealflint_def>`),  ``eflint`` and ``eflintc`` (see :ref:`eflint/eflintc <rst_erealflint_def>`), ``qflint`` and ``qflintc`` (see :ref:`qflint/qflint <rst_qrealflint_def>`), ``oflint`` and ``oflintc`` (see :ref:`oflint/oflintc <rst_orealflint_def>`), ``mflint`` and ``mflintc`` (see :ref:`mflint/mflintc <rst_mreal_def>`), ``aflint`` and ``aflintc`` (see :ref:`aflint/aflint <rst_areal_def>`). 












|newpage|


.. _rst_math53_def: 

Scalar functions with ``Double`` and ``Complex``: ``math53`` and  ``cmath53``
------------------------------------------------------------------------------------------

The C\# modules ``math53`` and ``cmath53`` provide support for real and complex floating point numbers in double precision (see https://en.wikipedia.org/wiki/Double-precision_floating-point_format). The corresponding real and complex data types, ``Double`` and ``Complex``, are implemented in hardware and are part of .Net Framework (and are therefore quite fast).


Note: automatic conversion from ``Double`` in .Net Framework to ``float``

Note: no conversion from  ``Complex`` in .Net Framework to ``complex`` in Python. Explain workarounds.

DAMath library.





Examples in C\#, ``math53``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some math53 functions");
        SrealTest0();
        SrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void Math53Test0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "ScplxTest0"  + "\"" + ">");

        var a = cmath53.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = cmath53.abs(a);
        Console.WriteLine("res1 = cmath53.abs(a): {0}", res1);

        var res2 = cmath53.exp(a);
        Console.WriteLine("res2 = cmath53.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void Math53Test1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "ScplxTest1"  + "\"" + ">");

        var a = cmath53.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = cmath53.asin(a);
        Console.WriteLine("res1 = cmath53.asin(a) {0}", res1);

        var res2 = cmath53.sin(a);
        Console.WriteLine("res2 = cmath53.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02a_Math53.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D02a_Math53.cs>`__.







Examples in C\#, ``cmath53``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some math53 functions");
        SrealTest0();
        SrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void ScplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "ScplxTest0"  + "\"" + ">");

        var a = cmath53.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = cmath53.abs(a);
        Console.WriteLine("res1 = cmath53.abs(a): {0}", res1);

        var res2 = cmath53.exp(a);
        Console.WriteLine("res2 = cmath53.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void ScplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "ScplxTest1"  + "\"" + ">");

        var a = cmath53.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = cmath53.asin(a);
        Console.WriteLine("res1 = cmath53.asin(a) {0}", res1);

        var res2 = cmath53.sin(a);
        Console.WriteLine("res2 = cmath53.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02b_Cmath53.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D02b_Cmath53.cs>`__.





Examples in Python, ``math53``
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




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02a_Math53.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D02a_Math53.py>`__.





Examples in Python, ``cmath53``
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



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02b_Cmath53.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D02b_Cmath53.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the module ``math53`` can be found here: `math53.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/math53.cs>`__.

The C\# source code for the module ``cmath53`` can be found here: `cmath53.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/cmath53.cs>`__.



The Pascal source code which is called from ``math53.cs`` and ``cmath53.cs`` can be found here:  `libwe64d.pas <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/Pascal/we64/Lib/libwe64d.pas>`__.

The C++ source code which is called from ``math53.cs`` and ``cmath53.cs`` can be found here:  `XSF.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/XSF/XSF.cpp>`__.


The C\# source code (transcribed from the Julia project) which is called from ``math53.cs`` and ``cmath53.cs`` can be found here:  `fromjulia.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/fromjulia.cs>`__.















|newpage|

.. _rst_sreal_def: 

Binary floating point, single precision: ``sreal`` and ``scplx``
----------------------------------------------------------------------

The C\# modules ``sreal`` and ``scplx`` provide support for real and complex floating point numbers in single precision (see https://en.wikipedia.org/wiki/Single-precision_floating-point_format). The corresponding real data type, ``Single``, is implemented in hardware and is part of .Net Framework (and is therefore quite fast), the corresponding complex data type, ``SingleC``, is also implemented in hardware, but has been added as an object in XlCalcNet (and has therefore the overhead of objects).

The C\# modules ``sreal`` and ``scplx`` fully support Boost.Math and Eigen.

TODO: python code showing larget, lowest, machine epsilon etc.





Examples in C\#, ``sreal``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some sreal functions");
        SrealTest0();
        SrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void ScplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "ScplxTest0"  + "\"" + ">");

        var a = scplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = scplx.abs(a);
        Console.WriteLine("res1 = scplx.abs(a): {0}", res1);

        var res2 = scplx.exp(a);
        Console.WriteLine("res2 = scplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void ScplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "ScplxTest1"  + "\"" + ">");

        var a = scplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = scplx.asin(a);
        Console.WriteLine("res1 = scplx.asin(a) {0}", res1);

        var res2 = scplx.sin(a);
        Console.WriteLine("res2 = scplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02a_Sreal.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D03a_Sreal.cs>`__.







Examples in C\#, ``scplx``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some sreal functions");
        SrealTest0();
        SrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void ScplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "ScplxTest0"  + "\"" + ">");

        var a = scplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = scplx.abs(a);
        Console.WriteLine("res1 = scplx.abs(a): {0}", res1);

        var res2 = scplx.exp(a);
        Console.WriteLine("res2 = scplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void ScplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "ScplxTest1"  + "\"" + ">");

        var a = scplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = scplx.asin(a);
        Console.WriteLine("res1 = scplx.asin(a) {0}", res1);

        var res2 = scplx.sin(a);
        Console.WriteLine("res2 = scplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03b_Scplx.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D03b_Scplx.cs>`__.





Examples in Python, ``sreal``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import sreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_sreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = sreal.t(i)
        print('x = sreal.t(i):', x)

        x = sreal.t(5.7)
        print('x = srealT(5.7):', x)

        x = sreal.t(5.7)
        print('x = srealT(5.7):', x)
        x0 = sreal.t(2329456398453948563945639364827346)
        print('x0 = srealT(2329456398453948563945639364827346', x0)
        x1 = sreal.t("2329456398453948563945639364827346")
        print('x1 = sreal.t("2329456398453948563945639364827346"):', x1)
        x = sreal.t("5.5")
        print('x = srealT("5.5"):', x)

        print()
        x = sreal.t(55)
        print('x = sreal.t(5):', x)
        y = sreal.exp(x)
        print('y = sreal.exp(x):', y)

        z = sreal.exp(5.5)
        print('z = sreal.exp(5.5):', z)
        z = sreal.exp(5)
        print('z = sreal.exp(5):', z)
        z = sreal.exp("5.5")
        print('z = sreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = sreal.exp(dec)
        print('z = sreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = sreal.exp(frac)
        print('z = sreal.exp(frac):', z)

        print()
        x = sreal.t(5.5)
        print('x = sreal.t(55):', x)
        y = sreal.t(3.3)
        print('y = sreal.t(33):', y)
        z = sreal.pow(x, y)
        print('z = sreal.pow(x, y):        ', z)
        z = sreal.pow(5.5, 3.3)
        print('z = sreal.pow(5.5, 3.3):    ', z)
        z = sreal.pow("5.5", "3.3")
        print('z = sreal.pow("5.5", "3.3"):', z)
        z = sreal.pow(5, 3)
        print('z = sreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_sreal():
        print()
        print('<H1 Title="Arithmetic operators with sreal">')

        x = sreal.t(5.0)
        y = sreal.t(2.5)
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




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03a_SReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D03a_SReal.py>`__.





Examples in Python, ``scplx``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import sreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_sreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = sreal.t(i)
        print('x = sreal.t(i):', x)

        x = sreal.t(5.7)
        print('x = srealT(5.7):', x)

        x = sreal.t(5.7)
        print('x = srealT(5.7):', x)
        x0 = sreal.t(2329456398453948563945639364827346)
        print('x0 = srealT(2329456398453948563945639364827346', x0)
        x1 = sreal.t("2329456398453948563945639364827346")
        print('x1 = sreal.t("2329456398453948563945639364827346"):', x1)
        x = sreal.t("5.5")
        print('x = srealT("5.5"):', x)

        print()
        x = sreal.t(55)
        print('x = sreal.t(5):', x)
        y = sreal.exp(x)
        print('y = sreal.exp(x):', y)

        z = sreal.exp(5.5)
        print('z = sreal.exp(5.5):', z)
        z = sreal.exp(5)
        print('z = sreal.exp(5):', z)
        z = sreal.exp("5.5")
        print('z = sreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = sreal.exp(dec)
        print('z = sreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = sreal.exp(frac)
        print('z = sreal.exp(frac):', z)

        print()
        x = sreal.t(5.5)
        print('x = sreal.t(55):', x)
        y = sreal.t(3.3)
        print('y = sreal.t(33):', y)
        z = sreal.pow(x, y)
        print('z = sreal.pow(x, y):        ', z)
        z = sreal.pow(5.5, 3.3)
        print('z = sreal.pow(5.5, 3.3):    ', z)
        z = sreal.pow("5.5", "3.3")
        print('z = sreal.pow("5.5", "3.3"):', z)
        z = sreal.pow(5, 3)
        print('z = sreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_sreal():
        print()
        print('<H1 Title="Arithmetic operators with sreal">')

        x = sreal.t(5.0)
        y = sreal.t(2.5)
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



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03b_SCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D03b_SCplx.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the module ``sreal`` can be found here: `sreal.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/sreal.cs>`__.

The C\# source code for the module ``scplx`` can be found here: `scplx.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/scplx.cs>`__.



The C++ source code supporting scalars in general which is called from ``sreal.cs`` and ``scplx.cs`` can be found here:  `UseSReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C++/xlcalcnet/mpNum/UseSReal.cpp>`__.

The C++ source code which interacts directly with Boost can be found here: `BoostSReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostMath/BoostSReal.cpp>`__.



The C++ source code supporting Eigen which is called from ``sreal.cs`` and ``scplx.cs`` can be found here: `UseEigenSReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C++/xlcalcnet/mpNum/UseEigenSReal.cpp>`__.

The C++ source code which interacts directly with Eigen can be found in the folder: `BoostEigenMath.cpp <https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostEigenMath>`__.








|newpage|

.. _rst_dreal_def: 

Binary floating point, double precision: ``dreal`` and ``dcplx``
--------------------------------------------------------------------------

The C\# modules ``dreal`` and ``dcplx`` provide support for real and complex floating point numbers in double precision (see https://en.wikipedia.org/wiki/Double-precision_floating-point_format). The corresponding real and complex data types, ``Double`` and ``Complex``, are implemented in hardware and are part of .Net Framework (and are therefore quite fast).


The C\# modules ``dreal`` and ``dcplx`` fully support Boost.Math and Eigen.



Note: automatic conversion from ``Double`` in .Net Framework to ``float``

Note: no conversion from  ``Complex`` in .Net Framework to ``complex`` in Python. Explain workarounds.

Note: issues with multiplication scalar * matrix in complex





Examples in C\#, ``dreal``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some dreal functions");
        DrealTest0();
        DrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void DcplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "DcplxTest0"  + "\"" + ">");

        var a = dcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = dcplx.abs(a);
        Console.WriteLine("res1 = dcplx.abs(a): {0}", res1);

        var res2 = dcplx.exp(a);
        Console.WriteLine("res2 = dcplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void DcplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "DcplxTest1"  + "\"" + ">");

        var a = dcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = dcplx.asin(a);
        Console.WriteLine("res1 = dcplx.asin(a) {0}", res1);

        var res2 = dcplx.sin(a);
        Console.WriteLine("res2 = dcplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04a_Dreal.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D04a_Dreal.cs>`__.







Examples in C\#, ``dcplx``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some dreal functions");
        DrealTest0();
        DrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void DcplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "DcplxTest0"  + "\"" + ">");

        var a = dcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = dcplx.abs(a);
        Console.WriteLine("res1 = dcplx.abs(a): {0}", res1);

        var res2 = dcplx.exp(a);
        Console.WriteLine("res2 = dcplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void DcplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "DcplxTest1"  + "\"" + ">");

        var a = dcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = dcplx.asin(a);
        Console.WriteLine("res1 = dcplx.asin(a) {0}", res1);

        var res2 = dcplx.sin(a);
        Console.WriteLine("res2 = dcplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04b_Dcplx.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D04b_Dcplx.cs>`__.





Examples in Python, ``dreal``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import dreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_dreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = dreal.t(i)
        print('x = dreal.t(i):', x)

        x = dreal.t(5.7)
        print('x = drealT(5.7):', x)

        x = dreal.t(5.7)
        print('x = drealT(5.7):', x)
        x0 = dreal.t(2329456398453948563945639364827346)
        print('x0 = drealT(2329456398453948563945639364827346', x0)
        x1 = dreal.t("2329456398453948563945639364827346")
        print('x1 = dreal.t("2329456398453948563945639364827346"):', x1)
        x = dreal.t("5.5")
        print('x = drealT("5.5"):', x)

        print()
        x = dreal.t(55)
        print('x = dreal.t(5):', x)
        y = dreal.exp(x)
        print('y = dreal.exp(x):', y)

        z = dreal.exp(5.5)
        print('z = dreal.exp(5.5):', z)
        z = dreal.exp(5)
        print('z = dreal.exp(5):', z)
        z = dreal.exp("5.5")
        print('z = dreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = dreal.exp(dec)
        print('z = dreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = dreal.exp(frac)
        print('z = dreal.exp(frac):', z)

        print()
        x = dreal.t(5.5)
        print('x = dreal.t(55):', x)
        y = dreal.t(3.3)
        print('y = dreal.t(33):', y)
        z = dreal.pow(x, y)
        print('z = dreal.pow(x, y):        ', z)
        z = dreal.pow(5.5, 3.3)
        print('z = dreal.pow(5.5, 3.3):    ', z)
        z = dreal.pow("5.5", "3.3")
        print('z = dreal.pow("5.5", "3.3"):', z)
        z = dreal.pow(5, 3)
        print('z = dreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_dreal():
        print()
        print('<H1 Title="Arithmetic operators with dreal">')

        x = dreal.t(5.0)
        y = dreal.t(2.5)
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




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04a_DReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D04a_DReal.py>`__.





Examples in Python, ``dcplx``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import dreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_dreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = dreal.t(i)
        print('x = dreal.t(i):', x)

        x = dreal.t(5.7)
        print('x = drealT(5.7):', x)

        x = dreal.t(5.7)
        print('x = drealT(5.7):', x)
        x0 = dreal.t(2329456398453948563945639364827346)
        print('x0 = drealT(2329456398453948563945639364827346', x0)
        x1 = dreal.t("2329456398453948563945639364827346")
        print('x1 = dreal.t("2329456398453948563945639364827346"):', x1)
        x = dreal.t("5.5")
        print('x = drealT("5.5"):', x)

        print()
        x = dreal.t(55)
        print('x = dreal.t(5):', x)
        y = dreal.exp(x)
        print('y = dreal.exp(x):', y)

        z = dreal.exp(5.5)
        print('z = dreal.exp(5.5):', z)
        z = dreal.exp(5)
        print('z = dreal.exp(5):', z)
        z = dreal.exp("5.5")
        print('z = dreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = dreal.exp(dec)
        print('z = dreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = dreal.exp(frac)
        print('z = dreal.exp(frac):', z)

        print()
        x = dreal.t(5.5)
        print('x = dreal.t(55):', x)
        y = dreal.t(3.3)
        print('y = dreal.t(33):', y)
        z = dreal.pow(x, y)
        print('z = dreal.pow(x, y):        ', z)
        z = dreal.pow(5.5, 3.3)
        print('z = dreal.pow(5.5, 3.3):    ', z)
        z = dreal.pow("5.5", "3.3")
        print('z = dreal.pow("5.5", "3.3"):', z)
        z = dreal.pow(5, 3)
        print('z = dreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_dreal():
        print()
        print('<H1 Title="Arithmetic operators with dreal">')

        x = dreal.t(5.0)
        y = dreal.t(2.5)
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



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04b_DCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D04b_DCplx.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the module ``dreal`` can be found here: `dreal.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/dreal.cs>`__.

The C\# source code for the module ``dcplx`` can be found here: `dcplx.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/dcplx.cs>`__.



The C++ source code supporting scalars in general which is called from ``dreal.cs`` and ``dcplx.cs`` can be found here:  `UseFReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/mpNum/UseFReal.cpp>`__.

The C++ source code which interacts directly with Boost can be found here: `BoostSReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostMath/BoostFReal.cpp>`__, and  `BoostDouble.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostMath/BoostDouble.cpp>`__.



The C++ source code supporting Eigen which is called from ``dreal.cs`` and ``dcplx.cs`` can be found here: `UseEigenFReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/mpNum/UseEigenFReal.cpp>`__.

The C++ source code which interacts directly with Eigen can be found in the folder: `BoostEigenMath.cpp <https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostEigenMath>`__.

















|newpage|

.. _rst_ereal_def: 


Binary floating point, extended precision: ``ereal`` and ``ecplx``
----------------------------------------------------------------------------

The C\# modules ``ereal`` and ``ecplx`` provide support for real and complex floating point numbers in extended precision (see https://en.wikipedia.org/wiki/Extended_precision). The corresponding real and complex data types, ``Extended`` and ``ExtendedC``, have been added as objects in XlCalcNet (and have therefore the overhead of objects). They are, however, implemented in hardware, and are supported as native types in C++ (when using GCC). This means that the routines in extended precision provided in Boost and Eigen are much faster than the corresponding routines in quadruple precision.


The C\# modules ``ereal`` and ``ecplx`` fully support Boost.Math and Eigen.




Examples in C\#, ``ereal``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some ereal functions");
        ErealTest0();
        ErealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void EcplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "EcplxTest0"  + "\"" + ">");

        var a = ecplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = ecplx.abs(a);
        Console.WriteLine("res1 = ecplx.abs(a): {0}", res1);

        var res2 = ecplx.exp(a);
        Console.WriteLine("res2 = ecplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void EcplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "EcplxTest1"  + "\"" + ">");

        var a = ecplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = ecplx.asin(a);
        Console.WriteLine("res1 = ecplx.asin(a) {0}", res1);

        var res2 = ecplx.sin(a);
        Console.WriteLine("res2 = ecplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05a_Ereal.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D05a_Ereal.cs>`__.







Examples in C\#, ``ecplx``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some ereal functions");
        ErealTest0();
        ErealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void EcplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "EcplxTest0"  + "\"" + ">");

        var a = ecplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = ecplx.abs(a);
        Console.WriteLine("res1 = ecplx.abs(a): {0}", res1);

        var res2 = ecplx.exp(a);
        Console.WriteLine("res2 = ecplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void EcplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "EcplxTest1"  + "\"" + ">");

        var a = ecplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = ecplx.asin(a);
        Console.WriteLine("res1 = ecplx.asin(a) {0}", res1);

        var res2 = ecplx.sin(a);
        Console.WriteLine("res2 = ecplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05b_Ecplx.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D05b_Ecplx.cs>`__.





Examples in Python, ``ereal``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import ereal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_ereal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = ereal.t(i)
        print('x = ereal.t(i):', x)

        x = ereal.t(5.7)
        print('x = erealT(5.7):', x)

        x = ereal.t(5.7)
        print('x = erealT(5.7):', x)
        x0 = ereal.t(2329456398453948563945639364827346)
        print('x0 = erealT(2329456398453948563945639364827346', x0)
        x1 = ereal.t("2329456398453948563945639364827346")
        print('x1 = ereal.t("2329456398453948563945639364827346"):', x1)
        x = ereal.t("5.5")
        print('x = erealT("5.5"):', x)

        print()
        x = ereal.t(55)
        print('x = ereal.t(5):', x)
        y = ereal.exp(x)
        print('y = ereal.exp(x):', y)

        z = ereal.exp(5.5)
        print('z = ereal.exp(5.5):', z)
        z = ereal.exp(5)
        print('z = ereal.exp(5):', z)
        z = ereal.exp("5.5")
        print('z = ereal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = ereal.exp(dec)
        print('z = ereal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = ereal.exp(frac)
        print('z = ereal.exp(frac):', z)

        print()
        x = ereal.t(5.5)
        print('x = ereal.t(55):', x)
        y = ereal.t(3.3)
        print('y = ereal.t(33):', y)
        z = ereal.pow(x, y)
        print('z = ereal.pow(x, y):        ', z)
        z = ereal.pow(5.5, 3.3)
        print('z = ereal.pow(5.5, 3.3):    ', z)
        z = ereal.pow("5.5", "3.3")
        print('z = ereal.pow("5.5", "3.3"):', z)
        z = ereal.pow(5, 3)
        print('z = ereal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_ereal():
        print()
        print('<H1 Title="Arithmetic operators with ereal">')

        x = ereal.t(5.0)
        y = ereal.t(2.5)
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




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05a_EReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D05a_EReal.py>`__.





Examples in Python, ``ecplx``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import ereal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_ereal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = ereal.t(i)
        print('x = ereal.t(i):', x)

        x = ereal.t(5.7)
        print('x = erealT(5.7):', x)

        x = ereal.t(5.7)
        print('x = erealT(5.7):', x)
        x0 = ereal.t(2329456398453948563945639364827346)
        print('x0 = erealT(2329456398453948563945639364827346', x0)
        x1 = ereal.t("2329456398453948563945639364827346")
        print('x1 = ereal.t("2329456398453948563945639364827346"):', x1)
        x = ereal.t("5.5")
        print('x = erealT("5.5"):', x)

        print()
        x = ereal.t(55)
        print('x = ereal.t(5):', x)
        y = ereal.exp(x)
        print('y = ereal.exp(x):', y)

        z = ereal.exp(5.5)
        print('z = ereal.exp(5.5):', z)
        z = ereal.exp(5)
        print('z = ereal.exp(5):', z)
        z = ereal.exp("5.5")
        print('z = ereal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = ereal.exp(dec)
        print('z = ereal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = ereal.exp(frac)
        print('z = ereal.exp(frac):', z)

        print()
        x = ereal.t(5.5)
        print('x = ereal.t(55):', x)
        y = ereal.t(3.3)
        print('y = ereal.t(33):', y)
        z = ereal.pow(x, y)
        print('z = ereal.pow(x, y):        ', z)
        z = ereal.pow(5.5, 3.3)
        print('z = ereal.pow(5.5, 3.3):    ', z)
        z = ereal.pow("5.5", "3.3")
        print('z = ereal.pow("5.5", "3.3"):', z)
        z = ereal.pow(5, 3)
        print('z = ereal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_ereal():
        print()
        print('<H1 Title="Arithmetic operators with ereal">')

        x = ereal.t(5.0)
        y = ereal.t(2.5)
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



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05b_ECplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D05b_ECplx.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the module ``ereal`` can be found here: `ereal.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/ereal.cs>`__.

The C\# source code for the module ``ecplx`` can be found here: `ecplx.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/ecplx.cs>`__.



The C++ source code supporting scalars in general which is called from ``ereal.cs`` and ``ecplx.cs`` can be found here:  `UseXReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/mpNum/UseXReal.cpp>`__.

The C++ source code which interacts directly with Boost can be found here: `BoostXReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostMath/BoostXReal.cpp>`__.



The C++ source code supporting Eigen which is called from ``ereal.cs`` and ``ecplx.cs`` can be found here: `UseEigenXReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/mpNum/UseEigenXReal.cpp>`__.

The C++ source code which interacts directly with Eigen can be found in the folder: `BoostEigenMath.cpp <https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostEigenMath>`__.











|newpage|

.. _rst_qreal_def: 


Binary floating point, quadruple precision: ``qreal`` and ``qcplx``
------------------------------------------------------------------------------

The C\# modules ``qreal`` and ``qcplx`` provide support for real and complex floating point numbers in quadruple precision (see https://en.wikipedia.org/wiki/Quadruple-precision_floating-point_format). The corresponding real and complex data types, ``Quadruple`` and ``QuadrupleC``, have been added as objects in XlCalcNet (and have therefore the overhead of objects). They are implemented in software, using the ``float128`` data type of Boost Multiprecision. This means that the routines in quadruple precision provided in Boost and Eigen are much slower than the corresponding routines in extended precision.

The C\# modules ``qreal`` and ``qcplx`` fully support Boost.Math and Eigen.






Examples in C\#, ``qreal``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some qreal functions");
        QrealTest0();
        QrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void QcplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "QcplxTest0"  + "\"" + ">");

        var a = qcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qcplx.abs(a);
        Console.WriteLine("res1 = qcplx.abs(a): {0}", res1);

        var res2 = qcplx.exp(a);
        Console.WriteLine("res2 = qcplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void QcplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "QcplxTest1"  + "\"" + ">");

        var a = qcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qcplx.asin(a);
        Console.WriteLine("res1 = qcplx.asin(a) {0}", res1);

        var res2 = qcplx.sin(a);
        Console.WriteLine("res2 = qcplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06a_Qreal.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D06a_Qreal.cs>`__.







Examples in C\#, ``qcplx``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some qreal functions");
        QrealTest0();
        QrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void QcplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "QcplxTest0"  + "\"" + ">");

        var a = qcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qcplx.abs(a);
        Console.WriteLine("res1 = qcplx.abs(a): {0}", res1);

        var res2 = qcplx.exp(a);
        Console.WriteLine("res2 = qcplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void QcplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "QcplxTest1"  + "\"" + ">");

        var a = qcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qcplx.asin(a);
        Console.WriteLine("res1 = qcplx.asin(a) {0}", res1);

        var res2 = qcplx.sin(a);
        Console.WriteLine("res2 = qcplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02b_Qcplx.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D06b_Qcplx.cs>`__.





Examples in Python, ``qreal``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import qreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_qreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = qreal.t(i)
        print('x = qreal.t(i):', x)

        x = qreal.t(5.7)
        print('x = qrealT(5.7):', x)

        x = qreal.t(5.7)
        print('x = qrealT(5.7):', x)
        x0 = qreal.t(2329456398453948563945639364827346)
        print('x0 = qrealT(2329456398453948563945639364827346', x0)
        x1 = qreal.t("2329456398453948563945639364827346")
        print('x1 = qreal.t("2329456398453948563945639364827346"):', x1)
        x = qreal.t("5.5")
        print('x = qrealT("5.5"):', x)

        print()
        x = qreal.t(55)
        print('x = qreal.t(5):', x)
        y = qreal.exp(x)
        print('y = qreal.exp(x):', y)

        z = qreal.exp(5.5)
        print('z = qreal.exp(5.5):', z)
        z = qreal.exp(5)
        print('z = qreal.exp(5):', z)
        z = qreal.exp("5.5")
        print('z = qreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = qreal.exp(dec)
        print('z = qreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = qreal.exp(frac)
        print('z = qreal.exp(frac):', z)

        print()
        x = qreal.t(5.5)
        print('x = qreal.t(55):', x)
        y = qreal.t(3.3)
        print('y = qreal.t(33):', y)
        z = qreal.pow(x, y)
        print('z = qreal.pow(x, y):        ', z)
        z = qreal.pow(5.5, 3.3)
        print('z = qreal.pow(5.5, 3.3):    ', z)
        z = qreal.pow("5.5", "3.3")
        print('z = qreal.pow("5.5", "3.3"):', z)
        z = qreal.pow(5, 3)
        print('z = qreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_qreal():
        print()
        print('<H1 Title="Arithmetic operators with qreal">')

        x = qreal.t(5.0)
        y = qreal.t(2.5)
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




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06a_QReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D06a_QReal.py>`__.





Examples in Python, ``qcplx``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import qreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_qreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = qreal.t(i)
        print('x = qreal.t(i):', x)

        x = qreal.t(5.7)
        print('x = qrealT(5.7):', x)

        x = qreal.t(5.7)
        print('x = qrealT(5.7):', x)
        x0 = qreal.t(2329456398453948563945639364827346)
        print('x0 = qrealT(2329456398453948563945639364827346', x0)
        x1 = qreal.t("2329456398453948563945639364827346")
        print('x1 = qreal.t("2329456398453948563945639364827346"):', x1)
        x = qreal.t("5.5")
        print('x = qrealT("5.5"):', x)

        print()
        x = qreal.t(55)
        print('x = qreal.t(5):', x)
        y = qreal.exp(x)
        print('y = qreal.exp(x):', y)

        z = qreal.exp(5.5)
        print('z = qreal.exp(5.5):', z)
        z = qreal.exp(5)
        print('z = qreal.exp(5):', z)
        z = qreal.exp("5.5")
        print('z = qreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = qreal.exp(dec)
        print('z = qreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = qreal.exp(frac)
        print('z = qreal.exp(frac):', z)

        print()
        x = qreal.t(5.5)
        print('x = qreal.t(55):', x)
        y = qreal.t(3.3)
        print('y = qreal.t(33):', y)
        z = qreal.pow(x, y)
        print('z = qreal.pow(x, y):        ', z)
        z = qreal.pow(5.5, 3.3)
        print('z = qreal.pow(5.5, 3.3):    ', z)
        z = qreal.pow("5.5", "3.3")
        print('z = qreal.pow("5.5", "3.3"):', z)
        z = qreal.pow(5, 3)
        print('z = qreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_qreal():
        print()
        print('<H1 Title="Arithmetic operators with qreal">')

        x = qreal.t(5.0)
        y = qreal.t(2.5)
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



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06b_QCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D06b_QCplx.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the module ``qreal`` can be found here: `qreal.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/qreal.cs>`__.

The C\# source code for the module ``qcplx`` can be found here: `qcplx.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/qcplx.cs>`__.



The C++ source code supporting scalars in general which is called from ``qreal.cs`` and ``qcplx.cs`` can be found here:  `UseQReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/mpNum/UseQReal.cpp>`__.

The C++ source code which interacts directly with Boost can be found here: `BoostQReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostMath/BoostQReal.cpp>`__.



The C++ source code supporting Eigen which is called from ``qreal.cs`` and ``qcplx.cs`` can be found here: `UseEigenQReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/mpNum/UseEigenQReal.cpp>`__.

The C++ source code which interacts directly with Eigen can be found in the folder: `BoostEigenMath.cpp <https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostEigenMath>`__.







|newpage|

.. _rst_oreal_def: 


Binary floating point, octuple precision: ``oreal`` and  ``ocplx``
---------------------------------------------------------------------------------

The C\# modules ``oreal`` and ``ocplx`` provide support for real and complex floating point numbers in octuple precision (see https://en.wikipedia.org/wiki/Octuple-precision_floating-point_format). The corresponding real and complex data types, ``Octuple`` and ``OctupleC``, have been added as objects in XlCalcNet (and have therefore the overhead of objects). They are implemented in software, using the ``cpp_bin_float_oct`` data type of Boost Multiprecision. The routines in octuple precision provided in Boost and Eigen are typically much slower than the corresponding routines in quadruple precision.

The C\# modules ``oreal`` and ``ocplx``  fully support Boost.Math and Eigen.





Examples in C\#, ``oreal``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some oreal functions");
        OrealTest0();
        OrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void OcplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "OcplxTest0"  + "\"" + ">");

        var a = ocplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = ocplx.abs(a);
        Console.WriteLine("res1 = ocplx.abs(a): {0}", res1);

        var res2 = ocplx.exp(a);
        Console.WriteLine("res2 = ocplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void OcplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "OcplxTest1"  + "\"" + ">");

        var a = ocplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = ocplx.asin(a);
        Console.WriteLine("res1 = ocplx.asin(a) {0}", res1);

        var res2 = ocplx.sin(a);
        Console.WriteLine("res2 = ocplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07a_Oreal.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D07a_Oreal.cs>`__.







Examples in C\#, ``ocplx``
........................................................


General test code for C\# can be found here

.. code-block:: csharp

    #region Usings
    using System;
    using System.Numerics;
    using FixedPrecNet;
    #endregion


    public static void MainTests()
    {
        Console.WriteLine("Demo of some oreal functions");
        OrealTest0();
        OrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void OcplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "OcplxTest0"  + "\"" + ">");

        var a = ocplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = ocplx.abs(a);
        Console.WriteLine("res1 = ocplx.abs(a): {0}", res1);

        var res2 = ocplx.exp(a);
        Console.WriteLine("res2 = ocplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void OcplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "OcplxTest1"  + "\"" + ">");

        var a = ocplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = ocplx.asin(a);
        Console.WriteLine("res1 = ocplx.asin(a) {0}", res1);

        var res2 = ocplx.sin(a);
        Console.WriteLine("res2 = ocplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07b_Ocplx.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C06_ContextsFixedPrec/D07b_Ocplx.cs>`__.





Examples in Python, ``oreal``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import oreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_oreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = oreal.t(i)
        print('x = oreal.t(i):', x)

        x = oreal.t(5.7)
        print('x = orealT(5.7):', x)

        x = oreal.t(5.7)
        print('x = orealT(5.7):', x)
        x0 = oreal.t(2329456398453948563945639364827346)
        print('x0 = orealT(2329456398453948563945639364827346', x0)
        x1 = oreal.t("2329456398453948563945639364827346")
        print('x1 = oreal.t("2329456398453948563945639364827346"):', x1)
        x = oreal.t("5.5")
        print('x = orealT("5.5"):', x)

        print()
        x = oreal.t(55)
        print('x = oreal.t(5):', x)
        y = oreal.exp(x)
        print('y = oreal.exp(x):', y)

        z = oreal.exp(5.5)
        print('z = oreal.exp(5.5):', z)
        z = oreal.exp(5)
        print('z = oreal.exp(5):', z)
        z = oreal.exp("5.5")
        print('z = oreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = oreal.exp(dec)
        print('z = oreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = oreal.exp(frac)
        print('z = oreal.exp(frac):', z)

        print()
        x = oreal.t(5.5)
        print('x = oreal.t(55):', x)
        y = oreal.t(3.3)
        print('y = oreal.t(33):', y)
        z = oreal.pow(x, y)
        print('z = oreal.pow(x, y):        ', z)
        z = oreal.pow(5.5, 3.3)
        print('z = oreal.pow(5.5, 3.3):    ', z)
        z = oreal.pow("5.5", "3.3")
        print('z = oreal.pow("5.5", "3.3"):', z)
        z = oreal.pow(5, 3)
        print('z = oreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_oreal():
        print()
        print('<H1 Title="Arithmetic operators with oreal">')

        x = oreal.t(5.0)
        y = oreal.t(2.5)
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




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07a_OReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D07a_OReal.py>`__.





Examples in Python, ``ocplx``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import oreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_oreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = oreal.t(i)
        print('x = oreal.t(i):', x)

        x = oreal.t(5.7)
        print('x = orealT(5.7):', x)

        x = oreal.t(5.7)
        print('x = orealT(5.7):', x)
        x0 = oreal.t(2329456398453948563945639364827346)
        print('x0 = orealT(2329456398453948563945639364827346', x0)
        x1 = oreal.t("2329456398453948563945639364827346")
        print('x1 = oreal.t("2329456398453948563945639364827346"):', x1)
        x = oreal.t("5.5")
        print('x = orealT("5.5"):', x)

        print()
        x = oreal.t(55)
        print('x = oreal.t(5):', x)
        y = oreal.exp(x)
        print('y = oreal.exp(x):', y)

        z = oreal.exp(5.5)
        print('z = oreal.exp(5.5):', z)
        z = oreal.exp(5)
        print('z = oreal.exp(5):', z)
        z = oreal.exp("5.5")
        print('z = oreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = oreal.exp(dec)
        print('z = oreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = oreal.exp(frac)
        print('z = oreal.exp(frac):', z)

        print()
        x = oreal.t(5.5)
        print('x = oreal.t(55):', x)
        y = oreal.t(3.3)
        print('y = oreal.t(33):', y)
        z = oreal.pow(x, y)
        print('z = oreal.pow(x, y):        ', z)
        z = oreal.pow(5.5, 3.3)
        print('z = oreal.pow(5.5, 3.3):    ', z)
        z = oreal.pow("5.5", "3.3")
        print('z = oreal.pow("5.5", "3.3"):', z)
        z = oreal.pow(5, 3)
        print('z = oreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_oreal():
        print()
        print('<H1 Title="Arithmetic operators with oreal">')

        x = oreal.t(5.0)
        y = oreal.t(2.5)
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



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07b_OCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C06_ContextsFixedPrec/D07b_OCplx.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the module ``oreal`` can be found here: `oreal.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/oreal.cs>`__.

The C\# source code for the module ``ocplx`` can be found here: `ocplx.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/ocplx.cs>`__.



The C++ source code supporting scalars in general which is called from ``oreal.cs`` and ``ocplx.cs`` can be found here:  `UseOReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/mpNum/UseOReal.cpp>`__.

The C++ source code which interacts directly with Boost can be found here: `BoostSReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostMath/BoostOReal.cpp>`__.



The C++ source code supporting Eigen which is called from ``oreal.cs`` and ``ocplx.cs`` can be found here: `UseEigenSReal.cpp <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/mpNum/UseEigenOReal.cpp>`__.

The C++ source code which interacts directly with Eigen can be found in the folder: `BoostEigenMath.cpp <https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/C%2B%2B/xlcalcnet/BoostEigenMath>`__.





.. _rst_FixedPrec: 

Building the underlying C\#, C/C++ and Pascal libraries
------------------------------------------------------------------------------------------

On the Pascal/C/C++ side, XlCalcNet uses DAMath, Boost Math, Boost Multiprecision, Boost Odeint and Eigen to provide numerical functions in single, double, extended, quadruple and octuple precision, which are available to the user both from C# and Python.


The SourceOfBasicLibraries repository provides copies of the source code of the underlying numerical libraries, which are required to build the XlCalcNet library. These copies also include small patches, as required. They are provided to make it easier to reproduce the compilation results, as distributed as part of the XlCalcNet repository.



Installing MSYS2
...................................

Text descibing MSYS2



Eigen, (version 5.0.1)
...................................

Text descibing Eigen





Boost, (version 1.90.0)
...................................

Text descibing Boost



DAMath (version 2.27)
...................................

Text descibing DAMath





FixedPreNet (version 1.0.0)
...................................

Text descibing FixedPreNet



