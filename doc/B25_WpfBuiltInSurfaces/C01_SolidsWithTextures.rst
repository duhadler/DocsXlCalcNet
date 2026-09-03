

.. |newpage| raw:: latex

   \newpage



.. |cr| raw:: latex

   \hspace{0.0mm}








|newpage|



Builtin solids with support for textures
==============================================================



Sphere
---------------------------

A sphere is a geometrical object that is a three-dimensional analogue to a two-dimensional circle. 

See also: https://en.wikipedia.org/wiki/Sphere

See also: https://mathworld.wolfram.com/Sphere.html

See also: https://mathcurve.com/surfaces.gb/sphere/sphere.shtml



An example in C\#

.. code-block:: csharp

    var radius = 1.0;
    var numTheta = 20;
    var numPhi = 20;
    var proc = BuiltIn.SetSphere(radius, numTheta, numPhi);


|cr|


|D01a_Sphere.3D| `\quad` |D01b_Sphere.3D|

.. |D01a_Sphere.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D01a_Sphere.3D.jpg
    :width: 45 %

.. |D01b_Sphere.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D01b_Sphere.3D.jpg
    :width: 45 %


An example in C\#

.. code-block:: csharp

    var radius = 1.0;
    var numTheta = 20;
    var numPhi = 20;
    var proc = BuiltIn.SetSphere(radius, numTheta, numPhi);



|D01c_Sphere.3D| `\quad` |D01d_Sphere.3D|

.. |D01c_Sphere.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D01c_Sphere.3D.jpg
    :width: 45 %

.. |D01d_Sphere.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D01d_Sphere.3D.jpg
    :width: 45 %


An example in C\#

.. code-block:: csharp

    var radius = 1.0;
    var numTheta = 20;
    var numPhi = 20;
    var proc = BuiltIn.SetSphere(radius, numTheta, numPhi);


|D01e_Sphere.3D| `\quad` |D01e_Sphere.3D|

.. |D01e_Sphere.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D01e_Sphere.3D.jpg
    :width: 45 %

.. |D01f_Sphere.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D01f_Sphere.3D.jpg
    :width: 45 %











|newpage|

Prolate Spheroid
-----------------------------------------------------

See also: https://mathworld.wolfram.com/ProlateSpheroid.html

See also: https://mathworld.wolfram.com/Spheroid.html

See also: https://en.wikipedia.org/wiki/Spheroid#Prolate_spheroids

See also: https://en.wikipedia.org/wiki/Spheroid#


An example in C\#

.. code-block:: csharp

    var radius = 1.0;
    var factor1 = 1.5;
    var numTheta = 20;
    var numPhi = 20;
    var proc = BuiltIn.SetProlateSpheroid(radius, factor1, numTheta, numPhi);


|cr|



|D02a_PSpheroid.3D| `\quad` |D02b_PSpheroid_Rotated.3D|

.. |D02a_PSpheroid.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D02a_PSpheroid.3D.jpg
    :width: 45 %

.. |D02b_PSpheroid_Rotated.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D02b_PSpheroid_Rotated.3D.jpg
    :width: 45 %









|newpage|

Oblate Spheroid
-------------------------------------------------------------

See also: https://mathworld.wolfram.com/OblateSpheroid.html

See also: https://mathworld.wolfram.com/Spheroid.html


See also: https://en.wikipedia.org/wiki/Spheroid#Oblate_spheroids

See also: https://en.wikipedia.org/wiki/Spheroid#



An example in C\#

.. code-block:: csharp

    var radius = 1.0;
    var factor2 = 0.5;
    var numTheta = 20;
    var numPhi = 20;
    var proc = BuiltIn.SetOblateSpheroid(radius, factor2, numTheta, numPhi);

|cr|



|D03a_OSpheroid.3D| `\quad` |D03b_OSpheroid.3D|

.. |D03a_OSpheroid.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D03a_OSpheroid.3D.jpg
    :width: 45 %

.. |D03b_OSpheroid.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D03b_OSpheroid.3D.jpg
    :width: 45 %



An example in C\#

.. code-block:: csharp

    var radius = 1.0;
    var factor2 = 0.5;
    var numTheta = 20;
    var numPhi = 20;
    var proc = BuiltIn.SetOblateSpheroid(radius, factor2, numTheta, numPhi);

|cr|



|D03c_OSpheroid.3D| `\quad` |D03d_OSpheroid.3D|

.. |D03c_OSpheroid.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D03c_OSpheroid.3D.jpg
    :width: 45 %

.. |D03d_OSpheroid.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D03d_OSpheroid.3D.jpg
    :width: 45 %










|newpage|

Ellipsoid
----------------------------------------


See also: https://mathworld.wolfram.com/Ellipsoid.html


See also: https://en.wikipedia.org/wiki/Ellipsoid



An example in C\#

