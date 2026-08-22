



.. |newpage| raw:: latex

   \newpage


.. |begin_flushleft| raw:: latex

   \begin{flushleft}


.. |end_flushleft| raw:: latex

   \end{flushleft}


.. |vspace| raw:: html

   <br />






|newpage|



.. _rst_net_groups_of_contexts: 

Mathematical functions in fixed precision
=====================================================================================

Various additional numerical context support C\# and Python. It is convenient to divide them into groups to make referencing them per function description more efficient.

The following groups of contexts are available:

* Context group ``ctx53``: this context group includes ``math53`` and ``cmath53`` (see :ref:`math53 <rst_math53_def>`). Almost all functions are from the DAMath library, with a few functions from Boost Math, Scipy, Julia and other libraries available on Github.

* Context group ``ctxcpp``: this context group includes contexts which contain functions of the C++ standard library, the Boost Math/Multiprecision/Odeint libraries, the Eigen library, and functions which can easily be derived from them. They include contexts in fixed precision: ``sreal`` and ``scplx`` (see :ref:`sctx <rst_sreal_def>`), ``dreal`` and ``dcplx`` (see :ref:`dctx <rst_dreal_def>`),  ``ereal`` and ``ecplx`` (see :ref:`ectx <rst_ereal_def>`), ``qreal`` and ``qcplx`` (see :ref:`qctx <rst_qreal_def>`), ``oreal`` and ``ocplx`` (see :ref:`octx <rst_oreal_def>`), ; and contexts in arbitrary precision, which are part of XlCalcNet2 (which hence needs to be installed): ``mreal`` and ``mcplx`` (see :ref:`mctx <rst_mreal_def>`).

* Context group  ``ctxflint``: this context group includes contexts which contain functions of the Flint 3.1 library, the Eigen library, and functions which can easily be derived from them. These are contexts in fixed and in arbitrary precision, which are part of XlCalcNet2 (which hence needs to be installed). They include ``sflint`` and ``sflintc`` (see :ref:`sflint <rst_srealflint_def>`), ``dflint`` and ``dflintc`` (see :ref:`dflint <rst_drealflint_def>`),  ``eflint`` and ``eflintc`` (see :ref:`eflint <rst_erealflint_def>`), ``qflint`` and ``qflintc`` (see :ref:`qflint <rst_qrealflint_def>`), ``oflint`` and ``oflintc`` (see :ref:`oflint <rst_orealflint_def>`), ``mflint`` and ``mflintc`` (see :ref:`mflint <rst_mreal_def>`), ``aflint`` and ``aflintc`` (see :ref:`aflint <rst_areal_def>`). 












|newpage|


.. _rst_math53_def: 

Scalar functions with ``Double`` and ``Complex``: ``math53`` and  ``cmath53``
------------------------------------------------------------------------------------------

DAMath library.


The source code for the module ``math53`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/math53.cs


The source code for the module ``cmath53`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/cmath53.cs


Double and Complex fully support Boost.Math and Eigen.


https://en.wikipedia.org/wiki/Double-precision_floating-point_format






|newpage|

.. _rst_sreal_def: 

Binary floating point, single precision: ``sreal`` and ``scplx``
----------------------------------------------------------------------

sreal and scplx fully support Boost.Math and Eigen.

https://en.wikipedia.org/wiki/Single-precision_floating-point_format



The source code for the module ``sreal`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/sreal.cs


The source code for the module ``scplx`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/scplx.cs





|newpage|

.. _rst_dreal_def: 

Binary floating point, double precision: ``dreal`` and ``dcplx``
--------------------------------------------------------------------------

dreal and dcplx fully support Boost.Math and Eigen.

https://en.wikipedia.org/wiki/Double-precision_floating-point_format



The source code for the module ``dreal`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/dreal.cs


The source code for the module ``dcplx`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/dcplx.cs





|newpage|

.. _rst_ereal_def: 


Binary floating point, extended precision: ``ereal`` and ``ecplx``
----------------------------------------------------------------------------

ereal and ecplx fully support Boost.Math and Eigen.


https://en.wikipedia.org/wiki/Extended_precision



The source code for the module ``ereal`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/ereal.cs


The source code for the module ``ecplx`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/ecplx.cs





|newpage|

.. _rst_qreal_def: 


Binary floating point, quadruple precision: ``qreal`` and ``qcplx``
------------------------------------------------------------------------------

qreal and qcplx fully support Boost.Math and Eigen.

https://en.wikipedia.org/wiki/Quadruple-precision_floating-point_format



The source code for the module ``qreal`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/qreal.cs


The source code for the module ``qcplx`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/qcplx.cs






|newpage|

.. _rst_oreal_def: 


Binary floating point, octuple precision: ``oreal`` and  ``ocplx``
---------------------------------------------------------------------------------

oreal and ocplx fully support Boost.Math and Eigen.

https://en.wikipedia.org/wiki/Octuple-precision_floating-point_format




The source code for the module ``oreal`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/oreal.cs


The source code for the module ``ocplx`` can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/FixedPrec/ocplx.cs






