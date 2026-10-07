


.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />




|newpage|


.. _rst_LibreOfficeCalc: 

Using XlCalcNet within LibreOffice Calc
===========================================



.. _rst_setting_up_LOCalc: 

Preparing LibreOffice Calc for using XlCalcNet
---------------------------------------------------------------------------------------------

To enable the use of XlCalcNet in LibreOffice Calc, two extensions need to be installed: the first, named ``MpfunlabLocal.oxt``, contains functions and dialogs written in LibreOffice Basic and is intended to be modified by the user during normal use. The second, named ``Mpfunlab.oxt``, contains the functionality behind the spreadsheet functions ``APY0`` - ``APY9`` and ``ASDOUBLE``. It has been compiled using the SDK of LibreOfffice 7.4 and is NOT intended to be modified by the user during normal use. Both extensions are located in a subfolder of the ``DataXlCalcNet`` folder in the ``Documents`` folder: ``DataXlCalcNet\SpreadsheetAddins\LibreOfficeCalc``.


Installing MpfunlabLocal.oxt and Mpfunlab.oxt
..........................................................

To install these two extensions properly, following the correct order is important. First install ``MpfunlabLocal.oxt`` within a normally launched LibreOffice Calc (i.e. without administrator privileges): Open the Extension dialog from the main menu:``Tools`` -> ``Extensions...``. In the Extension dialog click the ``Add`` button and in the ``Documents`` folder navigate to the folder ``DataXlCalcNet\SpreadsheetAddins\LibreOfficeCalc``. Double- click on ``MpfunlabLocal.oxt``. Then click on the ``Close`` button in the Extension dialog. In the dialog ``Restart LibreOffice``, click on ``Restart Now``. This will close LibreOffice Calc and will open the general LibreOffice desktop. Exit LibreOffice.

Now start LibreOffice with administrator privileges: Right-click on the desktop icon of LibreOffice and select ``Run as administrator``. In the following dialog, confirm that you want to proceed. In the LibreOffice desktop, open a ``Calc Spreadsheet``. Open the Extension dialog from the main menu:``Tools`` -> ``Extensions...``. In the Extension dialog click the ``Add`` button and in the ``Documents`` folder navigate to the folder ``DataXlCalcNet\SpreadsheetAddins\LibreOfficeCalc``. Double- click on ``Mpfunlab.oxt``. In the following dialog box "For whom do you want to install the extension?", click on ``For all users``. In the following "License Agreement" dialog, click on ``Accept``. Then click on the ``Close`` button in the Extension dialog. In the dialog ``Restart LibreOffice``, click on ``Restart Now``. This will close LibreOffice Calc and will open the general LibreOffice desktop. Exit LibreOffice.

Within a normally launched LibreOffice Calc, open the Macro Editor from the main menu: ``Tools`` -> ``Macros`` -> ``Edit Macros...``. In the Object Catalog of the Macro Editor, select ``My Macros & Dialogs`` -> ``MpFunlabLocal`` -> ``CallsFromPython``: In the function ``GetCPythonExeDirLocal`` set the path of the external Python installation which matches the main internal Python version, e.g. ``GetCPythonExeDirLocal ="C:\Python313"``. Then close the Macro Editor.



.. _rst_LO_functions_standard: 

Using the Python standard library functions within spreadsheet formulas
---------------------------------------------------------------------------------------------

.. note::
    In the following subsections, we will work with the file ``LoDemoAPYstd.ods``, which contains examples for using the Python standard library. More advanced examples using Numpy, Matplotlib, Pandas, Scipy, Seaborn and XlCalcNet start  :ref:`here <rst_LO_functions_advanced>`.


Within LibreOffice Calc, open from the main menu ``File`` -> ``Open`` in the Documents folder the LibreOffice Calc workbook ``DataXlCalcNet\DataExamples\MainExamples\Workbooks\LoDemoAPYstd.ods``.

This file contains several worksheets which demonstrate different possibilities of using the Python standard library within Libreoffice Calc spreadsheet formulas.

Before we start with that we will briefly explore the use of these functions with the Function Wizard of  LibreOffice Calc: In the worksheet "Math", select cell ``B12`` and click on the icon of the Function Wizard in the Formula Bar. This opens the Function Wizard with the Structure tab selected:


.. image:: ../_static/LO_FunctionWizardStructureCeil.png
    :align: center
    :width: 50%



