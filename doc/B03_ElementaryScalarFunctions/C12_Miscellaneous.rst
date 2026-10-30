

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|


Miscellaneous functions
===============================================================================



Lambert `W` function, `W_0(x)`
-------------------------------------------------------------------------------

.. method:: ctx.lambert_w0(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.


    Returns `W_0(x)`, the real-valued principal branch of the Lambert W function for `x > -1/e`, with `W_0(x) \ge -1` for `x<0`. The Lambert W function is defined as the solution of `x = W(x) \exp(W(x))`.

    See also  Wikipedia :cite:p:`WikipediaFun82`, MathWorld :cite:p:`WolframFun82`, NIST :cite:p:`DLMFun82`,  BoostMath :cite:p:`BoostFun82`, :cite:t:`Corless1996`, :cite:t:`Ehrhardt2018` (3.10.15), Flint :cite:p:`FlintFun82`, Flint :cite:p:`FlintFun83`, Mpmath :cite:p:`MpmathFun82`.



    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -0.1; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.lambert_w0(x)))
            fpm:  -0.111832559158963
            mpm:  -0.111832559158962964833569456820265842272645362291265863329689772762194331960008827385487011
            dpm:  NaN
            ipm: [nan,
                  nan]
            gpm:  -0.111832559158962964833569456820265842272645362291265863329689772762194331960008827385487011
            apm: [-0.111832559158962964833569456820265842272645362291265863329689772762194331960008827385487011 +/- 1.47e-91]
         math53:  -0.111832559158963
          sreal:  -0.1118326
          dreal:  -0.111832559158963
          ereal:  -0.11183255915896296483
          qreal:  -0.111832559158962964833569456820266
          oreal:  -0.11183255915896296483356945682026584227264536229126586332968977276219433
          mreal:  -0.111832559158962964833569456820265842272645362291265863329689772762194331960008827385487011
         sflint:  -0.1118326
         dflint:  -0.111832559158963
         eflint:  -0.11183255915896296484
         qflint:  -0.111832559158962964833569456820266
         oflint:  -0.11183255915896296483356945682026584227264536229126586332968977276219433
         mflint:  -0.111832559158962964833569456820265842272645362291265863329689772762194331960008827385487011
         aflint: [-0.111832559158962964833569456820265842272645362291265863329689772762194331960008827385487011 +/- 2.17e-91]













Lambert `W` function, `W_{-1}(x)`
-------------------------------------------------------------------------------

.. method:: ctx.lambert_wm1(x)

    where ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflint``.

    Returns `W_{-1}(x)`, the second real-valued, non-principal, branch of the Lambert W function  for `-1/e < x < 0`, with `W_{-1}(x) \le -1` for `x<0`. The Lambert W function is defined as the solution of `x = W(x) \exp(W(x))`, Flint :cite:p:`FlintFun82`, Flint :cite:p:`FlintFun83`.

    See also  Wikipedia :cite:p:`WikipediaFun82`, MathWorld :cite:p:`WolframFun82`, NIST :cite:p:`DLMFun82`,  BoostMath :cite:p:`BoostFun82`, :cite:t:`Ehrhardt2018` (3.10.15), Mpmath :cite:p:`MpmathFun82`.

    

    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -0.1; gui.setdps(90)
        >>> for ctx in ctxlistreal: print(ctx.fmtname + ': ' + ctx.fmt(ctx.sin(x)))
            fpm:  -3.5771520639573
            mpm:  -3.57715206395729721840939196351199488040179625779307592368352775579168723635057546286146366
            dpm:  NaN
            ipm: [nan,
                  nan]
            gpm:  -3.5771520639572972184093919635119948804017962577930759236835277557916872363505754628614636599
            apm: [-3.57715206395729721840939196351199488040179625779307592368352775579168723635057546286146366 +/- 5.39e-90]
         math53:  -3.5771520639573
          sreal:  -3.577152
          dreal:  -3.5771520639573
          ereal:  -3.5771520639572972184
          qreal:  -3.57715206395729721840939196351199
          oreal:  -3.5771520639572972184093919635119948804017962577930759236835277557916872
          mreal:  -3.57715206395729721840939196351199488040179625779307592368352775579168723635057546286146365
         sflint:  -3.577152
         dflint:  -3.5771520639573
         eflint:  -3.5771520639572972184
         qflint:  -3.57715206395729721840939196351199
         oflint:  -3.5771520639572972184093919635119948804017962577930759236835277557916872
         mflint:  -3.57715206395729721840939196351199488040179625779307592368352775579168723635057546286146365
         aflint: [-3.57715206395729721840939196351199488040179625779307592368352775579168723635057546286146365 +/- 7.23e-90]









Lambert `W` (general case)
-------------------------------------------------------------------------------

