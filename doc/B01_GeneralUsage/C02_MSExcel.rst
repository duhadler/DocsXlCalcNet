


.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />




|newpage|


Using XlCalcNet within MS Excel
===========================================



.. _rst_setting_up_MSExcel: 

Preparing MS Excel for using XlCalcNet
---------------------------------------------------------------------------------------------


.. important::
    Before beginning to install the MS Excel addins, make sure that the socket server is up and running as expected (see the section above). When calling a function, which calls the socket server, for the first time, MS Excel will seem to freeze if the socket server does not respond quickly. However, subsequent calls will return quickly when the socket server is not up and running (there seems to be a learning effect).


To enable the use of XlCalcNet in MS Excel, two add-ins need to be installed: the first, named ``Mpfunlablocal.xlam``, contains functions written in Visual Basic for Applications (VBA), including functions populating the XlCalcNet Navigator dialog, and is intended to be modified by the user during normal use. This add-in is located in a subfolder of the ``DataXlCalcNet`` folder in the ``Documents`` folder: ``DataXlCalcNet\SpreadsheetAddins\MSExcel``.

The second, named ``Mpfunlab.xll``, contains the functionality behind the spreadsheet functions ``CPY_0`` - ``CPY_9`` and ``ASDOUBLE`` and the XlCalcNet Navigator dialog container. The files comprising the whole add-in (``Mpfunlab.xll``, ``ExcelDna.Integration.dll``, ``MpFunLabAddin64.dll``, ``MpFunLabClient.dll``, ``MpFunLab.Dna``) have been compiled using Visual Studio and are NOT intended to be modified by the user during normal use. This add-in is located in the ``Bin`` folder in the ``XlCalcNet`` package: ``PathToPython\Lib\site-packages\xlcalcnet\Addin\NET48\Bin``, where ``PathToPython`` is the path to the Python installation (in our example ``C:\Python313``).  



Installing Mpfunlablocal.xlam and Mpfunlab.xll
...................................................

To install these two add-ins properly, follow these steps:   

Again, make sure that the socket server is up and running.

Within MS Excel, on an Excel worksheet, open the Add-ins dialog from the main menu/ribbon: ``Developer`` -> ``Excel Add-ins``. In the Add-ins dialog,
click on ``Browse...`` and in the ``Documents`` folder navigate to the folder ``DataXlCalcNet\SpreadsheetAddins\MSExcel``. Double-click on ``Mpfunlablocal.xlam``, which will then appear in the Add-ins dialog under "Add-ins available". Still in the Add-ins dialog,
click on ``Browse...`` again, and navigate to the folder ``PathToPython\Lib\site-packages\xlcalcnet\Addin\NET48\Bin`` (see above). Double-click on ``MpFunlab.xll``, which will then appear in the Add-ins dialog under "Add-ins available". Still in the Add-ins dialog,
click on ``OK``. Exit MS Excel.

When starting MS Excel the next time, both add-ins will be loaded.





.. _rst_XL_functions_standard: 

Using the Python standard library functions within spreadsheet formulas
------------------------------------------------------------------------------------------

.. note::
    In the following subsections, we will work with the file ``XlDemoCPYstd.xlsx``, which contains examples for using the Python standard library. More advanced examples using Numpy, Matplotlib, Pandas, Scipy, Seaborn and XlCalcNet start  :ref:`here <rst_XL_functions_advanced>`.


Within MS Excel, open from the main menu ``File`` -> ``Open`` in the Documents folder the MS Excel workbook ``DataXlCalcNet\DataExamples\MainExamples\Workbooks\XlDemoCPYstd.xlsx``.

This file contains several worksheets which demonstrate different possibilities of using the Python standard library within MS Excel spreadsheet formulas.

Before we start with that we will briefly explore the use of these functions with the Function Dialog of  MS Excel: In the worksheet "Math", select cell ``B12`` and click on the icon of the Function Dialog in the Formula Bar. This opens the Function Dialog:



.. image:: ../_static/XL_FunctionArguments.png
    :width: 50 %
    :align: center