We see that the formula in the spreadsheeet cell is ``=APY1("result = math.ceil(P1)",C12)``. The function ``APY1`` has a required string parameter, ``Formula``, which contains a Python script. This python script can contain several Python statement. The last statement is always expected to assign a value to the variable result, in this case a Python float, which is coverted to a floating point number in double precision (a "Double") in LibreOffice. The next optional parameter, ``Param1``, can be a string, a Double, a Boolean value or a reference. In this case, it is a reference (``C12``) which points to a Double with the value ``3.123``. This optional parameter, ``Param1``, is referenced in the Python formula given above as ``P1``. The last but one parameter, ``Transposed``, and the last parameter, ``ShowShape``, are only relevant when arrays are returned; this is discussed :ref:`here <rst_LO_functions_Arrays>`.

If we open the Functions tab, the Functions wizard looks like this:


.. image:: ../_static/LO_FunctionWizardFunctionsCeil.png
    :align: center
    :width: 50%



We see that the function ``APY1`` is in the Category "Add-in", and that there are 10 functions,  ``APY0`` to ``APY9``, which differ only by the number of parameters ``Param1`` to ``Param9`` which they support (The function ``APY0`` does not have a parameter ``Param0``). There is also a function ``ASDOUBLE``, which is used to convert string representations of a Python Fraction or Decimal into a Double; this is discussed :ref:`here <rst_LO_functions_FractionsInput>`.



The worksheet "GeneralInfo"
.............................................


The worksheet "GeneralInfo" contains calls to the Python modules ``os``, ``platform`` and ``sys``. 

For example, the cell ``B4`` contains the formula ``=APY0("result = platform.processor()")``. The function result depends on the hardware, e.g. ``Intel64 Family 6 Model 165 Stepping 5, GenuineIntel``.

The cell ``B16`` contains the formula ``=APY0("result = os.getcwd()")``. The function result depends on the LibreOffice installation, e.g. ``C:\Program Files\LibreOffice\program``.

The cell ``B33`` contains the formula ``=APY0("result = str(sys.float_info.epsilon)")``, which return the machine epsilon in double precision. The function result is: ``2.220446049250313e-16``.



The worksheet "Math"
.............................................

The worksheet "Math" demonstrates the use of the Python module ``math`` and the use of parameters in functions. 

For example, the cell ``B33`` contains the formula ``=APY1("result = math.exp(P1)-1",C33)``, which calculates `\exp(\text{P1})-1` naively. The function result is ``1.00000500000696E-05``, with the cell ``C33`` containing the value ``0.00001``.

The cell ``B34`` contains the formula ``=APY1("result = math.expm1(P1)",C34)``, which calculates `\exp(\text{P1})-1` using the ``expm1`` function. The function result is ``1.00000500001667E-05``, with the cell ``C34`` again containing the value ``0.00001``.

The floating point  values ``NaN``, ``+inf`` and ``-inf`` are not supported in spreadsheet programs, which only return ``#NUM!`` in these cases. Use the string representation instead. This is shown in the cells ``A4:B9`` on this worksheet.

The cell ``B36`` contains the formula ``=APY2("result = math.log(P1, P2)",C36, D36)``, with the cell ``C36`` containing the value ``3.123`` and the cell ``D36`` containing the value ``10``. The function result is: ``0.494571984230199``.




.. _rst_LO_functions_Arrays: 

The worksheet "Arrays"
.............................................


The worksheet "Arrays" demonstrates the use of arrays in functions. The Python equivalent of arrays are lists.

For example, the cell ``B3`` contains the formula ``=APY0("result = str(sys.path)")``. The function ``sys.path`` returns a list of strings (containing the entries of the Python path), which is converted into one string by writing ``str(sys.path)``. This makes sure that the result can be displayed in one cell, but the result string is quite long and hard to read.

We can use an array formula to improve readability. We recall that in addition to the usual parameters ``P1`` - ``P9`` in the functions ``APY0`` to ``APY9`` there are two more: The last but one paramter, named ``Transposed``, which is optional with default value 0, where a non-zero value means that the returned array should be transposed; and the last paramter, named ``ShowShape``, which is optional with default value 0, where a non-zero value means that the shape of the returned array should be indicated like ``R7C3`` for an array with 7 rows and 3 columns.

As an example, the cell ``B6`` contains the formula ``=APY0("result = sys.path",1,1)`` and returns the shape information ``R12C1`` followed by the separator ``|``, followed by the first entry of the transposed array, i.e. in this case ``R12xC1| C:\Users\DUHad\Documents\DataXlCalcNet``.

We can build the corresponding array formula by first selecting a range like ``R12C1``, then typing in the input line of the formula bar ``=APY0("result = sys.path",1,0)``, and finally, while keeping the shift and control keys pressed down, pressing the enter key.

