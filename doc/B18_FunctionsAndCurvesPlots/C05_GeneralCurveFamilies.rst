

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />








|newpage|



General curve families
==============================================================






Regular star polygon
------------------------------------------------------------------------------------------

There exist infinitely many regular star polytopes in two dimensions, whose Schläfli symbols consist of rational numbers `\{n/m\}`. They are called star polygons and share the same vertex arrangements of the convex regular polygons.



.. math:: r = \frac{a}{\cos \left(t - \alpha/2 - \alpha \ \lfloor \theta/\alpha \rfloor \right)}, \quad \text{where } \alpha = \frac{2 m \pi}{n}.

.. math:: x(t) = r \cos(t)),

.. math:: y(t) = r \sin(t).




See also: https://en.wikipedia.org/wiki/Star_polygon


See also: https://mathworld.wolfram.com/StarPolygon.html



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_RegularStarPolygon.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D01_RegularStarPolygon.py>`__.




|Regular_star_polygon_a|

.. |Regular_star_polygon_a| image:: ../_static/ParametricCurves/General/Regular_StarPolygon.*
    :width: 30 %










|newpage|


Regular compound polygon (polygram)
------------------------------------------------------------------------------------------


The `n` vertices of the regular polygon being determined, all the associated regular polygons are obtained by joining the vertices from `m` to `m`, where `m` is coprime with `n` and between `1` and `n/2`. The case `m = 1` gives the only uncrossed polygon, which is convex.


.. math:: r = \frac{a}{\cos \left(t - \alpha/2 - \alpha \ \lfloor \theta/\alpha \rfloor \right)}, \quad \text{where } \alpha = \frac{2 m \pi}{n}.

.. math:: x(t) = r \cos(t)),

.. math:: y(t) = r \sin(t).



See also: https://en.wikipedia.org/wiki/Polygram_(geometry)#Regular_compound_polygons


See also: https://mathworld.wolfram.com/Polygram.html




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02_Polygram.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D02_Polygram.py>`__.




|Regular_polytope_compound_a| 

.. |Regular_polytope_compound_a| image:: ../_static/ParametricCurves/General/Polygram.*
    :width: 30 %







|newpage|


Epicycloid
---------------------------------------------------------------------------------


The epicycloids are the curves described by a point on a circle `(C)` rolling without slipping on a base circle `(C_0)`, the open disks with boundaries `(C)` and `(C_0)` being disjoint. Therefore, they are special cases of epitrochoids.  An epicycloid has parametric equations 


.. math:: q x(t) = a \left( (q+1) \cos(t) - \cos \left( (q+1) t \right) \right),

.. math:: q y(t) = a \left( (q+1) \sin(t) - \sin \left( (q+1) t \right) \right).


See also  Wikipedia :cite:p:`Wikipedia2D108`,  MathWorld :cite:p:`Wolfram2D108`,  MathCurve :cite:p:`MathCurve2D108`.

The epicycloids are curves composed of isometric arcs (the arches) joining at cuspidal points (obtained for `\displaystyle t = \frac{2\pi}{q}`) in a finite number equal to the numerator of `q` if `q` is rational, or in an infinite number otherwise.

When `q` is rational, `\displaystyle q = \frac{n}{m}`, the curve is algebraic and rational (take `\displaystyle u = \tan \left(\frac{t}{2m} \right)` as a parameter).

Its looks like a regular polygon, crossed if `m \ge 2`, with `n` vertices joined by `m` points by the curves located outside the circle `(C_0)`.

The notation of simple epicycloid with `n` cusps `(E_n)` refers to the case `q = n`, i.e. when there are no crossovers.


