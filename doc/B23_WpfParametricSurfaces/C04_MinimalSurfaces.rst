

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />









|newpage|




Minimal surfaces
==============================================





Catenoid
-----------------------------------------


See also: https://mathworld.wolfram.com/Catenoid.html




|01a_Catenoid.3D| `\quad` |01b_Catenoid.3D| `\quad` |01c_Catenoid.3D|



.. |01a_Catenoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/01a_Catenoid.3D.jpg
   :width: 30 %


.. |01b_Catenoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/01b_Catenoid.3D.jpg
   :width: 30 %


.. |01c_Catenoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/01c_Catenoid.3D.jpg
   :width: 30 %




**Left figure**: Catenoid




|newpage|



Helicoid
-------------------------------------


See also: https://mathworld.wolfram.com/Helicoid.html

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



|02a_Helicoid.3D| `\quad` |02b_Helicoid.3D| `\quad` |02c_Helicoid.3D|



.. |02a_Helicoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/02a_Helicoid.3D.jpg
   :width: 30 %


.. |02b_Helicoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/02b_Helicoid.3D.jpg
   :width: 30 %


.. |02c_Helicoid.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/02c_Helicoid.3D.jpg
   :width: 30 %






.. code-block:: csharp

    double a = 1;
    x = u * Math.Cos(v);
    z = u * Math.Sin(v);
    y = v;



References

Gray, A. Modern Differential Geometry of Curves and Surfaces with Mathematica, 2nd ed. Boca Raton, FL: CRC Press, pp. 449 and 644, 1997.






|newpage|


Bours minimal surface
------------------------------------------------


See also: https://mathworld.wolfram.com/BoursMinimalSurface.html

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



.. code-block:: csharp

    double sv = Math.Sin(v);
    double s2v = Math.Sin(2*v);
    double c32u = Math.Cos(1.5*v);
    double cv = Math.Cos(v);
    double c2v = Math.Cos(2*v);
    double u2 = 0.5*u*u;
    double u32 = (4/3)* Math.Sqrt(u*u*u);
    x = u * cv - u2 * c2v;
    y = -u * sv - u2 * s2v;
    z = u32 * c32u;



|03a_Bour.3D| `\quad` |03b_Bour.3D| `\quad` |03c_Bour.3D|



.. |03a_Bour.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/03a_Bour.3D.jpg
   :width: 30 %


.. |03b_Bour.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/03b_Bour.3D.jpg
   :width: 30 %


.. |03c_Bour.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/03c_Bour.3D.jpg
   :width: 30 %








|newpage|


Catalan minimal surface
--------------------------------------------------


See also: https://mathworld.wolfram.com/CatalanMinimalSurface.html

See also: https://en.wikipedia.org/wiki/Catalan%27s_minimal_surface

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.


.. code-block:: csharp

    x = u - u * u * u / 3 + u * v * v;
    y = u * u - v * v;
    z = v - v * v * v / 3 + v * u * u;




|04a_Catalan.3D| `\quad` |04b_Catalan.3D| `\quad` |04c_Catalan.3D|



.. |04a_Catalan.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/04a_Catalan.3D.jpg
   :width: 30 %


.. |04b_Catalan.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/04b_Catalan.3D.jpg
   :width: 30 %


.. |04c_Catalan.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/04c_Catalan.3D.jpg
   :width: 30 %






|newpage|






Ennepers first minimal surface
-------------------------------------------------------


See also: https://mathworld.wolfram.com/EnnepersMinimalSurface.html

See also: https://en.wikipedia.org/wiki/Enneper_surface

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



.. code-block:: csharp

    x = u - u * u * u / 3 + u * v * v;
    y = u * u - v * v;
    z = v - v * v * v / 3 + v * u * u;


    

|05a_Enneper.3D| `\quad` |05b_Enneper.3D| `\quad` |05c_Enneper.3D|



