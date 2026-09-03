

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />






Introduction to path surfaces
==============================================================




Borromean rings, A, B, C
---------------------------------------------------------

Some text explaining the importance of building the mesh in x-direction.


An example in C\#, for A

.. code-block:: csharp

    var r = Math.Sqrt(3) / 3;
    var x = Math.Cos(t);
    var y = Math.Sin(t) + r;
    var z = Math.Cos(3 * t) / 3;


An example in C\#, for B

.. code-block:: csharp

    var r = Math.Sqrt(3) / 3;
    var x = Math.Cos(t) + 0.5;
    var y = Math.Sin(t) - r / 2;
    var z = Math.Cos(3 * t) / 3;


An example in C\#, for C

.. code-block:: csharp

    var r = Math.Sqrt(3) / 3;
    var x = Math.Cos(t) - 0.5;
    var y = Math.Sin(t) - r / 2;
    var z = Math.Cos(3 * t) / 3;




|D01a_Path_BorromeanA.3D| `\quad` |D01b_Path_BorromeanA.3D| `\quad` |D01c_Path_BorromeanA.3D|



.. |D01a_Path_BorromeanA.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D01a_Path_BorromeanA.3D.jpg
   :width: 30 %


.. |D01b_Path_BorromeanA.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D01b_Path_BorromeanA.3D.jpg
   :width: 30 %


.. |D01c_Path_BorromeanA.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D01c_Path_BorromeanA.3D.jpg
   :width: 30 %





|newpage|



Ellipses, A, B, C
---------------------------------------------------------

Some text explaining the importance of building the mesh in x-direction.


An example in C\#, for A, B, C

.. code-block:: csharp

    var x = 2 * Math.Cos(t);
    var y = Math.Sin(t);
    var z = 0.0;

For A, the final rotations are: X=0, Y=0, Z=0.

For B, the final rotations are: X=90, Y=0, Z=90.

For C, the final rotations are: X=0, Y=90, Z=90.


|D02a_Path_Ellipses.3D| `\quad` |D02b_Path_Ellipses.3D| `\quad` |D02c_Path_Ellipses.3D|



.. |D02a_Path_Ellipses.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D02a_Path_Ellipses.3D.jpg
   :width: 30 %


.. |D02b_Path_Ellipses.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D02b_Path_Ellipses.3D.jpg
   :width: 30 %


.. |D02c_Path_Ellipses.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D02c_Path_Ellipses.3D.jpg
   :width: 30 %




|D02d_Path_Ellipses.3D| `\quad` |D02e_Path_Ellipses.3D| `\quad` |D02f_Path_Ellipses.3D|



.. |D02d_Path_Ellipses.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D02d_Path_Ellipses.3D.jpg
   :width: 30 %


.. |D02e_Path_Ellipses.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D02e_Path_Ellipses.3D.jpg
   :width: 30 %


.. |D02f_Path_Ellipses.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D02f_Path_Ellipses.3D.jpg
   :width: 30 %




|D02g_Path_Ellipses.3D| `\quad` |D02h_Path_Ellipses.3D| `\quad` |D02i_Path_Ellipses.3D|



.. |D02g_Path_Ellipses.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D02g_Path_Ellipses.3D.jpg
   :width: 30 %


.. |D02h_Path_Ellipses.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D02h_Path_Ellipses.3D.jpg
   :width: 30 %


.. |D02i_Path_Ellipses.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D02i_Path_Ellipses.3D.jpg
   :width: 30 %




|newpage|



Trefoil 2
---------------------------------------------------------

Some text explaining the importance of building the mesh in x-direction.


An example in C\#, for A, B, C

.. code-block:: csharp

    var D = 2.0; //  D = 1.0;  D = 2.0;
    var x = D * Math.Sin(t) + 2 * Math.Sin(2 * t);
    var y = D * Math.Cos(t) - 2 * Math.Cos(2 * t);
    var z = -D * Math.Sin(3 * t);



|D03a_Path_Trefoil02.3D| `\quad` |D03b_Path_Trefoil02.3D| `\quad` |D03c_Path_Trefoil02.3D|



.. |D03a_Path_Trefoil02.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D03a_Path_Trefoil02.3D.jpg
   :width: 30 %


.. |D03b_Path_Trefoil02.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D03b_Path_Trefoil02.3D.jpg
   :width: 30 %


.. |D03c_Path_Trefoil02.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D03c_Path_Trefoil02.3D.jpg
   :width: 30 %





|newpage|




Formatting options for path surfaces, Trefoil 5
----------------------------------------------------


These are the rough versions


An example in C\#, for A, B, C

.. code-block:: csharp

    var D = 1.0; //  D = 1.0;  D = 2.0;
    var x = D * Math.Sin(t) + 2 * Math.Sin(2 * t);
    var y = D * Math.Cos(t) - 2 * Math.Cos(2 * t);
    var z = -D * Math.Sin(3 * t);



These are the rough versions



|D04a_Path_Trefoil05.3D| `\quad` |D04b_Path_Trefoil05W.3D| `\quad` |D04c_Path_Trefoil05WO.3D|



.. |D04a_Path_Trefoil05.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D04a_Path_Trefoil05.3D.jpg
   :width: 30 %


.. |D04b_Path_Trefoil05W.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D04b_Path_Trefoil05W.3D.jpg
   :width: 30 %


.. |D04c_Path_Trefoil05WO.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D04c_Path_Trefoil05WO.3D.jpg
   :width: 30 %








These are the smooth versions



|D04d_Path_Trefoil05S.3D| `\quad` |D04e_Path_Trefoil05WS.3D| `\quad` |D04f_Path_Trefoil05WSO.3D|



.. |D04d_Path_Trefoil05S.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D04d_Path_Trefoil05S.3D.jpg
   :width: 30 %


.. |D04e_Path_Trefoil05WS.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D04e_Path_Trefoil05WS.3D.jpg
   :width: 30 %


.. |D04f_Path_Trefoil05WSO.3D| image:: ../_static/B24_WpfPathSurfaces/C01_Introduction/D04f_Path_Trefoil05WSO.3D.jpg
   :width: 30 %




