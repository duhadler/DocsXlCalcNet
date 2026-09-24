

.. |vspace| raw:: html

   <br />



.. only:: html

    .. figure:: _static/title_mpaddin.svg
        :align: center
        :figclass: align-center

    .. image:: _static/KuenGreen.png
        :align: center
        :width: 10%

    |vspace|


    Overview
    ---------------------------------------------------------------------------

    Welcome to the documentation of **XlCalcNet** (Microsoft E\ **x**\ ce\ **l** and LibreOffice **Calc** addin, based on Python\ **Net**\ ), a python library with focus on numerical calculations in multiple precision and data visualisation, which can also be used within MS Excel and LibreOffice Calc spreadsheet formulas. This edition of the documentation describes release |release|. The documentation can also be downloaded in PDF format from `here <https://github.com/duhadler/DocsXlCalcNet/raw/master/pdf/xlcalcnet.pdf>`__.

    XlCalcNet is free software released under the Mozilla Public License `2.0` (see  :ref:`License <rst_MPL_2.0_License>`). The git repository is https://github.com/duhadler/XlCalcNet.


    XlCalcNet can be installed as a python package from `PyPI <https://pypi.org/project/xlcalcnet/>`__. More detailed information regarding the installation and general usage of XlCalcNet can be found :ref:`here <rst_setting_up_XlCalcNet>`.


    Since one of the main goals of XlCalcNet is to enable the use of functions written in Python or C# within spreadsheet formulas, it is assumed that Microsoft Excel (2010 or later, 64 bit) and/or LibreOffice (version 7.0 or later, 64 bit) is installed on the users system, running under Windows (7.1 or later, 64 bit).




    Use with Microsoft Excel
    ---------------------------------------------------------------------------

    Once MS Excel has been prepared for using XlCalcNet (see :ref:`here <rst_setting_up_MSExcel>` for details), one can run small Python scripts in spreadsheet formulas, using parameters which are passed from other spreadsheet cells. If the example workbook "Simple.xlsx" has been loaded, the following dialog box will appear when the user clicks on the "Insert Function" button in Excel's formula bar:


    .. image:: _static/XL_FunctionArguments.png
        :align: center
        :width: 60%

    |vspace|

    XlCalcNet can also be used for procedures. To access the relevant dialog, right-click anywhere on the spreadsheet. The following context menu will appear:

    .. image:: _static/XL_ContextMenu.png
        :align: center
        :width: 40%

    |vspace|


    Click on Navigator for XlCalcNet. The following dialog box will appear:


    .. image:: _static/XL_NavigatorXlCalcNet.png
        :align: center
        :width: 60%

    |vspace|


    This can be used to call external procedures, which are not used in spreadsheet formulas. The procedures can be used to generate plots, for example. The generated plots can be saved as bitmap files or as interactive 3D plots in a separate window.

    |vspace|



    Use with LibreOffice Calc
    ---------------------------------------------------------------------------

    Once LibreOffice Calc has been prepared for using XlCalcNet (see :ref:`here <rst_setting_up_LOCalc>` for details), one can run small Python scripts in spreadsheet formulas, using parameters which are passed from other spreadsheet cells. If the example workbook "Simple.xlsx" has been loaded, the following dialog box will appear when the user clicks on the "Insert Function" button in LibreOffice Calc's formula bar:


    .. image:: _static/LO_FunctionArguments.png
        :align: center
        :width: 80%

    |vspace|

    XlCalcNet can also be used for procedures. To access the relevant dialog, click on the XlCalcNet logo (in orange) on the main menu bar. The following context menu will appear:

    .. image:: _static/LO_MainMenu.png
        :align: center
        :width: 40%

    |vspace|


    Click on Navigator for XlCalcNet. The following dialog box will appear:


    .. image:: _static/LO_NavigatorXlCalcNet.png
        :align: center
        :width: 60%

    |vspace|


    This can be used to call external procedures, which are not used in spreadsheet formulas. The procedures can be used to generate plots, for example. The generated plots can be saved as bitmap files or as interactive 3D plots in a separate window.

    |vspace|




    Navigating the manual
    ---------------------------------------------------------------------------
    This manual uses the `sphinx book theme <https://sphinx-book-theme.readthedocs.io/en/stable/>`__, which has a number of features that make it easy to navigate. 

    Searching
    ............
    Try the "Search " box in the upper left corner. If you can't see such a box, move the mouse cursor over the menu tree, and use the mouse wheel to move up the menu tree. As an example, type "gamma" in the search box. This will return not  only the entry for the gamma function, but also a list of all occurrences of the word "gamma" in  this documentation.


    Sidebars
    ...........
    The  `sphinx book theme <https://sphinx-book-theme.readthedocs.io/en/stable/>`__ is used, which has a primary (left) and secondary (right) sidebar. The secondary sidebar is invisible when the browser window is not wide enough. So if something seems to be missing, try to make the browser window wider.