.. code-block:: csharp

    var radius = 1.0;
    var factor1 = 1.5;
    var factor2 = 0.5;
    numTheta = 20;
    var numPhi = 20;
    var proc = BuiltIn.SetEllipsoid(radius, factor1, factor2, numTheta, numPhi);

|cr|




|D04a_Ellipsoid.3D| `\quad` |D04b_Ellipsoid_Rotated.3D|

.. |D04a_Ellipsoid.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D04a_Ellipsoid.3D.jpg
    :width: 45 %

.. |D04b_Ellipsoid_Rotated.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D04b_Ellipsoid_Rotated.3D.jpg
    :width: 45 %








|newpage|

Torus
-------------------------------------------

A torus is a surface of revolution generated by revolving a circle in three-dimensional space one full revolution about an axis that is coplanar with the circle. The main types of toruses include ring toruses, horn toruses, and spindle toruses. A ring torus is sometimes colloquially referred to as a donut or doughnut. 

See also: https://en.wikipedia.org/wiki/Torus

See also: https://mathworld.wolfram.com/Torus.html

See also: https://mathcurve.com/surfaces.gb/tore/tore.shtml



.. code-block:: csharp

    var Radius = 0.6;
    var radius = 0.2;
    var numTheta = 40;
    var numPhi = 40;
    var proc = BuiltIn.SetTorus(Radius, radius, numTheta, numPhi);

|cr|




|D05a_Torus.3D| `\quad` |D05b_Torus_Rotated.3D|

.. |D05a_Torus.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D05a_Torus.3D.jpg
    :width: 45 %

.. |D05b_Torus_Rotated.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D05b_Torus_Rotated.3D.jpg
    :width: 45 %








|newpage|


Rectangular cuboid
----------------------------------------------

A rectangular cuboid is a special case of a cuboid with rectangular faces in which all of its dihedral angles are right angles. This shape is also called rectangular parallelepiped or orthogonal parallelepiped.

See also: https://en.wikipedia.org/wiki/Rectangular_cuboid

See also: https://mathworld.wolfram.com/Cuboid.html


An example in C\#

.. code-block:: csharp

    var a = 1.0;
    var b = 3.0;
    var c = 2.0;
    var proc = BuiltIn.SetCuboid(a, b, c);



|cr|



|D06a_Cuboid.3D| `\quad` |D06b_Cuboid_Rotated.3D|

.. |D06a_Cuboid.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D06a_Cuboid.3D.jpg
    :width: 45 %

.. |D06b_Cuboid_Rotated.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D06b_Cuboid_Rotated.3D.jpg
    :width: 45 %








|newpage|

Rhombohedron
-----------------------------------------

A rhombohedron is a parallelepiped bounded by six rhombi such that opposite faces are congruent. Special cases include the cube, acute golden rhombohedron, and obtuse golden rhombohedron. 

See also: https://en.wikipedia.org/wiki/Rhombohedron

See also: https://mathworld.wolfram.com/Rhombohedron.html

    
See also: https://mathworld.wolfram.com/GoldenRhombohedron.html

See also: https://mathworld.wolfram.com/AcuteGoldenRhombohedron.html

See also: https://mathworld.wolfram.com/ObtuseGoldenRhombohedron.html


An example in C\#

.. code-block:: csharp

    var theta = 60.0;
    var proc = BuiltIn.SetRhombohedron(theta);



|cr|




|D07a_Rhombohedron_60.3D| `\quad` |D07b_Rhombohedron_90.3D| `\quad` |D07c_Rhombohedron_110.3D|

.. |D07a_Rhombohedron_60.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D07a_Rhombohedron_60.3D.jpg
    :width: 30 %

.. |D07b_Rhombohedron_90.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D07b_Rhombohedron_90.3D.jpg
    :width: 30 %

.. |D07c_Rhombohedron_110.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D07c_Rhombohedron_110.3D.jpg
    :width: 30 %








|newpage|

Parallelepiped
------------------------------------------------

A rectangular cuboid is a special case of a cuboid with rectangular faces in which all of its dihedral angles are right angles. This shape is also called rectangular parallelepiped or orthogonal parallelepiped.

See also: https://en.wikipedia.org/wiki/Parallelepiped

See also: https://mathworld.wolfram.com/Parallelepiped.html



An example in C\#

.. code-block:: csharp

    var a = 1.0;
    var b = 3.0;
    var c = 2.0;
    var alpha = 90.0;
    var beta = 90.0;

    var proc = BuiltIn.SetParallelepiped(a, b, c, alpha, beta);


|cr|




|D08a_Parallelepiped.3D| `\quad` |D08b_Parallelepiped_Rotated.3D|

.. |D08a_Parallelepiped.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D08a_Parallelepiped.3D.jpg
    :width: 45 %

.. |D08b_Parallelepiped_Rotated.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C01_SolidsWithTextures/D08b_Parallelepiped_Rotated.3D.jpg
    :width: 45 %