Special cases are the cardioid `(q=1)`, the nephroid `(q=2)`, and the double cardioid `(q=1/2)`,




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03_Epicycloid.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D03_Epicycloid.py>`__.



|Epicycloid_a|

.. |Epicycloid_a| image:: ../_static/ParametricCurves/General/Epicycloid.*
    :width: 30 %




|newpage|


Hypocycloid
----------------------------------------------------------------------------------


The hypocycloids are the curves described by a point on a circle `(C)` rolling without slipping on, and inside, a base circle `(C_0)`, when the rolling circle is smaller than the fixed one. Therefore, they are special cases of hypotrochoids. A hypocycloid has parametric equations 


.. math:: q x(t) = a \left( (q-1) \cos(t) - \cos \left( (q-1) t \right) \right),

.. math:: q y(t) = a \left( (q-1) \sin(t) - \sin \left( (q-1) t \right) \right).


See also  Wikipedia :cite:p:`Wikipedia2D105`,  MathWorld :cite:p:`Wolfram2D105`,  MathCurve :cite:p:`MathCurve2D105`.

The hypocycloids are curves composed of isometric arcs (the arches) connecting at cuspidal points (obtained for `\displaystyle t = \frac{2\pi}{q}`) in a finite number equal to the numerator of `q` if `q` is rational, or in an infinite number otherwise.

When `q` is rational, `\displaystyle q = \frac{n}{m}`, the curve is algebraic and rational (take `\displaystyle u = \tan \left(\frac{t}{2m} \right)` as a parameter).

It has the same structure as a regular polygon, crossed if `m \ge 2`, with `n` vertices linked  from `m` to  `m` by curves located inside  the circle `(C_0)`.

The notation of simple hypocycloid  with `n` cusps `(E_n)` refers to the case `q = n`, i.e. when there are no crossings.


Special cases are the point `(q=1)`, the La Hire line `(q=2)`, the deltoid `(q=3)`, and the astroid `(q=4)`.




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04_Hypocycloid.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D04_Hypocycloid.py>`__.



|Hypocycloid_a|

.. |Hypocycloid_a| image:: ../_static/ParametricCurves/General/Hypocycloid.*
    :width: 30 %








|newpage|


Epitrochoid
---------------------------------------------------------------------------------


The epitrochoids are the curves described by a point linked to a circle `(C)` rolling without slipping on a base circle `(C_0)`, the open disks with boundaries `(C)` and `(C_0)` being disjoint. An epitrochoid has parametric equations 


.. math:: q x(t) = a \left( (q+1) \cos(t) - k \cos \left( (q+1) t \right) \right),

.. math:: q y(t) = a \left( (q+1) \sin(t) - k \sin \left( (q+1) t \right) \right).


See also  Wikipedia :cite:p:`Wikipedia2D107`,  MathWorld :cite:p:`Wolfram2D107`,  MathCurve :cite:p:`MathCurve2D107`.



For `d = a + b`, we get the roses.

For `k < 1`, the curve is also called shortened epicycloid.

For `k > 1`, the curve is also called elongated epicycloid.

The limit case is `\displaystyle k = \frac{1}{q+1}`; there is then a flat point.

For `\displaystyle \frac{1}{q+1} < k < 1`, the curve undulates, with points of inflection.

For `k = 1`, we obtain the epicycloid, with cusps.

For `1<k<q+1`, the curve makes loops, with concave and convex portions, (positive angular speed, then negative alternately).

For `k = q + 1`, we get a rose with index `n < 1` , of polar equation `\displaystyle \rho = 2 d \cos \frac{q}{q+2} \theta`.

The case `k>q-1` leads to a more complicated pattern.




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05_Epitrochoids.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D05_Epitrochoids.py>`__.


The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05_EpitrochoidCS.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D05_EpitrochoidCS.py>`__.



|Epitrochoid_a| `\quad` |Epitrochoid_b|

.. |Epitrochoid_a| image:: ../_static/ParametricCurves/General/Epitrochoid.*
    :width: 30 %

.. |Epitrochoid_b| image:: ../_static/ParametricCurves/General/EpitrochoidCS.*
    :width: 30 %






|newpage|


Hypotrochoid
----------------------------------------------------------------------------------


The hypotrochoids are the curves described by a point linked to a circle `(C)` rolling without slipping internally on a base circle `(C0)`. A hypocycloid has parametric equations 


.. math:: q x(t) = a \left( (q-1) \cos(t) - k \cos \left( (q-1) t \right) \right),

.. math:: q y(t) = a \left( (q-1) \sin(t) - k \sin \left( (q-1) t \right) \right).


See also  Wikipedia :cite:p:`Wikipedia2D106`,  MathWorld :cite:p:`Wolfram2D106`,  MathCurve :cite:p:`MathCurve2D106`.


For  `k = 1`, we get the hypocycloids.

If `a` is fixed but `q` is changed into  `\displaystyle \frac{q}{q-1}` and k into  `\displaystyle \frac{1}{k}`, then the hypotrochoid obtained is the homothetic image of the initial one with ratio `k`. Therefore, we get all the hypotrochoids by considering only the case `q \ge 2`.