.. |05a_Enneper.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/05a_Enneper.3D.jpg
   :width: 30 %


.. |05b_Enneper.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/05b_Enneper.3D.jpg
   :width: 30 %


.. |05c_Enneper.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/05c_Enneper.3D.jpg
   :width: 30 %







|newpage|


Enneper second minimal surface
------------------------------------------------------


See also: https://mathcurve.com/surfaces.gb/enneper/enneper.shtml


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



.. code-block:: csharp

    double n = 2;
    double a = 1;
                
    Complex i = Complex.ImaginaryOne;
    Complex w = new Complex(u, v);
    Complex w2nm1 = Complex.Pow(w, 2*n-1)/(2*n-1);
    Complex wn = Complex.Pow(w, n);
    x = a * (w - w2nm1).Real;
    y = a * (-i*(w + w2nm1)).Real;
    z = 2 * a * (wn/n).Real;

    

|06a_Enneper2.3D| `\quad` |06b_Enneper2.3D| `\quad` |06c_Enneper2.3D|



.. |06a_Enneper2.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/06a_Enneper2.3D.jpg
   :width: 30 %


.. |06b_Enneper2.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/06b_Enneper2.3D.jpg
   :width: 30 %


.. |06c_Enneper2.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/06c_Enneper2.3D.jpg
   :width: 30 %






|newpage|


Hennebergs minimal surface
------------------------------------------------


See also: https://mathworld.wolfram.com/HennebergsMinimalSurface.html

See also: https://en.wikipedia.org/wiki/Henneberg_surface

See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.



.. code-block:: csharp

    double sv = Math.Sin(v);
    double s3v = Math.Sin(3*v);
    double cv = Math.Cos(v);
    double c2v = Math.Cos(2*v);
    double c3v = Math.Cos(3*v);
    double shu = Math.Sinh(u);
    double ch2u = Math.Cosh(2*u);
    double sh3u = Math.Sinh(3*u);
    x = 2*shu * cv - (2.0/3.0)*sh3u * c3v;
    y = 2*shu * sv + (2.0/3.0)*sh3u * s3v;
    z = 2*ch2u * c2v;


    

|07a_Henneberg.3D| `\quad` |07b_Henneberg.3D| `\quad` |07c_Henneberg.3D|



.. |07a_Henneberg.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/07a_Henneberg.3D.jpg
   :width: 30 %


.. |07b_Henneberg.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/07b_Henneberg.3D.jpg
   :width: 30 %


.. |07c_Henneberg.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/07c_Henneberg.3D.jpg
   :width: 30 %






|newpage|


Scherk’s first minimal surface
-------------------------------------------------


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.

See also https://mathcurve.com/surfaces.gb/scherk/scherk.shtml
See also  :cite:t:`Krivoshapko2015`, p. 431



.. code-block:: csharp

    var a = 1 / Math.PI;
    var x = u;
    var z = v;
    var y = a * Math.Log(Math.Cos(v / a) / Math.Cos(u / a));
    z = -z;




|08a_Scherk1.3D| `\quad` |08b_Scherk1.3D| `\quad` |08c_Scherk1.3D|



.. |08a_Scherk1.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/08a_Scherk1.3D.jpg
   :width: 30 %


.. |08b_Scherk1.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/08b_Scherk1.3D.jpg
   :width: 30 %


.. |08c_Scherk1.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/08c_Scherk1.3D.jpg
   :width: 30 %






|newpage|


Scherk’s second minimal surface
--------------------------------------------------


See also  Wikipedia :cite:p:`Wikipedia2D101`,  MathWorld :cite:p:`Wolfram3D101`.

See also https://mathworld.wolfram.com/ScherksMinimalSurfaces.html

See also  :cite:t:`Krivoshapko2015`, p. 442



