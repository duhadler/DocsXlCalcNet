

.. |newpage| raw:: latex

   \newpage




.. |cr| raw:: latex

   \hspace{0.0mm}









|newpage|



Builtin solids without support for textures
==============================================================



See also: https://mathworld.wolfram.com/topics/Prisms.html


See also: https://en.wikipedia.org/wiki/Prism_(geometry)

A prism is a polyhedron comprising an n-sided polygon base, a second base which is a translated copy (rigidly moved without rotation) of the first, and n other faces, necessarily all parallelograms, joining corresponding sides of the two bases. All cross-sections parallel to the bases are translations of the bases. Prisms are named after their bases, e.g. a prism with a pentagonal base is called a pentagonal prism.



Triangular Prism
-------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D01a_TriangularPrism.3D.xml (D01a-b) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D01a_TriangularPrism.3D.xml>`__.



A triangular prism or trigonal prism[1] is a prism with 2 triangular bases. If the edges pair with each triangle's vertex and if they are perpendicular to the base, it is a right triangular prism.

See also: https://mathworld.wolfram.com/TriangularPrism.html

See also: https://en.wikipedia.org/wiki/Triangular_prism


The example below uses the following code in C\#

.. code-block:: csharp

    var a = 0.50;
    var b = 0.50;
    var height = 1.0;
    var proc = BuiltIn.SetTriangularPrism(a, b, height, 0,0);




|cr|



|D01a_TriangularPrism.3D| `\quad` |D01b_TriangularPrism_Tilted.3D|

.. |D01a_TriangularPrism.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D01a_TriangularPrism.3D.jpg
    :width: 45 %

.. |D01b_TriangularPrism_Tilted.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D01b_TriangularPrism_Tilted.3D.jpg
    :width: 45 %








|newpage|

Square prism
-----------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D02a_SquarePrism.3D.xml (D02a-b) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D02a_SquarePrism.3D.xml>`__.


See also: https://mathworld.wolfram.com/Cube.html

See also: https://en.wikipedia.org/wiki/Cuboid

Cuboids have different types. A special case of a cuboid is a rectangular cuboid, with six rectangle faces and adjacent faces meeting at right angles. When all of the rectangular cuboid's edges are equal in length, it results in a cube, with six square faces and adjacent faces meeting at right angles.[1][3] Along with the rectangular cuboids, parallelepiped is a cuboid with six parallelogram. Rhombohedron is a cuboid with six rhombus faces. A square frustum is a frustum with a square base, but the rest of its faces are quadrilaterals.


The example below uses the following code in C\#

.. code-block:: csharp

    var a = 0.50;
    var b = 0.50;
    var height = 0.55;
    var proc = BuiltIn.SetSquarePrism(a, b, height, 0,0);



|cr|


|D02a_SquarePrism.3D| `\quad` |D02b_SquarePrism_Tilted.3D|

.. |D02a_SquarePrism.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D02a_SquarePrism.3D.jpg
    :width: 45 %

.. |D02b_SquarePrism_Tilted.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D02b_SquarePrism_Tilted.3D.jpg
    :width: 45 %







|newpage|

Hexagonal prism
---------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D03a_HexagonalPrism.3D.xml (D03a-b) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D03a_HexagonalPrism.3D.xml>`__.


The hexagonal prism is a prism with hexagonal base. Prisms are polyhedrons; this polyhedron has 8 faces, 18 edges, and 12 vertices.

See also: https://mathworld.wolfram.com/HexagonalPrism.html

See also: https://en.wikipedia.org/wiki/Hexagonal_prism


The example below uses the following code in C\#

.. code-block:: csharp

    var a = 0.50;
    var b = 0.50;
    var height = 1.0;
    var proc = BuiltIn.SetHexagonalPrism(a, b, height, 0,0);



|cr|



|D03a_HexagonalPrism.3D| `\quad` |D03b_HexagonalPrism_Tilted.3D|

.. |D03a_HexagonalPrism.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D03a_HexagonalPrism.3D.jpg
    :width: 45 %


.. |D03b_HexagonalPrism_Tilted.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D03b_HexagonalPrism_Tilted.3D.jpg
    :width: 45 %







|newpage|

Octagonal prism
----------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D04a_OctagonalPrism.3D.xml (D04a-b) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D04a_OctagonalPrism.3D.xml>`__.


The octagonal prism is a prism comprising eight rectangular sides joining two regular octagon caps. 