This is what has been done in cells ``B9:B20``. The formula is now displayed as ``{=APY0("result = sys.path",1,0)}``, with curly braces, to indicate that it is an array formula. We can change the range which is covered by the array formula by dragging the small blue rectangle in the lower right corner in the selected range (see the screenshot below).


.. image:: ../_static/LO_Change_Range.png
    :align: center
    :width: 60%








The worksheet "Data"
.............................................

The worksheet "Data " demonstrates the use of named ranges in LibreOffice Calc spreadsheet formulas.

Currently there a two small datasets with predefined as named ranges: ``matA`` defined as the range $Data.$A$3:$A$7 and  ``matB`` defined as the range $Data.$A$3:$A$7.

These ranges are used in the workbook "Arrays".







.. _rst_LO_functions_advanced: 

Using Numpy, Matplotlib, Pandas, Scipy, Seaborn and XlCalcNet within spreadsheet formulas
---------------------------------------------------------------------------------------------

.. note::
    In the following subsections. we will work with the file ``LoDemoAPYadv.ods``, which contains more advanced examples using Numpy, Matplotlib, Pandas, Scipy, Seaborn and XlCalcNet. Examples for using LibreOffice Calc with the Python standard library start :ref:`here <rst_LO_functions_standard>`.


Within LibreOffice Calc, open from the main menu ``File`` -> ``Open`` in the Documents folder the LibreOffice Calc workbook ``DataXlCalcNet\DataExamples\MainExamples\Workbooks\LoDemoAPYadv.ods``.

This file contains several worksheets which demonstrate different possibilities of using Numpy, Matplotlib, Pandas, Scipy, Seaborn and XlCalcNet within Libreoffice Calc spreadsheet formulas.

Some of these functions write their output  into the ``XlCalcNetIDE\OutputMonitor`` folder in the AppData\Local folder. In order to see it, we need to open the ``Output Monitor`` application: start the ``Tiny IDE`` by clicking on its icon in the task bar, and in the main menu, click on ``Tools`` -> ``Start Output Monitor``.





.. _rst_LO_functions_FractionsInput: 

The worksheet "FractionsInput"
.............................................

The worksheet "FractionsInput " demonstrates the use of the Python data type ``Fraction`` in LibreOffice Calc spreadsheet formulas.


.. image:: ../_static/LO_MpFractions.png
    :width: 90 %
    :align: center



If we try to enter a number like ``123456789012345678/901234567890``, i.e. a number with more than 16 digits into a spreadsheet cell, it will automatically be shortened to ``1.23456789012346E+029``. In order to be able to enter such numbers into spreadsheet cells, the cells must first be formatted as text, and thereafter these numbers can be entered as text. This is mostly useful when working with Python Fractions and Decimals.

However, this kind of input is hard to read; it is also not directly usable for numerical spreadsheet functions. This can be changed by using the function ``ASDOUBLE``, a shown in column ``B``

As an example, worksheet "FractionsInput" contains a named range called "MpInputFractions" in column ``A``, which can be used as input for descriptive statistics or linear algebra routines.

The module ``npm`` of XlCalcNet can be used to calculate desciptive statistics, like ``prod``, ``sum``, ``mean``, ``median``, ``variance`` with fractions. The function ``npm.mean`` can be called from a spreadsheet cell as follows:


.. code-block:: none

    =APY1("from xlcalcnet import npm, qpm $n x = npm.array(P1, dtype=qpm); result=str(npm.prod(x))",MpInputFractions)



Às before, we are using ``$n`` for newline and ``$t`` for indentation. The result is itself a ``Fraction`` (converted to a string), and is exact. The corresponding Python code with conventional formatting would look like this (where ``P1`` is the input range):


.. code-block:: python

    from xlcalcnet import npm, qpm
    x = npm.array(P1, dtype=qpm)
    result=str(npm.prod(x))

Note that the input range is converted into a Numpy array with data type ``qpm``, which is the data type for rational numbers in XlCalcNet. The result is then converted into a string, so that it can be displayed in a spreadsheet cell.

Since the string output is quite long, we can use ``result=float(npm.prod(x))`` instead of ``result=str(npm.prod(x))`` to get a floating point number in double precision, which is more readable. However, this will not be exact anymore.




.. _rst_LO_functions_DecimalsInput: 

The worksheet "DecimalsInput"
.............................................

The worksheet "DecimalsInput " demonstrates the use of the Python data type ``Decimal`` in LibreOffice Calc spreadsheet formulas.