.. code-block:: csharp

    var t = v;
    var r = u;
    var r2 = r * r;
    var ct = Math.Cos(t);
    var st = Math.Sin(t);
    var x = Math.Log((1 + r2 + 2 * r * ct) / (1 + r2 - 2 * r * ct));
    var y = Math.Log((1 + r2 - 2 * r * st) / (1 + r2 + 2 * r * st));
    var z = 2 * Math.Atan((2 * r2 * Math.Sin(2 * t)) / (r2 * r2 - 1));
    y = -y;





|09a_Scherk2.3D| `\quad` |09b_Scherk2.3D| `\quad` |09c_Scherk2.3D|



.. |09a_Scherk2.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/09a_Scherk2.3D.jpg
   :width: 30 %


.. |09b_Scherk2.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/09b_Scherk2.3D.jpg
   :width: 30 %


.. |09c_Scherk2.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/09c_Scherk2.3D.jpg
   :width: 30 %








|newpage|


Richmond minimal surface
-------------------------------------------------------------------------


// See also: http://www.3d-meier.de/tut3/Seite250.html  // Richmond Surface III
// See also: https://en.wikipedia.org/wiki/Richmond_surface



.. code-block:: csharp

    var n = 2.0;
    var u2s = Math.Pow(u, 2 * n + 1) / (4 * n + 2);
    var x = -Math.Cos(v) / (2 * u) - u2s * Math.Cos(-(2 * n + 1) * v);
    var y = -Math.Sin(v) / (2 * u) + u2s * Math.Sin(-(2 * n + 1) * v);
    var z = Math.Pow(u, n) * Math.Cos(n * v) / n;



    


|10a_Richmond.3D| `\quad` |10b_Richmond.3D| `\quad` |10c_Richmond.3D|



.. |10a_Richmond.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/10a_Richmond.3D.jpg
   :width: 30 %


.. |10b_Richmond.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/10b_Richmond.3D.jpg
   :width: 30 %


.. |10c_Richmond.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/10c_Richmond.3D.jpg
   :width: 30 %

      



|10d_Richmond.3D| `\quad` |10e_Richmond.3D| `\quad` |10f_Richmond.3D|



.. |10d_Richmond.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/10d_Richmond.3D.jpg
   :width: 30 %


.. |10e_Richmond.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/10e_Richmond.3D.jpg
   :width: 30 %


.. |10f_Richmond.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/10f_Richmond.3D.jpg
   :width: 30 %





|newpage|


Generalized Ennneper surfaces
-------------------------------------------------------------------------



// See also: http://www.3d-meier.de/tut3/Seite247.html  // Wavy Enneper Surface



.. code-block:: csharp

    var s = 2.0;
    var u2s = Math.Pow(u, 2 * s - 1) / (2 * s - 1);
    var x = u * Math.Cos(v) - u2s * Math.Cos((2 * s - 1) * v);
    var y = -u * Math.Sin(v) - u2s * Math.Sin((2 * s - 1) * v);
    var z = 2 * Math.Pow(u, s) * Math.Cos(s * v) / s;



    

|11a_GenEnneper.3D| `\quad` |11b_GenEnneper.3D| `\quad` |11c_GenEnneper.3D|



.. |11a_GenEnneper.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/11a_GenEnneper.3D.jpg
   :width: 30 %


.. |11b_GenEnneper.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/11b_GenEnneper.3D.jpg
   :width: 30 %


.. |11c_GenEnneper.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/11c_GenEnneper.3D.jpg
   :width: 30 %





|11d_GenEnneper.3D| `\quad` |11e_GenEnneper.3D| `\quad` |11f_GenEnneper.3D|



.. |11d_GenEnneper.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/11d_GenEnneper.3D.jpg
   :width: 30 %


.. |11e_GenEnneper.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/11e_GenEnneper.3D.jpg
   :width: 30 %


.. |11f_GenEnneper.3D| image:: ../_static/B23_WpfParametricSurfaces/C04_MinimalSurfaces/11f_GenEnneper.3D.jpg
   :width: 30 %