See also: https://mathworld.wolfram.com/OctagonalPrism.html

See also: https://en.wikipedia.org/wiki/Octagonal_prism


The example below uses the following code in C\#

.. code-block:: csharp

    var a = 0.50;
    var b = 0.50;
    var height = 1.0;
    var proc = BuiltIn.SetOctagonalPrism(a, b, height, 0,0);



|cr|




|D04a_OctagonalPrism.3D| `\quad` |D04b_OctagonalPrism_Tilted.3D|

.. |D04a_OctagonalPrism.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D04a_OctagonalPrism.3D.jpg
    :width: 45 %


.. |D04b_OctagonalPrism_Tilted.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D04b_OctagonalPrism_Tilted.3D.jpg
    :width: 45 %










|newpage|

Cylinder
------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05a_Cylinder.3D.xml <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D05a_Cylinder.3D.xml>`__.


A cylinder  is considered a prism with a circle as its base. The cylinder obtained by rotating a line segment about a fixed line that it is parallel to is a cylinder of revolution. A cylinder of revolution is a right circular cylinder.

See also: https://en.wikipedia.org/wiki/Cylinder

See also: https://en.wikipedia.org/wiki/Right_circular_cylinder


See also: https://mathworld.wolfram.com/Cylinder.html


The example below uses the following code in C\#

.. code-block:: csharp

    var numSides = 7;
    var a = 0.50;
    var b = 0.50;
    var height = 1.0;
    var proc = BuiltIn.SetCylinder(numSides, a, b, height, 0,0);


|cr|




|D05a_Cylinder.3D|

.. |D05a_Cylinder.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D05a_Cylinder.3D.jpg
    :width: 45 %






|newpage|

Cylinder, truncated by an inclined plane
---------------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D06a_Cylinder_Tilted.3D.xml (D06a-b) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D06a_Cylinder_Tilted.3D.xml>`__.


A cylinder  is considered a prism with a circle as its base. The cylinder obtained by rotating a line segment about a fixed line that it is parallel to is a cylinder of revolution. A cylinder of revolution is a right circular cylinder.

See also: https://en.wikipedia.org/wiki/Cylinder

See also: https://en.wikipedia.org/wiki/Right_circular_cylinder


See also: https://mathworld.wolfram.com/Cylinder.html



The example below uses the following code in C\#

.. code-block:: csharp

    var numSides = 7;
    var a = 0.50;
    var b = 0.50;
    var height = 1.0;
    var cutslope1 = -0.5;
    var cutslope2 = 0.5;
    var proc = BuiltIn.SetCylinder2CP(numSides, a, b, height, cutslope1, cutslope2);


|cr|


|D06a_Cylinder_Tilted.3D| `\quad` |D06b_Cylinder2CP.3D|

.. |D06a_Cylinder_Tilted.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D06a_Cylinder_Tilted.3D.jpg
    :width: 45 %


.. |D06b_Cylinder2CP.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D06b_Cylinder2CP.3D.jpg
    :width: 45 %










|newpage|


Pyramid
--------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07a_Pyramid.3D.xml <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D07a_Pyramid.3D.xml>`__.


A pyramid is a polyhedron formed by connecting a polygonal base and a point, called the apex. Each base edge and apex form a triangle, called a lateral face. It is a conic solid with a polygonal base. Many types of pyramids can be found by determining the shape of bases, or cutting off the apex. 

See also: https://en.wikipedia.org/wiki/Pyramid_(geometry)

See also: https://mathworld.wolfram.com/Pyramid.html


The example below uses the following code in C\#

.. code-block:: csharp

    var numSides = 7;
    var a = 0.50;
    var b = 0.50;
    var height = 1.0;
    var proc = BuiltIn.SetPyramid(numSides, a, b, height);


|cr|


|D07a_Pyramid.3D|

.. |D07a_Pyramid.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D07a_Pyramid.3D.jpg
    :width: 45 %






|newpage|

Pyramid frustum
-----------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D08a_Frustum.3D.xml <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D08a_Frustum.3D.xml>`__.


A frustum of a pyramid is the portion of the pyramid that lies between two parallel planes cutting the pyramid. In a truncated  pyramid, the truncation plane is not necessarily parallel to the pyramid's base (as in a frustum), i.e. it is inclined.

See also: https://en.wikipedia.org/wiki/Frustum

See also: https://mathworld.wolfram.com/PyramidalFrustum.html