.. image:: ../_static/LO_MpDecimals.png
    :width: 90 %
    :align: center



If we try to enter a number like ``123456789012345678.901234567890``, i.e. a number with more than 16 digits into a spreadsheet cell, it will automatically be shortened to ``1.23456789012346E+017``. In order to be able to enter such numbers into spreadsheet cells, the cells must first be formatted as text, and thereafter these numbers can be entered as text. This is mostly useful when working with Python Fractions and Decimals.

However, this kind of input is hard to read; it is also not directly usable for numerical spreadsheet functions. This can be changed by using the function ``ASDOUBLE``, a shown in column ``B``

As an example, worksheet "DecimalsInput" contains a named range called "MpInputDecimals" in column ``C``, which can be used as input for descriptive statistics or linear algebra routines.

The module ``npm`` of XlCalcNet can be used to calculate desciptive statistics, like ``prod``, ``sum``, ``mean``, ``median``, ``variance`` with decimals. The function ``npm.mean`` can be called from a spreadsheet cell as follows:


.. code-block:: none

    =APY2("from xlcalcnet import npm, dpm $n dpm.dps=int(P2); x = npm.array(P1, dtype=dpm); result=str(npm.mean(x))",MpInputDecimals, $B$2)



Às before, we are using ``$n`` for newline and ``$t`` for indentation. The result is itself a ``Decimal`` (converted to a string), and is correct to the number of digits specified. The corresponding Python code with conventional formatting would look like this (where ``P1`` is the input range and ``P2`` is the number of digits):


.. code-block:: python

    from xlcalcnet import npm, dpm
    dpm.dps=int(P2)
    x = npm.array(P1, dtype=dpm)
    result=str(npm.mean(x))


Note that the input range is converted into a Numpy array with data type ``dpm``, which is the data type for decimal numbers in XlCalcNet. The result is then converted into a string, so that it can be displayed in a spreadsheet cell.

Since the string output is quite long, we can use ``result=float(npm.prod(x))`` instead of ``result=str(npm.prod(x))`` to get a floating point number in double precision, which is more readable. However, this will then be correct only to the precision of a double-precision floating-point number.







The worksheet "Programming"
.............................................

The worksheet "Programming" demonstrates the use of small python scripts in LibreOffice Calc spreadsheet formulas.



.. image:: ../_static/LO_Programming.png
    :width: 60 %
    :align: center



The first example in this worksheeet shows how to program a simple loop. The formula in the cell ``B4``. is 

.. code-block:: none

    =APY1("temp = 0 $n for i in range(int(P1)): $n$t temp += i $n result = 2 * temp", B4)


The cell ``B4`` contains the value ``45``; the result is ``1980``. The corresponding Python code with conventional formatting would look like this(where ``P1`` is ``n``, the number of iterations):


.. code-block:: python

        temp = 0
        for i in range(int(P1)):
            temp += i
        result = 2 * temp


|br|


The second example in this worksheet shows how to perform numerical integration.The formula in the cell ``B15``. is 

.. code-block:: none

    =APY4("from scipy.integrate import quad $n def integrand(x, a, b): return a*x**2 + b $n a = float(P3); b = float(P4);  $n I = quad(integrand, float(P1), float(P2), args=(a,b))   $n result = str(I) ", B11, B12, B13, B14)


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


.. image:: ../_static/LO_OutputMonitorCSV.png
    :width: 60 %
    :align: center


The formula in the cell ``B1``. is 


.. code-block:: none

    =APY0(TEXTJOIN(" ",1,"from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues $n D01_StudentT_PValues.stats_student_t_1sample_test(n=",B3,", mu0=",B4,", mean=",B5,", std=",B6,", alpha=", B7, B8, ")"," $n result='Students t-test, 1 sample'"))


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



.. image:: ../_static/LO_OutputMonitorSVG.png
    :width: 70 %
    :align: center

    
The formula in the cell ``B1``. is 


.. code-block:: none

    ==APY0(TEXTJOIN(" ",1,"from A01_ExamplesPython.B18_FunctionsAndCurvesPlots.C01_Intro_Parametric2D import D07_DistPlotContinuous $n D07_DistPlotContinuous.DistPlotBeta(target=",B3,", a=",B4,", b=",B5,", Title=",B6,", OutputMode = 'svg'",  ")"," $n result='Beta distribution'"))


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






.. _rst_LO_functions_external: 

Using links to external ``*.csv``, ``*.xlsx`` and ``*.svg`` files
---------------------------------------------------------------------------------------------

