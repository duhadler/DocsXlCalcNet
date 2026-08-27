

.. |newpage| raw:: latex

   \newpage



.. |vspace| raw:: html

   <br />







|newpage|



Mathematical functions based on XlCalcNet2 (C\#, can be called from Python)
=================================================================================




.. _rst_mreal_def: 


Binary floating point, multiple precision: ``mreal``, ``mcplx``
--------------------------------------------------------------------------------------------


The C\# modules ``mreal`` and ``mcplx`` provide support for real and complex floating point numbers with an arbitrary precision  significand and a fixed size exponent. The corresponding real and complex data types, ``Mpfr`` and ``MpfrC``, have been added as objects in XlCalcNet2 (and have therefore the overhead of objects). They are implemented in software, using the ``mpfr_t`` data type of the MPFR library (see https://www.mpfr.org/) and the ``mpc_t`` data type of the MPC library (see https://www.multiprecision.org/mpc/).

The C\# modules ``mreal`` and ``mcplx``  fully support Boost.Math and Eigen.





Examples in C\#, ``mreal``
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
        Console.WriteLine("Demo of some mreal functions");
        MrealTest0();
        MrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void McplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "McplxTest0"  + "\"" + ">");

        var a = mcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = mcplx.abs(a);
        Console.WriteLine("res1 = mcplx.abs(a): {0}", res1);

        var res2 = mcplx.exp(a);
        Console.WriteLine("res2 = mcplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void McplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "McplxTest1"  + "\"" + ">");

        var a = mcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = mcplx.asin(a);
        Console.WriteLine("res1 = mcplx.asin(a) {0}", res1);

        var res2 = mcplx.sin(a);
        Console.WriteLine("res2 = mcplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01a_Mreal.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D01a_Mreal.cs>`__.







Examples in C\#, ``mcplx``
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
        Console.WriteLine("Demo of some mreal functions");
        MrealTest0();
        MrealTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void McplxTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "McplxTest0"  + "\"" + ">");

        var a = mcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = mcplx.abs(a);
        Console.WriteLine("res1 = mcplx.abs(a): {0}", res1);

        var res2 = mcplx.exp(a);
        Console.WriteLine("res2 = mcplx.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void McplxTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "McplxTest1"  + "\"" + ">");

        var a = mcplx.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = mcplx.asin(a);
        Console.WriteLine("res1 = mcplx.asin(a) {0}", res1);

        var res2 = mcplx.sin(a);
        Console.WriteLine("res2 = mcplx.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01b_Mcplx.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D01b_Mcplx.cs>`__.





Examples in Python, ``mreal``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import mreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_mreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = mreal.t(i)
        print('x = mreal.t(i):', x)

        x = mreal.t(5.7)
        print('x = mrealT(5.7):', x)

        x = mreal.t(5.7)
        print('x = mrealT(5.7):', x)
        x0 = mreal.t(2329456398453948563945639364827346)
        print('x0 = mrealT(2329456398453948563945639364827346', x0)
        x1 = mreal.t("2329456398453948563945639364827346")
        print('x1 = mreal.t("2329456398453948563945639364827346"):', x1)
        x = mreal.t("5.5")
        print('x = mrealT("5.5"):', x)

        print()
        x = mreal.t(55)
        print('x = mreal.t(5):', x)
        y = mreal.exp(x)
        print('y = mreal.exp(x):', y)

        z = mreal.exp(5.5)
        print('z = mreal.exp(5.5):', z)
        z = mreal.exp(5)
        print('z = mreal.exp(5):', z)
        z = mreal.exp("5.5")
        print('z = mreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = mreal.exp(dec)
        print('z = mreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = mreal.exp(frac)
        print('z = mreal.exp(frac):', z)

        print()
        x = mreal.t(5.5)
        print('x = mreal.t(55):', x)
        y = mreal.t(3.3)
        print('y = mreal.t(33):', y)
        z = mreal.pow(x, y)
        print('z = mreal.pow(x, y):        ', z)
        z = mreal.pow(5.5, 3.3)
        print('z = mreal.pow(5.5, 3.3):    ', z)
        z = mreal.pow("5.5", "3.3")
        print('z = mreal.pow("5.5", "3.3"):', z)
        z = mreal.pow(5, 3)
        print('z = mreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_mreal():
        print()
        print('<H1 Title="Arithmetic operators with mreal">')

        x = mreal.t(5.0)
        y = mreal.t(2.5)
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




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01a_MReal.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D01a_MReal.py>`__.





Examples in Python, ``mcplx``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import mreal
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_mreal()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = mreal.t(i)
        print('x = mreal.t(i):', x)

        x = mreal.t(5.7)
        print('x = mrealT(5.7):', x)

        x = mreal.t(5.7)
        print('x = mrealT(5.7):', x)
        x0 = mreal.t(2329456398453948563945639364827346)
        print('x0 = mrealT(2329456398453948563945639364827346', x0)
        x1 = mreal.t("2329456398453948563945639364827346")
        print('x1 = mreal.t("2329456398453948563945639364827346"):', x1)
        x = mreal.t("5.5")
        print('x = mrealT("5.5"):', x)

        print()
        x = mreal.t(55)
        print('x = mreal.t(5):', x)
        y = mreal.exp(x)
        print('y = mreal.exp(x):', y)

        z = mreal.exp(5.5)
        print('z = mreal.exp(5.5):', z)
        z = mreal.exp(5)
        print('z = mreal.exp(5):', z)
        z = mreal.exp("5.5")
        print('z = mreal.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = mreal.exp(dec)
        print('z = mreal.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = mreal.exp(frac)
        print('z = mreal.exp(frac):', z)

        print()
        x = mreal.t(5.5)
        print('x = mreal.t(55):', x)
        y = mreal.t(3.3)
        print('y = mreal.t(33):', y)
        z = mreal.pow(x, y)
        print('z = mreal.pow(x, y):        ', z)
        z = mreal.pow(5.5, 3.3)
        print('z = mreal.pow(5.5, 3.3):    ', z)
        z = mreal.pow("5.5", "3.3")
        print('z = mreal.pow("5.5", "3.3"):', z)
        z = mreal.pow(5, 3)
        print('z = mreal.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_mreal():
        print()
        print('<H1 Title="Arithmetic operators with mreal">')

        x = mreal.t(5.0)
        y = mreal.t(2.5)
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



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02b_TestMCplx.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D01b_MCplx.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the module ``mreal`` can be found here: `mreal.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/mreal.cs>`__.

The C\# source code for the module ``mcplx`` can be found here: `mcplx.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/mcplx.cs>`__.



The C++ source code supporting scalars in general which is called from ``mreal.cs`` and ``mcplx.cs`` can be found here:  `UseMpfr.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseMpfr.cpp>`__.

The C++ source code which interacts directly with Boost can be found here: `BoostMpfr.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/BoostEigenMath/BoostMpfr.cpp>`__.



The C++ source code supporting Eigen which is called from ``mreal.cs`` and ``mcplx.cs`` can be found here: `UseAnyEigenMat.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseAnyEigenMat.cpp>`__.

The C++ source code which interacts directly with Eigen can be found in the folder: `BoostEigenMath.cpp <https://github.com/duhadler/XlCalcNet2/tree/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/BoostEigenMath>`__.








|newpage|


.. _rst_areal_def: 


Binary arbitrary precision ball: ``aflint`` and ``aflintc``
------------------------------------------------------------------

The C\# modules ``aflint`` and ``aflintc`` provide support for real and complex ball arithmetic with an arbitrary precision  significand and an arbitrary size exponent. The corresponding real and complex data types, ``Arb`` and ``ArbC``, have been added as objects in XlCalcNet2 (and have therefore the overhead of objects). They are implemented in software, using the ``arb_t`` and and ``acb_t`` data types of the FLINT library (see https://flintlib.org/).

The C\# modules ``mreal`` and ``mcplx``  partially support Eigen.

Note: Exponent soft maximum and minimum





Examples in C\#, ``aflint``
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
        Console.WriteLine("Demo of some aflint functions");
        AflintTest0();
        AflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void AflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "AflintcTest0"  + "\"" + ">");

        var a = aflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = aflintc.abs(a);
        Console.WriteLine("res1 = aflintc.abs(a): {0}", res1);

        var res2 = aflintc.exp(a);
        Console.WriteLine("res2 = aflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void AflintcTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "AflintcTest1"  + "\"" + ">");

        var a = aflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = aflintc.asin(a);
        Console.WriteLine("res1 = aflintc.asin(a) {0}", res1);

        var res2 = aflintc.sin(a);
        Console.WriteLine("res2 = aflintc.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02a_Aflint.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D02a_Aflint.cs>`__.







Examples in C\#, ``aflintc``
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
        Console.WriteLine("Demo of some aflint functions");
        AflintTest0();
        AflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void AflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "AflintcTest0"  + "\"" + ">");

        var a = aflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = aflintc.abs(a);
        Console.WriteLine("res1 = aflintc.abs(a): {0}", res1);

        var res2 = aflintc.exp(a);
        Console.WriteLine("res2 = aflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }


General test code for C\# can be found here

.. code-block:: csharp

    public static void AflintcTest1()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "AflintcTest1"  + "\"" + ">");

        var a = aflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = aflintc.asin(a);
        Console.WriteLine("res1 = aflintc.asin(a) {0}", res1);

        var res2 = aflintc.sin(a);
        Console.WriteLine("res2 = aflintc.sin(a) {0}", res2);

        Console.WriteLine("</H1>");
    }


The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02b_Aflintc.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D02b_Aflintc.cs>`__.





Examples in Python, ``aflint``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import aflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_aflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = aflint.t(i)
        print('x = aflint.t(i):', x)

        x = aflint.t(5.7)
        print('x = aflintT(5.7):', x)

        x = aflint.t(5.7)
        print('x = aflintT(5.7):', x)
        x0 = aflint.t(2329456398453948563945639364827346)
        print('x0 = aflintT(2329456398453948563945639364827346', x0)
        x1 = aflint.t("2329456398453948563945639364827346")
        print('x1 = aflint.t("2329456398453948563945639364827346"):', x1)
        x = aflint.t("5.5")
        print('x = aflintT("5.5"):', x)

        print()
        x = aflint.t(55)
        print('x = aflint.t(5):', x)
        y = aflint.exp(x)
        print('y = aflint.exp(x):', y)

        z = aflint.exp(5.5)
        print('z = aflint.exp(5.5):', z)
        z = aflint.exp(5)
        print('z = aflint.exp(5):', z)
        z = aflint.exp("5.5")
        print('z = aflint.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = aflint.exp(dec)
        print('z = aflint.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = aflint.exp(frac)
        print('z = aflint.exp(frac):', z)

        print()
        x = aflint.t(5.5)
        print('x = aflint.t(55):', x)
        y = aflint.t(3.3)
        print('y = aflint.t(33):', y)
        z = aflint.pow(x, y)
        print('z = aflint.pow(x, y):        ', z)
        z = aflint.pow(5.5, 3.3)
        print('z = aflint.pow(5.5, 3.3):    ', z)
        z = aflint.pow("5.5", "3.3")
        print('z = aflint.pow("5.5", "3.3"):', z)
        z = aflint.pow(5, 3)
        print('z = aflint.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_aflint():
        print()
        print('<H1 Title="Arithmetic operators with aflint">')

        x = aflint.t(5.0)
        y = aflint.t(2.5)
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




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02a_AFlint.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D02a_AFlint.py>`__.





Examples in Python, ``aflintc``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import aflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_aflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = aflint.t(i)
        print('x = aflint.t(i):', x)

        x = aflint.t(5.7)
        print('x = aflintT(5.7):', x)

        x = aflint.t(5.7)
        print('x = aflintT(5.7):', x)
        x0 = aflint.t(2329456398453948563945639364827346)
        print('x0 = aflintT(2329456398453948563945639364827346', x0)
        x1 = aflint.t("2329456398453948563945639364827346")
        print('x1 = aflint.t("2329456398453948563945639364827346"):', x1)
        x = aflint.t("5.5")
        print('x = aflintT("5.5"):', x)

        print()
        x = aflint.t(55)
        print('x = aflint.t(5):', x)
        y = aflint.exp(x)
        print('y = aflint.exp(x):', y)

        z = aflint.exp(5.5)
        print('z = aflint.exp(5.5):', z)
        z = aflint.exp(5)
        print('z = aflint.exp(5):', z)
        z = aflint.exp("5.5")
        print('z = aflint.exp("5.5"):', z)
        print('</H1>')




General test code can be found here

.. code-block:: python


    def functions_with_argument_conversion():
        print()
        print('<H1 Title="Functions with argument conversion">')
        dec = Decimal(1) / Decimal(7)
        print('dec = Decimal(1) / Decimal(7):', dec)
        z = aflint.exp(dec)
        print('z = aflint.exp(dec):', z)
        frac = Fraction("-3/7")
        print('frac = Fraction("-3/7:")', frac)
        z = aflint.exp(frac)
        print('z = aflint.exp(frac):', z)

        print()
        x = aflint.t(5.5)
        print('x = aflint.t(55):', x)
        y = aflint.t(3.3)
        print('y = aflint.t(33):', y)
        z = aflint.pow(x, y)
        print('z = aflint.pow(x, y):        ', z)
        z = aflint.pow(5.5, 3.3)
        print('z = aflint.pow(5.5, 3.3):    ', z)
        z = aflint.pow("5.5", "3.3")
        print('z = aflint.pow("5.5", "3.3"):', z)
        z = aflint.pow(5, 3)
        print('z = aflint.pow(5, 3):', z)

        t = z + 3
        print('t = z + 3:', t)
        print('</H1>')



General test code can be found here

.. code-block:: python

    def arithmetic_operators_with_aflint():
        print()
        print('<H1 Title="Arithmetic operators with aflint">')

        x = aflint.t(5.0)
        y = aflint.t(2.5)
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



The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02b_AFlintc.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D02b_AFlintc.py>`__.






Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the module ``aflint`` can be found here: `aflint.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/aflint.cs>`__.

The C\# source code for the module ``aflintc`` can be found here: `aflintc.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/aflintc.cs>`__.



The C++ source code supporting scalars in general which is called from ``aflint.cs`` and ``aflintc.cs`` can be found here:  `UseArb.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseArb.cpp>`__.


The C++ source code supporting Eigen which is called from ``aflint.cs`` and ``aflintc.cs`` can be found here: `UseAnyEigenMat.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseAnyEigenMat.cpp>`__.

The C++ source code which interacts directly with Eigen can be found in the folder: `BoostEigenMath.cpp <https://github.com/duhadler/XlCalcNet2/tree/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/BoostEigenMath>`__.





















.. _rst_srealflint_def: 

Binary floating point, single precision: ``sflint`` and ``sflintc``
---------------------------------------------------------------------------------------

The C\# modules ``sflint`` and ``sflintc`` provide a rich set of elementary and special real and complex scalar functions for the ``Single`` and ``Single`` data types, with the actual calculations done using the ``Arb`` and ``ArbC`` data types, which allows control of the absolute and relative error of the result.





Examples in C\#, ``sflint``
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
        Console.WriteLine("Demo of some sflint functions");
        SflintTest0();
        SflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void SflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "SflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }





The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03a_Sflint.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D03a_Sflint.cs>`__.







Examples in C\#, ``sflintc``
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
        Console.WriteLine("Demo of some sflint functions");
        SflintTest0();
        SflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void SflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "SflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03b_Sflintc.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D03b_Sflintc.cs>`__.





Examples in Python, ``sflint``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import sflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_sflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = sflint.t(i)
        print('x = sflint.t(i):', x)

        x = sflint.t(5.7)
        print('x = sflintT(5.7):', x)

        x = sflint.t(5.7)
        print('x = sflintT(5.7):', x)
        x0 = sflint.t(2329456398453948563945639364827346)
        print('x0 = sflintT(2329456398453948563945639364827346', x0)
        x1 = sflint.t("2329456398453948563945639364827346")
        print('x1 = sflint.t("2329456398453948563945639364827346"):', x1)
        x = sflint.t("5.5")
        print('x = sflintT("5.5"):', x)

        print()
        x = sflint.t(55)
        print('x = sflint.t(5):', x)
        y = sflint.exp(x)
        print('y = sflint.exp(x):', y)

        z = sflint.exp(5.5)
        print('z = sflint.exp(5.5):', z)
        z = sflint.exp(5)
        print('z = sflint.exp(5):', z)
        z = sflint.exp("5.5")
        print('z = sflint.exp("5.5"):', z)
        print('</H1>')







The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03a_SFlint.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D03a_SFlint.py>`__.





Examples in Python, ``sflintc``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import sflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_sflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = sflint.t(i)
        print('x = sflint.t(i):', x)

        x = sflint.t(5.7)
        print('x = sflintT(5.7):', x)

        x = sflint.t(5.7)
        print('x = sflintT(5.7):', x)
        x0 = sflint.t(2329456398453948563945639364827346)
        print('x0 = sflintT(2329456398453948563945639364827346', x0)
        x1 = sflint.t("2329456398453948563945639364827346")
        print('x1 = sflint.t("2329456398453948563945639364827346"):', x1)
        x = sflint.t("5.5")
        print('x = sflintT("5.5"):', x)

        print()
        x = sflint.t(55)
        print('x = sflint.t(5):', x)
        y = sflint.exp(x)
        print('y = sflint.exp(x):', y)

        z = sflint.exp(5.5)
        print('z = sflint.exp(5.5):', z)
        z = sflint.exp(5)
        print('z = sflint.exp(5):', z)
        z = sflint.exp("5.5")
        print('z = sflint.exp("5.5"):', z)
        print('</H1>')






The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03b_SFlintc.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D03b_SFlintc.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the modules ``sflint`` and  ``sflintc``  can be found here: `srealcplxflint.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/srealcplxflint.cs>`__.



The C++ source code which is called from ``srealcplxflint.cs`` can be found here:  `UseSReal.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseSReal.cpp>`__.














|newpage|

.. _rst_drealflint_def: 

Binary floating point, double precision: ``dflint`` and ``dflintc``
------------------------------------------------------------------------------------------

The C\# modules ``dflint`` and ``dflintc`` provide a rich set of elementary and special real and complex scalar functions for the ``Double`` and ``Complex`` data types, with the actual calculations done using the ``Arb`` and ``ArbC`` data types, which allows control of the absolute and relative error of the result.



Examples in C\#, ``dflint``
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
        Console.WriteLine("Demo of some sflint functions");
        DflintTest0();
        DflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void DflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "DflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }





The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04a_Dflint.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D04a_Dflint.cs>`__.







Examples in C\#, ``dflintc``
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
        Console.WriteLine("Demo of some sflint functions");
        DflintTest0();
        DflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void DflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "DflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04b_Dflintc.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D04b_Dflintc.cs>`__.





Examples in Python, ``dflint``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import sflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_sflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = sflint.t(i)
        print('x = sflint.t(i):', x)

        x = sflint.t(5.7)
        print('x = sflintT(5.7):', x)

        x = sflint.t(5.7)
        print('x = sflintT(5.7):', x)
        x0 = sflint.t(2329456398453948563945639364827346)
        print('x0 = sflintT(2329456398453948563945639364827346', x0)
        x1 = sflint.t("2329456398453948563945639364827346")
        print('x1 = sflint.t("2329456398453948563945639364827346"):', x1)
        x = sflint.t("5.5")
        print('x = sflintT("5.5"):', x)

        print()
        x = sflint.t(55)
        print('x = sflint.t(5):', x)
        y = sflint.exp(x)
        print('y = sflint.exp(x):', y)

        z = sflint.exp(5.5)
        print('z = sflint.exp(5.5):', z)
        z = sflint.exp(5)
        print('z = sflint.exp(5):', z)
        z = sflint.exp("5.5")
        print('z = sflint.exp("5.5"):', z)
        print('</H1>')







The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04a_DFlint.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D04a_DFlint.py>`__.





Examples in Python, ``dflintc``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import sflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_sflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = sflint.t(i)
        print('x = sflint.t(i):', x)

        x = sflint.t(5.7)
        print('x = sflintT(5.7):', x)

        x = sflint.t(5.7)
        print('x = sflintT(5.7):', x)
        x0 = sflint.t(2329456398453948563945639364827346)
        print('x0 = sflintT(2329456398453948563945639364827346', x0)
        x1 = sflint.t("2329456398453948563945639364827346")
        print('x1 = sflint.t("2329456398453948563945639364827346"):', x1)
        x = sflint.t("5.5")
        print('x = sflintT("5.5"):', x)

        print()
        x = sflint.t(55)
        print('x = sflint.t(5):', x)
        y = sflint.exp(x)
        print('y = sflint.exp(x):', y)

        z = sflint.exp(5.5)
        print('z = sflint.exp(5.5):', z)
        z = sflint.exp(5)
        print('z = sflint.exp(5):', z)
        z = sflint.exp("5.5")
        print('z = sflint.exp("5.5"):', z)
        print('</H1>')






The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04b_DFlintc.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D04b_DFlintc.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the modules ``dflint`` and  ``dflintc``  can be found here: `drealcplxflint.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/drealcplxflint.cs>`__.



The C++ source code which is called from ``drealcplxflint.cs`` can be found here:  `UseFReal.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseFReal.cpp>`__.





















|newpage|

.. _rst_erealflint_def: 


Binary floating point, extended precision: ``eflint`` and ``eflintc``
--------------------------------------------------------------------------------------

The C\# modules ``eflint`` and ``eflintc`` provide a rich set of elementary and special real and complex scalar functions for the ``Extended`` and ``ExtendedC`` data types, with the actual calculations done using the ``Arb`` and ``ArbC`` data types, which allows control of the absolute and relative error of the result.




Examples in C\#, ``eflint``
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
        Console.WriteLine("Demo of some eflint functions");
        EflintTest0();
        EflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void EflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "EflintcTest0"  + "\"" + ">");

        var a = eflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = eflintc.abs(a);
        Console.WriteLine("res1 = eflintc.abs(a): {0}", res1);

        var res2 = eflintc.exp(a);
        Console.WriteLine("res2 = eflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }





The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05a_Eflint.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D05a_Eflint.cs>`__.







Examples in C\#, ``eflintc``
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
        Console.WriteLine("Demo of some eflint functions");
        EflintTest0();
        EflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void EflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "EflintcTest0"  + "\"" + ">");

        var a = eflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = eflintc.abs(a);
        Console.WriteLine("res1 = eflintc.abs(a): {0}", res1);

        var res2 = eflintc.exp(a);
        Console.WriteLine("res2 = eflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05b_Eflintc.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D05b_Eflintc.cs>`__.





Examples in Python, ``eflint``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import eflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_eflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = eflint.t(i)
        print('x = eflint.t(i):', x)

        x = eflint.t(5.7)
        print('x = eflintT(5.7):', x)

        x = eflint.t(5.7)
        print('x = eflintT(5.7):', x)
        x0 = eflint.t(2329456398453948563945639364827346)
        print('x0 = eflintT(2329456398453948563945639364827346', x0)
        x1 = eflint.t("2329456398453948563945639364827346")
        print('x1 = eflint.t("2329456398453948563945639364827346"):', x1)
        x = eflint.t("5.5")
        print('x = eflintT("5.5"):', x)

        print()
        x = eflint.t(55)
        print('x = eflint.t(5):', x)
        y = eflint.exp(x)
        print('y = eflint.exp(x):', y)

        z = eflint.exp(5.5)
        print('z = eflint.exp(5.5):', z)
        z = eflint.exp(5)
        print('z = eflint.exp(5):', z)
        z = eflint.exp("5.5")
        print('z = eflint.exp("5.5"):', z)
        print('</H1>')







The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05a_EFlint.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D05a_EFlint.py>`__.





Examples in Python, ``eflintc``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import eflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_eflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = eflint.t(i)
        print('x = eflint.t(i):', x)

        x = eflint.t(5.7)
        print('x = eflintT(5.7):', x)

        x = eflint.t(5.7)
        print('x = eflintT(5.7):', x)
        x0 = eflint.t(2329456398453948563945639364827346)
        print('x0 = eflintT(2329456398453948563945639364827346', x0)
        x1 = eflint.t("2329456398453948563945639364827346")
        print('x1 = eflint.t("2329456398453948563945639364827346"):', x1)
        x = eflint.t("5.5")
        print('x = eflintT("5.5"):', x)

        print()
        x = eflint.t(55)
        print('x = eflint.t(5):', x)
        y = eflint.exp(x)
        print('y = eflint.exp(x):', y)

        z = eflint.exp(5.5)
        print('z = eflint.exp(5.5):', z)
        z = eflint.exp(5)
        print('z = eflint.exp(5):', z)
        z = eflint.exp("5.5")
        print('z = eflint.exp("5.5"):', z)
        print('</H1>')






The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05b_EFlintc.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D05b_EFlintc.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the modules ``eflint`` and  ``eflintc``  can be found here: `erealcplxflint.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/erealcplxflint.cs>`__.



The C++ source code which is called from ``erealcplxflint.cs`` can be found here:  `UseXReal.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseXReal.cpp>`__.












|newpage|

.. _rst_qrealflint_def: 


Binary floating point, quadruple precision: ``qflint`` and ``qflintc``
-----------------------------------------------------------------------------------

The C\# modules ``qflint`` and ``qflintc`` provide a rich set of elementary and special real and complex scalar functions for the ``Quadruple`` and ``QuadrupleC`` data types, with the actual calculations done using the ``Arb`` and ``ArbC`` data types, which allows control of the absolute and relative error of the result.




Examples in C\#, ``qflint``
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
        Console.WriteLine("Demo of some qflint functions");
        SflintTest0();
        SflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void QflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "QflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }





The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06a_Qflint.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D06a_Qflint.cs>`__.







Examples in C\#, ``qflintc``
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
        Console.WriteLine("Demo of some qflint functions");
        SflintTest0();
        SflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void QflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "QflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06b_Qflintc.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D06b_Qflintc.cs>`__.





Examples in Python, ``qflint``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import qflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_qflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = qflint.t(i)
        print('x = qflint.t(i):', x)

        x = qflint.t(5.7)
        print('x = qflintT(5.7):', x)

        x = qflint.t(5.7)
        print('x = qflintT(5.7):', x)
        x0 = qflint.t(2329456398453948563945639364827346)
        print('x0 = qflintT(2329456398453948563945639364827346', x0)
        x1 = qflint.t("2329456398453948563945639364827346")
        print('x1 = qflint.t("2329456398453948563945639364827346"):', x1)
        x = qflint.t("5.5")
        print('x = qflintT("5.5"):', x)

        print()
        x = qflint.t(55)
        print('x = qflint.t(5):', x)
        y = qflint.exp(x)
        print('y = qflint.exp(x):', y)

        z = qflint.exp(5.5)
        print('z = qflint.exp(5.5):', z)
        z = qflint.exp(5)
        print('z = qflint.exp(5):', z)
        z = qflint.exp("5.5")
        print('z = qflint.exp("5.5"):', z)
        print('</H1>')







The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06a_QFlint.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D06a_QFlint.py>`__.





Examples in Python, ``qflintc``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import qflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_qflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = qflint.t(i)
        print('x = qflint.t(i):', x)

        x = qflint.t(5.7)
        print('x = qflintT(5.7):', x)

        x = qflint.t(5.7)
        print('x = qflintT(5.7):', x)
        x0 = qflint.t(2329456398453948563945639364827346)
        print('x0 = qflintT(2329456398453948563945639364827346', x0)
        x1 = qflint.t("2329456398453948563945639364827346")
        print('x1 = qflint.t("2329456398453948563945639364827346"):', x1)
        x = qflint.t("5.5")
        print('x = qflintT("5.5"):', x)

        print()
        x = qflint.t(55)
        print('x = qflint.t(5):', x)
        y = qflint.exp(x)
        print('y = qflint.exp(x):', y)

        z = qflint.exp(5.5)
        print('z = qflint.exp(5.5):', z)
        z = qflint.exp(5)
        print('z = qflint.exp(5):', z)
        z = qflint.exp("5.5")
        print('z = qflint.exp("5.5"):', z)
        print('</H1>')






The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06b_QFlintc.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D06b_QFlintc.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the modules ``qflint`` and  ``qflintc``  can be found here: `qrealcplxflint.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/qrealcplxflint.cs>`__.



The C++ source code which is called from ``qrealcplxflint.cs`` can be found here:  `UseQReal.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseQReal.cpp>`__.












|newpage|

.. _rst_orealflint_def: 


Binary floating point, octuple precision: ``oflint`` and ``oflintc``
---------------------------------------------------------------------------------

The C\# modules ``oflint`` and ``oflintc`` provide a rich set of elementary and special real and complex scalar functions for the ``Octuple`` and ``OctupleC`` data types, with the actual calculations done using the ``Arb`` and ``ArbC`` data types, which allows control of the absolute and relative error of the result.



Examples in C\#, ``oflint``
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
        Console.WriteLine("Demo of some oflint functions");
        OflintTest0();
        OflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void OflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "OflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }





The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07a_Oflint.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D07a_Oflint.cs>`__.







Examples in C\#, ``oflintc``
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
        Console.WriteLine("Demo of some oflint functions");
        OflintTest0();
        OflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void OflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "OflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07b_Oflintc.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D07b_Oflintc.cs>`__.





Examples in Python, ``oflint``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import oflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_oflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = oflint.t(i)
        print('x = oflint.t(i):', x)

        x = oflint.t(5.7)
        print('x = oflintT(5.7):', x)

        x = oflint.t(5.7)
        print('x = oflintT(5.7):', x)
        x0 = oflint.t(2329456398453948563945639364827346)
        print('x0 = oflintT(2329456398453948563945639364827346', x0)
        x1 = oflint.t("2329456398453948563945639364827346")
        print('x1 = oflint.t("2329456398453948563945639364827346"):', x1)
        x = oflint.t("5.5")
        print('x = oflintT("5.5"):', x)

        print()
        x = oflint.t(55)
        print('x = oflint.t(5):', x)
        y = oflint.exp(x)
        print('y = oflint.exp(x):', y)

        z = oflint.exp(5.5)
        print('z = oflint.exp(5.5):', z)
        z = oflint.exp(5)
        print('z = oflint.exp(5):', z)
        z = oflint.exp("5.5")
        print('z = oflint.exp("5.5"):', z)
        print('</H1>')







The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07a_OFlint.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D07a_OFlint.py>`__.





Examples in Python, ``oflintc``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import oflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_oflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = oflint.t(i)
        print('x = oflint.t(i):', x)

        x = oflint.t(5.7)
        print('x = oflintT(5.7):', x)

        x = oflint.t(5.7)
        print('x = oflintT(5.7):', x)
        x0 = oflint.t(2329456398453948563945639364827346)
        print('x0 = oflintT(2329456398453948563945639364827346', x0)
        x1 = oflint.t("2329456398453948563945639364827346")
        print('x1 = oflint.t("2329456398453948563945639364827346"):', x1)
        x = oflint.t("5.5")
        print('x = oflintT("5.5"):', x)

        print()
        x = oflint.t(55)
        print('x = oflint.t(5):', x)
        y = oflint.exp(x)
        print('y = oflint.exp(x):', y)

        z = oflint.exp(5.5)
        print('z = oflint.exp(5.5):', z)
        z = oflint.exp(5)
        print('z = oflint.exp(5):', z)
        z = oflint.exp("5.5")
        print('z = oflint.exp("5.5"):', z)
        print('</H1>')






The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07b_OFlintc.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D07b_OFlintc.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the modules ``oflint`` and  ``oflintc``  can be found here: `orealcplxflint.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/orealcplxflint.cs>`__.



The C++ source code which is called from ``orealcplxflint.cs`` can be found here:  `UseOReal.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseOReal.cpp>`__.











|newpage|


.. _rst_mflint_def: 


Binary floating point, multiple precision: ``mflint``, ``mflintc``
--------------------------------------------------------------------------------------------

The C\# modules ``mflint`` and ``mflintc`` provide a rich set of elementary and special real and complex scalar functions for the ``Octuple`` and ``OctupleC`` data types, with the actual calculations done using the ``Arb`` and ``ArbC`` data types, which allows control of the absolute and relative error of the result.




Examples in C\#, ``mflint``
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
        Console.WriteLine("Demo of some mflint functions");
        MflintTest0();
        MflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void MflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "MflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }





The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D08a_Mflint.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D08a_Mflint.cs>`__.







Examples in C\#, ``mflintc``
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
        Console.WriteLine("Demo of some mflint functions");
        MflintTest0();
        MflintTest1();
    }


General test code for C\# can be found here

.. code-block:: csharp


    public static void MflintcTest0()
    {
        Console.WriteLine("<H1 Title=" + "\"" + "MflintcTest0"  + "\"" + ">");

        var a = qflintc.t(3.5, 6.3);
        Console.WriteLine("a: {0}", a);

        var res1 = qflintc.abs(a);
        Console.WriteLine("res1 = qflintc.abs(a): {0}", res1);

        var res2 = qflintc.exp(a);
        Console.WriteLine("res2 = qflintc.exp(a): {0}", res2);

        Console.WriteLine("</H1>");
    }




The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D08b_Mflintc.cs <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B01_GeneralUsage/C07_ContextsXlCalcNet2/D08b_Mflintc.cs>`__.





Examples in Python, ``mflint``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import mflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_mflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = mflint.t(i)
        print('x = mflint.t(i):', x)

        x = mflint.t(5.7)
        print('x = mflintT(5.7):', x)

        x = mflint.t(5.7)
        print('x = mflintT(5.7):', x)
        x0 = mflint.t(2329456398453948563945639364827346)
        print('x0 = mflintT(2329456398453948563945639364827346', x0)
        x1 = mflint.t("2329456398453948563945639364827346")
        print('x1 = mflint.t("2329456398453948563945639364827346"):', x1)
        x = mflint.t("5.5")
        print('x = mflintT("5.5"):', x)

        print()
        x = mflint.t(55)
        print('x = mflint.t(5):', x)
        y = mflint.exp(x)
        print('y = mflint.exp(x):', y)

        z = mflint.exp(5.5)
        print('z = mflint.exp(5.5):', z)
        z = mflint.exp(5)
        print('z = mflint.exp(5):', z)
        z = mflint.exp("5.5")
        print('z = mflint.exp("5.5"):', z)
        print('</H1>')







The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D08a_MFlint.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D08a_MFlint.py>`__.





Examples in Python, ``mflintc``
........................................................


General test code for Python can be found here

.. code-block:: python

    import math
    from xlcalcnet import mflint
    from decimal import Decimal
    from fractions import Fraction
    i = 2329456398453948563945639364827346384753984573984573


    def main_tests():
        general_assignments()
        functions_with_argument_conversion()
        arithmetic_operators_with_mflint()




General test code can be found here

.. code-block:: python

    def general_assignments():
        print()
        print('<H1 Title="General assignments and conversions">')

        x = mflint.t(i)
        print('x = mflint.t(i):', x)

        x = mflint.t(5.7)
        print('x = mflintT(5.7):', x)

        x = mflint.t(5.7)
        print('x = mflintT(5.7):', x)
        x0 = mflint.t(2329456398453948563945639364827346)
        print('x0 = mflintT(2329456398453948563945639364827346', x0)
        x1 = mflint.t("2329456398453948563945639364827346")
        print('x1 = mflint.t("2329456398453948563945639364827346"):', x1)
        x = mflint.t("5.5")
        print('x = mflintT("5.5"):', x)

        print()
        x = mflint.t(55)
        print('x = mflint.t(5):', x)
        y = mflint.exp(x)
        print('y = mflint.exp(x):', y)

        z = mflint.exp(5.5)
        print('z = mflint.exp(5.5):', z)
        z = mflint.exp(5)
        print('z = mflint.exp(5):', z)
        z = mflint.exp("5.5")
        print('z = mflint.exp("5.5"):', z)
        print('</H1>')






The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D08b_MFlintc.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B01_GeneralUsage/C07_ContextsXlCalcNet2/D08b_MFlintc.py>`__.





Notes regarding the implementation in C\# and C++
........................................................

The C\# source code for the modules ``mflint`` and  ``mflintc``  can be found here: `mrealcplxflint.cs <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/ArbPrec/mrealcplxflint.cs>`__.



The C++ source code which is called from ``mrealcplxflint.cs`` can be found here:  `UseMpfr.cpp <https://github.com/duhadler/XlCalcNet2/blob/master/xlcalcnet2/Addin/NET48/Source/C%2B%2B/xlcalcnet2/mpNum/UseMpfr.cpp>`__.














.. _rst_ArbPrec: 

Building the underlying C\# and C/C++ libraries
------------------------------------------------------------------------------------------

The XlCalcNet2 library, which is licensed under the LGPL-3.0 and is therefore provided in a separate repository, is based on Boost Math, Boost Multiprecision, Boost Odeint, Eigen, GMP, MPFR, MPC and FLINT and provides functions for the same data types as XlCalcNet and also in arbitrary precision, which are available to the user both from C# and Python.


The SourceOfBasicLibraries2 repository provides copies of the source code of the underlying numerical libraries, which are required (in addition to Eigen and Boost, see SourceOfBasicLibraries) to build the XlCalcNet2 library.. These copies also include small patches and .sh files, as required. They are provided to make it easier to reproduce the compilation results, as distributed as part of the XlCalcNet2 repository.




GMP (version 6.3.0)
...................................

Text descibing GMP, including config files



MPFR (version 4.2.2)
...................................

Text descibing MPFR, including config files





MPC (version 1.3.1)
...................................

Text descibing MPC, including config files



FLINT (version 3.4.0)
...................................

Text descibing FLINT, including config files





ArbPreNet (version 1.0.0)
...................................

Text descibing ArbPreNet