We see that the formula in the spreadsheeet cell is ``=CPY_1("result = math.ceil(P1)",C12)``. The function ``CPY_1`` has a required string parameter, ``Formula``, which contains a Python script. This python script can contain several Python statement. The last statement is always expected to assign a value to the variable result, in this case a Python float, which is coverted to a floating point number in double precision (a "Double") in LibreOffice. The next optional parameter, ``Param1``, can be a string, a Double, a Boolean value or a reference. In this case, it is a reference (``C12``) which points to a Double with the value ``3.123``. This optional parameter, ``Param1``, is referenced in the Python formula given above as ``P1``. The last but one parameter, ``Transposed``, and the last parameter, ``ShowShape``, are only relevant when arrays are returned; this is discussed :ref:`here <rst_XL_functions_Arrays>`.

In the worksheet "Math", select an emptz cell and click on the icon of the Function Dialog in the Formula Bar. This opens the Function Insert Dialog:

.. image:: ../_static/XL_FunctionInsert.png
    :align: center
    :width: 50%



We see that the function ``CPY_1`` is in the Category "MpFunLab", and that there are 10 functions,  ``CPY_0`` to ``CPY_9``, which differ only by the number of parameters ``Param1`` to ``Param9`` which they support (The function ``CPY_0`` does not have a parameter ``Param0``). There is also a function ``ASDOUBLE``, which is used to convert string representations of a Python Fraction or Decimal into a Double; this is discussed :ref:`here <rst_XL_functions_MpInput>`.



The worksheet "GeneralInfo"
..............................................................................


The worksheet "GeneralInfo" contains calls to the Python modules ``os``, ``platform`` and ``sys``. 

For example, the cell ``B4`` contains the formula ``=CPY_0("result = platform.processor()")``. The function result depends on the hardware, e.g. ``Intel64 Family 6 Model 165 Stepping 5, GenuineIntel``.

The cell ``B16`` contains the formula ``=CPY_0("result = os.getcwd()")``. The function result depends on the LibreOffice installation, e.g. ``C:\Program Files\LibreOffice\program``.

The cell ``B33`` contains the formula ``=CPY_0("result = str(sys.float_info.epsilon)")``, which return the machine epsilon in double precision. The function result is: ``2.220446049250313e-16``.



The worksheet "Math"
..............................................................................

The worksheet "Math" demonstrates the use of the Python module ``math`` and the use of parameters in functions. 

For example, the cell ``B33`` contains the formula ``=CPY_1("result = math.exp(P1)-1",C33)``, which calculates `\exp(\text{P1})-1` naively. The function result is ``1.00000500000696E-05``, with the cell ``C33`` containing the value ``0.00001``.

The cell ``B34`` contains the formula ``=CPY_1("result = math.expm1(P1)",C34)``, which calculates `\exp(\text{P1})-1` using the ``expm1`` function. The function result is ``1.00000500001667E-05``, with the cell ``C34`` again containing the value ``0.00001``.

The floating point  values ``NaN``, ``+inf`` and ``-inf`` are not supported in spreadsheet programs, which only return ``#NUM!`` in these cases. Use the string representation instead. This is shown in the cells ``A4:B9`` on this worksheet.

The cell ``B36`` contains the formula ``=CPY_2("result = math.log(P1, P2)",C36, D36)``, with the cell ``C36`` containing the value ``3.123`` and the cell ``D36`` containing the value ``10``. The function result is: ``0.494571984230199``.


.. _rst_XL_functions_Arrays: 

The worksheet "Arrays"
..............................................................................


The worksheet "Arrays" demonstrates the use of arrays in functions. The Python equivalent of arrays are lists.

For example, the cell ``B3`` contains the formula ``=CPY_0("result = str(sys.path)")``. The function ``sys.path`` returns a list of strings (containing the entries of the Python path), which is converted into one string by writing ``str(sys.path)``. This makes sure that the result can be displayed in one cell, but the result string is quite long and hard to read.

We can use an array formula to improve readability. We recall that in addition to the usual parameters ``P1`` - ``P9`` in the functions ``CPY_0`` to ``CPY_9`` there are two more: The last but one paramter, named ``Transposed``, which is optional with default value 0, where a non-zero value means that the returned array should be transposed; and the last paramter, named ``ShowShape``, which is optional with default value 0, where a non-zero value means that the shape of the returned array should be indicated like ``R7C3`` for an array with 7 rows and 3 columns.

As an example, the cell ``B6`` contains the formula ``=CPY_0("result = sys.path",1,1)`` and returns the shape information ``R12C1`` followed by the separator ``|``, followed by the first entry of the transposed array, i.e. in this case ``R12xC1| C:\Users\DUHad\Documents\DataXlCalcNet``.