.. method:: ctx.lambert_wk(z, k=0)

    where ``ctx`` is ``math53``, ``ctxboost``, ``ctxflint``.

    Returns the Lambertw function of *z*.

    See also  BoostMath :cite:p:`BoostFun82`,   Wikipedia :cite:p:`WikipediaFun82`, MathWorld :cite:p:`WolframFun82`, NIST :cite:p:`DLMFun82`, :cite:t:`Corless1996`, :cite:t:`Ehrhardt2018` (4.2.39), Flint :cite:p:`FlintFun82`, Flint :cite:p:`FlintFun83`, Mpmath :cite:p:`MpmathFun82`.


    The Lambert W function `W(z)` is defined as the inverse function of `w \exp(w)`. In other words, the value of `W(z)` is such that `z = W(z) \exp(W(z))` for any complex number `z`.

    The Lambert W function is a multivalued function with infinitely many branches `W_k(z)`, indexed by `k \in \mathbb{Z}`. Each branch gives a different solution `w` of the equation `z = w \exp(w)`. All branches are supported:

    * ``lambertw(z)`` gives the principal solution (branch 0)

    * ``lambertw(z, k)`` gives the solution on branch `k`

    The Lambert W function has two partially real branches: the principal branch (`k = 0`) is real for real `z > -1/e`, and the `k = -1` branch is real for `-1/e < z < 0`. All branches except `k = 0` have a logarithmic singularity at `z = 0`.

    The definition, implementation and choice of branches is based on :cite:t:`Corless1996`.



    |06a_TestLambertW_re| `\quad` |06b_TestLambertW_im| `\quad` |06c_TestLambertW_abs|

    .. |06a_TestLambertW_re| image:: ../_static/ExplicitSurfaces/CplxRoots/06a_TestLambertW_re.3D.xml.jpg
       :width: 30 %

    .. |06b_TestLambertW_im| image:: ../_static/ExplicitSurfaces/CplxRoots/06b_TestLambertW_im.3D.xml.jpg
       :width: 30 %

    .. |06c_TestLambertW_abs| image:: ../_static/ExplicitSurfaces/CplxRoots/06c_TestLambertW_abs.3D.xml.jpg
       :width: 30 %



    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 3; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.lambert_wk(x, k)))
            fpm:  (-1.2961584376621, 19.9818493888978)
            mpm:  (-1.29615843766209539570813065197052520459642834616, 19.981849388897787833451280005096873265316351365421)
        cmath53:  (-1.2961584376621, 19.9818493888978)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 3; gui.setdps(50)
        >>> for ctx in gui.ctxlist_noboost_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.lambert_wk(x, k))))
            fpm:  -1.2961584376621
            mpm:  -1.29615843766209539570813065197052520459642834616
            dpm:  NaN
            ipm: [nan,
                  nan]
            gpm:  -1.29615843766209539570813065197052520459642834616
            apm: [-1.2961584376620953957081306519705252045964283461600 +/- 2.09e-50]
        cmath53:  -1.2961584376621
        sflintc:  -1.296158
        dflintc:  -1.2961584376621
        eflintc:  -1.2961584376620953957
        qflintc:  -1.29615843766209539570813065197053
        oflintc:  -1.2961584376620953957081306519705252045964283461600168785872763086319775
        mflintc:  -1.29615843766209539570813065197052520459642834616
        aflintc: [-1.2961584376620953957081306519705252045964283461600 +/- 2.54e-50]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = -5.1+2j;  k = 3; gui.setdps(50)
        >>> for ctx in gui.ctxlist_noboost_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.lambert_wk(x, k))))
            fpm:  19.9818493888978
            mpm:  19.9818493888977878334512800050968732653163513654210365975711218009705488766730856100222608
            dpm:  0
            ipm: [0.0,
                  0.0]
            gpm:  19.981849388897787833451280005096873265316351365421036597571121800970548876673085610022260802
            apm: [19.9818493888977878334512800050968732653163513654210365975711218009705488766730856100222608 +/- 2.57e-89]
        cmath53:  19.9818493888978
        sflintc:  19.98185
        dflintc:  19.9818493888978
        eflintc:  19.981849388897787834
        qflintc:  19.9818493888977878334512800050969
        oflintc:  19.981849388897787833451280005096873265316351365421036597571121800970549
        mflintc:  19.9818493888977878334512800050968732653163513654210365975711218009705488766730856100222608
        aflintc: [19.9818493888977878334512800050968732653163513654210365975711218009705488766730856100222608 +/- 3.74e-89]












Arithmetic-geometric mean
-------------------------------------------------------------------------------