.. note::
    In the following subsections. we will work with the file ``LoDemoAPYext.ods``, which contains more advanced examples using Numpy, Matplotlib, Pandas, Scipy, Seaborn and XlCalcNet. Examples for using LibreOffice Calc with the Python standard library start :ref:`here <rst_LO_functions_standard>`.


Within LibreOffice Calc, open from the main menu ``File`` -> ``Open`` in the Documents folder the LibreOffice Calc workbook ``\DataXlCalcNet\DataExamples\MainExamples\Workbooks\LoDemoAPYext.ods``.

This file contains several worksheets which demonstrate the use of links to external files in such a way that the output is displayed in the spreadsheet. This is demonstrated in the worksheets "ExternalCSV", "ExternalXlsx" and "ExternalSVG".

Using links to external files poses a security risk, because it allows the execution of arbitrary code on the local computer. This can be adressed by using "Trusted Locations": In the main menu, click on ``Tools`` -> ``Options`` -> ``LibreOffice`` -> ``Security`` -> ``Macro Security...``. In the dialog "Macro Security", select the tab "Trusted Sources" and in the section "Trusted File Locations", click "Add", and add the path to the folder of the file **containing the links**  to the external files (NOT the paths to the external files themselves!). In our case this is the file ``LoDemoAPYext.ods`` and the path to the folder containing this file is ``DataXlCalcNet\DataExamples\MainExamples\Workbooks``). Confirm with ``OK``. 

Still in the Options dialog, go to ``LibreOffice Calc`` -> ``General``. In the section "Update links when opening", select the item "Always (from trusted locations)" and confirm with ``OK``.




.. _rst_LO_functions_ExternalCSV: 

The worksheet "ExternalCSV"
.............................................

The worksheet "ExternalCSV" demonstrates the use of a link to an external ``*.csv`` file in such a way that the output is displayed in the spreadsheet and is updated automatically when the input data changes. This mimics, to some extend, the use of dynamic arrays in Excel, which are not available in LibreOffice Calc at the time of writing (October 2026).

This is a snapshot of the worksheet "ExternalCSV" with the formula in cell ``B1`` and the output starting at cell ``A10``. The output of the formula in cell ``B1`` is a CSV file named ``TTest1External.csv`` which is written to the Output Monitor folder.

.. image:: ../_static/LO_WS_ExternalCVS.png
    :width: 60 %
    :align: center



The formula in the cell ``B1``. is 


.. code-block:: none

    =APY0(TEXTJOIN(" ",1,"from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues $n D01_StudentT_PValues.stats_student_t_1sample_test(n=",B3,", mu0=",B4,", mean=",B5,", std=",B6,", alpha=", B7, B8, ")"," $n result='Students t-test, 1 sample'"))


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


To have the output displayed in the spreadsheet, follow these steps: 

Select the cell where the output should start to be displayed (in this case, cell ``A10``). In the main menu, click on ``Sheet`` -> ``External Links...``. In the dialog "External Data", click on ``Browse...``. In the dialog "Insert", select the file ``TTest1External.csv`` in the Output Monitor folder and click on ``Open``. 

This will open the dialog "Text Import - [TTest1External.csv]". 


.. image:: ../_static/LO_TextImport.png
    :width: 80 %
    :align: center

Make sure that the option "Separated by" is selected, and that the option "Semicolon" is checked. Then click on ``OK``. 

Back in the dialog "External Data", check the box "Update every" and and set the time to 5 seconds. The output of the function ``stats_student_t_1sample_test`` will now be displayed in the spreadsheet, starting at the cell which was selected when opening the dialog "External Data". And because the option "Update every" is checked, the output will be updated every 5 seconds. If you change any of the parameters in cells ``B3`` to ``B8``, the output will be updated accordingly.


.. image:: ../_static/LO_ExternalData_CSV.png
    :width: 40 %
    :align: center


If later on you want to change the settings of the external link, click in the main menu on ``Edit`` -> ``Links to External Files...``. In the dialog "Edit Links", select the link to the file ``TTest1External.csv`` and click on ``Modify...``. This will open the dialog "External Data" again, where you can change the settings.


.. image:: ../_static/LO_EditLinks_CSV.png
    :width: 60 %
    :align: center







The worksheet "ExternalXlsx"
.............................................

The worksheet "ExternalXlsx" demonstrates the use of a link to an external ``*.xlsx`` file in such a way that the output is displayed in the spreadsheet and is updated automatically when the input data changes. This mimics, to some extend, the use of dynamic arrays in Excel, which are not available in LibreOffice Calc at the time of writing (October 2026).