For `q = 2`, we get the ellipses.

For `q > 2`, the curve is also called curtate hypocycloid if `k < 1`, and prolate hypocycloid if `k > 1`.

However, according to the preceding paragraph, in the case `1 < q < 2`, the curtate hypocycloids are paradoxically obtained for `k > 1` and the prolate ones for `k < 1`.

For `k = q - 1`, we get a rose of index `n > 1`.

The hypocycloid with parameter `q = n/m` constitutes a "rounded" approximation of the regular polygon of type `(n, m)`; for the portions between two vertices to be as linear as possible, we can consider the limit case where this portion does not have an inflexion point, which corresponds to the case `k = 1 / (q - 1)`.




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06_Hypotrochoid.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D06_Hypotrochoid.py>`__.



|Hypotrochoid_a|

.. |Hypotrochoid_a| image:: ../_static/ParametricCurves/General/Hypotrochoid.*
    :width: 30 %













|newpage|


Rose curve
---------------------------------------------------------------------------


A rose curve, also called Grandi's rose or the multifolium, is a curve which has the shape of a petalled flower. The polar equation of the rose is generally given as `r = a \cos(nt)` or by the version rotated  by 90 degrees, `r = a \sin(nt)`. The sine version has the advantage that roses with odd `n` have a petal oriented vertically (up or down depending on `n`), whereas the cosine orientation gives a petal oriented to the right.

See also  Wikipedia :cite:p:`Wikipedia2D205`,  MathWorld :cite:p:`Wolfram2D205`, MathCurve :cite:p:`MathCurve2D205`.

If `n` is odd, the rose is `n`-petalled. If `n` is even, the rose is `2n`-petalled. 

The curve is algrebraic iff `n=p/q` is rational, with degree `p+q` when `pq` is odd and `2(p+q)` when `pq` is even. 

If `n=p/q` is a rational number, then the curve closes at a polar angle of `\theta = \pi q m`, where `m=1` if `pq` is odd and `m=2` if `pq` is even. If `n` is irrational, then there are an infinite number of petals. For `n>1` the curve is a hypotrochoid, and for `0<n<1` it is an epitrochoid. The roses are views from above of the clelias.


Special cases are the limaçon trisectrix (`n = 1/3`), the Dürer folium (`n=1/2`), the circle (`n=1`), the quadrifolium (`n=2`) and the trifolium (`n=3`).



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07_RoseCurve.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D07_RoseCurve.py>`__.



|Rose_curve_a|

.. |Rose_curve_a| image:: ../_static/ParametricCurves/General/Rose_Curve.*
    :width: 30 %







|newpage|



Lissajous curves
----------------------------------------------------------

Lissajous curves are the family of curves described by the parametric equations


.. math:: x(t) = a \sin(\omega t + \delta),

.. math:: y(t) = b \sin(t).


See also  Wikipedia :cite:p:`Wikipedia2D114`,  MathWorld :cite:p:`Wolfram2D114`, MathCurve :cite:p:`MathCurve2D114`.


Special cases are the line (`\omega = 1, \delta = 0`), the circle  (`a=b, \omega = 1, \delta = \pi/2`), the ellipse  (`a=b, \omega = 1, \delta = \pi/2`), the section of a parabola (`\omega = 2, \delta = \pi/2`).



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D08_LissajousCurve.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D08_LissajousCurve.py>`__.


|Lissajous_curve_a|

.. |Lissajous_curve_a| image:: ../_static/ParametricCurves/General/Lissajous_Curve.*
    :width: 30 %










|newpage|



Superellipses (Lamé curves)
----------------------------------------------------------


Superellipses are the family of curves described by the parametric equations


.. math:: x(t) = |\cos(t)|^{2/r} \cdot a \cdot \mathrm{sgn}(\cos(t)),

.. math:: y(t) = |\sin(t)|^{2/r} \cdot b \cdot \mathrm{sgn}(\sin(t)),

with `0 \le t \le \pi/2`.


See also  Wikipedia :cite:p:`Wikipedia2D113`,  MathWorld :cite:p:`Wolfram2D113`, MathCurve :cite:p:`MathCurve2D113`.

    The restriction to r>2 is sometimes made.

The generalization to a three-dimensional surface is known as a superellipsoid.

Superellipses with a=b are also known as Lamé curves or Lamé ovals, and the case `a=b` with `r=4` is sometimes known as the squircle.

Special cases are the astroid (`r =2/3`), the diamond (`r =1`), the ellipse (`r =2`).




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D09_Superellipses.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D09_Superellipses.py>`__.


