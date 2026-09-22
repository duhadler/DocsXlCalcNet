

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />








|newpage|




Generalisations of common surfaces
==============================================



Parametric Surfaces: `x=f(u,v),` `y=g(u,v),` `z=h(u,v)`



Ellipsoid
-------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D01a_Ellipsoid.3D.xml (D01a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D01a_Ellipsoid.3D.xml>`__.


    The parametric equations of an ellipsoid can be written as 


.. math:: x(u, v) = a \cos(u) \sin(v),

.. math:: y(u, v) = b \sin(u) \sin(v),

.. math:: z(u, v) = r \sin(t),

for `u \in [0, 2 \pi)` and `v \in [0, \pi]`.


See also: http://paulbourke.net/geometry/spherical/
See also: https://mathcurve.com/surfaces.gb/lame/lame.shtml
See also: https://mathworld.wolfram.com/Ellipsoid.html        

See also  :cite:t:`Gray2006`,  :cite:t:`Krivoshapko2015`.

    

.. code-block:: text

    var a = 1.0;
    var b = 2.0;
    var c = 3.0;
    var x = a * Math.Cos(u) * Math.Cos(v);
    var y = b * Math.Cos(u) * Math.Sin(v);
    var z = c * Math.Sin(u);



If the lengths of two axes of an ellipsoid are the same, the figure is called an ellipsoid of revolution or spheroid. Denote the equal semi-axes lengths of a spheroid `a=b`, call `a` the equatorial radius, and call the other semi-axis length the polar radius `c`. Then if `a>c`, the spheroid is called an oblate spheroid, and if `a<c`, the spheroid is called an prolate spheroid. If all three semi-axes lengths are the same so `a=b=c`, the ellipsoid is a sphere. 



|01a_Ellipsoid.3D| `\quad` |01b_Ellipsoid.3D| `\quad` |01c_Ellipsoid.3D|



.. |01a_Ellipsoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/01a_Ellipsoid.3D.jpg
   :width: 30 %


.. |01b_Ellipsoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/01b_Ellipsoid.3D.jpg
   :width: 30 %


.. |01c_Ellipsoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/01c_Ellipsoid.3D.jpg
   :width: 30 %










|newpage|



Superellipsoid
------------------------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D02a_SuperEllipse.3D.xml (D02a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D02a_SuperEllipse.3D.xml>`__.


Superellipsoid is the name given to a family of shapes formed from the spherical product of two superquadratric curves. These shapes can be used to model a wide range of shapes including spheres, cylinders, and parallelepipeds as well as shapes in between. The parametric equations of an superellipsoid can be written as 


.. math:: x(u, v) =  \mathrm{sgn}(\cos(u)) \cdot |\cos(u)| ^{p1} \cdot \mathrm{sgn}(\cos(v)) \cdot |\cos(v)|^{p2},

.. math:: y(u, v) =  \mathrm{sgn}(\cos(u)) \cdot |\cos(u)| ^{p1} \cdot \mathrm{sgn}(\sin(v)) \cdot |\sin(v)|^{p2},

.. math:: z(u, v) = \mathrm{sgn}(\sin(u)) \cdot |\sin(u)|^{p1},

where `\displaystyle \frac{-\pi}{2} \le u  \le \frac{\pi}{2}`, `-\pi \le v  \le \pi`, and `0 < p1, p2 < \infty`.



.. code-block:: text

    double p1 = 2.0;
    double p2 = 3.8; 

    double u = u;
    double v = v;

    \cos(u) = Math.Cos(u);
    \cos(v) = Math.Cos(v);
    \sin(u) = Math.Sin(u);
    \sin(v) = Math.Sin(v);

    tmp  = Math.Sign(\cos(u)) * Math.Pow(Math.Abs(\cos(u)),p1);
    x = tmp * Math.Sign(\cos(v)) * Math.Pow(Math.Abs(\cos(v)),p2);
    y = -Math.Sign(\sin(u)) * Math.Pow(Math.Abs(\sin(u)),p1);
    z = tmp * Math.Sign(\sin(v)) * Math.Pow(Math.Abs(\sin(v)),p2);



|02a_SuperEllipse.3D| `\quad` |02b_SuperEllipse.3D| `\quad` |02c_SuperEllipse.3D|



.. |02a_SuperEllipse.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/02a_SuperEllipse.3D.jpg
   :width: 30 %


.. |02b_SuperEllipse.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/02b_SuperEllipse.3D.jpg
   :width: 30 %


.. |02c_SuperEllipse.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/02c_SuperEllipse.3D.jpg
   :width: 30 %








|newpage|


Hexaedron
-------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D03a_Hexaedron.3D.xml (D03a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D03a_Hexaedron.3D.xml>`__.


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.


.. code-block:: csharp

    double cosu = Math.Cos(u);
    double sinu = Math.Sin(u);
    double cosv = Math.Cos(v);
    double sinv = Math.Sin(v);
    x = cosv * cosv * cosv * cosu * cosu * cosu;
    y = -sinu * sinu * sinu;
    z = sinv * sinv * sinv * cosu * cosu * cosu;



|03a_Hexaedron.3D| `\quad` |03b_Hexaedron.3D| `\quad` |03c_Hexaedron.3D|



.. |03a_Hexaedron.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/03a_Hexaedron.3D.jpg
   :width: 30 %


.. |03b_Hexaedron.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/03b_Hexaedron.3D.jpg
   :width: 30 %


.. |03c_Hexaedron.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/03c_Hexaedron.3D.jpg
   :width: 30 %










|newpage|


Super Toroid
------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D04a_SuperToroid.3D.xml (D04a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D04a_SuperToroid.3D.xml>`__.


See also: http://paulbourke.net/geometry/toroidal/


|04a_SuperToroid.3D| `\quad` |04b_SuperToroid.3D| `\quad` |04c_SuperToroid.3D|



.. |04a_SuperToroid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/04a_SuperToroid.3D.jpg
   :width: 30 %


.. |04b_SuperToroid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/04b_SuperToroid.3D.jpg
   :width: 30 %


.. |04c_SuperToroid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/04c_SuperToroid.3D.jpg
   :width: 30 %





.. code-block:: csharp

    double r0 = 1;
    double r1 = 0.3;
                
    double tmp;
    double ct1,ct2,st1,st2;
                
    double p1 = 2.0;
    double p2 = 3.8; 
    double t1 = u;
    double t2 = v;
                
    ct1 = Math.Cos(t1);
    ct2 = Math.Cos(t2);
    st1 = Math.Sin(t1);
    st2 = Math.Sin(t2);
                
    tmp  = r0 + r1 * Math.Sign(ct2) * Math.Pow(Math.Abs(ct2),p2);

    x = tmp * Math.Sign(ct1) * Math.Pow(Math.Abs(ct1),p1);
    y = -tmp * Math.Sign(st1) * Math.Pow(Math.Abs(st1),p1);
    z = r1 * Math.Sign(st2) * Math.Pow(Math.Abs(st2),p2);






|newpage|


Elliptic Helicoid
-----------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D05a_EllipticHelicoid.3D.xml (D05a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D05a_EllipticHelicoid.3D.xml>`__.


See also: https://mathworld.wolfram.com/EllipticHelicoid.html


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.




|05a_EllipticHelicoid.3D| `\quad` |05b_EllipticHelicoid.3D| `\quad` |05c_EllipticHelicoid.3D|



.. |05a_EllipticHelicoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/05a_EllipticHelicoid.3D.jpg
   :width: 30 %


.. |05b_EllipticHelicoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/05b_EllipticHelicoid.3D.jpg
   :width: 30 %


.. |05c_EllipticHelicoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/05c_EllipticHelicoid.3D.jpg
   :width: 30 %




.. code-block:: csharp

    double a = 0.5;
    double b = 1.5;
    double c = 1;
    double su = Math.Sin(u);
    double cu = Math.Cos(u);
                
    x = a * v * cu;
    z = b * v * su;
    y = c * u;





|newpage|


Hyperbolic Helicoid
-----------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D06a_Hyperhelicoid.3D.xml (D06a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D06a_Hyperhelicoid.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    var x = (Math.Sinh(v) * Math.Cos(3 * u)) / (1 + Math.Cosh(u) * Math.Cosh(v));
    var y = (Math.Sinh(v) * Math.Sin(3 * u)) / (1 + Math.Cosh(u) * Math.Cosh(v));
    var z = (Math.Cosh(v) * Math.Sinh(u)) / (1 + Math.Cosh(u) * Math.Cosh(v));



See also: https://mathworld.wolfram.com/HyperbolicHelicoid.html

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.




|06a_Hyperhelicoid.3D| `\quad` |06b_Hyperhelicoid.3D| `\quad` |06c_Hyperhelicoid.3D|



.. |06a_Hyperhelicoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/06a_Hyperhelicoid.3D.jpg
   :width: 30 %


.. |06b_Hyperhelicoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/06b_Hyperhelicoid.3D.jpg
   :width: 30 %


.. |06c_Hyperhelicoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/06c_Hyperhelicoid.3D.jpg
   :width: 30 %






   
|newpage|


Lemniscate
---------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D07a_Lemniscate.3D.xml (D07a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D07a_Lemnescate.3D.xml>`__.


See also: http://paulbourke.net/geometry/lemniscape/



.. code-block:: csharp

    var x = Math.Cos(v) * Math.Sqrt(Math.Abs(Math.Sin(2 * u))) * Math.Cos(u);
    var y = Math.Cos(v) * Math.Sqrt(Math.Abs(Math.Sin(2 * u))) * Math.Sin(u);
    var z = x * x - y * y + 2 * x * y * Math.Tan(v) * Math.Tan(v);




|07a_Lemnescate.3D| `\quad` |07b_Lemnescate.3D| `\quad` |07c_Lemnescate.3D|



.. |07a_Lemnescate.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/07a_Lemnescate.3D.jpg
   :width: 30 %


.. |07b_Lemnescate.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/07b_Lemnescate.3D.jpg
   :width: 30 %


.. |07c_Lemnescate.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/07c_Lemnescate.3D.jpg
   :width: 30 %










|newpage|


Bohemian Dome
-------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D08a_BohemianDome.3D.xml (D08a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D08a_BohemianDome.3D.xml>`__.


See also: https://mathworld.wolfram.com/BohemianDome.html

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.


.. code-block:: csharp

    var a = 0.5;
    var b = 1.5;
    var c = 1;
    var su = Math.Sin(u);
    var sv = Math.Sin(v);
    var cu = Math.Cos(u);
    var cv = Math.Cos(v);

    var x = a * cu;
    var z = b * cv + a * su;
    var y = c * sv;





|08a_BohemianDome.3D| `\quad` |08b_BohemianDome.3D| `\quad` |08c_BohemianDome.3D|



.. |08a_BohemianDome.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/08a_BohemianDome.3D.jpg
   :width: 30 %


.. |08b_BohemianDome.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/08b_BohemianDome.3D.jpg
   :width: 30 %


.. |08c_BohemianDome.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/08c_BohemianDome.3D.jpg
   :width: 30 %















|newpage|


Dupin1 surface
-----------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D09a_Dupin1.3D.xml (D09a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D09a_Dupin1.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    var a = 1.5;
    var b = 1.4;
    var c = Math.Sqrt(a * a - b * b);
    var d = b / 2;
    var su = Math.Sin(u);
    var sv = Math.Sin(v);
    var cu = Math.Cos(u);
    var cv = Math.Cos(v);
    var den = a - c * cu * cv;

    var x = (b * sv * (c * cu - d)) / den;
    var y = (d * (c - a * cu * cv) + b * b * cu) / den;
    var z = (b * su * (a - d * cv)) / den;



See also: https://mathcurve.com/surfaces.gb/cycliddedupin/cyclidededupin.shtml

See also: https://en.wikipedia.org/wiki/Dupin_cyclide#Elliptic_cyclides


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



|09a_Dupin1.3D| `\quad` |09b_Dupin1.3D| `\quad` |09c_Dupin1.3D|



.. |09a_Dupin1.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/09a_Dupin1.3D.jpg
   :width: 30 %


.. |09b_Dupin1.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/09b_Dupin1.3D.jpg
   :width: 30 %


.. |09c_Dupin1.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/09c_Dupin1.3D.jpg
   :width: 30 %







|newpage|


Dupin2 surface
-------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D10a_Dupin2.3D.xml (D10a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D10a_Dupin2.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    var p = 2;
    var k = 0.7;
    var den = 1 + u * u + v * v;
    var x = 0.5 * p * (2 * v * v + k * (1 - u * u - v * v)) / den;
    var y = p * u * (v * v + k) / den;
    var z = p * v * (1 + u * u - k) / den;


See also: https://mathcurve.com/surfaces.gb/cycliddedupin/cyclidededupin.shtml

See also: https://en.wikipedia.org/wiki/Dupin_cyclide#Parabolic_cyclides

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



|10a_Dupin2.3D| `\quad` |10b_Dupin2.3D| `\quad` |10c_Dupin2.3D|



.. |10a_Dupin2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/10a_Dupin2.3D.jpg
   :width: 30 %


.. |10b_Dupin2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/10b_Dupin2.3D.jpg
   :width: 30 %


.. |10c_Dupin2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/10c_Dupin2.3D.jpg
   :width: 30 %








|newpage|


Dinis Surface (twisted pseudosphere)
------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D11a_Dini.3D.xml (D11a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D11a_Dini.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    var a = 1;
    var b = 0.2;
    var x = a * Math.Cos(u) * Math.Sin(v);
    var y = a * Math.Sin(u) * Math.Sin(v);
    var z = a * (Math.Cos(v) + Math.Log(Math.Tan(0.5 * v))) + b * u;


See also: https://mathworld.wolfram.com/DinisSurface.html

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



|11a_Dini.3D| `\quad` |11b_Dini.3D| `\quad` |11c_Dini.3D|



.. |11a_Dini.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/11a_Dini.3D.jpg
   :height: 300 px


.. |11b_Dini.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/11b_Dini.3D.jpg
   :height: 300 px


.. |11c_Dini.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/11c_Dini.3D.jpg
   :height: 300 px








|newpage|



Plueckers conoid
-----------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D12a_Pluecker.3D.xml (D12a-f) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D12a_Pluecker.3D.xml>`__.


// See : https://mathworld.wolfram.com/PlueckersConoid.html
// See : Gray, p. 436
// See : https://en.wikipedia.org/wiki/Pl%C3%BCcker%27s_conoid


.. code-block:: csharp

    var n = 2;
    var r = u;
    var theta = v;

    var x = r * Math.Cos(theta);
    var y = r * Math.Sin(theta);
    var z = Math.Sin(n * theta);



|12a_Pluecker.3D| `\quad` |12b_Pluecker.3D| `\quad` |12c_Pluecker.3D|



.. |12a_Pluecker.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/12a_Pluecker.3D.jpg
   :width: 30 %


.. |12b_Pluecker.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/12b_Pluecker.3D.jpg
   :width: 30 %


.. |12c_Pluecker.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/12c_Pluecker.3D.jpg
   :width: 30 %




|12d_Pluecker.3D| `\quad` |12e_Pluecker.3D| `\quad` |12f_Pluecker.3D|



.. |12d_Pluecker.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/12d_Pluecker.3D.jpg
   :width: 30 %


.. |12e_Pluecker.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/12e_Pluecker.3D.jpg
   :width: 30 %


.. |12f_Pluecker.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/12f_Pluecker.3D.jpg
   :width: 30 %





References

Gray, A. "Plücker's Conoid." Modern Differential Geometry of Curves and Surfaces with Mathematica, 2nd ed. Boca Raton, FL: CRC Press, pp. 435-437, 1997.











|newpage|


Umbilic Torus
----------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D13a_UmbilicTorus.3D.xml (D13a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D13a_UmbilicTorus.3D.xml>`__.


.. code-block:: csharp

    var x = Math.Cos(u) * (7 + Math.Cos(u / 3 - 2 * v) + 2 * Math.Cos(u / 3 + v));
    var y = Math.Sin(u) * (7 + Math.Cos(u / 3 - 2 * v) + 2 * Math.Cos(u / 3 + v));
    var z = Math.Sin(u / 3 - 2 * v) + 2 * Math.Sin(u / 3 + v);


// See also: http://www.3d-meier.de/tut3/Seite61.html  // Umbilic Torus



|13a_UmbilicTorus.3D| `\quad` |13b_UmbilicTorus.3D| `\quad` |13c_UmbilicTorus.3D|



.. |13a_UmbilicTorus.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/13a_UmbilicTorus.3D.jpg
   :width: 30 %


.. |13b_UmbilicTorus.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/13b_UmbilicTorus.3D.jpg
   :width: 30 %


.. |13c_UmbilicTorus.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/13c_UmbilicTorus.3D.jpg
   :width: 30 %





|newpage|


Skidian's ruled surface
-----------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D14a_Skidan.3D.xml (D14a-f) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D14a_Skidan.3D.xml>`__.


.. code-block:: csharp

    var a = Math.PI / 4.0;
    var h = 2.0;
    var n = 4.0;

    var b = h * Math.Abs(Math.Cos(n * v));
    var ca = Math.Cos(a);
    var sa = Math.Sin(a);

    var x = (u * sa + b * ca) * Math.Sin(v);
    var y = (u * sa + b * ca) * Math.Cos(v);
    var z = (u * ca - b * sa);


// See also: http://www.3d-meier.de/tut3/Seite227.html  // Skidan Ruled Surface
// See Krivoshapko, p. 499



|14a_Skidan.3D| `\quad` |14b_Skidan.3D| `\quad` |14c_Skidan.3D|



.. |14a_Skidan.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/14a_Skidan.3D.jpg
   :width: 30 %


.. |14b_Skidan.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/14b_Skidan.3D.jpg
   :width: 30 %


.. |14c_Skidan.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/14c_Skidan.3D.jpg
   :width: 30 %







|14d_Skidan.3D| `\quad` |14e_Skidan.3D| `\quad` |14f_Skidan.3D|



.. |14d_Skidan.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/14d_Skidan.3D.jpg
   :width: 30 %


.. |14e_Skidan.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/14e_Skidan.3D.jpg
   :width: 30 %


.. |14f_Skidan.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/14f_Skidan.3D.jpg
   :width: 30 %





|newpage|


Umbrella surface
------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D15a_Umbrella.3D.xml (D15a-f) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D15a_Umbrella.3D.xml>`__.


.. code-block:: csharp

    var R = 0.6;
    var h = 0.6;
    var n = 8.0;

    var r = R / n;
    var x = ctx.cbrt(u) * ((R - r)) * Math.Cos(v) + r * Math.Cos((n - 1) * v);
    var y = ctx.cbrt(u) * ((R - r)) * Math.Sin(v) - r * Math.Sin((n - 1) * v);
    var z = h * (1 - u);


// See also: http://www.3d-meier.de/tut3/Seite215.html  // Umbrella Surface
// See Krivoshapko, p. 507 - 509 
// See Krivoshapko, p. 513 - 515 
// See Krivoshapko, p. 521, 526, 530, 531, 533



|15a_Umbrella.3D| `\quad` |15b_Umbrella.3D| `\quad` |15c_Umbrella.3D|



.. |15a_Umbrella.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/15a_Umbrella.3D.jpg
   :width: 30 %


.. |15b_Umbrella.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/15b_Umbrella.3D.jpg
   :width: 30 %


.. |15c_Umbrella.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/15c_Umbrella.3D.jpg
   :width: 30 %





|15d_Umbrella.3D| `\quad` |15e_Umbrella.3D| `\quad` |15f_Umbrella.3D|



.. |15d_Umbrella.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/15d_Umbrella.3D.jpg
   :width: 30 %


.. |15e_Umbrella.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/15e_Umbrella.3D.jpg
   :width: 30 %


.. |15f_Umbrella.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/15f_Umbrella.3D.jpg
   :width: 30 %




|newpage|


Cyclic surfaces (generalized torus)
---------------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D16a_CyclicSurface1.3D.xml (D16a-n) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D16a_CyclicSurface1.3D.xml>`__.


.. code-block:: csharp

    var a = 1.0;
    var b = 2.0;
    var d = 0.0;
    var p = 1.0;

    var R = a * (1 - d * Math.Cos(p * u));
    var x = (b + R * Math.Cos(v)) * Math.Cos(u);
    var y = (b + R * Math.Cos(v)) * Math.Sin(u);
    var z = R * Math.Sin(v);


// See Krivoshapko, p. 376




|16a_CyclicSurface1.3D| `\quad` |16b_CyclicSurface2.3D| `\quad` |16c_CyclicSurface1.3D|



.. |16a_CyclicSurface1.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16a_CyclicSurface1.3D.jpg
   :width: 30 %


.. |16b_CyclicSurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16b_CyclicSurface2.3D.jpg
   :width: 30 %


.. |16c_CyclicSurface1.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16c_CyclicSurface1.3D.jpg
   :width: 30 %





|16d_CyclicSurface2.3D| `\quad` |16e_CyclicSurface2.3D| `\quad` |16f_CyclicSurface2.3D|



.. |16d_CyclicSurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16d_CyclicSurface2.3D.jpg
   :width: 30 %


.. |16e_CyclicSurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16e_CyclicSurface2.3D.jpg
   :width: 30 %


.. |16f_CyclicSurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16f_CyclicSurface2.3D.jpg
   :width: 30 %








|16g_CyclicSurface2.3D| `\quad` |16h_CyclicSurface2.3D| `\quad` |16i_CyclicSurface2.3D|



.. |16g_CyclicSurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16g_CyclicSurface2.3D.jpg
   :width: 30 %


.. |16h_CyclicSurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16h_CyclicSurface2.3D.jpg
   :width: 30 %


.. |16i_CyclicSurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16i_CyclicSurface2.3D.jpg
   :width: 30 %
   






|16j_CyclicSurface2.3D| `\quad` |16k_CyclicSurface2.3D| `\quad` |16l_CyclicSurface3.3D|



.. |16j_CyclicSurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16j_CyclicSurface2.3D.jpg
   :width: 30 %


.. |16k_CyclicSurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16k_CyclicSurface2.3D.jpg
   :width: 30 %


.. |16l_CyclicSurface3.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16l_CyclicSurface3.3D.jpg
   :width: 30 %







|16m_CyclicSurface3.3D| `\quad` |16n_CyclicSurface3.3D| 


.. |16m_CyclicSurface3.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16m_CyclicSurface3.3D.jpg
   :width: 30 %


.. |16n_CyclicSurface3.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/16n_CyclicSurface3.3D.jpg
   :width: 30 %








|newpage|


Goursat surfaces 
-------------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D17a_Goursat1.3D.xml (D17a-f) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D17a_Goursat1.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    var a = -0.33;
    var b = 0.2;
    var c = -3;
    var p = 1;

    var su = Math.Sin(u);
    var cu = Math.Cos(u);
    var sv = Math.Sin(v);
    var cv = Math.Cos(v);

    var su4 = su * su * su * su;
    var cu4 = cu * cu * cu * cu;

    var sv4 = sv * sv * sv * sv;
    var cv4 = cv * cv * cv * cv;

    var D = (su4 + cu4) * cv4 + sv4;
    var R = Math.Sqrt((-b + p * Math.Sqrt(b * b - 4 * c * (a + D))) / (2 * (a + D)));
    var x = R * cv * cu;
    var y = R * cv * su;
    var z = R * sv;



// See : Krivoshapko (2015), p. 643
// See: https://mathworld.wolfram.com/GoursatsSurface.html
// See Gray 1997, p. 314)
// See: https://mathcurve.com/surfaces.gb/goursat/goursat.shtml





|17a_Goursat1.3D| `\quad` |17b_Goursat4.3D| `\quad` |17c_Goursat2.3D|



.. |17a_Goursat1.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/17a_Goursat1.3D.jpg
   :width: 30 %


.. |17b_Goursat4.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/17b_Goursat4.3D.jpg
   :width: 30 %


.. |17c_Goursat2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/17c_Goursat2.3D.jpg
   :width: 30 %




|17d_Goursat1.3D| `\quad` |17e_Goursat4.3D| `\quad` |17f_Goursat2.3D|



.. |17d_Goursat1.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/17d_Goursat1.3D.jpg
   :width: 30 %


.. |17e_Goursat4.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/17e_Goursat4.3D.jpg
   :width: 30 %


.. |17f_Goursat2.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/17f_Goursat2.3D.jpg
   :width: 30 %






|newpage|


Cyclides triples
--------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D18a_CyclidesTriple.3D.xml (D18a-f) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D18a_CyclidesTriple.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    var su = Math.Sin(u);
    var s2u = Math.Sin(2 * u);
    var cu = Math.Cos(u);
    var sv = Math.Sin(v);
    var cv = Math.Cos(v);

    var x = cv * sv * sv * sv * s2u * cu;
    var y = cv * sv * sv * sv * s2u * su;
    var z = cv * sv * sv * s2u;


// See : Krivoshapko (2015), p. 651




|18a_CyclidesTriple.3D| `\quad` |18b_CyclidesTriple.3D| `\quad` |18c_CyclidesTriple.3D|



.. |18a_CyclidesTriple.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/18a_CyclidesTriple.3D.jpg
   :width: 30 %


.. |18b_CyclidesTriple.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/18b_CyclidesTriple.3D.jpg
   :width: 30 %


.. |18c_CyclidesTriple.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/18c_CyclidesTriple.3D.jpg
   :width: 30 %




|18d_CyclidesTriple.3D| `\quad` |18e_CyclidesTriple.3D| `\quad` |18f_CyclidesTriple.3D|



.. |18d_CyclidesTriple.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/18d_CyclidesTriple.3D.jpg
   :width: 30 %


.. |18e_CyclidesTriple.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/18e_CyclidesTriple.3D.jpg
   :width: 30 %


.. |18f_CyclidesTriple.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/18f_CyclidesTriple.3D.jpg
   :width: 30 %





|newpage|


Ship Lamé
------------------------------

The XML code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the files `D19a_ShipLame.3D.xml (D19a-c) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/Plots3DWpfExamples/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/D19a_ShipLame.3D.xml>`__.


The example below uses the following code in C\#

.. code-block:: csharp

    var B = 6.5;
    var L = 4.0;
    var T = 2.0;

    var x = u * L;
    var y = Math.Sign(Math.Cos(v)) * B * Math.Sqrt(1 - u * u * u * u) * Math.Sqrt(Math.Abs(Math.Cos(v))) / 2.0;
    var z = Math.Sign(Math.Sin(v)) * T * Math.Sqrt(1 - u * u) * Math.Sqrt(Math.Abs(Math.Sin(v)));


// See : Krivoshapko (2015), p. 671




|19a_ShipLame.3D| `\quad` |19b_ShipLame.3D| `\quad` |19c_ShipLame.3D|



.. |19a_ShipLame.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/19a_ShipLame.3D.jpg
   :width: 30 %


.. |19b_ShipLame.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/19b_ShipLame.3D.jpg
   :width: 30 %


.. |19c_ShipLame.3D| image:: ../_static/B23_WpfParametricSurfaces/C03_GeneralisationsOfSurfaces/19c_ShipLame.3D.jpg
   :width: 30 %