The example below uses the following code in C\#

.. code-block:: csharp

    var numSides = 7;
    var a = 0.50;
    var b = 0.50;
    var height = 1.2;
    var cutheight = 0.8;
    var cutslope = 0.0;
    var proc = BuiltIn.SetFrustum(numSides, a, b, height, cutheight, cutslope);


|cr|

|D08a_Frustum.3D|

.. |D08a_Frustum.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D08a_Frustum.3D.jpg
    :width: 45 %








|newpage|

Pyramid, truncated by an inclined plane
---------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D09a_Frustum_Inclined.3D.xml <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D09a_Frustum_Inclined.3D.xml>`__.


A frustum of a pyramid is the portion of the pyramid that lies between two parallel planes cutting the pyramid. In a truncated  pyramid, the truncation plane is not necessarily parallel to the pyramid's base (as in a frustum), i.e. it is inclined.

See also: https://en.wikipedia.org/wiki/Frustum

See also: https://mathworld.wolfram.com/PyramidalFrustum.html



The example below uses the following code in C\#

.. code-block:: csharp

    var numSides = 7;
    var a = 0.50;
    var b = 0.50;
    var height = 1.2;
    var cutheight = 0.8;
    var cutslope = 0.3;
    var proc = BuiltIn.SetFrustum(numSides, a, b, height, cutheight, cutslope);



|cr|

|D09a_Frustum_Inclined.3D|

.. |D09a_Frustum_Inclined.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D09a_Frustum_Inclined.3D.jpg
    :width: 45 %








|newpage|

Cone 
----------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D10a_Cone.3D.xml <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D10a_Cone.3D.xml>`__.


A cone is a three-dimensional geometric shape that tapers smoothly from a flat base (frequently, though not necessarily, circular) to a point called the apex or vertex. A cone with a polygonal base is called a pyramid.


See also: https://en.wikipedia.org/wiki/Cone

See also: https://mathworld.wolfram.com/Cone.html


The example below uses the following code in C\#

.. code-block:: csharp

    var numSides = 32;
    var a = 0.50;
    var b = 0.50;
    var height = 1.0;
    var proc = BuiltIn.SetCone(numSides, a, b, height);


|cr|

|D10a_Cone.3D|

.. |D10a_Cone.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D10a_Cone.3D.jpg
    :width: 45 %







|newpage|

Cone Frustum
-------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D11a_ConeFrustum.3D.xml <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D11a_ConeFrustum.3D.xml>`__.


A cone is a three-dimensional geometric shape that tapers smoothly from a flat base (frequently, though not necessarily, circular) to a point called the apex or vertex. A cone with a polygonal base is called a pyramid.


See also: https://en.wikipedia.org/wiki/Frustum

See also: https://mathworld.wolfram.com/ConicalFrustum.html



The example below uses the following code in C\#

.. code-block:: csharp

    var numSides = 32;
    var a = 0.50;
    var b = 0.50;
    var height = 1.2;
    var cutheight = 0.6;
    var cutslope = 0.0;
    var proc = BuiltIn.SetConeFrustum(numSides, a, b, height, cutheight, cutslope);




|cr|

|D11a_ConeFrustum.3D|

.. |D11a_ConeFrustum.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D11a_ConeFrustum.3D.jpg
    :width: 45 %






|newpage|

Cone, truncated by an inclined plane
------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D12a_ConeFrustum_Inclined.3D.xml <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D12a_ConeFrustum_Inclined.3D.xml>`__.


A cone is a three-dimensional geometric shape that tapers smoothly from a flat base (frequently, though not necessarily, circular) to a point called the apex or vertex. A cone with a polygonal base is called a pyramid.


See also: https://en.wikipedia.org/wiki/Frustum

See also: https://mathworld.wolfram.com/ConicalFrustum.html


The example below uses the following code in C\#

.. code-block:: csharp

    var numSides = 32;
    var a = 0.50;
    var b = 0.50;
    var height = 1.2;
    var cutheight = 0.6;
    var cutslope = 0.3;
    var proc = BuiltIn.SetConeFrustum(numSides, a, b, height, cutheight, cutslope);


|cr|

|D12a_ConeFrustum_Inclined.3D|

.. |D12a_ConeFrustum_Inclined.3D| image:: ../_static/B25_WpfBuiltInSurfaces/C02_SolidsWithoutTextures/D12a_ConeFrustum_Inclined.3D.jpg
    :width: 45 %





