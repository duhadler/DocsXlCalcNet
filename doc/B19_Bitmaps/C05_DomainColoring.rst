

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />







|newpage|




Domain coloring
==============================================================



See also: https://www.dynamicmath.xyz/domain-coloring/

See also: https://iquilezles.org/articles/palettes/


See also: https://github.com/jcponce/complex/tree/gh-pages/dctools

See also:  Wegert :cite:p:`Wegert2012`.

See also: Matplotlib and MayaVi implementation of domain coloring by E. Petrisor,  https://nbviewer.org/github/empet/Math/blob/master/DomainColoring.ipynb


See also: https://en.wikipedia.org/wiki/Domain_coloring

See also: https://notebook.community/empet/Math/DomainColoring





|newpage|


Domain coloring without contours: `f(z) = (z^3-1)/z`
--------------------------------------------------------------------------------


The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_DomainColoring.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C05_DomainColoring/D01_DomainColoring.py>`__.

To produce the figure as shown below, the try-block at the end of the file should look like this:


.. code-block:: python

    try:
        if __name__ == '__main__':
            DomainColoring(func=lambda z:(z**3-1)/z, style='c', re=[-1.5, 1.5], 
                im=[-1.5, 1.5], Title=r'$f(z)=\dfrac{z^3-1}{z}$', daxis=True)


.. image:: ../_static/Combining2D3D/DomainColoring1/domaincoloring_c.*




|newpage|



Domain coloring with contours of the phase: `f(z) = (z^3-1)/z`
--------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_DomainColoring.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C05_DomainColoring/D01_DomainColoring.py>`__.

To produce the figure as shown below, the try-block at the end of the file should look like this:


.. code-block:: python

    try:
        if __name__ == '__main__':
            DomainColoring(func=lambda z:(z**3-1)/z, style='p', re=[-1.5, 1.5], 
                im=[-1.5, 1.5], Title=r'$f(z)=\dfrac{z^3-1}{z}$', daxis=True)



.. image:: ../_static/Combining2D3D/DomainColoring1/domaincoloring_p.*




|newpage|


Domain coloring with contours of the modulus: `f(z) = (z^3-1)/z`
--------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_DomainColoring.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C05_DomainColoring/D01_DomainColoring.py>`__.

To produce the figure as shown below, the try-block at the end of the file should look like this:


.. code-block:: python

    try:
        if __name__ == '__main__':
            DomainColoring(func=lambda z:(z**3-1)/z, style='m', re=[-1.5, 1.5], 
                im=[-1.5, 1.5], Title=r'$f(z)=\dfrac{z^3-1}{z}$', daxis=True)


.. image:: ../_static/Combining2D3D/DomainColoring1/domaincoloring_m.*




|newpage|


Domain coloring with contours of phase and modulus: `f(z) = (z^3-1)/z`
--------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_DomainColoring.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C05_DomainColoring/D01_DomainColoring.py>`__.

To produce the figure as shown below, the try-block at the end of the file should look like this:


.. code-block:: python

    try:
        if __name__ == '__main__':
            DomainColoring(func=lambda z:(z**3-1)/z, style='pm', re=[-1.5, 1.5], 
                im=[-1.5, 1.5], Title=r'$f(z)=\dfrac{z^3-1}{z}$', daxis=True)


.. image:: ../_static/Combining2D3D/DomainColoring1/domaincoloring_pm.*









|newpage|


Domain coloring with contours of phase and modulus: `f(z) = (z^6-1)/(z^{12}+1)`
--------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_DomainColoring.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C05_DomainColoring/D01_DomainColoring.py>`__.

To produce the figure as shown below, the try-block at the end of the file should look like this:


.. code-block:: python

    try:
        if __name__ == '__main__':
            DomainColoring(func=lambda z:(z**6-1) / (z**12+1), style='pm', re=[-2.0, 2.0], 
                im=[-2.0, 2.0], Title=r'$f(z)=\dfrac{z^6-1}{z^{12}+1}$', daxis=True)

.. image:: ../_static/Combining2D3D/DomainColoring2/dc_poly6_12.*




|newpage|


Domain coloring with contours of phase and modulus: `f(z) = \exp(1/z)`
--------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_DomainColoring.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C05_DomainColoring/D01_DomainColoring.py>`__.

To produce the figure as shown below, the try-block at the end of the file should look like this:


.. code-block:: python

    try:
        if __name__ == '__main__':
            DomainColoring(func=lambda z:np.exp(1/z), style='pm', re=[-2.0, 2.0], 
                im=[-2.0, 2.0], Title=r'$f(z)=\exp(1/z)$', daxis=True)


.. image:: ../_static/Combining2D3D/DomainColoring2/dc_exp_1overz.*





|newpage|


Domain coloring with contours of phase and modulus: `f(z) = \exp(1/z^2)`
--------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_DomainColoring.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C05_DomainColoring/D01_DomainColoring.py>`__.

To produce the figure as shown below, the try-block at the end of the file should look like this:


.. code-block:: python

    try:
        if __name__ == '__main__':
            DomainColoring(func=lambda z:np.exp(1.0 / z**2), style='pm', re=[-1.5, 1.5], 
                im=[-1.5, 1.5], Title=r'$f(z)=\exp(1/z^2)$', daxis=True)


.. image:: ../_static/Combining2D3D/DomainColoring2/dc_exp_1overz2_.*





|newpage|


Domain coloring with contours of phase and modulus: `f(z) = z \sin(1/z)`
--------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_DomainColoring.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C05_DomainColoring/D01_DomainColoring.py>`__.

To produce the figure as shown below, the try-block at the end of the file should look like this:


.. code-block:: python

    try:
        if __name__ == '__main__':
            DomainColoring(func=lambda z:z*np.sin(1/z), style='pm', re=[-0.6, 0.6], 
                im=[-0.6, 0.6], Title=r'$f(z)=z \cdot \sin(1/z)$', daxis=True)


.. image:: ../_static/Combining2D3D/DomainColoring2/dc_z_sin_1overz.*





|newpage|


Domain coloring with contours of phase and modulus: `f(z) = \sin(z) / (z-i)^2`
--------------------------------------------------------------------------------

The Python code for the example below can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder in the file `D01_DomainColoring.py <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B19_Bitmaps/C05_DomainColoring/D01_DomainColoring.py>`__.

To produce the figure as shown below, the try-block at the end of the file should look like this:


.. code-block:: python

    try:
        if __name__ == '__main__':
            DomainColoring(func=lambda z:np.sin(z) / (z-1j)**2, style='pm', re=[-3, 3], 
                im=[-3, 3], Title=r'$f(z)=\dfrac{\sin(z)}{(z-i)^2}$', daxis=True)


.. image:: ../_static/Combining2D3D/DomainColoring2/dc_z_sin_z_over_z-i_2.*







