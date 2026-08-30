

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />






|newpage|



Contours
==============================================================




Open Contourplot
------------------------------------------------------------------------------------------


The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_ContourOpen.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C07_Contours/D01_ContourOpen.py>`__.



|ContourOpen|

.. |ContourOpen| image:: ../_static/ParametricCurves/Contourplots/ContourOpen.*











|newpage|

Filled Contourplot
------------------------------------------------------------------------------------------


The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02_ContourFilled.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C07_Contours/D02_ContourFilled.py>`__.



|ContourFilled|

.. |ContourFilled| image:: ../_static/ParametricCurves/Contourplots/ContourFilled.*











|newpage|


Electric dipole: field lines and open contours
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03_08_FieldLinesContours.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C07_Contours/D03_08_FieldLinesContours.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            ContourFilled_ = False
            Model_ = 1  # 1, 2, 3, 4
            FieldLinesContours(ContourFilled=ContourFilled_, Model=Model_)


`\quad` |FieldLinesDipole2ContoursOpen|

.. |FieldLinesDipole2ContoursOpen| image:: ../_static/ParametricCurves/Contourplots/FieldLinesDipole2ContoursOpen.jpeg
   :width: 80%












|newpage|


Electric quadrupole: field lines and open contours
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03_08_FieldLinesContours.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C07_Contours/D03_08_FieldLinesContours.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            ContourFilled_ = False
            Model_ = 2  # 1, 2, 3, 4
            FieldLinesContours(ContourFilled=ContourFilled_, Model=Model_)



`\quad` |FieldLinesQuadContoursOpen|

.. |FieldLinesQuadContoursOpen| image:: ../_static/ParametricCurves/Contourplots/FieldLinesQuadContoursOpen.jpeg
   :width: 80%







|newpage|


Electric dipoles: field lines and filled contours
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03_08_FieldLinesContours.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C07_Contours/D03_08_FieldLinesContours.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            ContourFilled_ = True
            Model_ = 1  # 1, 2, 3, 4
            FieldLinesContours(ContourFilled=ContourFilled_, Model=Model_)



`\quad` |FieldLinesDipole2ContoursClosed|

.. |FieldLinesDipole2ContoursClosed| image:: ../_static/ParametricCurves/Contourplots/FieldLinesDipole2ContoursClosed.jpeg
   :width: 80%








|newpage|


Electric quadrupole: field lines and filled contours
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03_08_FieldLinesContours.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C07_Contours/D03_08_FieldLinesContours.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            ContourFilled_ = True
            Model_ = 2  # 1, 2, 3, 4
            FieldLinesContours(ContourFilled=ContourFilled_, Model=Model_)


`\quad` |FieldLinesQuadContoursClosed|

.. |FieldLinesQuadContoursClosed| image:: ../_static/ParametricCurves/Contourplots/FieldLinesQuadContoursClosed.jpeg
   :width: 80%






|newpage|


Orthogonal electric dipoles: field lines and filled contours
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03_08_FieldLinesContours.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C07_Contours/D03_08_FieldLinesContours.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            ContourFilled_ = True
            Model_ = 3  # 1, 2, 3, 4
            FieldLinesContours(ContourFilled=ContourFilled_, Model=Model_)


`\quad` |FieldLines3ContoursClosed|

.. |FieldLines3ContoursClosed| image:: ../_static/ParametricCurves/Contourplots/FieldLines3ContoursClosed.jpeg
   :width: 80%






|newpage|


Electric field lines around a point charge with grounded sphere
------------------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03_08_FieldLinesContours.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C07_Contours/D03_08_FieldLinesContours.py>`__.


To produce the figure as shown below, the try-block at the end of the file should look like this:

.. code-block:: python

    try:
        if __name__ == '__main__':
            ContourFilled_ = True
            Model_ = 4  # 1, 2, 3, 4
            FieldLinesContours(ContourFilled=ContourFilled_, Model=Model_)


`\quad` |FieldLinesConductingSphere|

.. |FieldLinesConductingSphere| image:: ../_static/ParametricCurves/Contourplots/FieldLinesConductingSphere.jpeg
   :width: 80%




