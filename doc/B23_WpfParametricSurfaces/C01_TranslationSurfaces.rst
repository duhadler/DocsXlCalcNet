

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />




Surfaces of translation
=================================================================================

See also: https://en.wikipedia.org/wiki/Translation_surface_(differential_geometry)

See also:http://www.3d-meier.de/tut3/Seite0.html

See also: https://en.wikipedia.org/wiki/Implicit_surface



Fermat spiral as generator
------------------------------------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01a_FermatSpiral.3D.xml (D01a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D01a_FermatSpiral.3D.xml>`__.



The example below uses the following code in C\#

.. code-block:: csharp

    var h = 2; 
    var x = 4*Math.Sqrt(u) * Math.Cos(u);
    var y = 4*Math.Sqrt(u) * Math.Sin(u);
    var z = h * v;


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.


|D01a_FermatSpiral.3D| `\quad` |D01b_FermatSpiral.3D| `\quad` |D01c_FermatSpiral.3D|



.. |D01a_FermatSpiral.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D01a_FermatSpiral.3D.jpg
   :width: 30 %


.. |D01b_FermatSpiral.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D01b_FermatSpiral.3D.jpg
   :width: 30 %


.. |D01c_FermatSpiral.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D01c_FermatSpiral.3D.jpg
   :width: 30 %






|newpage|

Lemniscate as generator
-----------------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D02a_Lemniscate.3D.xml (D02a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D02a_Lemniscate.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    double a = 0.3;
    double c = 1.0;
    double r = c * 0.5;
    var x = r * (Math.Cos(u) / (1 + Math.Sin(u) * Math.Sin(u)));
    var y = r * (Math.Sin(u) * Math.Cos(u) / (1 + Math.Sin(u) * Math.Sin(u)));
    var z = a * v;



// see also: http://www.3d-meier.de/tut3/Seite152.html


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



|D02a_Lemniscate.3D| `\quad` |D02b_Lemniscate.3D| `\quad` |D02c_Lemniscate.3D|



.. |D02a_Lemniscate.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D02a_Lemniscate.3D.jpg
   :width: 30 %


.. |D02b_Lemniscate.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D02b_Lemniscate.3D.jpg
   :width: 30 %


.. |D02c_Lemniscate.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D02c_Lemniscate.3D.jpg
   :width: 30 %







|newpage|


Tanh spiral as generator
-----------------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D03a_TanhSpiral.3D.xml (D03a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D03a_TanhSpiral.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    var h = 0.5; 
    double c = 0.2;
    double a = 6.0;
    var x = c * (Math.Sinh(2 * u) / (Math.Cos(2 * a * u) + Math.Cosh(2 * u)));
    var y = c * (Math.Sin(2 * a * u) / (Math.Cos(2 * a * u) + Math.Cosh(2 * u)));
    var z = h * v;



// see http://www.3d-meier.de/tut3/Seite187.html
// see Krivoshapko, p. 498


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.




See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



|D03a_TanhSpiral.3D| `\quad` |D03b_TanhSpiral.3D| `\quad` |D03c_TanhSpiral.3D|



.. |D03a_TanhSpiral.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D03a_TanhSpiral.3D.jpg
   :width: 30 %


.. |D03b_TanhSpiral.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D03b_TanhSpiral.3D.jpg
   :width: 30 %


.. |D03c_TanhSpiral.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D03c_TanhSpiral.3D.jpg
   :width: 30 %







|newpage|


Rose curve as generator
-----------------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D04a_RoseCurve.3D.xml (D04a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D04a_RoseCurve.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    double a = 0.6;
    double h = 2.0;
    double n = 3.0;
    double ca = Math.Cos(a);

    var x = (h * Math.Abs(Math.Cos(n * u)) * ca) * Math.Cos(u);
    var y = (h * Math.Abs(Math.Cos(n * u)) * ca) * Math.Sin(u);
    var z = a * v;




// see http://www.3d-meier.de/tut3/Seite189.html


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.




|D04a_RoseCurve.3D| `\quad` |D04b_RoseCurve.3D| `\quad` |D04c_RoseCurve.3D|



.. |D04a_RoseCurve.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D04a_RoseCurve.3D.jpg
   :width: 30 %


.. |D04b_RoseCurve.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D04b_RoseCurve.3D.jpg
   :width: 30 %


.. |D04c_RoseCurve.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D04c_RoseCurve.3D.jpg
   :width: 30 %









|newpage|


Hypocycloid as generator
-----------------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D05a_Hypocycloid_55.3D.xml (D05a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D05a_Hypocycloid_55.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    double a = 3.7; 
    double r = 1.5;
    double k = 5.5;
    var x = r * (k - 1) * Math.Cos(u) + r * Math.Cos((k - 1) * u);
    var y = r * (k - 1) * Math.Sin(u) - r * Math.Sin((k - 1) * u);
    var z = a * v;



// see http://www.3d-meier.de/tut3/Seite189.html


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.





|D05a_Hypocycloid_55.3D| `\quad` |D05b_Hypocycloid_55.3D| `\quad` |D05c_Hypocycloid_55.3D|



.. |D05a_Hypocycloid_55.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D05a_Hypocycloid_55.3D.jpg
   :width: 30 %


.. |D05b_Hypocycloid_55.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D05b_Hypocycloid_55.3D.jpg
   :width: 30 %


.. |D05c_Hypocycloid_55.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D05c_Hypocycloid_55.3D.jpg
   :width: 30 %









|newpage|


Epicycloid as generator
-----------------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D06a_Epicycloid_55.3D.xml (D06a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D06a_Epicycloid_55.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    double a = 2.0; 
    double r = 1.0;
    double k = 5.5;
    var h = 1.5;
    var x = r * (k + 1) * Math.Cos(u) - h * r * Math.Cos((k + 1) * u);
    var y = r * (k + 1) * Math.Sin(u) - h * r * Math.Sin((k + 1) * u);
    var z = a * v;


// see http://www.3d-meier.de/tut3/Seite189.html


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.





|D06a_Epicycloid_55.3D| `\quad` |D06b_Epicycloid_55.3D| `\quad` |D06c_Epicycloid_55.3D|



.. |D06a_Epicycloid_55.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D06a_Epicycloid_55.3D.jpg
   :width: 30 %


.. |D06b_Epicycloid_55.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D06b_Epicycloid_55.3D.jpg
   :width: 30 %


.. |D06c_Epicycloid_55.3D| image:: ../_static/B23_WpfParametricSurfaces/C01_TranslationSurfaces/D06c_Epicycloid_55.3D.jpg
   :width: 30 %





