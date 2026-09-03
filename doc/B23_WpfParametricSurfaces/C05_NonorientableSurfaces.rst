

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />









|newpage|




Nonorientable (one-sided) Surfaces
========================================




Moebius Strip
------------------------------------------


See also: http://en.wikipedia.org/wiki/M%C3%B6bius_strip

See also: https://mathworld.wolfram.com/MoebiusStrip.html


.. code-block:: csharp

    x = (1 + (v / 2) * Math.Cos(u / 2)) * Math.Cos(u);
    z = (1 + (v / 2) * Math.Cos(u / 2)) * Math.Sin(u);
    y = (v / 2) * Math.Sin(u / 2);




|01a_Moebius.3D| `\quad` |01b_Moebius.3D| `\quad` |01c_Moebius.3D|



.. |01a_Moebius.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/01a_Moebius.3D.jpg
   :width: 30 %


.. |01b_Moebius.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/01b_Moebius.3D.jpg
   :width: 30 %


.. |01c_Moebius.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/01c_Moebius.3D.jpg
   :width: 30 %









|newpage|






Cross-Cap Surface
------------------------------


See also: https://mathworld.wolfram.com/Cross-Cap.html

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



.. code-block:: csharp

    double su = Math.Sin(u);
    double sv = Math.Sin(v);
    double s2v = Math.Sin(2*v);
    double cu = Math.Cos(u);
    double cv = Math.Cos(v);
    x = 0.5 * cu * s2v;
    z = 0.5 * su * s2v;
    y = 0.5 * (cv*cv - cu*cu * sv*sv);




|02a_CrossCap.3D| `\quad` |02b_CrossCap.3D| `\quad` |02c_CrossCap.3D|



.. |02a_CrossCap.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/02a_CrossCap.3D.jpg
   :width: 30 %


.. |02b_CrossCap.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/02b_CrossCap.3D.jpg
   :width: 30 %


.. |02c_CrossCap.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/02c_CrossCap.3D.jpg
   :width: 30 %







|newpage|



Pseudo Cross-Cap Surface
--------------------------------------------


See also: https://mathworld.wolfram.com/Pseudocrosscap.html

See also: http://www.3d-meier.de/tut3/Seite51.html

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.


.. code-block:: csharp

    double sv = Math.Sin(v);
    double s2v = Math.Sin(2*v);
    x = (1 - u*u) * sv;
    y = (1 - u*u) * s2v;
    z = u;

    

|03a_PseudoCrossCap.3D| `\quad` |03b_PseudoCrossCap.3D| `\quad` |03c_PseudoCrossCap.3D|



.. |03a_PseudoCrossCap.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/03a_PseudoCrossCap.3D.jpg
   :width: 30 %


.. |03b_PseudoCrossCap.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/03b_PseudoCrossCap.3D.jpg
   :width: 30 %


.. |03c_PseudoCrossCap.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/03c_PseudoCrossCap.3D.jpg
   :width: 30 %





|newpage|


Roman Surface (or Steiner Surface)
-----------------------------------------------


See also: https://mathworld.wolfram.com/RomanSurface.html

See also: https://en.wikipedia.org/wiki/Roman_surface

See also: http://paulbourke.net/geometry/steiner/


.. code-block:: csharp

    double r2 = 1;
    double su = Math.Sin(u);
    double sv = Math.Sin(v);
    double cu = Math.Cos(u);
    double cv = Math.Cos(v);
    x = r2 * cu * su * sv;
    y = r2 * cu * su * cv;
    z = r2 * cu*cu * sv * cv;


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.




|04a_Roman.3D| `\quad` |04b_Roman.3D| `\quad` |04c_Roman.3D|



.. |04a_Roman.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/04a_Roman.3D.jpg
   :width: 30 %


.. |04b_Roman.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/04b_Roman.3D.jpg
   :width: 30 %


.. |04c_Roman.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/04c_Roman.3D.jpg
   :width: 30 %











|newpage|


Klein bagel
-----------------------------


See also: https://en.wikipedia.org/wiki/Klein_bottle#The_figure_8_immersion

See also: https://mathworld.wolfram.com/KleinBottle.html


.. code-block:: csharp

    double r = 2.1;
    x = (r + Math.Cos(u / 2) * Math.Sin(v) - Math.Sin(u / 2) * Math.Sin(2 * v)) * Math.Cos(u);
    z = (r + Math.Cos(u / 2) * Math.Sin(v) - Math.Sin(u / 2) * Math.Sin(2 * v)) * Math.Sin(u);
    y = Math.Sin(u / 2) * Math.Sin(v) + Math.Cos(u / 2) * Math.Sin(2 * v);



This is the 'bagel' form of a Klein bottle, a 4 dimensional object with a single surface (lacking 'inside' or 'outside'), projected into 3-space as a self-intersecting solid.




|05a_KleinBagel.3D| `\quad` |05b_KleinBagel.3D| `\quad` |05c_KleinBagel.3D|



.. |05a_KleinBagel.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/05a_KleinBagel.3D.jpg
   :width: 30 %


.. |05b_KleinBagel.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/05b_KleinBagel.3D.jpg
   :width: 30 %


.. |05c_KleinBagel.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/05c_KleinBagel.3D.jpg
   :width: 30 %







|newpage|


Klein bottle
---------------------------------------


See also: http://www.mapleprimes.com/maplesoftblog/95570-Klein-Bottle-Plot

See also: http://www.chebfun.org/examples/geom/ParametricSurfaces.html

See also: https://mathworld.wolfram.com/KleinBottle.html


