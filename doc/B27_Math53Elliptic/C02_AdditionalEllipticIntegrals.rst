

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Elliptic integrals
===============================================================================




Legendre complete elliptic integral `B(k)`
-------------------------------------------------------------------------------

.. method:: math53.elliptic_b(k)

    Returns the Legendre complete elliptic integral  `\displaystyle  B(k) = \int_0^{\pi/2} \frac{ \cos^2(t) \mathrm{d}t}{\sqrt{1-k^2 \sin^2(t)}} = \frac{E(k)-\sqrt{1-k^2} K(k)}{k^2}`. See also Wikipedia :cite:p:`WikipediaFun148`, MathWorld :cite:p:`WolframFun148`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun148`, :cite:t:`Ehrhardt2018` (3.2.1.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.elliptic_b(-0.9333)
        0.9305395801783577
        >>> math53.elliptic_b(0.0)
        0.7853981633974483
        >>> math53.elliptic_b(0.9333)
        0.9305395801783577







Legendre complete elliptic integral `D(k)`
-------------------------------------------------------------------------------

.. method:: math53.elliptic_d(k)

    Returns the Legendre complete elliptic integral  `\displaystyle  D(k) = \int_0^{\pi/2} \frac{ \sin^2(t) \mathrm{d}t}{\sqrt{1-k^2 \sin^2(t)}} = \frac{K(k) - E(k)}{k^2}`. See also  Wikipedia :cite:p:`WikipediaFun148`, MathWorld :cite:p:`WolframFun148`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun148`, :cite:t:`Ehrhardt2018` (3.2.1.5).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.elliptic_d(-0.9333)
        1.5285669226805516
        >>> math53.elliptic_d(0.0)
        0.7853981633974483
        >>> math53.elliptic_d(0.9333)
        1.5285669226805516






Legendre incomplete elliptic integral `B(\phi, k)`
-------------------------------------------------------------------------------

.. method:: math53.elliptic_b_inc(phi, k)

    Returns the Legendre complete elliptic integral ,  `\displaystyle  B(k) = \int_0^{\phi} \frac{ \cos^2(t) \mathrm{d}t}{\sqrt{1-k^2 \sin^2(t)}} = \frac{E(\phi, k)-\sqrt{1-k^2} F(\phi, k)}{k^2}`. See also Wikipedia :cite:p:`WikipediaFun148`, MathWorld :cite:p:`WolframFun148`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun148`, :cite:t:`Ehrhardt2018` (3.2.1.9).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.elliptic_b_inc(0.4, -0.9333)
        0.3880334013629784
        >>> math53.elliptic_b_inc(0.7, 0.0)
        0.5963624324971151
        >>> math53.elliptic_b_inc(1.2, 0.9333)
        0.8930544029455502







Legendre incomplete elliptic integral `D(\phi, k)`
-------------------------------------------------------------------------------

.. method:: math53.elliptic_d_inc(phi, k)

    Returns the Legendre complete elliptic integral ,  `\displaystyle  D(k) = \int_0^{\phi} \frac{ \sin^2(t) \mathrm{d}t}{\sqrt{1-k^2 \sin^2(t)}} = \frac{F(\phi, k)-E(\phi, k)}{k^2}`. See also Wikipedia :cite:p:`WikipediaFun148`, MathWorld :cite:p:`WolframFun148`, NIST :cite:p:`DLMFun148`, BoostMath :cite:p:`BoostFun153a`, :cite:t:`Ehrhardt2018` (3.2.1.10).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.elliptic_d_inc(0.4, -0.9333)
        0.021551828843784506
        >>> math53.elliptic_d_inc(0.7, 0.0)
        0.10363756750288494
        >>> math53.elliptic_d_inc(1.2, 0.9333)
        0.6473333304003238







Heuman's Lambda function, `\Lambda_0(\phi,k)`
-------------------------------------------------------------------------------

.. method:: math53.heuman_lambda(phi,k)

    Returns Heuman's Lambda function `\Lambda_0(\phi,k)`. See also MathWorld :cite:p:`WolframFun154b`, BoostMath :cite:p:`BoostFun154b`, :cite:t:`Ehrhardt2018` (3.2.6).

    .. math ::    \Lambda_0(\phi,k) = \frac{F(\phi, \sqrt{1-k^2})}{K(\sqrt{1-k^2})} + \frac{2}{\pi} K(k)  Z(\phi, \sqrt{1-k^2}) , \quad |k| \le 1.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.heuman_lambda(0.4, -0.9333)
        0.28392272091599396
        >>> math53.heuman_lambda(0.7, 0.0)
        0.644217687237691
        >>> math53.heuman_lambda(1.2, 0.9333)
        0.7921071008822748





Jacobi Zeta function, `Z(\phi,k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_zeta(phi,k)

    Returns the Jacobi Zeta function `Z(\phi,k)`.  See also MathWorld :cite:p:`WolframFun154a`, BoostMath :cite:p:`BoostFun154a`, :cite:t:`Ehrhardt2018` (3.2.7).

    .. math ::    Z(\phi,k) = E(\phi,k) - \frac{E(k)}{K(k)} F(\phi,k), \quad |k| \le 1.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_zeta(0.4, -0.9333)
        0.2029927800760033
        >>> math53.jacobi_zeta(0.7, 0.0)
        0.0
        >>> math53.jacobi_zeta(1.2, 0.9333)
        0.2701672377293978