|Lame_curve_a|

.. |Lame_curve_a| image:: ../_static/ParametricCurves/General/Superellipse.*
    :width: 30 %





|newpage|


Epispirals
------------------------------------------------------------------------


The epispirals are solutions of the problem that consists in determining the trajectories in space of a massive point subject to a force centred on `O` proportional to `\displaystyle \frac{1}{\rho^3}` (this force is, thanks to the Binet formula, proportional to `\displaystyle u^2 (u + u'')` which is here `\displaystyle (1+n^2)u^2`, with `\displaystyle u = \frac{1}{\rho}`); the other solutions are the Poinsot spirals, with intermediary case the hyperbolic spiral.


The curve is composed of an infinite branch obtained for `\displaystyle -\frac{\pi}{2n} < 0 < \frac{\pi}{2n}`, and of all its images by rotations by angle `\displaystyle k \left(\pi + \frac{\pi}{n} \right)` for integer values of `k`. When `n` is a rational number with numerator `p`, and denominator `q`, the curve is symmetrical about `O` iff `p` or `q` is even.

In this case, the curve is composed of `2p` branches derived from the initial branch by rotations by angles `\displaystyle \frac{2 k \pi}{n}` and `\displaystyle \frac{2 k \pi}{n} + \pi`.



Special cases are the line (`n=1`), the crosscurve (`n=2`), the rectangukar trefoil (`n=3`), the Delanges trisectrix (`n=1/2`), the MacLaurin trisectrix (`n=1/3`).



See also  Wikipedia :cite:p:`Wikipedia2D214`,  MathWorld :cite:p:`Wolfram2D214`,  MathCurve :cite:p:`MathCurve2D214`.



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D10_Epispirals.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D10_Epispirals.py>`__.



|Epispiral_a|

.. |Epispiral_a| image:: ../_static/ParametricCurves/General/Epispiral.*
    :width: 30 %









|newpage|


Nodal curves (stereographic projections of the clelia)
------------------------------------------------------------------------


Polar equation: `\rho = a \tan (n \theta)`.

The nodal curves are the Brocard transforms of the Kappa, when the pole is at the centre of the Kappa. Each curve is composed of an infinite branch, the base, obtained for `\displaystyle -\frac{\pi}{2n} < 0 < \frac{\pi}{2n}`, and all its images by the rotations of angle `\displaystyle k \frac{\pi}{n}` when `k` is an integer.

If n is rational and its numerator is p and its denominator q, then the curve is composed of 2p branches, images of the base branch by rotation when q is odd, and p branches when it is even. 

Special cases are the Kappa (`n=1`), the windmill (`n=2`),the right strophoid (`n=1/2`).

All nodal curves are stereographic projections of the clelia.
The inverse (with centre `O` and radius `a^2`) of a nodal curve is the same curve turned by `\displaystyle \frac{\pi}{2n}`.


See also:  MathCurve :cite:p:`MathCurve2D223`.



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D11_NodalCurves.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D11_NodalCurves.py>`__.


|Nodal_curve_a|

.. |Nodal_curve_a| image:: ../_static/ParametricCurves/General/Nodal_Curve.*
    :width: 30 %











|newpage|


Cyclic-harmonic curves
------------------------------------------------------------------------


Polar equation: `\rho = a (1 + e \cos (n \theta)`.

The cyclic-harmonic curves are the conchoids of roses with respect to their centre.
The curve is composed of a base pattern, symmetrical about Ox, obtained for  `\displaystyle -\frac{\pi}{n} \le 0 \le \frac{\pi}{n}`, transformed by all the rotations of `\displaystyle 2 k \frac{\pi}{n}` for integer values of `k`. When `n` is a rational number and `p` is its numerator, `p` rotations give the whole curve.

Case `e < 1`:
For `n = p / q`, the cyclic-harmonic curve of parameter `n` is one of the possible projections of the Turk's head knot of type `(p,q)`; its `p` external summits and its `p` internal vertices form a regular polygon, and it has `p(q-1)` double points.

