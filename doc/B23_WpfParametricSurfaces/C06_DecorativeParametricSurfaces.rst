

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />







|newpage|




Decorative parametric surfaces
==============================================



https://de.mathworks.com/help/matlab/ref/plot3.html

https://doc.sagemath.org/html/en/reference/plot3d/index.html

http://www.3d-meier.de/tut3/Seite0.html

http://www.3d-meier.de/tut8/Seite3.html

https://docs.ambientcg.com/books/website-licensing/page/license-information

https://ambientcg.com/list?category=&date=&createdUsing=&basedOn=&q=&method=&type=&sort=Downloads






Bourke Seashell
-----------------------------------------


See also: http://paulbourke.net/geometry/spiral/


.. code-block:: csharp

    double n = 3;  // number of spirals
    double a = 1;  // final shell radius
    double b = 2;  // height
    double c = 0.4;  // inner radius
                
    double s = v;
    double t = u;
    double pt = t/(2*Math.PI);  // inner radius
                
    x = a * (1 - pt) * Math.Cos(n*t) * (1 + Math.Cos(s)) + c * Math.Cos(n*t);
    z = a * (1 - pt) * Math.Sin(n*t) * (1 + Math.Cos(s)) + c * Math.Sin(n*t);
    y = b * pt + a * (1 - pt) * Math.Sin(s);



|01a_BourkeSeaShell.3D| `\quad` |01b_BourkeSeaShell.3D| `\quad` |01c_BourkeSeaShell.3D|



.. |01a_BourkeSeaShell.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/01a_BourkeSeaShell.3D.jpg
   :width: 30 %


.. |01b_BourkeSeaShell.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/01b_BourkeSeaShell.3D.jpg
   :width: 30 %


.. |01c_BourkeSeaShell.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/01c_BourkeSeaShell.3D.jpg
   :width: 30 %







|newpage|


Seashell (mathworld.wolfram)
---------------------------------------------


See also: https://mathworld.wolfram.com/Seashell.html



.. code-block:: csharp

    double a = Math.Exp(u / (6.0 * Math.PI));
    double b = Math.Cos(v / 2.0);

    x = 2.0 * (1.0 - a) * Math.Cos(u) * b * b;
    y = 2.0 * (-1.0 + a) * Math.Sin(u) * b * b;
    z = (1.0 - a * a - Math.Sin(v) * (1.0 - a));


    

|02a_Seashell.3D| `\quad` |02b_Seashell.3D| `\quad` |02c_Seashell.3D|



.. |02a_Seashell.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/02a_Seashell.3D.jpg
   :width: 30 %


.. |02b_Seashell.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/02b_Seashell.3D.jpg
   :width: 30 %


.. |02c_Seashell.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/02c_Seashell.3D.jpg
   :width: 30 %






|newpage|



3D Apple
-------------------------

.. code-block:: csharp

    double R1 = 5.0;
    double R2 = 4.8;
    double su = Math.Sin(u);
    double sv = Math.Sin(v);
    double cu = Math.Cos(u);
    double c5u = Math.Cos(5*u);
    double cv = Math.Cos(v);
    x = cu * (R1 + R2 * cv) + Math.Pow(v/Math.PI, 20);
    z = su * (R1 + R2 * cv) + 0.25 * c5u;
    y = -2.3 * Math.Log(1 - v * 0.3157) + 6 * sv + 2 * cv;



|03a_Apple.3D| `\quad` |03b_Apple.3D| `\quad` |03c_Apple.3D|



.. |03a_Apple.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/03a_Apple.3D.jpg
   :width: 30 %


.. |03b_Apple.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/03b_Apple.3D.jpg
   :width: 30 %


.. |03c_Apple.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/03c_Apple.3D.jpg
   :width: 30 %






|newpage|


Bow curve
----------------------------------


See also: http://paulbourke.net/geometry/toroidal/


.. code-block:: csharp

    double p2 = 2*Math.PI;
    double p4 = 4*Math.PI;
    double T = 0.5; //Thickness
                
    x = (2 + T * Math.Sin(p2 * u)) * Math.Sin(p4 * v);
    y = (2 + T * Math.Sin(p2 * u)) * Math.Cos(p4 * v);
    z = T * Math.Cos(p2 * u) + 3 * Math.Cos(p2 * v);



