

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />







|newpage|


Coil springs
==============================================================


See also: https://en.wikipedia.org/wiki/Coil_spring

See also: https://en.wikipedia.org/wiki/Spring_(device)


Spring 2
--------------------------------------------



An example in C\#

.. code-block:: csharp

    var x = ((-3.75 * t + 100) * Math.Sin(t * Math.PI)) / 100;
    var z = (20 * t) / 100;
    var y = ((-3.75 * t + 100) * Math.Cos(t * Math.PI)) / 100;




|D01a_Path_Spiral2.3D| `\quad` |D01b_Path_Spiral2.3D| `\quad` |D01c_Path_Spiral2.3D|



.. |D01a_Path_Spiral2.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D01a_Path_Spiral2.3D.jpg
   :width: 30 %


.. |D01b_Path_Spiral2.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D01b_Path_Spiral2.3D.jpg
   :width: 30 %


.. |D01c_Path_Spiral2.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D01c_Path_Spiral2.3D.jpg
   :width: 30 %



|newpage|

Spring 6
---------------------------------------------


An example in C\#

.. code-block:: csharp

    var x = (Math.Sqrt(10000 - 100 * t * t) * Math.Sin(t * Math.PI)) / 100;
    var z = (20 * t) / 100;
    var y = (Math.Sqrt(10000 - 100 * t * t) * Math.Cos(t * Math.PI)) / 100;





|D02a_Path_Spiral6.3D| `\quad` |D02b_Path_Spiral6.3D|



.. |D02a_Path_Spiral6.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D02a_Path_Spiral6.3D.jpg
   :width: 30 %


.. |D02b_Path_Spiral6.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D02b_Path_Spiral6.3D.jpg
   :width: 30 %






|newpage|

Spring 7a
----------------------------------------


An example in C\#

.. code-block:: csharp

    var x = (Math.Sqrt(10000 - 100 * t * t) * Math.Sin(t * Math.PI)) / 100;
    var z = 209.22 * (Math.Tanh(0.1896 * t)) / 100;
    var y = (Math.Sqrt(10000 - 100 * t * t) * Math.Cos(t * Math.PI)) / 100;




|D03a_Path_Spiral7a.3D| `\quad` |D03b_Path_Spiral7a.3D|



.. |D03a_Path_Spiral7a.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D03a_Path_Spiral7a.3D.jpg
   :width: 30 %


.. |D03b_Path_Spiral7a.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D03b_Path_Spiral7a.3D.jpg
   :width: 30 %








|newpage|

Spring 7b
------------------------------------------


An example in C\#

.. code-block:: csharp

    var x = (200 * Math.Cos(0.05 * t * Math.PI) * Math.Sin(t * Math.PI)) / 100;
    var z = 209.22 * (Math.Tanh(0.1896 * t)) / 100;
    var y = (200 * Math.Cos(0.05 * t * Math.PI) * Math.Cos(t * Math.PI)) / 100;



|D04a_Path_Spiral7b.3D| `\quad` |D04b_Path_Spiral7b.3D|



.. |D04a_Path_Spiral7b.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D04a_Path_Spiral7b.3D.jpg
   :width: 30 %


.. |D04b_Path_Spiral7b.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D04b_Path_Spiral7b.3D.jpg
   :width: 30 %










|newpage|

Spring 7c
--------------------------------------------


An example in C\#

.. code-block:: csharp

    double e = Math.Exp(-(0.2 * t) * (0.2 * t));
    var x = (200 * e * Math.Sin(t * Math.PI)) / 100;
    var z = 209.22 * (Math.Tanh(0.1896 * t)) / 100;
    var y = (200 * e * Math.Cos(t * Math.PI)) / 100;




|D05a_Path_Spiral7c.3D| `\quad` |D05b_Path_Spiral7c.3D|



.. |D05a_Path_Spiral7c.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D05a_Path_Spiral7c.3D.jpg
   :width: 30 %


.. |D05b_Path_Spiral7c.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D05b_Path_Spiral7c.3D.jpg
   :width: 30 %








|newpage|

Spring 7d
------------------------------------------


An example in C\#

.. code-block:: csharp

    double e = Math.Exp(-(0.2 * t) * (0.2 * t));
    var x = ((200 - 140 * e) * Math.Sin(t * Math.PI)) / 100;
    var z = 207.46 * (Math.Tanh(0.2 * t)) / 100;
    var y = ((200 - 140 * e) * Math.Cos(t * Math.PI)) / 100;




|D06a_Path_Spiral7d.3D| `\quad` |D06b_Path_Spiral7d.3D|



.. |D06a_Path_Spiral7d.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D06a_Path_Spiral7d.3D.jpg
   :width: 30 %


.. |D06b_Path_Spiral7d.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D06b_Path_Spiral7d.3D.jpg
   :width: 30 %









|newpage|

Spring 8
-------------------------------------------


An example in C\#

.. code-block:: csharp

    var x = (200 * Math.Cos(t) * Math.Cos(Math.Atan(0.15 * t))) / 100;
    var z = -200 * Math.Sin(Math.Atan(0.15 * t)) / 100;
    var y = (200 * Math.Sin(t) * Math.Cos(Math.Atan(0.15 * t))) / 100;




|D07a_Path_Spiral8.3D| `\quad` |D07b_Path_Spiral8.3D| `\quad` |D07c_Path_Spiral8.3D|



.. |D07a_Path_Spiral8.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D07a_Path_Spiral8.3D.jpg
   :width: 30 %


.. |D07b_Path_Spiral8.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D07b_Path_Spiral8.3D.jpg
   :width: 30 %


.. |D07c_Path_Spiral8.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D07c_Path_Spiral8.3D.jpg
   :width: 30 %


   



|newpage|

Spring 9
-------------------------------------------


An example in C\#

.. code-block:: csharp

    double R = 100.0;
    double G = 160.0;
    double D = 15.0;
    double N = 10.0;
    var x = (Math.Cos(t * Math.PI) * R + Math.Cos(t * Math.PI) * D * Math.Cos(N * t * Math.PI)) / 100;
    var y = (D * Math.Sin(N * t * Math.PI) + 0.5 * G * t) / 100;
    var z = (Math.Sin(t * Math.PI) * R + Math.Sin(t * Math.PI) * D * Math.Cos(N * t * Math.PI)) / 100;




|D08a_Path_Spiral9.3D| `\quad` |D08b_Path_Spiral9.3D| `\quad` |D08c_Path_Spiral9.3D|



.. |D08a_Path_Spiral9.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D08a_Path_Spiral9.3D.jpg
   :width: 30 %


.. |D08b_Path_Spiral9.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D08b_Path_Spiral9.3D.jpg
   :width: 30 %


.. |D08c_Path_Spiral9.3D| image:: ../_static/B24_WpfPathSurfaces/C05_CoilSprings/D08c_Path_Spiral9.3D.jpg
   :width: 30 %