We can build the corresponding array formula by first selecting a range like ``R12C1``, then typing in the input line of the formula bar ``=CPY_0("result = sys.path",1,0)``, and finally, while keeping the shift and control keys pressed down, pressing the enter key.

This is what has been done in cells ``B9:B20``. The formula is now displayed as ``{=CPY_0("result = sys.path",1,0)}``, with curly braces, to indicate that it is an array formula. We can change the range which is covered by the array formula by dragging the small blue rectangle in the lower right corner in the selected range (see the screenshot below).


.. image:: ../_static/XL_Change_Range.png
    :align: center
    :width: 60%








The worksheet "Data"
...................................................

The worksheet "Data " demonstrates the use of named ranges in MS Excel spreadsheet formulas.

Currently there a two small datasets with predefined as named ranges: ``matA`` defined as the range $Data.$A$3:$A$7 and  ``matB`` defined as the range $Data.$A$3:$A$7.

These ranges are used in the workbook "Arrays".







.. _rst_XL_functions_advanced: 

Using Numpy, Matplotlib, Pandas, Scipy, Seaborn and XlCalcNet within spreadsheet formulas
------------------------------------------------------------------------------------------

.. note::
    In the following subsections. we will work with the file ``XlDemoCPYadv.xlsx``, which contains more advanced examples using Numpy, Matplotlib, Pandas, Scipy, Seaborn and XlCalcNet. Examples for using MS Excel with the Python standard library start :ref:`here <rst_XL_functions_standard>`.


Within MS Excel, open from the main menu ``File`` -> ``Open`` in the Documents folder the MS Excel workbook ``DataXlCalcNet\DataExamples\MainExamples\Workbooks\XlDemoCPYadv.xlsx``.

This file contains several worksheets which demonstrate different possibilities of using Numpy, Matplotlib, Pandas, Scipy, Seaborn and XlCalcNet within MS Excel spreadsheet formulas.

Some of these functions write their output  into the ``XlCalcNetIDE\OutputMonitor`` folder in the AppData\Local folder. In order to see it, we need to open the ``Output Monitor`` application: start the ``Tiny IDE`` by clicking on its icon in the task bar, and in the main menu, click on ``Tools`` -> ``Start Output Monitor``.





.. _rst_XL_functions_MpInput: 

The worksheet "FractionsInput"
...................................................

The worksheet "FractionsInput " demonstrates the use of the Python data type ``Fraction`` in MS Excel spreadsheet formulas.


.. image:: ../_static/XL_MpFractions.png
    :width: 90 %
    :align: center



If we try to enter a number like ``123456789012345678/901234567890``, i.e. a number with more than 16 digits into a spreadsheet cell, it will automatically be shortened to ``1.23456789012346E+029``. In order to be able to enter such numbers into spreadsheet cells, the cells must first be formatted as text, and thereafter these numbers can be entered as text. This is mostly useful when working with Python Fractions and Decimals.

However, this kind of input is hard to read; it is also not directly usable for numerical spreadsheet functions. This can be changed by using the function ``ASDOUBLE``, a shown in column ``B``

As an example, worksheet "FractionsInput" contains a named range called "MpInputFractions" in column ``A``, which can be used as input for descriptive statistics or linear algebra routines.

The module ``npm`` of XlCalcNet can be used to calculate desciptive statistics, like ``prod``, ``sum``, ``mean``, ``median``, ``variance`` with fractions. The function ``npm.mean`` can be called from a spreadsheet cell as follows:


.. code-block:: none

    =CPY_1("from xlcalcnet import npm, qpm $n x = npm.array(P1, dtype=qpm); result=str(npm.prod(x))",MpInputFractions)



Às before, we are using ``$n`` for newline and ``$t`` for indentation. The result is itself a ``Fraction`` (converted to a string), and is exact. The corresponding Python code with conventional formatting would look like this (where ``P1`` is the input range):


.. code-block:: python

    from xlcalcnet import npm, qpm
    x = npm.array(P1, dtype=qpm)
    result=str(npm.prod(x))

Note that the input range is converted into a Numpy array with data type ``qpm``, which is the data type for rational numbers in XlCalcNet. The result is then converted into a string, so that it can be displayed in a spreadsheet cell.

Since the string output is quite long, we can use ``result=float(npm.prod(x))`` instead of ``result=str(npm.prod(x))`` to get a floating point number in double precision, which is more readable. However, this will not be exact anymore.