|04a_BowCurve.3D| `\quad` |04b_BowCurve.3D| `\quad` |04c_BowCurve.3D|



.. |04a_BowCurve.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/04a_BowCurve.3D.jpg
   :width: 30 %


.. |04b_BowCurve.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/04b_BowCurve.3D.jpg
   :width: 30 %


.. |04c_BowCurve.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/04c_BowCurve.3D.jpg
   :width: 30 %





|newpage|


Fish Surface
--------------------------------------


See also: http://www.3d-meier.de/tut3/Seite47.html



See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.


.. code-block:: csharp

    double su = Math.Sin(u);
    double s2u = Math.Sin(2*u);
    double sv = Math.Sin(v);
    double cu = Math.Cos(u);
    double c2u = Math.Cos(2*u);
    double cv = Math.Cos(v);
    x = (cu - c2u) * cv / 4.0;
    y = (su - s2u) * sv / 4.0;
    z = cu;



|05a_Fish.3D| `\quad` |05b_Fish.3D| `\quad` |05c_Fish.3D|



.. |05a_Fish.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/05a_Fish.3D.jpg
   :width: 30 %


.. |05b_Fish.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/05b_Fish.3D.jpg
   :width: 30 %


.. |05c_Fish.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/05c_Fish.3D.jpg
   :width: 30 %








|newpage|


Bourke Horn
--------------------------------------


See also: http://paulbourke.net/geometry/spiral/


.. code-block:: csharp

    double p2 = 2*Math.PI;
    x = (2 + u * Math.Cos(v)) * Math.Sin(p2 * u);
    y = (2 + u * Math.Cos(v)) * Math.Cos(p2 * u) + 2 * u;
    z = u * Math.Sin(v);



|06a_BourkeHorn.3D| `\quad` |06b_BourkeHorn.3D| `\quad` |06c_BourkeHorn.3D|



.. |06a_BourkeHorn.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/06a_BourkeHorn.3D.jpg
   :width: 30 %


.. |06b_BourkeHorn.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/06b_BourkeHorn.3D.jpg
   :width: 30 %


.. |06c_BourkeHorn.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/06c_BourkeHorn.3D.jpg
   :width: 30 %









|newpage|





Hexa torus
--------------------------------------


See also: http://paulbourke.net/geometry/toroidal/

The C\# code for the Klein bottle: 

.. code-block:: csharp

    double a = Math.Cos(u);
    double b = Math.Sin(u);
    double c = Math.Cos(v);
    double a2 = a * a;
    double a4 = a2 * a2;

    x = -(2.0 / 15.0) * a * (3 * c + b * (-30 + a4 * (90 - 60 * a2) + 5 * a * c));
    z = -(1.0 / 15.0) * b * b * (c * b * (3 - 48 * a4 + 5 * a * b * (1 - 16 * a4)) - 60);
    y = (2.0 / 15.0) * (3 + 5 * a * b) * Math.Sin(v);




|07a_HexaTorus.3D| `\quad` |07b_HexaTorus.3D| `\quad` |07c_HexaTorus.3D|



.. |07a_HexaTorus.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/07a_HexaTorus.3D.jpg
   :width: 30 %


.. |07b_HexaTorus.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/07b_HexaTorus.3D.jpg
   :width: 30 %


.. |07c_HexaTorus.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/07c_HexaTorus.3D.jpg
   :width: 30 %








|newpage|





3D Breather Surface
-------------------------

.. code-block:: csharp

    const double b = 0.4;
    double r = 1 - b * b;
    double w = Math.Sqrt(r);
    double denom = b * (
        (w * Math.Cosh(b * u)) * (w * Math.Cosh(b * u)) +
        (b * Math.Sin(w * v)) * (b * Math.Sin(w * v)));
    
    x = -u + (2 * r * Math.Cosh(b * u) * Math.Sinh(b * u)) / denom;
    y = (2 * w * Math.Cosh(b * u) * (-(w * Math.Cos(v) * Math.Cos(w * v)) - Math.Sin(v) * Math.Sin(w * v))) / denom;
    z = (2 * w * Math.Cosh(b * u) * (-(w * Math.Sin(v) * Math.Cos(w * v)) + Math.Cos(v) * Math.Sin(w * v))) / denom;




|08a_Breather.3D| `\quad` |08b_Breather.3D| `\quad` |08c_Breather.3D|



