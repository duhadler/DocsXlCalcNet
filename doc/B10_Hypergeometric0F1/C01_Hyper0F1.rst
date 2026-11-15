

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





Hypergeometric Limit Function `\,_0F_1`
===============================================================================




Confluent Hypergeometric Limit Function `{}_0F_1(b,x)`
-------------------------------------------------------------------------------------

.. method:: ctx.hyperg_0f1(b, x)

    Returns `\displaystyle {}_0F_1(b,x) = \sum_{k=0}^{\infty} \frac{1}{(b)_k} \frac{x^k}{k!}`, the confluent hypergeometric limit function, where `b \ne 0,-1,-2,\ldots`

    See also  Wikipedia :cite:p:`WikipediaFun90`, MathWorld :cite:p:`WolframFun90`  BoostMath :cite:p:`BoostFun90`, :cite:t:`Ehrhardt2018` (3.8.6), Flint :cite:p:`FlintFun90`, Flint :cite:p:`FlintFun90a`, Mpmath :cite:p:`MpmathFun90`.

    If ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `b, x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `b \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `b, x \in \mathbb{C}` is accepted. 



    |01a_TestHypergeom0F1_re| `\quad` |01b_TestHypergeom0F1_im| `\quad` |01c_TestHypergeom0F1_abs|

    .. |01a_TestHypergeom0F1_re| image:: ../_static/ExplicitSurfaces/Cplx0F1/01a_TestHypergeom0F1_re.3D.xml.jpg
       :width: 30 %

    .. |01b_TestHypergeom0F1_im| image:: ../_static/ExplicitSurfaces/Cplx0F1/01b_TestHypergeom0F1_im.3D.xml.jpg
       :width: 30 %

    .. |01c_TestHypergeom0F1_abs| image:: ../_static/ExplicitSurfaces/Cplx0F1/01c_TestHypergeom0F1_abs.3D.xml.jpg
       :width: 30 %


   

    **3D wpf plot**: real part (left figure), imaginary part (middle figure) and absolute value with color-coded phase (right figure) of the confluent hypergeometric limit function `z = {}_0F_1(b, x + iy)`, with `-6 \le x \le 6` (blue axis), `-6 \le y \le 6` (red axis), `-10 \le z \le 10` (green axis).






    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> b = 5.1; x = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_0f1(b, x)))
            fpm:  1.66274304199531
            mpm:  1.66274304199531316588189352423566440322055406857592936486429514269829008002070629426453764
            dpm:  1.66274304199531316588189352423566440322055406857592936486429514269829008002070629426453764
            gpm:  1.6627430419953131658818935242356644032205540685759293648642951426982900800207062942645376399
            apm: [1.662743041995313165881893524235664403220554068575929364864295142698290080020706294264538 +/- 4.20e-88]
         math53:  1.66274304199531
          sreal:  1.662743
          dreal:  1.66274304199531
          ereal:  1.6627430419953131657
          qreal:  1.66274304199531316588189352423566
          oreal:  1.6627430419953131658818935242356644032205540685759293648642951426982901
          mreal:  1.66274304199531316588189352423566440322055406857592936486429514269829008002070629426453764
         sflint:  1.662743
         dflint:  1.66274304199531
         eflint:  1.6627430419953131659
         qflint:  1.66274304199531316588189352423566
         oflint:  1.6627430419953131658818935242356644032205540685759293648642951426982901
         mflint:  1.66274304199531316588189352423566440322055406857592936486429514269829008002070629426453764
         aflint: [1.662743041995313165881893524235664403220554068575929364864295142698290080020706294264538 +/- 6.39e-88]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> b = -5.1;  x = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_0f1(b, x)))
            fpm:  (0.460183166364689, -0.371845943064386)
            mpm:  (0.460183166364689146797903793103889773271, -0.3718459430643864013938003628810750931339)
        cmath53:  (0.460183166364686, -0.371845943064386)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> b = -5.1;  x = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.hyperg_0f1(b, x))))
            fpm:  0.460183166364689
            mpm:  0.460183166364689146797903793103889773271070275977862226162287713985164793549649466398461056
            dpm:  0.460183166364689146797903793103889773271070275977862226162287713985164793549649466398461056
            gpm:  0.46018316636468914679790379310388977327107027597786222616228771398516479354964946639846105602
            apm: [0.4601831663646891467979037931038897732710702759778622261622877139851647935496494663984611 +/- 8.22e-89]
        cmath53:  0.460183166364686
        sflintc:  0.460183
        dflintc:  0.460183166364689
        eflintc:  0.46018316636468914666
        qflintc:  0.460183166364689146797903793103889
        oflintc:  0.46018316636468914679790379310388977327107027597786222616228771398516477
        mflintc:  0.460183166364689146797903793103889773271070275977862226162287713985164793549649466398461053
        aflintc: [0.460183166364689146797903793103889773271070275977862226162287713985164793549649466398461 +/- 1.58e-88]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> b = -5.1;  x = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hyperg_0f1(b, x))))
            fpm:  -0.371845943064386
            mpm:  -0.371845943064386401393800362881075093133834600776006198970238575885003896657030432130818945
            dpm:  -0.371845943064386401393800362881075093133834600776006198970238575885003896657030432130818945
            gpm:  -0.371845943064386401393800362881075093133834600776006198970238575885003896657030432130818945
            apm: [-0.3718459430643864013938003628810750931338346007760061989702385758850038966570304321308189 +/- 7.10e-89]
        cmath53:  -0.371845943064386
        sflintc:  -0.3718461
        dflintc:  -0.371845943064387
        eflintc:  -0.37184594306438640158
        qflintc:  -0.371845943064386401393800362881076
        oflintc:  -0.37184594306438640139380036288107509313383460077600619897023857588500393
        mflintc:  -0.371845943064386401393800362881075093133834600776006198970238575885003896657030432130818947
        aflintc: [-0.371845943064386401393800362881075093133834600776006198970238575885003896657030432130819 +/- 1.31e-88]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C01_Hyper0F1/D01a_Hyperg0F1Real.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C01_Hyper0F1/D01b_Hyperg0F1Cplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C01_Hyper0F1/D01_Hyperg0F1.cs>`__. 







|newpage|


Regularized Confluent Hypergeometric Limit Function `{}_0\widetilde{F}_1(b;x)`
------------------------------------------------------------------------------------------------------

.. method:: ctx.hyperg_0f1r(b, x)

    Returns `\displaystyle {}_0\widetilde{F}_1(b;x)  = \frac{1}{\Gamma(b)} {}_0F_1(b;x)`, the regularized  confluent hypergeometric limit function, for `b \ne 0, -1, -2, \cdots`, or, `\\` if `b = 0, -1, -2, \cdots = -n`, the corresponding limit `\displaystyle {}_0\widetilde{F}_1(b;x) = x^{n+1} {}_0\widetilde{F}_1(n+2;x) = \frac{x^{n+1}}{\Gamma(n+2)} {}_0F_1(n+2;x)`.

    See also  Wikipedia :cite:p:`WikipediaFun90`, MathWorld :cite:p:`WolframFun90a`  BoostMath :cite:p:`BoostFun90`, :cite:t:`Ehrhardt2018` (3.8.7), Flint :cite:p:`FlintFun90`, Flint :cite:p:`FlintFun90a`, Mpmath :cite:p:`MpmathFun90`.

    If ``ctx`` is ``math53``, ``ctxboost`` or ``ctxflintreal``, then `b, x \in \mathbb{R}` is exspected. If ``ctx`` is ``cmath53``, then `b \in \mathbb{R}` and `x \in \mathbb{C}` is exspected.  If ``ctx`` is ``ctxflintcplx`` then `b, x \in \mathbb{C}` is accepted. 





    An example with real input:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> b = -1.0; x = 2.7; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noipm_real: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_0f1r(b, x)))
            fpm:  8.25621044956316
            mpm:  8.25621044956316427799030242096803175226037688625271057469959714018855685554715047395265477
            dpm:  8.25621044956316427799030242096803175226037688625271057469959714018855685554715047395265477
            gpm:  8.2562104495631642779903024209680317522603768862527105746995971401885568555471504739526547702
            apm: [8.2562104495631642779903024209680317522603768862527105746995971401885568555471504739526548 +/- 4.41e-89]
         math53:  8.25621044956316
          sreal:  8.256211
          dreal:  8.25621044956316
          ereal:  8.2562104495631642798
          qreal:  8.25621044956316427799030242096803
          oreal:  8.2562104495631642779903024209680317522603768862527105746995971401885566
          mreal:  8.25621044956316427799030242096803175226037688625271057469959714018855685554715047395265476
         sflint:  8.256211
         dflint:  8.25621044956317
         eflint:  8.2562104495631642781
         qflint:  8.25621044956316427799030242096803
         oflint:  8.2562104495631642779903024209680317522603768862527105746995971401885569
         mflint:  8.25621044956316427799030242096803175226037688625271057469959714018855685554715047395265476
         aflint: [8.2562104495631642779903024209680317522603768862527105746995971401885568555471504739526548 +/- 7.47e-89]



    An example with complex input, using C\#-style formatting for complex numbers for the result 

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> b = -1.0;  x = 2.7+2j; gui.setdps(40)
        >>> for ctx in [fpm, mpm, cmath53]: print(ctx.fmtname + ': ' + ctx.fmt(ctx.hyperg_0f1r(b, x)))
            fpm:  (-3.33950514325732, 12.7488380828593)
            mpm:  (-3.339505143257323832539336034201892278158, 12.74883808285931598356818624276434101411)
        cmath53:  (-3.33950514325733, 12.7488380828594)



    An example with the same complex input as above, showing only the real part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> b = -5.1;  x = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.real(ctx.hyperg_0f1(b, x))))
            fpm:  -3.33950514325732
            mpm:  -3.33950514325732383253933603420189227815805627248594344260565996987141867019270768892436121
            dpm:  -3.33950514325732383253933603420189227815805627248594344260565996987141867019270768892436121
            gpm:  -3.3395051432573238325393360342018922781580562724859434426056599698714186701927076889243612101
            apm: [-3.3395051432573238325393360342018922781580562724859434426056599698714186701927076889243612 +/- 2.12e-89]
        cmath53:  -3.33950514325733
        sflintc:  -3.339505
        dflintc:  -3.33950514325732
        eflintc:  -3.3395051432573238325
        qflintc:  -3.33950514325732383253933603420189
        oflintc:  -3.3395051432573238325393360342018922781580562724859434426056599698714187
        mflintc:  -3.33950514325732383253933603420189227815805627248594344260565996987141867019270768892436121
        aflintc: [-3.3395051432573238325393360342018922781580562724859434426056599698714186701927076889243612 +/- 2.65e-89]


    An example with the same complex input as above, showing only the imaginary part of the result:

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> b = -5.1;  x = 2.7+2j; gui.setdps(90)
        >>> for ctx in gui.ctxlist_noboost_cplx: 
        ...     print(ctx.fmtname + ': ' +  ctx.realctx.fmt(ctx.imag(ctx.hyperg_0f1(b, x))))
            fpm:  12.7488380828593
            mpm:  12.7488380828593159835681862427643410141060265077001449080649084109964442628031290850774142
            dpm:  12.7488380828593159835681862427643410141060265077001449080649084109964442628031290850774142
            gpm:  12.748838082859315983568186242764341014106026507700144908064908410996444262803129085077414201
            apm: [12.7488380828593159835681862427643410141060265077001449080649084109964442628031290850774142 +/- 3.30e-89]
        cmath53:  12.7488380828594
        sflintc:  12.74884
        dflintc:  12.7488380828593
        eflintc:  12.748838082859315984
        qflintc:  12.7488380828593159835681862427643
        oflintc:  12.748838082859315983568186242764341014106026507700144908064908410996444
        mflintc:  12.7488380828593159835681862427643410141060265077001449080649084109964442628031290850774142
        aflintc: [12.7488380828593159835681862427643410141060265077001449080649084109964442628031290850774142 +/- 4.22e-89]


    The above and additional examples can be found online in the ``DataXlCalcNet`` repository or in the corresponding local ``DataXlCalcNet`` folder for `Python (real input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C01_Hyper0F1/D02a_Hyperg0F1rReal.py>`__, `Python (complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A01_ExamplesPython/B10_Hypergeometric0F1/C01_Hyper0F1/D02b_Hyperg0F1rCplx.py>`__, and `C\# (real or complex input) <https://github.com/duhadler/DataXlCalcNet/blob/master/DataXlCalcNet/A02_ExamplesCSharp/B10_Hypergeometric0F1/C01_Hyper0F1/D02_Hyperg0F1r.cs>`__. 