.. method:: ctx.agm(x, y=1)

    where ``ctx`` is ``math53``, ``mathc53``, ``ctxboost`` or ``ctxflint``.



    Returns the arithmetic-geometric mean of `|x|` and `|y|`. See also  Wikipedia :cite:p:`WikipediaFun113`, MathWorld :cite:p:`WolframFun113`, :cite:t:`Ehrhardt2018` (4.2.1), :cite:t:`Ehrhardt2018` (4.2.2), Mpmath :cite:p:`MpmathFun113`. 

    With `a_0 = \max(|x|, |y|)`, `b_0 = \min(|x|, |y|)` the AGM is calculated using the recurrence formulas

    .. math:: a_{n+1} = \tfrac{1}{2} (a_n + b_n), \quad b_{n+1} = \sqrt{a_n b_n}.

    The sequences converge quadratically to a common limit and `a_n \geq b_n`. The iteration is terminated if `a_n - b_n \leq \epsilon a_n`, where `\epsilon` is less than the square root of the machine epsilon. The result is `(a_n + b_n )/2`.


    The function `\text{agm}(a,b)` can also be expressed in closed form in terms of the complete elliptic integral of the first kind `K(k)` as

    .. math :: \text{agm}(a,b) = \frac{(a+b)\pi}{4K((a-b)/(a+b))}. 



    |01a_TestAGM_re| `\quad` |01b_TestAGM_im| `\quad` |01c_TestAGM_abs|

    .. |01a_TestAGM_re| image:: ../_static/ExplicitSurfaces/CplxElliptic/01a_TestAGM_re.3D.xml.jpg
       :width: 30 %

    .. |01b_TestAGM_im| image:: ../_static/ExplicitSurfaces/CplxElliptic/01b_TestAGM_im.3D.xml.jpg
       :width: 30 %

    .. |01c_TestAGM_abs| image:: ../_static/ExplicitSurfaces/CplxElliptic/01c_TestAGM_abs.3D.xml.jpg
       :width: 30 %


   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the complex sine function `z = \sin(x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis). Function values are :ref:`loglog-transformed <rst_mpm_loglog_transformation>`.



    

    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1; y = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.agm(x, y)))
            fpm:  3.80480946181798
            mpm:  3.80480946181797638640492371413247210535521151164124372537438823873487755230166530999087551
            dpm:  NaN
            ipm: [nan,
                  nan]
            gpm:  3.8048094618179763864049237141324721053552115116412437253743882387348775523016653099908755102
            apm: [3.80480946181797638640492371413247210535521151164124372537438823873487755230166530999087551 +/- 5.60e-90]
         math53:  3.80480946181798
          sreal:  3.80481
          dreal:  3.80480946181798
          ereal:  3.8048094618179763866
          qreal:  3.80480946181797638640492371413247
          oreal:  3.8048094618179763864049237141324721053552115116412437253743882387348776
          mreal:  3.80480946181797638640492371413247210535521151164124372537438823873487755230166530999087551
         sflint:  3.804809
         dflint:  3.80480946181798
         eflint:  3.8048094618179763864
         qflint:  3.80480946181797638640492371413247
         oflint:  3.8048094618179763864049237141324721053552115116412437253743882387348776
         mflint:  3.80480946181797638640492371413247210535521151164124372537438823873487755230166530999087551
         aflint: [3.8048094618179763864049237141324721053552115116412437253743882387348775523016653099908755 +/- 1.97e-89]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1+2j;  y = 2.7+3j; gui.setdps(50)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.agm(x, y)))
            fpm:  (3.88305290215932, 2.58876620479596)
            mpm:  (3.8830529021593203337030666542457879036456014594432, 2.5887662047959584832206870784308826491321583155897)
        cmath53:  (3.88305290215932, 2.58876620479596)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1+2j;  y = 2.7+3j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.agm(x, y))))
            fpm:  3.88305290215932
            mpm:  3.88305290215932033370306665424578790364560145944321244383222669322061560629984624030717368
            dpm:  NaN
            ipm: [nan,
                  nan]
            gpm:  3.8830529021593203337030666542457879036456014594432124438322266932206156062998462403071736798
            apm: [3.8830529021593203337030666542457879036456014594432124438322266932206156062998462403071737 +/- 3.82e-89]
        cmath53:  3.88305290215932
        sflintc:  3.883053
        dflintc:  3.88305290215932
        eflintc:  3.8830529021593203336
        qflintc:  3.88305290215932033370306665424579
        oflintc:  3.8830529021593203337030666542457879036456014594432124438322266932206156
        mflintc:  3.88305290215932033370306665424578790364560145944321244383222669322061560629984624030717366
        aflintc: [3.8830529021593203337030666542457879036456014594432124438322266932206156062998462403071737 +/- 7.69e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> x = 5.1+2j;  y = 2.7+3j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.agm(x, y))))
            fpm:  2.58876620479596
            mpm:  2.5887662047959584832206870784308826491321583155896964154174485102720221605220006010768377
            dpm:  0
            ipm: [0.0,
                  0.0]
            gpm:  2.5887662047959584832206870784308826491321583155896964154174485102720221605220006010768377001
            apm: [2.5887662047959584832206870784308826491321583155896964154174485102720221605220006010768377 +/- 9.49e-90]
        cmath53:  2.58876620479596
        sflintc:  2.588766
        dflintc:  2.58876620479596
        eflintc:  2.5887662047959584832
        qflintc:  2.58876620479595848322068707843088
        oflintc:  2.5887662047959584832206870784308826491321583155896964154174485102720222
        mflintc:  2.58876620479595848322068707843088264913215831558969641541744851027202216052200060107683769
        aflintc: [2.5887662047959584832206870784308826491321583155896964154174485102720221605220006010768377 +/- 3.48e-89]












