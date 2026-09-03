

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />






|newpage|

Lissajous knots
==============================================================

See also: https://en.wikipedia.org/wiki/Lissajous_knot

See also: https://mathcurve.com/courbes3d.gb/lissajous3d/noeudlissajous.shtml

See also: https://knotplot.com/manual/LissajousParams.html


The Lissajous knots are the knots associated to the 3D Lissajous curves when they are closed and without double point.

As is proved in the above article by Jones and Przytycki, they also are the knots associated to the trajectories of a ball (not subject to gravity) in a parallelepipedic billiard, or even a cubic one (imagine a glass box).

It can be proved that for all values of p, q, r, there exist values of j and y such that the knot is trivial, and that certain knots such as the trefoil knot are not Lissajous knots. 


See also: https://mathcurve.com/courbes3d.gb/lissajous3d/lissajous3d.shtml


The 3D Lissajous curves are the trajectories of a point in space the rectangular components of which have a sinusoidal motion.
The projections on the 3 coordinate planes are the classic 2D Lissajous curves.

For n = 1 or n = m, we get a cylindrical sine wave.
We get a closed curve if and only if n and m are rational.

When the curve does not have double points, nor a cusp, it forms a knot in space, called Lissajous knot, equivalent to a cubic billiard knot.







|newpage|

Lissajous knot 1-1-1
----------------------------------


An example in C\#

.. code-block:: csharp

    double pi = Math.PI;
    double a1, k1, l1;
    double a2, k2, l2;
    double a3, k3, l3;
    a1 = 100; k1 = 1; l1 = 0;
    a2 = 100; k2 = 1; l2 = pi / 2;
    a3 = 100; k3 = 1; l3 = pi / 2;
    var x = (a1 * Math.Cos(k1 * t + l1)) / 50;
    var y = (a3 * Math.Cos(k3 * t + l3)) / 50;
    var z = (a2 * Math.Cos(k2 * t + l2)) / 50;




|D01a_Path_111_LKnot_P090T090.3D| `\quad` |D01b_Path_111_LKnot_P090T180.3D| `\quad` |D01c_Path_111_LKnot_P135T180.3D|



.. |D01b_Path_111_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D01b_Path_111_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D01a_Path_111_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D01a_Path_111_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D01c_Path_111_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D01c_Path_111_LKnot_P135T180.3D.jpg
   :width: 30 %



|D01d_Path_111_LKnot_P090T090.3D| `\quad` |D01e_Path_111_LKnot_P090T180.3D| `\quad` |D01f_Path_111_LKnot_P135T180.3D|



.. |D01d_Path_111_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D01d_Path_111_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D01e_Path_111_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D01e_Path_111_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D01f_Path_111_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D01f_Path_111_LKnot_P135T180.3D.jpg
   :width: 30 %







|newpage|



Lissajous knot 1-2-1
-------------------------------------


An example in C\#

.. code-block:: csharp

    double pi = Math.PI;
    double a1, k1, l1;
    double a2, k2, l2;
    double a3, k3, l3;
    a1 = 100; k1 = 1; l1 = 0;
    a2 = 100; k2 = 2; l2 = pi / 2;
    a3 = 100; k3 = 1; l3 = pi / 2;
    var x = (a1 * Math.Cos(k1 * t + l1)) / 50;
    var y = (a3 * Math.Cos(k3 * t + l3)) / 50;
    var z = (a2 * Math.Cos(k2 * t + l2)) / 50;



|D02a_Path_121_LKnot_P090T090.3D| `\quad` |D02b_Path_121_LKnot_P090T180.3D| `\quad` |D02c_Path_121_LKnot_P135T180.3D|



.. |D02a_Path_121_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D02a_Path_121_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D02b_Path_121_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D02b_Path_121_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D02c_Path_121_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D02c_Path_121_LKnot_P135T180.3D.jpg
   :width: 30 %



|D02d_Path_121_LKnot_P090T090.3D| `\quad` |D02e_Path_121_LKnot_P090T180.3D| `\quad` |D02f_Path_121_LKnot_P135T180.3D|



.. |D02d_Path_121_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D02d_Path_121_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D02e_Path_121_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D02e_Path_121_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D02f_Path_121_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D02f_Path_121_LKnot_P135T180.3D.jpg
   :width: 30 %






|newpage|


Lissajous knot 1-5-3
----------------------------------


An example in C\#

