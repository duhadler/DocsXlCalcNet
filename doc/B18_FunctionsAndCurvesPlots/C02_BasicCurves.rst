

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />






|newpage|

Basic curves
==============================================================



Regular convex polygon
------------------------------------------------------------------------------------------

A regular polygon is a polygon that is direct equiangular (all angles are equal in measure) and equilateral (all sides have the same length). Regular polygons may be either convex, star or skew. In the limit, a sequence of regular polygons with an increasing number of sides approximates a circle.

.. math:: r = \frac{a}{\cos \left(t - \alpha/2 - \alpha \ \lfloor \theta/\alpha \rfloor \right)}, \quad \text{where } \alpha = \frac{2 \pi}{n}.

.. math:: x(t) = r \cos(t)),

.. math:: y(t) = r \sin(t).



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_RegularConvexPolygon.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D01_RegularConvexPolygon.py>`__.




|Regular_polygon_a| 

.. |Regular_polygon_a| image:: ../_static/ParametricCurves/BasicCurves/RegularConvexPolygon.*
    :width: 30 %



See also: https://en.wikipedia.org/wiki/Star_polygon

See also: https://mathcurve.com/polyedres/regulier/polygoneregulier.shtml



See also: https://mathcurve.com/courbes2d/goursat/goursat.shtml

See also: https://mathcurve.com/courbes3d.gb/polygramme/polygramme.shtml

See also: https://mathcurve.com/courbes3d.gb/billardcylindrique/billardcylindrique.shtml








|newpage|


Circle
------------------------------------------------------------------------------------------


A circle is the set of points in a plane that are equidistant from a given point `O`. The parametric equations for a circle of radius `a` can be given by 


.. math:: x(t) = a \cos(t)),

.. math:: y(t) = a \sin(t).


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram2D101`,  MathCurve :cite:p:`MathCurve2D101`.



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02_Circle.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D02_Circle.py>`__.




|Circle_a|

.. |Circle_a| image:: ../_static/ParametricCurves/BasicCurves/Circle.*
    :width: 30 %







|newpage|


Ellipse
------------------------------------------------------------------------------------------


An ellipse is a plane curve surrounding two focal points, such that for all points on the curve, the sum of the two distances to the focal points is a constant. The parametric equations of a standard ellipse centered at the origin with width `2a` and height `2b` can be given by (with `0 \le t < 2\pi`):

.. math:: x(t) = a \cos(t)),

.. math:: y(t) = b \sin(t).

Assuming `a \ge b`, the focal points are `(\pm \sqrt{a^2-b^2}, 0)`.


See also  Wikipedia :cite:p:`Wikipedia2D102`,  MathWorld :cite:p:`Wolfram2D102`,  MathCurve :cite:p:`MathCurve2D102`.




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03_Ellipse.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D03_Ellipse.py>`__.




|Ellipse_a|

.. |Ellipse_a| image:: ../_static/ParametricCurves/BasicCurves/Ellipse.*
    :width: 30 %








|newpage|


Parabola
-------------------------------------------------------------------------------

A parabola is a plane curve which is mirror-symmetrical and is approximately U-shaped. It fits several superficially different mathematical descriptions, which can all be proved to define exactly the same curves. 

The graph of a quadratic function `y = a x^2 + b x + c` (with `a \ne 0`) is a parabola with its axis parallel to the `y`-axis. Conversely, every such parabola is the graph of a quadratic function.

The surface of revolution obtained by rotating a parabola about its axis of symmetry is called a paraboloid. 

See also:  https://mathworld.wolfram.com/Parabola.html

See also: https://en.wikipedia.org/wiki/Parabola


In polar coordinates, the equation of a parabola with parameter a and center (0, 0) is given by `\displaystyle r(t) = - \frac{2a}{1 + \cos(t)}`. It can also be written parametrically as 

.. math:: x(t) = a t^2,

