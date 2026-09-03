

.. |newpage| raw:: latex

   \newpage



.. |cr| raw:: latex

   \hspace{0.0mm}








|newpage|


Platonic solids, and related solids
==============================================================

A Platonic solid is a convex, regular polyhedron in three-dimensional Euclidean space. Being a regular polyhedron means that the faces are congruent (identical in shape and size) regular polygons (all angles congruent and all edges congruent), and the same number of faces meet at each vertex.

See also: https://en.wikipedia.org/wiki/Platonic_solid

See also: https://mathworld.wolfram.com/PlatonicSolid.html

Augmentation is the operation of replacing the faces of a polyhedron with pyramids of height `h` (where `h` may be positive, zero, or negative) having the face as the base. Augmentation with `h=0` gives a triangulated version of the original solid. 

See also: https://mathworld.wolfram.com/Augmentation.html




Tetrahedron
------------------------------------------------------------------------------

A regular tetrahedron is a tetrahedron in which all four faces are equilateral triangles. In other words, all of its faces are the same size and shape (congruent) and all edges are the same length.

See also: https://en.wikipedia.org/wiki/Tetrahedron#Regular_tetrahedron

See also: https://mathworld.wolfram.com/RegularTetrahedron.html

See also: https://mathcurve.com/polyedres/tetraedre/tetraedre.shtml



An example in C\#

.. code-block:: csharp

    var proc = BuiltIn.SetTetrahedron();



|cr|


|D01a_Tetrahedron.3D|

.. |D01a_Tetrahedron.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D01a_Tetrahedron.3D.jpg
    :width: 45 %








|newpage|

Cube
---------------------------------------


A cube is a three-dimensional solid object bounded by six square faces. It has twelve edges and eight vertices. It can be represented as a rectangular cuboid with six square faces, or a parallelepiped with equal edges.


See also: https://en.wikipedia.org/wiki/Cube

See also: https://mathworld.wolfram.com/Cube.html

See also: https://mathcurve.com/polyedres/cube/cube.shtml


An example in C\#

.. code-block:: csharp

    var proc = BuiltIn.SetCube();



|cr|

|D02a_Cube.3D|

.. |D02a_Cube.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D02a_Cube.3D.jpg
    :width: 45 %









|newpage|

Octahedron
---------------------------------


A regular octahedron is an octahedron that is a regular polyhedron. All the faces of a regular octahedron are equilateral triangles of the same size, and exactly four triangles meet at each vertex. A regular octahedron is convex, meaning that for any two points within it, the line segment connecting them lies entirely within it. 


See also: https://en.wikipedia.org/wiki/Octahedron#Regular_octahedron

See also: https://mathworld.wolfram.com/RegularOctahedron.html

See also: https://mathcurve.com/polyedres/octaedre/octaedre.shtml



An example in C\#

.. code-block:: csharp

    var proc = BuiltIn.SetOctahedron();





|cr|

|D03a_Octahedron.3D|

.. |D03a_Octahedron.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D03a_Octahedron.3D.jpg
    :width: 45 %







|newpage|

Dodecahedron
----------------------------------


A regular dodecahedron or pentagonal dodecahedron is a dodecahedron composed of regular pentagonal faces, three meeting at each vertex.

See also: https://en.wikipedia.org/wiki/Regular_dodecahedron

See also: https://mathworld.wolfram.com/RegularDodecahedron.html

See also: https://mathcurve.com/polyedres/dodecaedre/dodecaedre.shtml



An example in C\#

.. code-block:: csharp

    var proc = BuiltIn.SetDodecahedron();





|cr|

|D04a_Dodecahedron.3D|

.. |D04a_Dodecahedron.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D04a_Dodecahedron.3D.jpg
    :width: 45 %







|newpage|

Icosahedron 
-----------------------------------


A regular icosahedron (or simply icosahedron) is a convex polyhedron that can be constructed from pentagonal antiprism by attaching two pentagonal pyramids with regular faces to each of its pentagonal faces, or by putting points onto the cube.

See also: https://en.wikipedia.org/wiki/Regular_icosahedron

See also: https://mathworld.wolfram.com/RegularIcosahedron.html

See also: https://mathcurve.com/polyedres/icosaedre/icosaedre.shtml



An example in C\#

.. code-block:: csharp

    var proc = BuiltIn.SetIcosahedron();



|cr|

|D05a_Icosahedron.3D|

.. |D05a_Icosahedron.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D05a_Icosahedron.3D.jpg
    :width: 45 %







|newpage|

Geodesic sphere
-----------------------------------------


