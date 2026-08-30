

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />






|newpage|



Complex functions rendered as contours
==============================================================




Complex square function
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_8_ContourComplex.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C08_Complex/D01_8_ContourComplex.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            Contour2dComplex(func=lambda z:z*z, wclip=20.0, 
                showlevels=True, Title=r'$f(z)=z^2$')




|CplxSquareContour|

.. |CplxSquareContour| image:: ../_static/FuncPlots2D/Complex/f(z)_=_z^2.*






|newpage|

Complex sqrt function
------------------------------------------------------------------------------------------


The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_8_ContourComplex.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C08_Complex/D01_8_ContourComplex.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            Contour2dComplex(func=np.sqrt, wclip=20.0, Title='f(z)=sqrt(z)')



|CplxSqrtContour|

.. |CplxSqrtContour| image:: ../_static/FuncPlots2D/Complex/f(z)_=_sqrt(z).*








|newpage|

Complex exp function
------------------------------------------------------------------------------------------


The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_8_ContourComplex.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C08_Complex/D01_8_ContourComplex.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            Contour2dComplex(func=np.exp, wclip=20.0, Title='f(z)=exp(z)')



|CplxExpContour|

.. |CplxExpContour| image:: ../_static/FuncPlots2D/Complex/f(z)_=_exp(z).*








|newpage|

Complex log function
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_8_ContourComplex.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C08_Complex/D01_8_ContourComplex.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            Contour2dComplex(func=np.log, wclip=2.5, Title='f(z)=log(z)')


|CplxLogContour|

.. |CplxLogContour| image:: ../_static/FuncPlots2D/Complex/f(z)_=_log(z).*









|newpage|

Complex sine function
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_8_ContourComplex.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C08_Complex/D01_8_ContourComplex.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            Contour2dComplex(func=np.sin, wclip=20.0, Title='f(z)=sin(z)')


|CplxSinContour|

.. |CplxSinContour| image:: ../_static/FuncPlots2D/Complex/f(z)_=_sin(z).*









|newpage|

Complex asin function
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_8_ContourComplex.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C08_Complex/D01_8_ContourComplex.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            Contour2dComplex(func=np.asin, wclip=20.0, Title='f(z)=asin(z)')



|CplxAsinContour|

.. |CplxAsinContour| image:: ../_static/FuncPlots2D/Complex/f(z)_=_asin(z).*









|newpage|

Complex tan function
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_8_ContourComplex.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C08_Complex/D01_8_ContourComplex.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            Contour2dComplex(func=np.tan, wclip=2.0, Title='f(z)=tan(z)')




|CplxTanContour|

.. |CplxTanContour| image:: ../_static/FuncPlots2D/Complex/f(z)_=_tan(z).*








|newpage|

Complex atan function
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_8_ContourComplex.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C08_Complex/D01_8_ContourComplex.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            Contour2dComplex(func=np.atan, wclip=20.0, Title='f(z)=atan(z)')




|CplxAtanContour|

.. |CplxAtanContour| image:: ../_static/FuncPlots2D/Complex/f(z)_=_atan(z).*