.. math:: y(t) = 2 a t.



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04_Parabola.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D04_Parabola.py>`__.




|Parabola_a|

.. |Parabola_a| image:: ../_static/ParametricCurves/BasicCurves/Parabola.*
    :width: 30 %








|newpage|


Hyperbola
-------------------------------------------------------------------------------

In polar coordinates, the equation of a hyperbola centered at the origin (i.e., with `x_0=y_0=0`) is `\displaystyle r2(t) = \frac{a^2 b^2}{b^2 \cos^2(t) - a^2 \sin^2(t)}`.

Parametric equations for the right branch of a hyperbola are given by


.. math:: x(t) = a \cosh(t),

.. math:: y(t) = b \sinh(t),

which ranges over the right branch of the hyperbola. 

A parametric representation which ranges over both branches of the hyperbola is


.. math:: x(t) = a \sec(t),

.. math:: y(t) = b \tan(t),

with `t \in (-\pi,\pi)` and discontinuities at `\pm \pi/2`.


See also:  https://mathworld.wolfram.com/Hyperbola.html

See also:  https://mathworld.wolfram.com/ConicSection.html





The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05_Hyperbola.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D05_Hyperbola.py>`__.



|Hyperbola_a|

.. |Hyperbola_a| image:: ../_static/ParametricCurves/BasicCurves/Hyperbola.*
    :width: 30 %







|newpage|


Cycloid
-------------------------------------------------------------------------------


The cycloid is the locus of a point on the rim of a circle of radius a rolling along a straight line. If the cycloid has a cusp at the origin and its humps are oriented upward, its parametric equation is 


.. math:: x(t) = a (t - \sin(t)),

.. math:: y(t) = a (t - \cos(t)).



See also  Wikipedia :cite:p:`Wikipedia2D103`,  MathWorld :cite:p:`Wolfram2D103`,  MathCurve :cite:p:`MathCurve2D103`.





The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06_Cycloid.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D06_Cycloid.py>`__.



|Cycloid_a|

.. |Cycloid_a| image:: ../_static/ParametricCurves/BasicCurves/Cycloid.*
    :width: 30 %






|newpage|


Trochoid
-------------------------------------------------------------------------------


A trochoid is the locus of a point at a distance b from the center of a circle of radius a rolling on a fixed line. A trochoid has parametric equations 


.. math:: x(t) = a t - b \sin(t),

.. math:: y(t) = a t - b \cos(t)).

If `b<a`, the trochoid is known as a curtate cycloid; if `b=a`, it is a cycloid; and if `b>a`, the curve is a prolate cycloid. 


See also  Wikipedia :cite:p:`Wikipedia2D104`,  MathWorld :cite:p:`Wolfram2D104`,  MathCurve :cite:p:`MathCurve2D104`.




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07_Trochoid.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D07_Trochoid.py>`__.



|Trochoid_a|

.. |Trochoid_a| image:: ../_static/ParametricCurves/BasicCurves/Trochoid.*
    :width: 30 %






|newpage|


Cardioid
--------------------------------------------------------------------

In geometry, a cardioid is a plane curve traced by a point on the perimeter of a circle that is rolling around a fixed circle of the same radius.


The polar equation is given by
    
.. math:: r = a (1 - \cos (\theta)).

See also:  Wikipedia :cite:p:`Wikipedia2D201`,  MathWorld :cite:p:`Wolfram2D201`




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D08_Cardioid.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D08_Cardioid.py>`__.




|picCardioid_p|

.. |picCardioid_p| image:: ../_static/ParametricCurves/BasicCurves/Cardioid.*
    :width: 30%






|newpage|


Limaçon curve
---------------------------------------------------------


Returns the curve given by the polar equation 
    
.. math:: r = b + a \cos (\theta).


See also: see also  Wikipedia :cite:p:`Wikipedia2D202`,  MathWorld :cite:p:`Wolfram2D202`



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D09_LimaconCurve.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D09_LimaconCurve.py>`__.





|picLimacon_p|

.. |picLimacon_p| image:: ../_static/ParametricCurves/BasicCurves/Limacon.*
    :width: 30%





|newpage|


Conchoid of de Sluze
--------------------------------------------------------


Returns the curve given by the polar equation 