.. |08a_Breather.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/08a_Breather.3D.jpg
   :width: 30 %


.. |08b_Breather.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/08b_Breather.3D.jpg
   :width: 30 %


.. |08c_Breather.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/08c_Breather.3D.jpg
   :width: 30 %





|newpage|


Kuen surface
----------------------------------


See also: https://mathworld.wolfram.com/KuenSurface.html

See also: https://virtualmathmuseum.org/Surface/kuen/kuen.html

See also: https://mathcurve.com/surfaces.gb/kuen/kuen.shtml



.. code-block:: csharp

    double a = 1.0 * Math.Sin(v);
    double b = 1.0 + u * u * a * a;

    x = 2.0 * a * (Math.Cos(u) + u * Math.Sin(u)) / b;
    z = 2.0 * a * (Math.Sin(u) - u * Math.Cos(u)) / b;
    y = Math.Log(Math.Tan(v / 2.0)) + 2.0 * Math.Cos(v) / b;





|09a_Kuen.3D| `\quad` |09b_Kuen.3D| `\quad` |09c_Kuen.3D|



.. |09a_Kuen.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/09a_Kuen.3D.jpg
   :width: 30 %


.. |09b_Kuen.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/09b_Kuen.3D.jpg
   :width: 30 %


.. |09c_Kuen.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/09c_Kuen.3D.jpg
   :width: 30 %











|newpage|


Tranguloid trefoil
--------------------------------------


See also: http://paulbourke.net/geometry/tranguloid/




There are other parametrizations:

See also: http://www.3d-meier.de/tut3/Seite56.html
See also: https://mathart.org/sw/GreenSnake/Toroid2.html

See also: http://www.3d-meier.de/tut3/Seite159.html


.. code-block:: csharp

    double p2 = 2*Math.PI/3;
    x = 2 * Math.Sin(3 * u) / (2 + Math.Cos(v));
    y = 2 * (Math.Sin(u) + 2 * Math.Sin(2 * u)) / (2 + Math.Cos(v + p2));
    z = (Math.Cos(u) - 2 * Math.Cos(2 * u)) * (2 + Math.Cos(v)) * (2 + Math.Cos(v + p2)) / 4;





|10a_TranguloidTrefoil.3D| `\quad` |10b_TranguloidTrefoil.3D| `\quad` |10c_TranguloidTrefoil.3D|



.. |10a_TranguloidTrefoil.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/10a_TranguloidTrefoil.3D.jpg
   :width: 30 %


.. |10b_TranguloidTrefoil.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/10b_TranguloidTrefoil.3D.jpg
   :width: 30 %


.. |10c_TranguloidTrefoil.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/10c_TranguloidTrefoil.3D.jpg
   :width: 30 %





|newpage|


Triaxial teardrop
--------------------------------------


See also: http://paulbourke.net/geometry/triaxtear/

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



.. code-block:: csharp

    double p2 = 2*Math.PI/3;
    x = ( 1 - Math.Cos(u) ) * Math.Cos(u + p2) * Math.Cos(v + p2) / 2;
    y = -( 1 - Math.Cos(u) ) * Math.Cos(u + p2) * Math.Cos(v - p2) / 2;
    z = Math.Cos(u - p2);





|11a_TearDrop.3D| `\quad` |11b_TearDrop.3D| `\quad` |11c_TearDrop.3D|



.. |11a_TearDrop.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/11a_TearDrop.3D.jpg
   :width: 30 %


.. |11b_TearDrop.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/11b_TearDrop.3D.jpg
   :width: 30 %


.. |11c_TearDrop.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/11c_TearDrop.3D.jpg
   :width: 30 %







|newpage|


Gray Bottle
--------------------------------------


See also: http://paulbourke.net/geometry/toroidal/


.. code-block:: csharp

    x = Math.Cos(v) * Math.Sqrt(Math.Abs(Math.Sin(2 * u))) * Math.Cos(u);
    y = Math.Cos(v) * Math.Sqrt(Math.Abs(Math.Sin(2 * u))) * Math.Sin(u);
    z = x*x - y*y + 2 * x * y * Math.Tan(v) * Math.Tan(v);




|12a_GrayBottel.3D| `\quad` |12b_GrayBottel.3D| `\quad` |12c_GrayBottel.3D|