Special cases are the trefoil knot (`n=3/2`), the projection of the 5.1 knot  (`n=5/2`) the projection of the figure-eight knot  (`n=2/3`).


Case `e = 1`:

Special cases are the cardioid for `n=1` (see also  Wikipedia :cite:p:`Wikipedia2D201`,  MathWorld :cite:p:`Wolfram2D201`,  MathCurve :cite:p:`MathCurve2D201`), the double egg (`n=2`)



Case `e > 1`:

Special cases are the limaçon of Pascal for `n=1` (see also  Wikipedia :cite:p:`Wikipedia2D202`,  MathWorld :cite:p:`Wolfram2D202`,  MathCurve :cite:p:`MathCurve2D202`), the cycloid (or trisectrix) of Ceva for `n=2`  (see also  Wikipedia :cite:p:`Wikipedia2D208`,  MathWorld :cite:p:`Wolfram2D208`,  MathCurve :cite:p:`MathCurve2D208`), and Freeth's nephroid for `n=1/2`  (see also  Wikipedia :cite:p:`Wikipedia2D206`,  MathWorld :cite:p:`Wolfram2D206`,  MathCurve :cite:p:`MathCurve2D206`).



See also:  MathCurve :cite:p:`MathCurve2D224`.



The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D12_CyclicHarmonicCurves.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D12_CyclicHarmonicCurves.py>`__.


|Cyclic_harmonic_curve_a|

.. |Cyclic_harmonic_curve_a| image:: ../_static/ParametricCurves/General/CyclicHarmonic_Curve.*
    :width: 30 %




|newpage|


Rational circular cubics
------------------------------------------------------------------------


The rational circular cubics have the following parametrization (see  MathCurve :cite:p:`MathCurve2D225`):

.. math:: x(t) = \frac{d t^2 + 2bt + 2a + d}{1 + t^2}

.. math:: y(t) =  \frac{d t^3 + 2bt^2 + 2at + d t}{1 + t^2} = t x(t).

They have a real singularity (see  Wikipedia :cite:p:`Wikipedia2D227`), which is necessarily unique.

* For `\sqrt{a^2+b^2} > |a+d|`, the cubic is called crunodal, i.e. this singularity is a double point with different tangents (see  Wikipedia :cite:p:`Wikipedia2D228`,  MathWorld :cite:p:`Wolfram2D228`).

* For `\sqrt{a^2+b^2} = |a+d|`, the cubic is called cuspidal, i.e. this singularity is a cuspidal point (see  Wikipedia :cite:p:`Wikipedia2D229`,  MathWorld :cite:p:`Wolfram2D229`).

* For `\sqrt{a^2+b^2} < |a+d|`, the cubic is called acnodal, i.e. this singularity is an isolated point (see  Wikipedia :cite:p:`Wikipedia2D230`,  MathWorld :cite:p:`Wolfram2D230`).


Many other parametric curves can be obtained as special cases:



* For `b=0`, we get the right rational circular cubics  (see also: MathCurve :cite:p:`MathCurve2D226`).


* For `\sqrt{a^2+b^2} = |a+d|`, we get the cissoids (see Wikipedia :cite:p:`Wikipedia2D231`,  MathWorld :cite:p:`Wolfram2D231`,  MathCurve :cite:p:`MathCurve2D231`).


* For `d=-a`, we get the strophoids (see Wikipedia :cite:p:`Wikipedia2D207`,  MathWorld :cite:p:`Wolfram2D207`,  MathCurve :cite:p:`MathCurve2D207`).



* For `a = -2d, b = 0`, we get the Maclaurin trisectrix (see Wikipedia :cite:p:`Wikipedia2D232`,  MathWorld :cite:p:`Wolfram2D232`,  MathCurve :cite:p:`MathCurve2D232`).



* In the right and acnodal case (i.e. b = 0, d > 0), we get the cubic (or conchoid) of de Sluze (see Wikipedia :cite:p:`Wikipedia2D204`,  MathWorld :cite:p:`Wolfram2D204`,  MathCurve :cite:p:`MathCurve2D204`).




The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D13_RationalCircularCubics.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B18_FunctionsAndCurvesPlots/C05_GeneralCurveFamilies/D13_RationalCircularCubics.py>`__.


|RccMacLauren_a|

.. |RccMacLauren_a| image:: ../_static/ParametricCurves/General/Maclaurin_trisectrix.*
    :width: 30 %