.. code-block:: csharp

    double a = Math.Cos(u);
    double b = Math.Sin(u);
    double c = Math.Cos(v);
    double a2 = a * a;
    double a4 = a2 * a2;
    x = -(2.0 / 15.0) * a * (3 * c + b * (-30 + a4 * (90 - 60 * a2) + 5 * a * c));
    z = -(1.0 / 15.0) * b * b * (c * b * (3 - 48 * a4 + 5 * a * b * (1 - 16 * a4)) - 60);
    y = -(2.0 / 15.0) * (3 + 5 * a * b) * Math.Sin(v);


    

|08a_KleinBottle3.3D| `\quad` |08b_KleinBottle3.3D| `\quad` |08c_KleinBottle3.3D|



.. |08a_KleinBottle3.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/08a_KleinBottle3.3D.jpg
   :width: 30 %


.. |08b_KleinBottle3.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/08b_KleinBottle3.3D.jpg
   :width: 30 %


.. |08c_KleinBottle3.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/08c_KleinBottle3.3D.jpg
   :width: 30 %






|newpage|



3D Boy Surface, version 1
-----------------------------------


See also: https://en.wikipedia.org/wiki/Boy%27s_surface

See also: http://mathworld.wolfram.com/BoySurface.html



.. code-block:: csharp

    double sqrt5 = Math.Sqrt(5);
    // w = u*e^(iv)
    double wr = Math.Cos(v);
    double wi = Math.Sin(v);
    Complex w = u * new Complex(wr, wi);
    Complex w3 = w * w * w;
    Complex w4 = w3 * w;
    Complex w6 = w3 * w3;
    Complex d = w6 + sqrt5 * w3 - 1;
    Complex wa = w * (1 - w4) / d;
    Complex wb = w * (1 + w4) / d;
    Complex wc = (1 + w6) / d;
    double g1 = -1.5 * wa.Imaginary;
    double g2 = -1.5 * wb.Real;
    double g3 = wc.Imaginary - 0.5;
    double l2 = g1 * g1 + g2 * g2 + g3 * g3;
    x = g1 / l2;
    y = -g2 / l2;
    z = g3 / l2;




|09a_BoySurface.3D| `\quad` |09b_BoySurface.3D| `\quad` |09c_BoySurface.3D|



.. |09a_BoySurface.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/09a_BoySurface.3D.jpg
   :width: 30 %


.. |09b_BoySurface.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/09b_BoySurface.3D.jpg
   :width: 30 %


.. |09c_BoySurface.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/09c_BoySurface.3D.jpg
   :width: 30 %




|newpage|



3D Boy Surface, version 2
-------------------------------------------


See also: https://en.wikipedia.org/wiki/Boy%27s_surface

See also: http://mathworld.wolfram.com/BoySurface.html



.. code-block:: csharp

    double sqrt2 = Math.Sqrt(2);
    double s2v = Math.Sin(2 * v);
    double cu = Math.Cos(u);
    double cv = Math.Cos(v);
    double cv2 = cv * cv;
    double n1 = sqrt2 * cv2 * Math.Cos(2*u);
    double xn = sqrt2 * cv2 * Math.Cos(2 * u) + cu * s2v;
    double yn = sqrt2 * cv2 * Math.Sin(2 * u) - Math.Sin(u) * s2v;
    double zn = 3 * cv2;
    double d = 2 - sqrt2 * Math.Sin(3 * u) * s2v;
    x = xn / d;
    y = yn / d;
    z = zn / d;




|10a_BoySurface2.3D| `\quad` |10b_BoySurface2.3D| `\quad` |10c_BoySurface2.3D|



.. |10a_BoySurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/10a_BoySurface2.3D.jpg
   :width: 30 %


.. |10b_BoySurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/10b_BoySurface2.3D.jpg
   :width: 30 %


.. |10c_BoySurface2.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/10c_BoySurface2.3D.jpg
   :width: 30 %





|newpage|



Morin Surface
-------------------------------------------


// See also: http://www.3d-meier.de/tut3/Seite221.html  // Morin Surface
// See also: https://mathcurve.com/surfaces.gb/morin/morin.shtml
// See also: https://en.wikipedia.org/wiki/Morin_surface
// See also: Bednorz 2019


.. code-block:: csharp

    var k = 1.0;
    var n = 3.0;

    var Sqrt2 = Math.Sqrt(2);
    var cu = Math.Cos(u);
    var su = Math.Sin(u);
    var K = cu / (Sqrt2 - k * Math.Sin(2 * u) * Math.Sin(n * v));

    var x = K * (2 / (n - 1) * cu * Math.Cos((n - 1) * v) + Sqrt2 * su * Math.Cos(v));
    var y = K * (2 / (n - 1) * cu * Math.Sin((n - 1) * v) - Sqrt2 * su * Math.Sin(v));
    var z = K * cu;



|11a_Morin3.3D| `\quad` |11b_Morin5.3D| `\quad` |11c_Morin9.3D|



.. |11a_Morin3.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/11a_Morin3.3D.jpg
   :width: 30 %


.. |11b_Morin5.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/11b_Morin5.3D.jpg
   :width: 30 %


.. |11c_Morin9.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/11c_Morin9.3D.jpg
   :width: 30 %



|11d_Morin3.3D| `\quad` |11e_Morin5.3D| `\quad` |11f_Morin9.3D|



.. |11d_Morin3.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/11d_Morin3.3D.jpg
   :width: 30 %


.. |11e_Morin5.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/11e_Morin5.3D.jpg
   :width: 30 %


.. |11f_Morin9.3D| image:: ../_static/B23_WpfParametricSurfaces/C05_NonorientableSurfaces/11f_Morin9.3D.jpg
   :width: 30 %