.. _rst_XL_functions_DecimalsInput: 

The worksheet "DecimalsInput"
.............................................

The worksheet "DecimalsInput " demonstrates the use of the Python data type ``Decimal`` in MS Excel spreadsheet formulas.


.. image:: ../_static/XL_MpDecimals.png
    :width: 90 %
    :align: center



If we try to enter a number like ``123456789012345678.901234567890``, i.e. a number with more than 16 digits into a spreadsheet cell, it will automatically be shortened to ``1.23456789012346E+017``. In order to be able to enter such numbers into spreadsheet cells, the cells must first be formatted as text, and thereafter these numbers can be entered as text. This is mostly useful when working with Python Fractions and Decimals.

However, this kind of input is hard to read; it is also not directly usable for numerical spreadsheet functions. This can be changed by using the function ``ASDOUBLE``, a shown in column ``B``

As an example, worksheet "DecimalsInput" contains a named range called "MpInputDecimals" in column ``C``, which can be used as input for descriptive statistics or linear algebra routines.

The module ``npm`` of XlCalcNet can be used to calculate desciptive statistics, like ``prod``, ``sum``, ``mean``, ``median``, ``variance`` with decimals. The function ``npm.mean`` can be called from a spreadsheet cell as follows:


.. code-block:: none

    =CPY_2("from xlcalcnet import npm, dpm $n dpm.dps=int(P2); x = npm.array(P1, dtype=dpm); result=str(npm.mean(x))",MpInputDecimals, $B$2)



Às before, we are using ``$n`` for newline and ``$t`` for indentation. The result is itself a ``Decimal`` (converted to a string), and is correct to the number of digits specified. The corresponding Python code with conventional formatting would look like this (where ``P1`` is the input range and ``P2`` is the number of digits):


.. code-block:: python

    from xlcalcnet import npm, dpm
    dpm.dps=int(P2)
    x = npm.array(P1, dtype=dpm)
    result=str(npm.mean(x))


Note that the input range is converted into a Numpy array with data type ``dpm``, which is the data type for decimal numbers in XlCalcNet. The result is then converted into a string, so that it can be displayed in a spreadsheet cell.

Since the string output is quite long, we can use ``result=float(npm.prod(x))`` instead of ``result=str(npm.prod(x))`` to get a floating point number in double precision, which is more readable. However, this will then be correct only to the precision of a double-precision floating-point number.











The worksheet "Programming"
...................................................

The worksheet "Programming" demonstrates the use of small python scripts in MS Excel spreadsheet formulas.



.. image:: ../_static/XL_Programming.png
    :width: 60 %
    :align: center



The first example in this worksheeet shows how to program a simple loop. The formula in the cell ``B4``. is 

.. code-block:: none

    =CPY_1("temp = 0 $n for i in range(int(P1)): $n$t temp += i $n result = 2 * temp", B4)


The cell ``B4`` contains the value ``45``; the result is ``1980``. The corresponding Python code with conventional formatting would look like this(where ``P1`` is ``n``, the number of iterations):


.. code-block:: python

        temp = 0
        for i in range(int(P1)):
            temp += i
        result = 2 * temp


|br|


The second example in this worksheet shows how to perform numerical integration.The formula in the cell ``B15``. is 

.. code-block:: none

    =CPY_4("from scipy.integrate import quad $n def integrand(x, a, b): return a*x**2 + b $n a = float(P3); b = float(P4);  $n I = quad(integrand, float(P1), float(P2), args=(a,b))   $n result = str(I) ", B11, B12, B13, B14)


This formula calls the function ``quad`` from the module ``scipy.integrate`` in the package ``scipy``. The parameters of this function are taken from the cells ``B11`` to ``B14``. The result is a tuple containing the intergral and an error estimate. The corresponding Python code with conventional formatting would look like this (with P1 is the lower limit of integration, P2 is the upper limit, P3 is the coefficient of x^2, and P4 is the constant term):


.. code-block:: python

    from scipy.integrate import quad
    def integrand(x, a, b): return a*x**2 + b
    a = float(P3); b = float(P4)
    I = quad(integrand, float(P1), float(P2), args=(a,b))
    result = str(I) 


The cells ``B16`` to ``B17`` show the same result as an array formula, with ``B16`` containing the integral and ``B17`` the error estimate. 





The worksheet "OutputMonitorCSV"
.............................................


