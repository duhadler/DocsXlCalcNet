

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Maple style elliptic integrals
===============================================================================


Complete integral of the 1st kind, `\mathrm{EllipticK}(k)`
-------------------------------------------------------------------------------

.. method:: math53.EllipticK(k)

    Returns the complete elliptic integral of the first kind K(k) and the real part if `|k| > 1`. See also Maplesoft :cite:p:`Maplesoft101`, :cite:t:`Ehrhardt2018` (3.2.4.1).

    .. math:: \mathrm{EllipticK}(k) = \int_0^{1} \frac{\mathrm{d}t}{\sqrt{(1-t^2)(1-k^2 t^2)}}


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticK(-0.9333)
        2.459106502858909
        >>> math53.EllipticK(0.01)
        1.570835598912152
        >>> math53.EllipticK(0.9333)
        2.459106502858909







Complete integral of the 1st kind for imaginary modulus, `\mathrm{EllipticKim}(k)`
----------------------------------------------------------------------------------------

.. method:: math53.EllipticKim(k)

    Returns the complete elliptic integral of the first kind for the imaginary modulus `ik` with `k \in \mathbb{R}`. See also Maplesoft :cite:p:`Maplesoft101`, :cite:t:`Ehrhardt2018` (3.2.4.2).

    .. math:: \mathrm{EllipticKim}(k) = \int_0^{1} \frac{\mathrm{d}t}{\sqrt{(1-t^2)(1+k^2 t^2)}}


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticKim(-0.9333)
        1.334879017781761
        >>> math53.EllipticKim(0.01)
        1.5707570590955058
        >>> math53.EllipticKim(0.9333)
        1.334879017781761







Complementary complete integral of the 1st kind, `\mathrm{EllipticCK}(k) = K'(k)`
-----------------------------------------------------------------------------------------------

.. method:: math53.EllipticCK(k)

    Returns the complementary complete elliptic integral of the first kind with `k \ne 0`. See also Maplesoft :cite:p:`Maplesoft101`, :cite:t:`Ehrhardt2018` (3.2.4.3), :cite:t:`Ehrhardt2018` (4.2.28).

    .. math:: \mathrm{EllipticCK}(k) = \mathrm{EllipticK}(k_c) = \int_0^{1} \frac{\mathrm{d}t}{\sqrt{(1-t^2)(1-k_c^2 t^2)}}


    Note: the complex version is called Ellck(z) in Amath.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticCK(-0.9333)
        1.6254736111454573
        >>> math53.EllipticCK(0.01)
        5.991589340506996
        >>> math53.EllipticCK(0.9333)
        1.6254736111454573







Complete integral of the 2nd kind, `\mathrm{EllipticEC}(k)`
-------------------------------------------------------------------------------

.. method:: math53.EllipticEC(k)

    Returns the complete elliptic integral of the second kind `E(k)` and the real part if `|k| > 1`. See also Maplesoft :cite:p:`Maplesoft102`, :cite:t:`Ehrhardt2018` (3.2.4.4).

    .. math:: \mathrm{EllipticEC}(k) = \int_0^{1} \frac{\sqrt{(1-k^2 t^2)}}{\sqrt{(1-t^2)}} \mathrm{d}t


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticEC(-0.9333)
        1.127649981567299
        >>> math53.EllipticEC(0.01)
        1.5707570561503852
        >>> math53.EllipticEC(0.9333)
        1.127649981567299








Complete integral of the 2nd kind for imaginary modulus, `\mathrm{EllipticECim}(k)`
----------------------------------------------------------------------------------------

.. method:: math53.EllipticECim(k)

    Returns the complete elliptic integral of the second kind for the imaginary modulus `ik` with `k \in \mathbb{R}`. See also Maplesoft :cite:p:`Maplesoft102`, :cite:t:`Ehrhardt2018` (3.2.4.5).

    .. math:: \mathrm{EllipticECim}(k) = E(ik) = \int_0^{1} \frac{\sqrt{(1+k^2 t^2)}}{\sqrt{(1-t^2)}} \mathrm{d}t


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticECim(-0.9333)
        1.870953551376072
        >>> math53.EllipticECim(0.01)
        1.5708355959667861
        >>> math53.EllipticECim(0.9333)
        1.870953551376072








Complementary complete integral of the 2nd kind, `\mathrm{EllipticCE}(k)`
-------------------------------------------------------------------------------

.. method:: math53.EllipticCE(k)

    Returns the complementary complete elliptic integral of the second kind. See also Maplesoft :cite:p:`Maplesoft102`, :cite:t:`Ehrhardt2018` (3.2.4.6).

    .. math:: \mathrm{EllipticEC}(k) = \mathrm{EllipticEC}(k_c) = \int_0^{1} \frac{\sqrt{(1-k_c^2 t^2)}}{\sqrt{(1-t^2)}} \mathrm{d}t


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticCE(-0.9333)
        1.5188621404561577
        >>> math53.EllipticCE(0.01)
        1.0002745824306631
        >>> math53.EllipticCE(0.9333)
        1.5188621404561577








Complete integral of the 3rd kind, `\mathrm{EllipticPiC}(\nu, k)`
-------------------------------------------------------------------------------