.. |12a_GrayBottel.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/12a_GrayBottel.3D.jpg
   :width: 30 %


.. |12b_GrayBottel.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/12b_GrayBottel.3D.jpg
   :width: 30 %


.. |12c_GrayBottel.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/12c_GrayBottel.3D.jpg
   :width: 30 %









|newpage|

Surfaces mimicking snail shells
-----------------------------------------------


See also: http://www.3d-meier.de/tut3/Seite89.html




|21a_Snail1.3D| `\quad` |21b_Snail1.3D| `\quad` |21c_Snail1.3D|



.. |21a_Snail1.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/21a_Snail1.3D.jpg
   :width: 30 %


.. |21b_Snail1.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/21b_Snail1.3D.jpg
   :width: 30 %


.. |21c_Snail1.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/21c_Snail1.3D.jpg
   :width: 30 %





.. code-block:: csharp

    double R = 1;
    double a = 1.6;
    double b = 1.6;
    double c = 1.0;
    double h = 1.5;
    double k = -7.0;
    double w = 0.075;
    //  umin = -50, umax = -1,    name:  Pseudoheliceras subcatenatum
                
    double su = Math.Sin(u);
    double scu = Math.Sin(c*u);
    double sv = Math.Sin(v);
    double cv = Math.Cos(v);
    double ccu = Math.Cos(c*u);
                
    double ewu = Math.Exp(w*u);
                
    x = ewu * (h+a*cv) * ccu;
    z = R * ewu * (h+a*cv) * scu;
    y = ewu * (k + b * sv);




|newpage|



|22a_Snail2.3D| `\quad` |22b_Snail2.3D| `\quad` |22c_Snail2.3D|



.. |22a_Snail2.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/22a_Snail2.3D.jpg
   :width: 30 %


.. |22b_Snail2.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/22b_Snail2.3D.jpg
   :width: 30 %


.. |22c_Snail2.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/22c_Snail2.3D.jpg
   :width: 30 %



|23a_Snail3.3D| `\quad` |23b_Snail3.3D| `\quad` |23c_Snail3.3D|



.. |23a_Snail3.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/23a_Snail3.3D.jpg
   :width: 30 %


.. |23b_Snail3.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/23b_Snail3.3D.jpg
   :width: 30 %


.. |23c_Snail3.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/23c_Snail3.3D.jpg
   :width: 30 %



|24a_Snail4.3D| `\quad` |24b_Snail4.3D| `\quad` |24c_Snail4.3D|



.. |24a_Snail4.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/24a_Snail4.3D.jpg
   :width: 30 %


.. |24b_Snail4.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/24b_Snail4.3D.jpg
   :width: 30 %


.. |24c_Snail4.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/24c_Snail4.3D.jpg
   :width: 30 %




**Left figure**: Astroceras surface.

**Middle figure**: Bellerophina surface.

**Right figure**: Euhoplites Surface.




|newpage|



|25a_Snail5.3D| `\quad` |25b_Snail5.3D| `\quad` |25c_Snail5.3D|



.. |25a_Snail5.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/25a_Snail5.3D.jpg
   :width: 30 %


.. |25b_Snail5.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/25b_Snail5.3D.jpg
   :width: 30 %


.. |25c_Snail5.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/25c_Snail5.3D.jpg
   :width: 30 %



|26a_Snail6.3D| `\quad` |26b_Snail6.3D| `\quad` |26c_Snail6.3D|



.. |26a_Snail6.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/26a_Snail6.3D.jpg
   :width: 30 %


.. |26b_Snail6.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/26b_Snail6.3D.jpg
   :width: 30 %


.. |26c_Snail6.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/26c_Snail6.3D.jpg
   :width: 30 %




|27a_Snail7.3D| `\quad` |27b_Snail7.3D| `\quad` |27c_Snail7.3D|



.. |27a_Snail7.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/27a_Snail7.3D.jpg
   :height: 300 px


.. |27b_Snail7.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/27b_Snail7.3D.jpg
   :height: 300 px


.. |27c_Snail7.3D| image:: ../_static/B23_WpfParametricSurfaces/C06_DecorativeParametricSurfaces/27c_Snail7.3D.jpg
   :height: 300 px




**Left figure**: Nautilus surface.

**Middle figure**: Natica stellata surface.

**Right figure**: Mya arenaria surface.



