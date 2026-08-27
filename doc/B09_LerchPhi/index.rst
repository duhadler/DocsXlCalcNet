



************************************************************************
Lerch's phi and related
************************************************************************


The Lerch transcendent generalizes various other functions:

The polygamma function (see :ref:`polygamma() <rst_mpm_polygamma>`) is given by

.. math ::   \psi^{(n)}(z) = (-1)^{n+1} n! \: \Phi(1, n+1, z).


The polylogarithm  (see :ref:`polylog() <rst_mpm_polylog>`) is given by

.. math :: \text{Li}_s(z) = z \Phi(z, s, 1)).


The Legendre chi function (see :ref:`legendre_chi() <rst_mpm_legendre_chi>`) is  given by

.. math ::  \chi _{n}(z)=2^{-n}z\Phi (z^{2},n,1/2).


The Hurwitz zeta function  (see :ref:`hurwitz() <rst_mpm_hurwitz>`) is given by

.. math :: \zeta(s,a) =  \Phi(1, s, a).


The Riemann zeta function (see :ref:`zeta() <rst_mpm_zeta>`) is given by

.. math ::  \zeta (s)=\Phi (1,s,1).


The Dirichlet eta function (see :ref:`dirichlet_eta() <rst_mpm_dirichlet_eta>`) is given by

.. math ::  \eta (s)=\Phi (-1,s,1).



Various identities include:

.. math ::  \Phi (z,s,a)=z^{n}\Phi (z,s,a+n)+\sum _{k=0}^{n-1}{\frac {z^{k}}{(k+a)^{s}}}



and


.. math ::  \Phi (z,s-1,a)=\left(a+z{\frac {\partial }{\partial z}}\right)\Phi (z,s,a)

and

.. math ::  \Phi (z,s+1,a)=-\,{\frac {1}{s}}{\frac {\partial }{\partial a}}\Phi (z,s,a).




The source code for the C\# tests in Visual Studio is divided by real and complex modules:

The source code for the C\# tests in Visual Studio using real modules can be found online in the ``XlCalcNet`` repository or in the corresponding local ``XlCalcNet`` folder in the file `B09a_RealLerchPhi.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/TestFixedAndArbPrecCS/B09a_RealLerchPhi.cs>`__,

The source code for the C\# tests in Visual Studio using complex modules can be found online in the ``XlCalcNet`` repository or in the corresponding local ``XlCalcNet`` folder in the file `B09b_CplxLerchPhi.cs <https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Source/TestFixedAndArbPrecCS/B09b_CplxLerchPhi.cs>`__,











.. toctree ::
    :maxdepth: 5


    C01_LerchPhi.rst

    C02_Polygamma.rst

    C03_Polylogarithm.rst

    C04_HurwitzZeta.rst

    C05_RiemannZeta.rst