.. code-block:: csharp

    double pi = Math.PI;
    double a1, k1, l1;
    double a2, k2, l2;
    double a3, k3, l3;
    a1 = 100; k1 = 1; l1 = 0;
    a2 = 100; k2 = 5; l2 = pi / 2;
    a3 = 100; k3 = 3; l3 = pi / 2;
    var x = (a1 * Math.Cos(k1 * t + l1)) / 50;
    var y = (a3 * Math.Cos(k3 * t + l3)) / 50;
    var z = (a2 * Math.Cos(k2 * t + l2)) / 50;




|D03a_Path_153_LKnot_P090T090.3D| `\quad` |D03b_Path_153_LKnot_P090T180.3D| `\quad` |D03c_Path_153_LKnot_P135T180.3D|



.. |D03a_Path_153_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D03a_Path_153_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D03b_Path_153_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D03b_Path_153_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D03c_Path_153_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D03c_Path_153_LKnot_P135T180.3D.jpg
   :width: 30 %



|D03d_Path_153_LKnot_P090T090.3D| `\quad` |D03e_Path_153_LKnot_P090T180.3D| `\quad` |D03f_Path_153_LKnot_P135T180.3D|



.. |D03d_Path_153_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D03d_Path_153_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D03e_Path_153_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D03e_Path_153_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D03f_Path_153_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D03f_Path_153_LKnot_P135T180.3D.jpg
   :width: 30 %







|newpage|


Lissajous knot 3-5-2
--------------------------------


An example in C\#

.. code-block:: csharp

    double pi = Math.PI;
    double a1, k1, l1;
    double a2, k2, l2;
    double a3, k3, l3;
    a1 = 100; k1 = 3; l1 = 0;
    a2 = 100; k2 = 5; l2 = pi / 2;
    a3 = 100; k3 = 2; l3 = pi / 2;
    var x = (a1 * Math.Cos(k1 * t + l1)) / 50;
    var y = (a3 * Math.Cos(k3 * t + l3)) / 50;
    var z = (a2 * Math.Cos(k2 * t + l2)) / 50;




|D04a_Path_352_LKnot_P090T090.3D| `\quad` |D04b_Path_352_LKnot_P090T180.3D| `\quad` |D04c_Path_352_LKnot_P135T180.3D|



.. |D04a_Path_352_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D04a_Path_352_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D04b_Path_352_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D04b_Path_352_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D04c_Path_352_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D04c_Path_352_LKnot_P135T180.3D.jpg
   :width: 30 %



|D04d_Path_352_LKnot_P090T090.3D| `\quad` |D04e_Path_352_LKnot_P090T180.3D| `\quad` |D04f_Path_352_LKnot_P135T180.3D|



.. |D04d_Path_352_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D04d_Path_352_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D04e_Path_352_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D04e_Path_352_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D04f_Path_352_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D04f_Path_352_LKnot_P135T180.3D.jpg
   :width: 30 %








|newpage|


Lissajous knot 3-5-7
----------------------------


An example in C\#

.. code-block:: csharp

    double pi = Math.PI;
    double a1, k1, l1;
    double a2, k2, l2;
    double a3, k3, l3;
    a1 = 100; k1 = 3; l1 = 7;
    a2 = 100; k2 = 5; l2 = 5;
    a3 = 100; k3 = 7; l3 = 3;
    var x = (a1 * Math.Cos(k1 * t + l1)) / 50;
    var y = (a3 * Math.Cos(k3 * t + l3)) / 50;
    var z = (a2 * Math.Cos(k2 * t + l2)) / 50;



|D05a_Path_357_LKnot_P090T090.3D| `\quad` |D05b_Path_357_LKnot_P090T180.3D| `\quad` |D05c_Path_357_LKnot_P135T180.3D|



.. |D05a_Path_357_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D05a_Path_357_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D05b_Path_357_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D05b_Path_357_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D05c_Path_357_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D05c_Path_357_LKnot_P135T180.3D.jpg
   :width: 30 %



|D05d_Path_357_LKnot_P090T090.3D| `\quad` |D05e_Path_357_LKnot_P090T180.3D| `\quad` |D05f_Path_357_LKnot_P135T180.3D|



.. |D05d_Path_357_LKnot_P090T090.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D05d_Path_357_LKnot_P090T090.3D.jpg
   :width: 30 %


.. |D05e_Path_357_LKnot_P090T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D05e_Path_357_LKnot_P090T180.3D.jpg
   :width: 30 %


.. |D05f_Path_357_LKnot_P135T180.3D| image:: ../_static/B24_WpfPathSurfaces/C08_LissajousKnots/D05f_Path_357_LKnot_P135T180.3D.jpg
   :width: 30 %





