A spherical polyhedron or spherical tiling is a tiling of the sphere in which the surface is divided or partitioned by great arcs into bounded regions called spherical polygons

See also: https://en.wikipedia.org/wiki/Geodesic_polyhedron

See also: https://en.wikipedia.org/wiki/Spherical_polyhedron



An example in C\#

.. code-block:: csharp

    var radius = 1.0;
    var numDiv = 1;
    var proc = BuiltIn.SetGeodesicSphere(radius, numDiv);


|cr|


|D06a_Scatter_Geodesic_Sphere1.3D| `\quad` |D06b_Scatter_Geodesic_Sphere2.3D| `\quad` |D06c_Scatter_Geodesic_Sphere3.3D|

.. |D06a_Scatter_Geodesic_Sphere1.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D06a_Scatter_Geodesic_Sphere1.3D.jpg
    :width: 30 %

.. |D06b_Scatter_Geodesic_Sphere2.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D06b_Scatter_Geodesic_Sphere2.3D.jpg
    :width: 30 %

.. |D06c_Scatter_Geodesic_Sphere3.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D06c_Scatter_Geodesic_Sphere3.3D.jpg
    :width: 30 %


|D06d_Scatter_Geodesic_Sphere5.3D| `\quad` |D06e_Scatter_Geodesic_Sphere7.3D| `\quad` |D06f_Scatter_Geodesic_Sphere9.3D|

.. |D06d_Scatter_Geodesic_Sphere5.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D06d_Scatter_Geodesic_Sphere5.3D.jpg
    :width: 30 %

.. |D06e_Scatter_Geodesic_Sphere7.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D06e_Scatter_Geodesic_Sphere7.3D.jpg
    :width: 30 %

.. |D06f_Scatter_Geodesic_Sphere9.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D06f_Scatter_Geodesic_Sphere9.3D.jpg
    :width: 30 %





|newpage|




Augmented Octahedron
--------------------------------------------

Returns the augmented Octahedron.


An example in C\#

.. code-block:: csharp

    var starRadius = 3.0;
    var proc = BuiltIn.SetAugmentedOctahedron(starRadius );


|cr|


|D07b_Augm_Octahedron_b.3D| `\quad` |D07c_Augm_Octahedron_c.3D| `\quad` |D07d_Augm_Octahedron_d.3D|

.. |D07b_Augm_Octahedron_b.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D07b_Augm_Octahedron_b.3D.jpg
    :width: 30 %

.. |D07c_Augm_Octahedron_c.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D07c_Augm_Octahedron_c.3D.jpg
    :width: 30 %

.. |D07d_Augm_Octahedron_d.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D07d_Augm_Octahedron_d.3D.jpg
    :width: 30 %








|newpage|



Augmented Dodecahedron
-------------------------------------------

Returns the augmented Dodecahedron.


An example in C\#

.. code-block:: csharp

    var starRadius = 6.0;
    var proc = BuiltIn.SetAugmentedDodecahedron(starRadius );


|cr|


|D08b_Augm_Dodecahedron_b.3D| `\quad` |D08c_Augm_Dodecahedron_c.3D| `\quad` |D08d_Augm_Dodecahedron_d.3D|

.. |D08b_Augm_Dodecahedron_b.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D08b_Augm_Dodecahedron_b.3D.jpg
    :width: 30 %

.. |D08c_Augm_Dodecahedron_c.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D08c_Augm_Dodecahedron_c.3D.jpg
    :width: 30 %

.. |D08d_Augm_Dodecahedron_d.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D08d_Augm_Dodecahedron_d.3D.jpg
    :width: 30 %









|newpage|


Augmented Icosahedron
-------------------------------------------


Returns the augmented Dodecahedron.


An example in C\#

.. code-block:: csharp

    var starRadius = 2.0;
    var proc = BuiltIn.SetAugmentedIcosahedron(starRadius );



|cr|


|D09b_Augm_Icosahedron_b.3D| `\quad` |D09c_Augm_Icosahedron_c.3D| `\quad` |D09d_Augm_Icosahedron_d.3D|

.. |D09b_Augm_Icosahedron_b.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D09b_Augm_Icosahedron_b.3D.jpg
    :width: 30 %

.. |D09c_Augm_Icosahedron_c.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D09c_Augm_Icosahedron_c.3D.jpg
    :width: 30 %

.. |D09d_Augm_Icosahedron_d.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D09d_Augm_Icosahedron_d.3D.jpg
    :width: 30 %





|newpage|


Augmented Geodesic Sphere
-----------------------------------------


Returns augmented versions of the Geodesic.

See also: https://mathworld.wolfram.com/IcosahedronStellations.html