.. only:: latex

    .. toctree ::
        :maxdepth: 5

        000_Preface/01_preface.rst





    ######################################################
    Getting started
    ######################################################



    .. toctree ::
        :caption: Getting started
        :maxdepth: 5

        B01_GeneralUsage/index.rst
        B02_BasicFloatingPointFunctions/index.rst

        B03_ElementaryScalarFunctions/index.rst

        B04_StatisticalDistributions/index.rst

        B05_NumericalCalculus/index.rst

        B06_EigenDenseAndSparse/index.rst
        B07_NumpyMultiprecision/index.rst




    ######################################################
    Special Functions
    ######################################################


    .. toctree ::
        :caption: Special Functions
        :maxdepth: 5


        B08_EllipticFunctions/index.rst
        B09_LerchPhi/index.rst
        B10_Hypergeometric0F1/index.rst
        B11_Hypergeometric1F1/index.rst
        B12_HypergeometricpFq/index.rst




    ######################################################
    Supporting Functions
    ######################################################


    .. toctree ::
        :caption: Supporting Functions
        :maxdepth: 5


        B13_AlgebraWithRandomVariables/index.rst
        B14_SeriesAndIntegrals/index.rst
        B15_PmfVectors/index.rst
        B16_FastApproximations/index.rst




    ######################################################
    Gallery of Plots
    ######################################################



    .. toctree ::
        :caption: Gallery of Plots
        :maxdepth: 5


        B17_VisualisationOfDatasets/index.rst
        B18_FunctionsAndCurvesPlots/index.rst
        B19_Bitmaps/index.rst
        B20_Matplotlib3D/index.rst
        B21_Plotly/index.rst





    ######################################################
    Interactive 3D Wpf Plots
    ######################################################



    .. toctree ::
        :caption: Interactive 3D Wpf Plots
        :maxdepth: 5

        B22_WpfAltitudeSurfacesRealAndComplex/index.rst
        B23_WpfParametricSurfaces/index.rst
        B24_WpfPathSurfaces/index.rst
        B25_WpfBuiltInSurfaces/index.rst





    ######################################################
    Additional functions in double precision
    ######################################################



    .. toctree ::
        :caption: Additional functions in double precision
        :maxdepth: 5

        B26_MoreElementary/index.rst
        B27_MoreElliptic/index.rst
        B28_MoreLerchPhi/index.rst
        B29_More0F1/index.rst
        B30_More1F1AndOther/index.rst
        B31_MoreComplex/index.rst



    ######################################################
    User library: numerical
    ######################################################



    .. toctree ::
        :caption: User library: numerical
        :maxdepth: 5

        C01_UserGeneral/index.rst
        C02_UserDistributions/index.rst
        C03_UserInferentialStatistics/index.rst


    ######################################################
    User library: graphics
    ######################################################



    .. toctree ::
        :caption: User library: graphics
        :maxdepth: 5

        C05_UserDistributionPlots/index.rst
        C06_UserSpecialCplxPlots/index.rst



    ######################################################
    Back matter
    ######################################################


    .. toctree ::
        :caption: Back matter
        :maxdepth: 5

        99BackMatter/index.rst