.. method:: math53.EllipticPiC(nu, k)

    Returns the complete elliptic integral of the third kind with `|k| \ne 1, \nu \ne 1` (or its real part if `|k| > 1`). See also Maplesoft :cite:p:`Maplesoft103`, :cite:t:`Ehrhardt2018` (3.2.4.7).

    .. math:: \mathrm{EllipticPiC}(\nu, k) = \int_0^{1} \frac{\mathrm{d}t}{(1-\nu t^2)\sqrt{(1-t^2)(1-k^2 t^2)}}


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticPiC(-0.9333, 0.01)
        1.129742159472719
        >>> math53.EllipticPiC(0.01, -0.9333)
        2.4745180633508044
        >>> math53.EllipticPiC(0.9333, 0.01)
        6.0823893714986585









Complete integral of the 3rd kind for imaginary modulus, `\mathrm{EllipticPiCim}(\nu, k)`
-----------------------------------------------------------------------------------------------

.. method:: math53.EllipticPiCim(nu, k)

    Returns the complementary complete elliptic integral of the third kind with `\nu \ne 1`. See also Maplesoft :cite:p:`Maplesoft102`, :cite:t:`Ehrhardt2018` (3.2.4.8).

    .. math:: \mathrm{EllipticPiCim}(\nu, k) = \mathrm{EllipticPiC}(\nu, k) = \int_0^{1} \frac{\mathrm{d}t}{(1-\nu t^2)\sqrt{(1-t^2)(1+k^2 t^2)}}


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticPiCim(-0.9333, 0.01)
        1.1296948994491276
        >>> math53.EllipticPiCim(0.01, -0.9333)
        1.3410787572966438
        >>> math53.EllipticPiCim(0.9333, 0.01)
        6.08190599516054








Complementary complete integral of the 3rd kind, `\mathrm{EllipticCPi}(\nu, k)`
---------------------------------------------------------------------------------------

.. method:: math53.EllipticCPi(nu, x)

    Returns the complementary complete elliptic integral of the third kind with `|k| \ne 0, \nu \ne 1`. See also Maplesoft :cite:p:`Maplesoft102`, :cite:t:`Ehrhardt2018` (3.2.4.9).

    .. math:: \mathrm{EllipticCPi}(\nu, k) = \mathrm{EllipticPiC}(\nu, k_c) = \int_0^{1} \frac{\mathrm{d}t}{(1-\nu t^2)\sqrt{(1-t^2)(1-k_c^2 t^2)}}


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticCPi(-0.9333, 0.01)
        3.4829363034929215
        >>> math53.EllipticCPi(0.01, -0.9333)
        1.6338040919783785
        >>> math53.EllipticCPi(0.9333, 0.01)
        60.46495296527363








Incomplete integral of the 1st kind, `\mathrm{EllipticF}(z, k)`
-------------------------------------------------------------------------------

.. method:: math53.EllipticF(z, k)

    Returns the incomplete elliptic integral of the first kind with `|z| \le 1, |kz| \le 1`. See also Maplesoft :cite:p:`Maplesoft101`, :cite:t:`Ehrhardt2018` (3.2.4.10).

    .. math:: \mathrm{EllipticF}(z, k) = \int_0^{z} \frac{\mathrm{d}t}{\sqrt{(1-t^2)(1-k^2 t^2)}}


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticF(-0.9333, 0.01)
        -1.2035171794595962
        >>> math53.EllipticF(0.01, -0.9333)
        0.010000311859028539
        >>> math53.EllipticF(0.9333, 0.01)
        1.2035171794595962








Incomplete integral of the 2nd kind, `\mathrm{EllipticE}(z, k)`
-------------------------------------------------------------------------------

.. method:: math53.EllipticE(z, k)

    Returns the incomplete elliptic integral of the second kind with `|z| \le 1, |kz| \le 1`. See also Maplesoft :cite:p:`Maplesoft102`, :cite:t:`Ehrhardt2018` (3.2.4.11).

    .. math:: \mathrm{EllipticE}(z, k) = \int_0^{z} \frac{\sqrt{(1-k^2 t^2)}}{\sqrt{(1-t^2)}} \mathrm{d}t


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticE(-0.9333, 0.01)
        -1.2034737607138424
        >>> math53.EllipticE(0.01, -0.9333)
        0.01000002149309969
        >>> math53.EllipticE(0.9333, 0.01)
        1.2034737607138424








Incomplete integral of the 3rd kind, `\mathrm{EllipticPi}(z, \nu, k)`
---------------------------------------------------------------------------------------

.. method:: math53.EllipticPi(z, nu, k)

    Returns the incomplete elliptic integral of the third kind with `|z| \le 1, |kz| \le 1`. See also Maplesoft :cite:p:`Maplesoft103`, :cite:t:`Ehrhardt2018` (3.2.4.12).

    .. math:: \mathrm{EllipticPi}(z, \nu, k) = \int_0^{z} \frac{\mathrm{d}t}{(1-\nu t^2)\sqrt{(1-t^2)(1-k_c^2 t^2)}}


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.EllipticPi(-0.9333, 0.01, 0.9333)
        -1.5540650009536827
        >>> math53.EllipticPi(0.01, -0.9333, 0.9333)
        0.010000000758985845
        >>> math53.EllipticPi(0.9333, 0.01, -0.9333)
        1.5540650009536827