This is a snapshot of the worksheet "OutputMonitorCSV" with the relevant formula in cell ``B1``. The output of the formula in cell ``B1`` is a CSV file named ``TTest1External.csv`` which is written to the Output Monitor folder. The Output Monitor application must be running in order to see the output. The Output Monitor can be started from the main menu of the Tiny IDE by clicking on ``Tools`` -> ``Start Output Monitor``.


.. image:: ../_static/XL_OutputMonitorCSV.png
    :width: 60 %
    :align: center


The formula in the cell ``B1``. is 


.. code-block:: none

    =CPY_0(TEXTJOIN(" ",1,"from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues $n D01_StudentT_PValues.stats_student_t_1sample_test(n=",B3,", mu0=",B4,", mean=",B5,", std=",B6,", alpha=", B7, B8, ")"," $n result='Students t-test, 1 sample'"))


This formula calls the function ``stats_student_t_1sample_test`` from the module ``D01_StudentT_PValues`` in the package ``A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample``. The parameters of this function are taken from the cells ``B3`` to ``B8``. The result is a CSV file named ``TTest1External.csv`` which is written to the Output Monitor folder.  The corresponding Python code with conventional formatting and substitution of the referenced cell values would look like this:


.. code-block:: python

    from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues
    D01_StudentT_PValues.stats_student_t_1sample_test(n=[10, 20, 30], mu0=1.0, mean=[4.5,4.7], std=[1,2,3,14], alpha=0.015, I=True, D=True, T=True, C=True, Onesided=True, Twosided=True, OutputMode='csv')
    result='Students t-test, 1 sample'




The cell ``A3`` contains ``="n:"``, and the cell ``B3`` contains ``="[10, 20, 30]"``. This passes the list ``[10, 20, 30]`` as the parameter ``n`` to the function ``stats_student_t_1sample_test``.

The cell ``A4`` contains ``="mu0:"``, and the cell ``B4`` contains ``="1.0"``. This passes the value ``1.0`` as the parameter ``mu0`` to the function ``stats_student_t_1sample_test``. 

The cell ``A5`` contains ``="mean:"``, and the cell ``B5`` contains ``="[4.5,4.7]"``. This passes the list ``[4.5,4.7]`` as the parameter ``mean`` to the function ``stats_student_t_1sample_test``. 

The cell ``A6`` contains ``="std:"``, and the cell ``B6`` contains ``="[1,2,3,14]"``. This passes the list ``[1,2,3,14]`` as the parameter ``std`` to the function ``stats_student_t_1sample_test``. 

The cell ``A7`` contains ``="alpha:"``, and the cell ``B7`` contains ``="0.015"``. This passes the value ``0.015`` as the parameter ``alpha`` to the function ``stats_student_t_1sample_test``.

The cell ``A8`` contains ``="Options:"``, and the cell ``B8`` contains ``=",I=True, D=True, T=True, C=True, Onesided=True, Twosided = True, OutputMode='csv'"``. This passes the options ``I=True, D=True, T=True, C=True, Onesided=True, Twosided = True, OutputMode='csv'`` as keyword arguments to the function ``stats_student_t_1sample_test``.



And this is the Output Monitor showing the result (with the project panel hidden)

.. image:: ../_static/CSV_Output_Monitor.png
    :width: 50 %
    :align: center





The worksheet "OutputMonitorSVG"
.............................................

This is a snapshot of the worksheet "OutputMonitorSVG" with the relevant formula in cell ``B1``. The output of the formula in cell ``B1`` is a SVG file named ``D07_DistPlotContinuous.svg`` which is written to the Output Monitor folder. The Output Monitor application must be running in order to see the output. The Output Monitor can be started from the main menu of the Tiny IDE by clicking on ``Tools`` -> ``Start Output Monitor``.



.. image:: ../_static/XL_OutputMonitorSVG.png
    :width: 70 %
    :align: center




    
The formula in the cell ``B1``. is 


.. code-block:: none

    ==CPY_0(TEXTJOIN(" ",1,"from A01_ExamplesPython.B18_FunctionsAndCurvesPlots.C01_Intro_Parametric2D import D07_DistPlotContinuous $n D07_DistPlotContinuous.DistPlotBeta(target=",B3,", a=",B4,", b=",B5,", Title=",B6,", OutputMode = 'svg'",  ")"," $n result='Beta distribution'"))