This is a snapshot of the worksheet "ExternalXlsx" with the formula in cell ``B1`` and the output starting at cell ``A10``. The output of the formula in cell ``B1`` is an Excel file named ``TTest1External.xlsx`` which is written to the Output Monitor folder.

.. image:: ../_static/LO_WS_ExternalXLSX.png
    :width: 60 %
    :align: center



The formula in the cell ``B1``. is 


.. code-block:: none

    =APY0(TEXTJOIN(" ",1,"from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues $n D01_StudentT_PValues.stats_student_t_1sample_test(n=",B3,", mu0=",B4,", mean=",B5,", std=",B6,", alpha=", B7, B8, ")"," $n result='Students t-test, 1 sample'"))


This formula calls the function ``stats_student_t_1sample_test`` from the module ``D01_StudentT_PValues`` in the package ``A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample``. The parameters of this function are taken from the cells ``B3`` to ``B8``. The result is a CSV file named ``TTest1External.csv`` which is written to the Output Monitor folder.  The corresponding Python code with conventional formatting and substitution of the referenced cell values would look like this:


.. code-block:: python

    from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues
    D01_StudentT_PValues.stats_student_t_1sample_test(n=[10, 20, 30], mu0=1.0, mean=[4.5,4.7], std=[1,2,3,14], alpha=0.015, I=True, D=True, T=True, C=True, Onesided=True, Twosided=True, OutputMode='xlsx')
    result='Students t-test, 1 sample'



The cell ``A3`` contains ``="n:"``, and the cell ``B3`` contains ``="[10, 20, 30]"``. This passes the list ``[10, 20, 30]`` as the parameter ``n`` to the function ``stats_student_t_1sample_test``.

The cell ``A4`` contains ``="mu0:"``, and the cell ``B4`` contains ``="1.0"``. This passes the value ``1.0`` as the parameter ``mu0`` to the function ``stats_student_t_1sample_test``. 

The cell ``A5`` contains ``="mean:"``, and the cell ``B5`` contains ``="[4.5,4.7]"``. This passes the list ``[4.5,4.7]`` as the parameter ``mean`` to the function ``stats_student_t_1sample_test``. 

The cell ``A6`` contains ``="std:"``, and the cell ``B6`` contains ``="[1,2,3,14]"``. This passes the list ``[1,2,3,14]`` as the parameter ``std`` to the function ``stats_student_t_1sample_test``. 

The cell ``A7`` contains ``="alpha:"``, and the cell ``B7`` contains ``="0.015"``. This passes the value ``0.015`` as the parameter ``alpha`` to the function ``stats_student_t_1sample_test``.

The cell ``A8`` contains ``="Options:"``, and the cell ``B8`` contains ``=",I=True, D=True, T=True, C=True, Onesided=True, Twosided = True, OutputMode='csv'"``. This passes the options ``I=True, D=True, T=True, C=True, Onesided=True, Twosided = True, OutputMode='xlsx'`` as keyword arguments to the function ``stats_student_t_1sample_test``.


To have the output displayed in the spreadsheet, follow these steps: 

Select the cell where the output should start to be displayed (in this case, cell ``A10``). In the main menu, click on ``Sheet`` -> ``External Links...``. In the dialog "External Data", click on ``Browse...``. In the dialog "Insert", select the file ``TTest1External.xlsx`` in the Output Monitor folder and click on ``Open``. 


Back in the dialog "External Data", check the box "Update every" and and set the time to 5 seconds. The output of the function ``stats_student_t_1sample_test`` will now be displayed in the spreadsheet, starting at the cell which was selected when opening the dialog "External Data". And because the option "Update every" is checked, the output will be updated every 5 seconds. If you change any of the parameters in cells ``B3`` to ``B8``, the output will be updated accordingly.


.. image:: ../_static/LO_ExternalData_XLSX.png
    :width: 40 %
    :align: center


If later on you want to change the settings of the external link, click in the main menu on ``Edit`` -> ``Links to External Files...``. In the dialog "Edit Links", select the link to the file ``TTest1External.xlsx`` and click on ``Modify...``. This will open the dialog "External Data" again, where you can change the settings.


.. image:: ../_static/LO_EditLinks_XLSX.png
    :width: 60 %
    :align: center






The worksheet "ExternalSVG"
.............................................


The worksheet "ExternalSVG" demonstrates the use of a link to an external ``*.svg`` file in such a way that the output is displayed in the spreadsheet and is updated manually when the input data changes.

This is a snapshot of the worksheet "ExternalSVG" with the formula in cell ``B1`` and the output starting at cell ``A10``. The output of the formula in cell ``B1`` is an SVG file named ``D07_DistPlotContinuous.svg`` which is written to the Output Monitor folder.