.. math:: r = \sec(\theta) + a \cos (\theta).


See also: see also  Wikipedia :cite:p:`Wikipedia2D204`,  MathWorld :cite:p:`Wolfram2D204`




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D10_ConchoidOfDeSluze.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D10_ConchoidOfDeSluze.py>`__.



|Conchoid_of_de_Sluze_p_a|

.. |Conchoid_of_de_Sluze_p_a| image:: ../_static/ParametricCurves/BasicCurves/Conchoid_of_de_Sluze.*
    :width: 30%







|newpage|


Freeth's Nephroid
--------------------------------------------------


The curve has the polar equation


.. math:: r = a \left[1 + 2 \sin \left(\tfrac{1}{2} \theta \right) \right]



See also: Wikipedia :cite:p:`Wikipedia2D206`,  MathWorld :cite:p:`Wolfram2D206`




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D11_FreethNephroid.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D11_FreethNephroid.py>`__.



|Freeth_Nephroid_p_a|

.. |Freeth_Nephroid_p_a| image:: ../_static/ParametricCurves/BasicCurves/FreethNephroid.*
    :width: 30%





|newpage|


Strophoid
--------------------------------------------

The name strophoid means "belt with a twist". The polar form for a general strophoid is 

.. math:: r = \frac{b \sin(a - 2 \theta)}{\sin(a - \theta)}


See also: Wikipedia :cite:p:`Wikipedia2D207`,  MathWorld :cite:p:`Wolfram2D207`

A special cases is the right strophoid with `a = \pi/2`.




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D12_Strophoid.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D12_Strophoid.py>`__.




|Strophoid_p_a|

.. |Strophoid_p_a| image:: ../_static/ParametricCurves/BasicCurves/Right_Strophoid.*
    :width: 30%







|newpage|


Cycloid of Ceva
-------------------------------------------

A curve with the polar form

.. math:: r = 1 + 2 \cos(2 \theta).



See also: Wikipedia :cite:p:`Wikipedia2D208`,  MathWorld :cite:p:`Wolfram2D208`



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D13_CycloidOfCeva.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D13_CycloidOfCeva.py>`__.



|Cycloid_of_Ceva_p_a|

.. |Cycloid_of_Ceva_p_a| image:: ../_static/ParametricCurves/BasicCurves/Cycloid_of_Ceva.*
    :width: 30%









|newpage|


Lemniscate of Gerono
-------------------------------------------------------------------------------


This curve is also known as Eight curve. It has parametric equations


.. math:: x(t) = a \sin(t),

.. math:: y(t) = x(t) \cos(t)).


See also  Wikipedia :cite:p:`Wikipedia2D110`,  MathWorld :cite:p:`Wolfram2D110`, MathCurve :cite:p:`MathCurve2D110`.




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D14_LemniscateOfGerono.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D14_LemniscateOfGerono.py>`__.


|Lemniscate_of_Gerono_a|

.. |Lemniscate_of_Gerono_a| image:: ../_static/ParametricCurves/BasicCurves/Lemniscate_of_Gerono.*
    :width: 30 %









|newpage|



Lemniscate of Bernoulli
-------------------------------------------------------------------------------


The lemniscate of Bernoulli is a polar curve defined as the locus of points such that the the product of distances from two fixed points `(-a,0)` and `(a,0)`  is a constant `a^2`. It has parametric equations


.. math:: x(t) = \frac{a \cos(t)}{1 + \sin^2(t)},

.. math:: y(t) = x(t) \sin(t)).


See also  Wikipedia :cite:p:`Wikipedia2D109`,  MathWorld :cite:p:`Wolfram2D109`, MathCurve :cite:p:`MathCurve2D109`.



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D15_LemniscateOfBernoulli.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C02_BasicCurves/D15_LemniscateOfBernoulli.py>`__.



|Lemniscate_of_Bernoulli_a|

.. |Lemniscate_of_Bernoulli_a| image:: ../_static/ParametricCurves/BasicCurves/Lemniscate_of_Bernoulli.*
    :width: 30 %