This formula calls the function ``DistPlotBeta`` from the module ``D07_DistPlotContinuous`` in the package ``A01_ExamplesPython.B18_FunctionsAndCurvesPlots.C01_Intro_Parametric2D``. The parameters of this function are taken from the cells ``B3`` to ``B8``. The result is a CSV file named ``TTest1External.csv`` which is written to the Output Monitor folder. The corresponding Python code with conventional formatting and substitution of the referenced cell values would look like this:


.. code-block:: python

    from A01_ExamplesPython.B18_FunctionsAndCurvesPlots.C01_Intro_Parametric2D import D07_DistPlotContinuous 
    D07_DistPlotContinuous.DistPlotBeta(target='pdf', a=[5, 10.0, 20.5], b=[20.5, 10.0, 5], Title='Beta distribution', OutputMode = 'svg')
    result='Beta distribution'




The cell ``A3`` contains ``="target:"``, and the cell ``B3`` contains ``="pdf"``. This passes the string ``"pdf"`` as the parameter ``target`` to the function ``DistPlotBeta``.

The cell ``A4`` contains ``="a:"``, and the cell ``B4`` contains ``="[5, 10.0, 20.5]"``. This passes This passes the list ``[5, 10.0, 20.5]``  as the parameter ``a`` to the function ``DistPlotBeta``. 

The cell ``A5`` contains ``="b:"``, and the cell ``B5`` contains ``="[20.5, 10.0, 5]"``. This passes the list ``[20.5, 10.0, 5]`` as the parameter ``b`` to the function ``DistPlotBeta``. 

The cell ``A6`` contains ``="Title:"``, and the cell ``B6`` contains ``="Beta distribution"``. This passes the string ``"Beta distribution"`` as the keyword argument ``Title`` to the function ``DistPlotBeta``. 



And this is the Output Monitor showing the result (with the project panel hidden)

.. image:: ../_static/SVG_Output_Monitor.png
    :width: 50 %
    :align: center






Using dynamic arrrays in MS Excel
---------------------------------------------


The worksheet "Student_t_1sample_test"
.............................................

Dynamic arrays are only supported in MS Excel 365 and MS Excel 2021 or later. In these versions, the output of a function can be an array, which is then automatically "spilled" into the cells below and to the right of the cell containing the formula. The size of the output array can be changed by changing the input parameters of the function.

The worksheet "Student_t_1sample_test" demonstrates  the use of dynamic arrays in Excel with XlCalcNet.

This is a snapshot of the worksheet "Student_t_1sample_test" with the formula in cell ``A11``, which is also where the output is starting. The main difference to the example with ``*.csv`` output is that now in "Options" we have ``OutputMode='list'`` and not ``OutputMode='csv'``.

.. image:: ../_static/XL_WS_DynamicArray.png
    :width: 60 %
    :align: center



The formula in the cell ``A11`` is 


.. code-block:: none

    =CPY_0(TEXTJOIN(" ",1,"from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues $n D01_StudentT_PValues.stats_student_t_1sample_test(n=",B3,", mu0=",B4,", mean=",B5,", std=",B6,", alpha=", B7, B8, ")"," $n result='Students t-test, 1 sample'"))


This formula calls the function ``stats_student_t_1sample_test`` from the module ``D01_StudentT_PValues`` in the package ``A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample``. The parameters of this function are taken from the cells ``B3`` to ``B8``. The result is a Python list, which is displayed as a dynamic array.  The corresponding Python code with conventional formatting and substitution of the referenced cell values would look like this:


.. code-block:: python

    from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues
    D01_StudentT_PValues.stats_student_t_1sample_test(n=[10, 20, 30], mu0=1.0, mean=[4.5,4.7], std=[1,2,3,14], alpha=0.015, I=True, D=True, T=True, C=True, Onesided=True, Twosided=True, OutputMode='list')
    result='Students t-test, 1 sample'



The cell ``A3`` contains ``="n:"``, and the cell ``B3`` contains ``="[10, 20, 30]"``. This passes the list ``[10, 20, 30]`` as the parameter ``n`` to the function ``stats_student_t_1sample_test``.

The cell ``A4`` contains ``="mu0:"``, and the cell ``B4`` contains ``="1.0"``. This passes the value ``1.0`` as the parameter ``mu0`` to the function ``stats_student_t_1sample_test``. 