.. image:: ../_static/LO_WS_ExternalSVG.png
    :width: 60 %
    :align: center



The formula in the cell ``B1``. is 


.. code-block:: none

    ==APY0(TEXTJOIN(" ",1,"from A01_ExamplesPython.B18_FunctionsAndCurvesPlots.C01_Intro_Parametric2D import D07_DistPlotContinuous $n D07_DistPlotContinuous.DistPlotBeta(target=",B3,", a=",B4,", b=",B5,", Title=",B6,", OutputMode = 'svg'",  ")"," $n result='Beta distribution'"))


This formula calls the function ``DistPlotBeta`` from the module ``D07_DistPlotContinuous`` in the package ``A01_ExamplesPython.B18_FunctionsAndCurvesPlots.C01_Intro_Parametric2D``. The parameters of this function are taken from the cells ``B3`` to ``B8``. The result is a CSV file named ``TTest1External.csv`` which is written to the Output Monitor folder. The corresponding Python code with conventional formatting and substitution of the referenced cell values would look like this:


.. code-block:: python

    from A01_ExamplesPython.B18_FunctionsAndCurvesPlots.C01_Intro_Parametric2D import D07_DistPlotContinuous 
    D07_DistPlotContinuous.DistPlotBeta(target='pdf', a=[5, 10.0, 20.5], b=[20.5, 10.0, 5], Title='Beta distribution', OutputMode = 'svg')
    result='Beta distribution'




The cell ``A3`` contains ``="target:"``, and the cell ``B3`` contains ``="pdf"``. This passes the string ``"pdf"`` as the parameter ``target`` to the function ``DistPlotBeta``.

The cell ``A4`` contains ``="a:"``, and the cell ``B4`` contains ``="[5, 10.0, 20.5]"``. This passes This passes the list ``[5, 10.0, 20.5]``  as the parameter ``a`` to the function ``DistPlotBeta``. 

The cell ``A5`` contains ``="b:"``, and the cell ``B5`` contains ``="[20.5, 10.0, 5]"``. This passes the list ``[20.5, 10.0, 5]`` as the parameter ``b`` to the function ``DistPlotBeta``. 

The cell ``A6`` contains ``="Title:"``, and the cell ``B6`` contains ``="Beta distribution"``. This passes the string ``"Beta distribution"`` as the keyword argument ``Title`` to the function ``DistPlotBeta``. 


To have the output displayed in the spreadsheet, follow these steps: 

In the main menu, click on ``Insert`` -> ``Image...``.  In the dialog "Insert Image", select ``Anchor: To page`` and then select the file ``D07_DistPlotContinuous.svg`` in the Output Monitor folder and click on ``Open``. 


.. image:: ../_static/LO_ConfirmLinkedGraphic.png
    :width: 40 %
    :align: center



The "Confirm Linked Graphic" dialog will appear. Click on ``Keep Link``.

Unfortunately, LibreOffice Calc does not allow to update the linked graphic automatically when the input parameters have changed and the modified ``*.svg`` file has been written to the Output Monitor folder. 


.. image:: ../_static/LO_UpdateGraphic.png
    :width: 60 %
    :align: center



To manually update the linked graphic, click in the main menu on ``Edit`` -> ``Links to External Files...``. In the dialog "Edit Links", select the link to the file ``D07_DistPlotContinuous.svg`` and click on ``Update``. This will immediately display the updated graphic.






|br|








Managing procedures instead of functions
---------------------------------------------------------------------------------------------

It is possible to call the spreadsheet functions  ``APY0`` to ``APY9`` from LibreOffice Basic and to use this to start procedures instead of functions. A few simple examples have already been prepared to demonstrate the technique. 


To access the relevant dialog, click on the XlCalcNet logo (in orange) on the main menu bar:

.. image:: ../_static/LO_MainMenu.png
    :align: center
    :width: 30%


The following dialog box with the title **Navigator for XlCalcNet** will appear:


.. image:: ../_static/LO_NavigatorXlCalcNet.png
    :align: center
    :width: 50%


The first example, with ``CSV Output`` in "Category" and ``ShowTTest1`` in "Subroutine", will write a CSV file into the ``XlCalcNetIDE\OutputMonitor`` folder in the AppData\Local folder. In order to see it, we need to open the ``Output Monitor`` application: start the ``Tiny IDE`` by clicking on its icon in the task bar, and in the main menu, click on ``Tools`` -> ``Start Output Monitor``. With the ``Output Monitor`` application running, click ``OK``. The CSV file will then immediately appear in the ``Output Monitor``. 


