

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Modified Bessel functions of integer order
===============================================================================



Modified Bessel function of the 1st kind, order `0, I_{0}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_i0(x)

    Returns I0(x), the modified Bessel function of the 1st kind, order zero. See also Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun86`, NIST :cite:p:`DLMFun86`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.1).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_i0(0.01)
        1.0000250001562505
        >>> math53.bessel_i0(10.5)
        4527.441714638888
        >>> math53.bessel_i0(20.9333)
        108234695.25162585







Modified Bessel function of the 1st kind, order `1, I_{1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_i1(x)

    Returns I1(x), the modified Bessel function of the 1st kind, order one. See also Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun86`, NIST :cite:p:`DLMFun86`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_i1(0.01)
        0.005000062500260419
        >>> math53.bessel_i1(10.5)
        4306.134875096274
        >>> math53.bessel_i1(20.9333)
        105616995.41931723







Modified Bessel function of the 1st kind, integer order `n, I_{n}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_in(x)

    Returns I_n(x), the modified Bessel function of the 1st kind, order n. See also Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun86`, NIST :cite:p:`DLMFun86`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.5).

    .. math:: I_{\nu}\left(z\right)=(\tfrac{1}{2}z)^{\nu}\sum_{k=0}^{\infty}\frac{(\tfrac{1}{4}z^{2})^{k}}{k!\Gamma\left(\nu+k+1\right)}.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_in(2, 0.01)
        1.2500104166992188e-05
        >>> math53.bessel_in(3, 10.5)
        2893.8584758757465
        >>> math53.bessel_in(4, 20.9333)
        73246703.18288033







Modified Bessel function of the 2nd kind, order 0, `K_{0}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_k0(x)

    Returns K0(x), the modified Bessel function of the 2nd kind, order zero, x>0.  See also  Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun87`, NIST :cite:p:`DLMFun87`,  BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.6).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_k0(0.01)
        4.721244730161095
        >>> math53.bessel_k0(10.5)
        1.0529988143865325e-05
        >>> math53.bessel_k0(20.9333)
        2.2074463556036048e-10







Modified Bessel function of the 2nd kind, order `1, K_{1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_k1(x)

    Returns K1(x), the modified Bessel function of the 2nd kind, order one, x>0.  See also  Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun87`, NIST :cite:p:`DLMFun87`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.8).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_k1(0.01)
        99.97389411829626
        >>> math53.bessel_k1(10.5)
        1.1020472311353894e-05
        >>> math53.bessel_k1(20.9333)
        2.2595704164348006e-10







Modified Bessel function of the 2nd kind, integer order `n, K_{n}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_kn(x)

    Returns K_n(x), the modified Bessel function of the 2nd kind, order n, x > 0.  See also  Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun87`, NIST :cite:p:`DLMFun87`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.10).

    .. math::
       :nowrap:

       \begin{eqnarray}
        K_{n}\left(z\right) & = & \tfrac{1}{2}(\tfrac{1}{2}z)^{-n}\sum_{k=0}^{n-1}\frac{(n-k-1)!}{k!}(-\tfrac{1}{4}z^{2})^{k}+(-1)^{n+1}\log\left(\tfrac{1}{2}z\right)I_{n}\left(z\right) \\
        & + & (-1)^{n}\tfrac{1}{2}(\tfrac{1}{2}z)^{n}\sum_{k=0}^{\infty}\left(\psi\left(k+1\right)+\psi\left(n+k+1\right)\right)\frac{(\tfrac{1}{4}z^{2})^{k}}{k!(n+k)!} \nonumber 
       \end{eqnarray}


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_kn(2, 0.01)
        19999.50006838941
        >>> math53.bessel_kn(3, 10.5)
        1.583156782639403e-05
        >>> math53.bessel_kn(4, 20.9333)
        3.203701460743069e-10






Exponentially scaled modified Bessel function of the 1st kind, order `0, I_{0,e}(x)`
---------------------------------------------------------------------------------------

.. method:: math53.bessel_i0e(x)

    Returns I0(x)*exp(-`|x|`), the exponentially scaled modified Bessel function of the 1st kind, order zero. See also Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun86`, NIST :cite:p:`DLMFun86`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_i0e(0.01)
        0.9900745851497076
        >>> math53.bessel_i0e(10.5)
        0.12466966945908617
        >>> math53.bessel_i0e(20.9333)
        0.08773034165079278






Exponentially scaled modified Bessel function of the 1st kind, order `1, I_{1,e}(x)`
-----------------------------------------------------------------------------------------

.. method:: math53.bessel_i1e(x)

    Returns I1(x)*exp(-`|x|`), the exponentially scaled modified Bessel function of the 1st kind, order one. See also Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun86`, NIST :cite:p:`DLMFun86`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_i1e(0.01)
        0.004950311047118277
        >>> math53.bessel_i1e(10.5)
        0.11857566488126836
        >>> math53.bessel_i1e(20.9333)
        0.08560854789423662






Exponentially scaled modified Bessel function of the 2nd kind, order 0, `K_{0,e}(x)`
-----------------------------------------------------------------------------------------

.. method:: math53.bessel_k0e(x)

    Returns K0(x)*exp(x),    the exponentially scaled modified Bessel function of the 2nd kind, order zero, x>0. See also  Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun87`, NIST :cite:p:`DLMFun87`,  BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.7).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_k0e(0.01)
        4.768694028544461
        >>> math53.bessel_k0e(10.5)
        0.3824018125983266
        >>> math53.bessel_k0e(20.9333)
        0.27233711745257894





Exponentially scaled modified Bessel function of the 2nd kind, order `1, K_{1,e}(x)`
------------------------------------------------------------------------------------------

.. method:: math53.bessel_k1e(x)

    Returns K1(x)*exp(x),    the exponentially scaled modified Bessel function of the 2nd kind, order one, x>0.  See also  Wikipedia :cite:p:`WikipediaFun86`, MathWorld :cite:p:`WolframFun87`, NIST :cite:p:`DLMFun87`, BoostMath :cite:p:`BoostFun86`, :cite:t:`Ehrhardt2018` (3.1.2.9).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_k1e(0.01)
        100.97864845824004
        >>> math53.bessel_k1e(10.5)
        0.4002139916944334
        >>> math53.bessel_k1e(20.9333)
        0.2787677681638209