An example in C\#

.. code-block:: csharp

    var starRadius = 2.0;
    var numDiv = 2;
    var proc = BuiltIn.SetAugmentedGeodesic(starRadius, numDiv);



|cr|


|D10b_Augm_Geodesic_b.3D| `\quad` |D10c_Augm_Geodesic_c.3D| `\quad` |D10d_Augm_Geodesic_d.3D|

.. |D10b_Augm_Geodesic_b.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D10b_Augm_Geodesic_b.3D.jpg
    :width: 30 %

.. |D10c_Augm_Geodesic_c.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D10c_Augm_Geodesic_c.3D.jpg
    :width: 30 %

.. |D10d_Augm_Geodesic_d.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D10d_Augm_Geodesic_d.3D.jpg
    :width: 30 %






|newpage|

Stella Octangula
----------------------------------------


The stella octangula is a polyhedron compound composed of a tetrahedron and its dual (a second tetrahedron rotated 180 degrees with respect to the first). The stella octangula is also (incorrectly) called the augmented tetrahedron, and is the only stellation of the octahedron.

It can be constructed from a regular octahedron by augmentation with `h = \sqrt{6}/3`.

See also: https://mathworld.wolfram.com/StellaOctangula.html

See also: https://en.wikipedia.org/wiki/Stellated_octahedron


An example in C\#

.. code-block:: csharp

    var starRadius = 2.0;
    var proc = BuiltIn.SetAugmentedOctahedron(starRadius );



|cr|


|D11a_StellaOctangula.3D|

.. |D11a_StellaOctangula.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D11a_StellaOctangula.3D.jpg
    :width: 45 %







|newpage|

Small stellated Dodecahedron
---------------------------------------


The small stellated dodecahedron is the Kepler-Poinsot polyhedra whose dual polyhedron is the great dodecahedron.

It can be constructed from a regular dodecahedron by augmentation with `h = \sqrt{(5 + 2\sqrt{5})/5 }`.


See also: https://mathworld.wolfram.com/SmallStellatedDodecahedron.html

See also: https://mathworld.wolfram.com/Augmentation.html

See also: https://en.wikipedia.org/wiki/Small_stellated_dodecahedron

See also: https://mathworld.wolfram.com/Kepler-PoinsotPolyhedron.html



An example in C\#

.. code-block:: csharp

    var starRadius = 6.0;
    var proc = BuiltIn.SetAugmentedDodecahedron(starRadius );



|cr|

|D12a_SmallStellatedDodecahedron.3D|

.. |D12a_SmallStellatedDodecahedron.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D12a_SmallStellatedDodecahedron.3D.jpg
    :width: 45 %






|newpage|

Great Dodecahedron
------------------------------------------

The great dodecahedron is the Kepler-Poinsot polyhedron whose dual is the small augmented dodecahedron. 

It can be constructed from a regular icosahedron by augmentation with `h = (\sqrt{3} (\sqrt{5}-3))/6`.



See also: https://mathworld.wolfram.com/GreatDodecahedron.html

See also: https://mathworld.wolfram.com/Augmentation.html

See also: https://en.wikipedia.org/wiki/Great_dodecahedron

See also: https://mathworld.wolfram.com/Kepler-PoinsotPolyhedron.html


An example in C\#

.. code-block:: csharp

    var starRadius = 0.25;
    var proc = BuiltIn.SetAugmentedIcosahedron(starRadius );



|cr|

|D13a_GreatDodecahedron.3D|

.. |D13a_GreatDodecahedron.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D13a_GreatDodecahedron.3D.jpg
    :width: 45 %












|newpage|

Great stellated Dodecahedron
--------------------------------------------

The great augmented dodecahedron is one of the Kepler-Poinsot polyhedra. 

It can be constructed from a regular icosahedron by augmentation with `h = (\sqrt{3} (3+\sqrt{5}))/6`.


See also: https://mathworld.wolfram.com/GreatStellatedDodecahedron.html

See also: https://mathworld.wolfram.com/Augmentation.html

See also: https://en.wikipedia.org/wiki/Great_stellated_dodecahedron

See also: https://mathworld.wolfram.com/Kepler-PoinsotPolyhedron.html




An example in C\#

.. code-block:: csharp

    var starRadius = 2.0;
    var proc = BuiltIn.SetAugmentedIcosahedron(starRadius );




|cr|

|D14a_GreatStellatedDodecahedron.3D|

.. |D14a_GreatStellatedDodecahedron.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C03_PlatonicSolids/D14a_GreatStellatedDodecahedron.3D.jpg
    :width: 45 %