The corresponding code in the module ``MpFunlabLocal`` -> ``BasicAndDialogs`` is shown below:

.. code-block:: visualbasic

    Sub ShowTTest1()
        REM Output (a .csv file) is shown in output monitor
        fa = createUnoService("com.sun.star.sheet.FunctionAccess")  
        Code = "from A06_UserlibExamplesPython.B29_InferentialStatistics.C01_BasicTests1Sample import D01_StudentT_PValues;"
        Code = Code + "D01_StudentT_PValues.demo_stats_student_t_1sample_test(); result='Done';"
        ResultArray = fa.callFunction("APY0", Array(Code))
        result = ResultArray(0)(0)
    End Sub 



The second example, with ``SVG Output`` in "Category" and ``ShowPolygon`` in "Subroutine", will write a SVG file into the ``XlCalcNetIDE\OutputMonitor`` folder in the AppData\Local folder. With the ``Output Monitor`` application running (see above), click ``OK``. The SVG file will then immediately appear in the ``Output Monitor``. 


The corresponding code in the module ``MpFunlabLocal`` -> ``BasicAndDialogs`` is shown below:

.. code-block:: visualbasic


    Sub ShowPolygon()
        REM Graphics is shown in output monitor
        fa = createUnoService("com.sun.star.sheet.FunctionAccess")  
        Code = "from A01_ExamplesPython.B18_FunctionsAndCurvesPlots.C02_BasicCurves import D01_RegularConvexPolygon;"
        Code = Code + "D01_RegularConvexPolygon.RegularConvexPolygon(OutputMode='svg'); result='Done';"
        ResultArray = fa.callFunction("APY0", Array(Code))
        result = ResultArray(0)(0)
    End Sub 





Exporting and uninstalling
---------------------------------------------------------------------------------------------

Exporting changes in MpfunlabLocal to MpfunlabLocal.oxt
...............................................................

Changes which are made in the MpfunlabLocal library are stored in the script folders of LibreOffice and are not automatically saved to MpfunlabLocal.oxt. However, they can be exported to MpfunlabLocal.oxt, so that they are available for installation (re-installation at the current LibreOffice installation or new installation for another LibreOffice installation). 

To export the MpfunlabLocal library to MpfunlabLocal.oxt, follow these steps: 
open the Macro Editor from the main menu of LibreOffice Calc: ``Tools`` -> ``Macros`` -> ``Edit Macros...``. In the main menu of the Macro Editor, select ``Dialogs`` -> ``Organize Dialogs``. In the dialog "Basic Macro Organizer" select the tab "Libraries". "Location" should be set to "My Macros & Dialogs" and "Library: Name" should be "MpFunlabLocal". Click on ``Export...``. In the following dialog box select "Export as extension", and click on ``OK``. In the dialog "Export library as extension" navigate to the documents folder, and within this folder to ``DataXlCalcNet\SpreadsheetAddins\LibreOfficeCalc``. Select ``MpfunlabLocal.oxt`` and click on ``Save``. Confirm to replace. In the dialog "Basic Macro Organizer" click on ``Close``. Then close the Macro Editor.





Uninstalling MpfunlabLocal.oxt and Mpfunlab.oxt
...................................................

To uninstall these two extensions properly, following the correct order is important. 

First start LibreOffice with administrator privileges: Right-click on the desktop icon of LibreOffice and select ``Run as administrator``. In the following dialog, confirm that you want to proceed. In the LibreOffice desktop, open a ``Calc Spreadsheet``. Open the Extension dialog from the main menu:``Tools`` -> ``Extensions...``. In the Extension dialog select ``MpFunlab.oxt``, click the ``Remove`` button and click on ``OK`` in the confirmation dialog. Then click on the ``Close`` button in the Extension dialog. In the dialog ``Restart LibreOffice``, click on ``Restart Now``. This will close LibreOffice Calc and will open the general LibreOffice desktop. Exit LibreOffice.

Now uninstall ``MpfunlabLocal.oxt`` within a normally launched LibreOffice Calc (i.e. without administrator privileges): Open the Extension dialog from the main menu: ``Tools`` -> ``Extensions...``. In the Extension dialog select ``MpfunlabLocal.oxt``, click the ``Remove`` button and click on ``OK`` in the confirmation dialog. Then click on the ``Close`` button in the Extension dialog. In the dialog ``Restart LibreOffice``, click on ``Restart Now``. This will close LibreOffice Calc and will open the general LibreOffice desktop. Exit LibreOffice.





