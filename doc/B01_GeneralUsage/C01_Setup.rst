


.. |newpage| raw:: latex

   \newpage




|newpage|

Setting up XlCalcNet
=========================


Downloading and installing the "right" version of CPython
-------------------------------------------------------------

Describe the dependency on Python.Net.

Explain The 3 folder concept: user, application local data, python installation


The data which are directly maniplated by the user are located in:

The data which generated as a result of running a python script or C\# program are written to: 

The data which contain the installation are located in:


Describe the choices for downloading python

Describe how to install python as a "free-standing" version without need to uninstall.

Describe choices for locating this version of python

Describe copying the batch files into 





|newpage|

Installing and using Python.NET: Calling C\# from Python
---------------------------------------------------------

Python.NET is a package that gives Python programmers nearly seamless integration with the .NET Common Language Runtime (CLR) and provides a powerful application scripting tool for .NET developers. It allows Python code to interact with the CLR, and may also be used to embed Python into a .NET application.

See https://github.com/pythonnet/pythonnet



.NET Framework is part of the Microsoft Windows operating system since Windows Vista; .NET Framework 4.x can be installed since Windows XP. Recent versions of Windows (Windows 7 - Windows 11), which have been kept fully maintained, have .NET Framework 4.8 installed, which is the latest version of .NET Framework and will continue to be distributed with future releases of Windows. As long as it is installed on a supported version of Windows, .NET Framework 4.8 will continue to also be supported (see https://dotnet.microsoft.com/en-us/platform/support/policy/dotnet-framework). 


As part of the  .NET Framework 4.x runtime, 3 different compilers are provided: csc.exe (C\#), vbc.exe (Visual Basic), and jsc.exe (JScript). 

The 32 bit targeting versions are located in ``C:\Windows\Microsoft.NET\Framework\v4.0.30319`` and those for 64 bit in ``C:\Windows\Microsoft.NET\Framework64\v4.0.30319``.

It is important to note that these compilers are not part of Visual Studio but part of Windows; they are, in a way, the closest to a compiler as part of the operating system that Windows has ever come up with. On the other hand, these compilers have been tugged away with the rest of the .NET Framework 4.x runtime; in that sense, they are "hidden" compilers.

In the following, we will ignore the Visual Basic and JScript compilers, but focus only on C\#. The C\# compiler supports only language versions up to C\# 5. Luckily, this still provides us with all language features which we need for our purposes.

In terms of usability, the .NET Framework 4.x runtime does not include an IDE; we therefore include a tiny IDE as described below.





|newpage|

Installing the DataXlCalcNet folder
--------------------------------------------------------

Describe how to download and unpack the core repositories from Github


Emphasize the need to use Microsoft defender for the unzipped repositories.



Describe the copying and exploring the DataXlCalcNet folder

Describe the copying and exploring the DataXlCalcNet folder




|newpage|

Installing XlCalcNet
--------------------------------------------------------

Describe how to download and unpack the core repositories from Github


Emphasize the need to use Microsoft defender for the unzipped repositories.



Describe the copying and exploring the DataXlCalcNet folder

Describe the copying and exploring the DataXlCalcNet folder




|newpage|

Installing XlCalcNet2 (optional)
--------------------------------------------------------

Describe how to download and unpack the core repositories from Github


Emphasize the need to use Microsoft defender for the unzipped repositories.


The data which are directly maniplated by the user are located in:

The data which generated as a result of running a python script or C\# program are written to: 

The data which contain the installation are located in:






|newpage|

Installing and using the Tiny IDE as a Python application
----------------------------------------------------------------

Editing and compiling can be done with "Tiny C\#/Python IDE":



.. image:: ../_static/TinyEditor.png
   :width: 50 %
   :align: center


Follow the steps to make the Tiny IDE available:

* In the Python installation folder, rightclick on ``pythonw.exe``.

* Select ``Verknüpfung erstellen`` -> Result: ``pythonw.exe-Verknüpfung``.

* Rightclick on ``pythonw.exe-Verknüpfung``; Select Properties.


* In the dialogue Properties, select "Target", and type:``C:\Python313\pythonw.exe C:\Python313\Lib\site-packages\xlcalcnet\ShowEditor.py``. Then save.

* Rename ``pythonw.exe-Verknüpfung`` to ``TinyIDE_Python313``

* Doubleclick on ``TinyIDE_Python313``

* In the task-bar, rightclick on the appearing symbol, and select "An Taskleiste anheften"




|newpage|

Installing and using of the MS Excel XlNet addin: first steps
--------------------------------------------------------------------------------


!!! Describe the need for starting  the socket server first !!!

When starting the socket server for the first time to allow acces of Pyton to networks. Confirm.



Describe the installation of the MS Excel addin.




MS Excel: TestCPython.xlsx



.. image:: ../_static/FunctionArguments.png
    :width: 50 %
    :align: center


MS Excel: TestCPython.xlsx



.. image:: ../_static/ContextMenu.png
    :width: 30 %
    :align: center


MS Excel: TestCPython.xlsx


.. image:: ../_static/NavigatorXlCalcNet.png
    :width: 50 %
    :align: center


MS Excel: TestCPython.xlsx





|newpage|

Reasons for using multiprecision arithmetic
---------------------------------------------

An introduction to the problems of rounding errors and catastrophic cancellation can be found in :cite:t:`Goldberg1991`. Excellent reference texts are :cite:t:`Higham2002` and :cite:t:`Higham2009`.

In the following sections we will give a few examples of how the use of double precision without special precaution can give wrong results.






**Example: Sums**

Sums are often calculated exactly if all summands have an exact representation. If this is not the case, results can be unpredictable. In MS Excel, the formula

``=SUM(10000000000,-16000000000,6000000000)``

will give the correct result `0`, but the analogous formula

``=SUM(1E+40,-1.6E+40,6E+39)``

returns `1.20893E+24` instead of the correct result `0`.


**Example: Standard Deviation**

Like sums, variances and standard deviations are often calculated exactly if all arguments have an exact representation. If this is not the case, results can again be unpredictable. In MS Excel, the formula

``=VAR(1E+30,1E+30,1E+30)``

returns `2.97106E+28` instead of the correct result `0`, which should be the obvious results since all arguments are the same.


**Example: Overflow and underflow**

In many situations where the final result is representable in double precision, some of the interim results cause overflow or underflow. A popular example is the function `f(x,y) = \sqrt{x^2+y^2}`. With `x=3 \cdot 10^{300}` and `y=4 \cdot 10^{300}` the result `f(x,y) = 5 \cdot 10^{300}` is representable in double precision, but the (naive) calculation will overflow.



**Example: Polynomials**

Consider the following example from :cite:t:`Cuyt2001`: 

For `a=77617` and `b=33096`, calculate

.. math::     Y = 333.75 b^6 + a^2  (11 a^2  b^2 - b^6 - 121 b^4 - 2) + 5.5  b^8 + \frac{a}{2b} 

The correct result is `Y = -54767 / 66192 = -8.27396\ldots \cdot 10^{-1}`




**Example: Trigonometric Functions**

Trigonometric functions are sensitive to small perturbations. 

In double precision and binary floating point arithmetic, the tangent of `x = 1.57079632679489` is calculated as `\tan(x) = 1.48752 \cdot 10^{14}`, whereas the correct result is `\tan(x) = 1.51075 \cdot 10^{14}`. This amounts to an absolute error of `2.32287  \cdot 10^{12}` and a relative error of `1.54\%`.

There are also limits on the range of arguments, e.g. `\sin(10^{8})` returns the value  `-9.31639 \cdot 10^{-1}`   (with an relative error of `-6.22776 \cdot 10^{-13}`), whereas  `\sin(10^{9})` returns an invalid result (the exact result is  `5.45843 \cdot 10^{-1}`)





**Example: Logarithms and Exponential Functions**

Consider the following example from :cite:t:`Ghazi2010`: 

Determine 10 decimal digits of the constant

.. math::     Y = 173746a + 94228b - 78487c, \quad \text{where } 
.. math::     a = \sin(10^{22}), b = \log(17.1), c = \exp(0.42). 

The expected result is `Y = -1.341818958 \cdot 10^{-12}`.





**Example: Linear Algebra**

The following example is from :cite:t:`Hofschuster2004`:

We want to solve the (ill-conditioned) system of linear equations `Ax = b` with


.. math:: 

    A = \begin{pmatrix}
        a_{11} & a_{12} \\
        a_{21} & a_{22} 
    \end{pmatrix}  = \begin{pmatrix}
    64919121 & -159018721 \\
    41869520.5 & -102558961 
    \end{pmatrix}, b = \begin{pmatrix}
    b_{1} \\
    b_{2} 
    \end{pmatrix}
    = \begin{pmatrix}
    1 \\
    0
    \end{pmatrix} , x = \begin{pmatrix}
    x_{1} \\
    x_{2} 
    \end{pmatrix}

The correct solution is `x_1 = 205117922`, `x_2 = 83739041`.

To solve this `2 \times 2` system numerically we first use the well known formulas

.. math:: x_1 = \frac{a_{22}}{a_{11}a_{22} - a_{12}a_{21}}, \quad x_2 = \frac{-a_{21}}{a_{11}a_{22} - a_{12}a_{21}},

Calculating this directly in double precision gives the following wrong result:  

`x_1 = 102558961`, `x_2 = 41869520.5`





**Example: Eigenvalues**

The following example is from :cite:t:`Brown2010`:

The behaviour and stability of many physical systems are connected with the spectral properties of non-self-adjoint operators. However, numerical approximations of eigenvalues of non-selfadjoint operators (even matrices) may fail dramatically. For example, the non-normal 7 `\times` 7 matrix

.. math:: 

    A = \begin{pmatrix}
        289 & 2054 & 326 & 128 & 70 & 32 & 6  \\
        1152 & 30 & 1312 & 512 & 288 & 128 & 32  \\    
        -29 & -1990 & 766 & 384 & 1018 & 224 & 58  \\
        512 & 128 & 640 & 0 & 640 & 512 & 128  \\    
        1053 & 2246 & -514 & -384 & -766 & 800 & 198  \\    
        -287 & -6 & 1722 & -128 & 1978 & -30 & -2042  \\
        -2176 & -285 & -1563 & -512 & -539 & -1152 & -287     
    \end{pmatrix}

has the eigenvalues  `-2, -4, 0, 1, 1, 2, 4`. Calculations in double precision yield a set of complex eigenvalues, such as `8.57 \pm 3.73 i; 2.29 \pm 8.33 i; -5.43 \pm 6.56 i; -8.85` with imaginary parts as large as `8.33`, which are nowhere near the true eigenvalues. The reason for this is that owing to the nonnormality of the matrix, its eigenvalues are highly sensitive to perturbations, and therefore unavoidable rounding errors render the numerical eigenvalue computations unreliable.






|newpage|

Reasons for calling C\# from Python
---------------------------------------------

Speed: Give some comparative data

Access to the full .Net Framework runtime: Gui applications as examples

Availability: It is available anyway, as a component of Windows.











|newpage|

Rebuilding the .dll files of XlCalcNet and XlCalcNet2 from source code
--------------------------------------------------------------------------

The XlCalcNet and XlCalcNet2 repositories contain both precompiled .dll files and their source code.

This section descibes how to rebuild the .dll files of XlCalcNet and XlCalcNet2 from source code, either completely or only in part. The building process itself is not particularly difficult, but it requires the installation of MSYS2 (version 3.4.9.x86_64 or later: about 4 GB in size), Free Pascal (version 2.6.4 or later: about 320 MB in size), and Visual Studio Community (version 2019 or later: about 4.6 GB in size).

In the following it is assumed that the user has installed MSYS2, Free Pascal and Visual Studio Community and is comfortable using them.

MSYS2 is required to build the file ``FixedPrecGCC64K8.dll`` in the XlCalcNet ``Bin`` folder. The details of the building process are described in :ref:`FixedPrec <rst_FixedPrec>`.

MSYS2 is also required to build the file ``ArbPrecNetGCCK8.dll`` in the XlCalcNet2 ``Bin`` folder. The details of the building process are described in :ref:`ArbPrec <rst_ArbPrec>`.

Free Pascal is required to build  the file ``libwe64d.dll`` in the XlCalcNet ``Bin`` folder. The details of the building process are described in :ref:`FixedPrec <rst_FixedPrec>`.


Erverything else can be done in Visual Studio Community:

The details of the building the file ``FixedPrecNet.dll`` in the XlCalcNet ``Bin`` folder are described in :ref:`FixedPrec <rst_FixedPrec>`.

The details of the building the file ``ArbPrecNet.dll`` in the XlCalcNet2 ``Bin`` folder are described in :ref:`ArbPrec <rst_ArbPrec>`.


The details of the building the file ``ArbPrecNet.dll`` in the XlCalcNet ``Bin`` folder are described in :ref:`ClientServer <rst_ClientServer>`.


The details of the building the file ``ArbPrecNet.dll`` in the XlCalcNet ``Bin`` folder are described in :ref:`OutputMonitor <rst_OutputMonitor>`.


The details of the building the file ``ArbPrecNet.dll`` in the XlCalcNet ``Bin`` folder are described in :ref:`TinyIde <rst_TinyIde>`.


The details of the building the file ``ArbPrecNet.dll`` in the XlCalcNet ``Bin`` folder are described in :ref:`GalleryOfPlots <rst_GalleryOfPlots>`.


The details of the building the file ``ArbPrecNet.dll`` in the XlCalcNet ``Bin`` folder are described in :ref:`Wpf3D <rst_Wpf3D>`.





