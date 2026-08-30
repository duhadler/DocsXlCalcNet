

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />






|newpage|


Fractals related to the Mandelbrot set
==============================================================

See also: http://www.juliasets.dk/Pictures_of_Julia_and_Mandelbrot_sets.htm


See also: http://www.3d-meier.de/, Mandelbrot und Julia Mengen

See also: http://www.dhushara.com/DarkHeart/quasif/quasi.htm (includes Kleinian fractals)


See also: https://en.wikipedia.org/wiki/Mandelbrot_set




Difference Method: https://en.wikibooks.org/wiki/Fractals/Iterations_in_the_complex_plane/demm

MandelbrotSetExterior: https://en.wikibooks.org/wiki/Fractals/Iterations_in_the_complex_plane/MandelbrotSetExterior#Real_Escape_Time

Fractals/fractalzoomer: https://en.wikibooks.org/wiki/Fractals/fractalzoomer





Mandelbrot set, example 1, classical set: `z_{n+1} = z_n^2 + c`
--------------------------------------------------------------------------------

Classical formula: `z_{n+1} = z_n^2 + c`.


The Python code for the example below, *without* using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01a_Mandelbrot1.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D01a_Mandelbrot1.py>`__.


The Python code for the example below, using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01b_Mandelbrot1.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D01b_Mandelbrot1.py>`__.


.. image:: ../_static/Combining2D3D/Mandelbrot/Mandelbrot1.*
   :width: 50 %






|newpage|


Mandelbrot set, example 2: higher powers
--------------------------------------------------------------------------------


Recursion formula: `\displaystyle z_{n+1} = z_n^5 + c`.


The Python code for the example below, *without* using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02a_Mandelbrot2.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D02a_Mandelbrot2.py>`__.


The Python code for the example below, using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D02b_Mandelbrot2.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D02b_Mandelbrot2.py>`__.


See also: https://paulbourke.net/fractals/mandelpower/


See also: http://www.3d-meier.de/, Mandelbrot und Julia Mengen



.. image:: ../_static/Combining2D3D/Mandelbrot/Mandelbrot2.*
   :width: 50 %




|newpage|


Mandelbrot set, example 3: `z_{n+1} = z_n^5 + \frac{c}{z_n}`
--------------------------------------------------------------------------------

Recursion formula: `\displaystyle z_{n+1} = z_n^5 + \frac{c}{z_n}`.


See also: http://www.3d-meier.de/, Mandelbrot und Julia Mengen


The Python code for the example below, *without* using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03a_Mandelbrot3.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D03a_Mandelbrot3.py>`__.


The Python code for the example below, using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D03b_Mandelbrot3.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D03b_Mandelbrot3.py>`__.



.. image:: ../_static/Combining2D3D/Mandelbrot/Mandelbrot6.*
   :width: 50 %





|newpage|


Mandelbrot set, example 4: `z_{n+1} = z_n^5 + \frac{c}{z_n^5}`
--------------------------------------------------------------------------------


Recursion formula: `\displaystyle z_{n+1} = z_n^5 + \frac{c}{z_n^5}`.



See also: http://www.3d-meier.de/, Mandelbrot und Julia Mengen



The Python code for the example below, *without* using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04a_Mandelbrot4.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D04a_Mandelbrot4.py>`__.


The Python code for the example below, using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D04b_Mandelbrot4.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D04b_Mandelbrot4.py>`__.





.. image:: ../_static/Combining2D3D/Mandelbrot/Mandelbrot7.*
   :width: 50 %





|newpage|


Mandelbrot set, example 5, "Inverse Mandelbrot"
---------------------------------------------------------------------------------------


Recursion formula: `\displaystyle z_{n+1} = z_n^2 + \frac{1}{c}`.


See also: http://www.3d-meier.de/, Mandelbrot und Julia Mengen



The Python code for the example below, *without* using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05a_Mandelbrot5.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D05a_Mandelbrot5.py>`__.


The Python code for the example below, using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D05b_Mandelbrot5.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D05b_Mandelbrot5.py>`__.




.. image:: ../_static/Combining2D3D/Mandelbrot/Mandelbrot5.*
   :width: 50 %









|newpage|


Mandelbrot set, example 6, "Marek Dragon Fractal": 
--------------------------------------------------------------------------------

Compare this with "Phoenix Julia fractals"

Recursion formula: `\displaystyle z_{n+1} = \exp(2 \pi i r) z_n + z_n^2` where r is an irrational number, in this example it is `1 - (\sqrt{2} - \sqrt{3} + \sqrt{5} )/2`.

See also: https://paulbourke.net/fractals/marek/



The Python code for the example below, *without* using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06a_Mandelbrot6.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D06a_Mandelbrot6.py>`__.


The Python code for the example below, using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D06b_Mandelbrot6.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D06b_Mandelbrot6.py>`__.





.. image:: ../_static/Combining2D3D/Mandelbrot/Mandelbrot4.*
   :width: 50 %






|newpage|


Mandelbrot set, example 7, "Burning Ship Fractal"
--------------------------------------------------------------------------------


Recursion formula: `\displaystyle z_{n+1} = \left(|\Re(z_n)| + i|\Im(z_n)| \right)^2 + c`.



See also: http://www.3d-meier.de/, Mandelbrot und Julia Mengen

See also: https://paulbourke.net/fractals/burnship/



The Python code for the example below, *without* using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07a_Mandelbrot7.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D07a_Mandelbrot7.py>`__.


The Python code for the example below, using ``numba``, can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D07b_Mandelbrot7.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C02_MandelbrotSet/D07b_Mandelbrot7.py>`__.




.. image:: ../_static/Combining2D3D/Mandelbrot/Mandelbrot3.*
   :width: 50 %