The cell ``A5`` contains ``="mean:"``, and the cell ``B5`` contains ``="[4.5,4.7]"``. This passes the list ``[4.5,4.7]`` as the parameter ``mean`` to the function ``stats_student_t_1sample_test``. 

The cell ``A6`` contains ``="std:"``, and the cell ``B6`` contains ``="[1,2,3,14]"``. This passes the list ``[1,2,3,14]`` as the parameter ``std`` to the function ``stats_student_t_1sample_test``. 

The cell ``A7`` contains ``="alpha:"``, and the cell ``B7`` contains ``="0.015"``. This passes the value ``0.015`` as the parameter ``alpha`` to the function ``stats_student_t_1sample_test``.

The cell ``A8`` contains ``="Options:"``, and the cell ``B8`` contains ``=",I=True, D=True, T=True, C=True, Onesided=True, Twosided = True, OutputMode='csv'"``. This passes the options ``I=True, D=True, T=True, C=True, Onesided=True, Twosided = True, OutputMode='list'`` as keyword arguments to the function ``stats_student_t_1sample_test``.







Managing procedures instead of functions
---------------------------------------------

It is possible to call the spreadsheet functions  ``CPY_0`` to ``CPY_9`` from LibreOffice Basic and to use this to start procedures instead of functions. A few simple examples have already been prepared to demonstrate the technique. 


To access the relevant dialog, click on the XlCalcNet logo (in orange) on the main menu bar:

.. image:: ../_static/XL_ContextMenu.png
    :align: center
    :width: 40%


The following dialog box with the title **Navigator for XlCalcNet** will appear:


.. image:: ../_static/XL_NavigatorXlCalcNet.png
    :align: center
    :width: 50%


The first example, with ``CSV Output`` in "Category" and ``ShowTTest1`` in "Subroutine", will write a CSV file into the ``XlCalcNetIDE\OutputMonitor`` folder in the AppData\Local folder. In order to see it, we need to open the ``Output Monitor`` application: start the ``Tiny IDE`` by clicking on its icon in the task bar, and in the main menu, click on ``Tools`` -> ``Start Output Monitor``. With the ``Output Monitor`` application running, click ``OK``. The CSV file will then immediately appear in the ``Output Monitor``. 


The corresponding code in the module ``MpFunlabLocal`` -> ``BasicAndDialogs`` is shown below:

.. code-block:: visualbasic

    Sub ShowTTest1()
        Rem Output (a .csv file) is shown in output monitor
        Code = "from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues;"
        Code = Code + "D01_StudentT_PValues.demo_stats_student_t_1sample_test(); result='Done';"
        Result = Application.Run("CPY_0", Code)
        showResult (Result)
    End Sub


The second example, with ``SVG Output`` in "Category" and ``ShowPolygon`` in "Subroutine", will write a SVG file into the ``XlCalcNetIDE\OutputMonitor`` folder in the AppData\Local folder. With the ``Output Monitor`` application running (see above), click ``OK``. The SVG file will then immediately appear in the ``Output Monitor``. 


The corresponding code in the module ``MpFunlabLocal`` -> ``BasicAndDialogs`` is shown below:

.. code-block:: visualbasic

    Sub ShowPolygon()
        Rem Graphics is shown in output monitor
        Code = "from A01_ExamplesPython.B18_FunctionsAndCurvesPlots.C02_BasicCurves import D01_RegularConvexPolygon;"
        Code = Code + "D01_RegularConvexPolygon.RegularConvexPolygon(OutputMode='svg'); result='Done';"
        Result = Application.Run("CPY_0", Code)
        showResult (Result)
    End Sub







Uninstalling
---------------------------------------------

To uninstall these two Add-ins properly, follow these steps:   
Within MS Excel, on an Excel worksheet, open the Add-ins dialog from the main menu/ribbon: ``Developer`` -> ``Excel Add-ins``. In the Add-ins dialog, unselect ``MpFunlab`` and ``Mpfunlablocal``,  and click on ``OK``. Close MS Excel. When Excel is started the next time these Add-ins will not be loaded, however, they will still appear (unselected) in the Add-ins dialog (this seems to be a decade-old bug/feature). To remove them also from the Add-ins dialog, you need to rename them in their original location, start Excel again, and start the Add-ins dialog again. When you then re-select these unselected items, a dialog stating that the add-in cannot be found will appear, followed by "Delete from list?". Click on `Yes`, and the add-in will be removed from the list.













