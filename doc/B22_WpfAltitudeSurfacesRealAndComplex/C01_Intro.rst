

.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />










Special techniques for height surfaces, real and complex functions
================================================================================



.. _rst_wpf_complex_function: 

Wpf figures as standard display of complex functions
-------------------------------------------------------------

This is a description of the standard display of complex functions, using the square function as an example:


The figures below are showing the real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex function `z = \mathrm{sqr}(x + iy)` with  `-2 \le x \le 2` (blue axis), `-2 \le y \le 2` (red axis), `-10 \le z \le 10` (green axis).



|01a_TestSquare_re1| `\quad` |01b_TestSquare_im1| `\quad` |01c_TestSquare_abs1|

.. |01a_TestSquare_re1| image:: ../_static/ExplicitSurfaces/CplxRoots/01a_TestSquare_re.3D.xml.jpg
   :width: 30 %

.. |01b_TestSquare_im1| image:: ../_static/ExplicitSurfaces/CplxRoots/01b_TestSquare_im.3D.xml.jpg
   :width: 30 %

.. |01c_TestSquare_abs1| image:: ../_static/ExplicitSurfaces/CplxRoots/01c_TestSquare_abs.3D.xml.jpg
   :width: 30 %



.. note::
    Although the range of the green axis is stated in the form `z_{\text{min}} \le z \le z_{\text{max}}`, with `z_{\text{min}} \ne 0` in general, this applies only for the figures showing the real and imaginary part. For the figure showing the absolute value we have always `z_{\text{min}} = 0`. This note is omitted from the standard text describing complex functions in this manual for better readability.






.. _rst_mpm_loglog_transformation: 

Truncation vs loglog transformation
---------------------------------------------------



    |TestTruncated| `\quad` |TestLogLog|

    .. |TestTruncated| image:: ../_static/ExplicitSurfaces/Intro/01a_TestLogLogErf_abs.3D.xml.jpg
       :width: 30 %

    .. |TestLogLog| image:: ../_static/ExplicitSurfaces/Intro/01b_TestLogLogErf_abs.3D.xml.jpg
       :width: 30 %



    **3D wpf plot**: Surface plot without cutting of the branch cut (left figure), Surface plot with cutting of the branch cut  (right figure)







Displaying branch cuts
-----------------------------------------------------



    |TestWithoutCut| `\quad` |TestWithCut|

    .. |TestWithoutCut| image:: ../_static/ExplicitSurfaces/Intro/02a_TestBranchCutsLog_im.3D.xml.jpg
       :width: 30 %

    .. |TestWithCut| image:: ../_static/ExplicitSurfaces/Intro/02b_TestBranchCutsLog_im.3D.xml.jpg
       :width: 30 %




    **3D wpf plot**: Surface plot without cutting of the branch cut (left figure). Surface plot with cutting of the branch cut (right figure).






