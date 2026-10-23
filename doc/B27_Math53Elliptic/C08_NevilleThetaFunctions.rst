

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Neville theta functions
===============================================================================







Neville `\theta_c(x,k)`
-------------------------------------------------------------------------------

.. method:: math53.neville_theta_c(x, k)

    Returns the Neville theta function `\displaystyle \theta_c(x,k) = \frac{\theta_2(v,q(k))}{\theta_2(0,q(k))}, \quad v = \frac{\pi x}{2K(k)}, |k| \le  1`, and `q(k)` is the elliptic nome.

    See also: Wikipedia :cite:p:`WikipediaFun170a`, MathWorld :cite:p:`WolframFun170c`, :cite:t:`Ehrhardt2018` (3.2.15.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.neville_theta_c(0.01, 0.5)
        0.999956474832081
        >>> math53.neville_theta_c(0.5, 0.9333)
        0.9436331810661398
        >>> math53.neville_theta_c(0.9333, 0.5)
        0.6446023742055126







Neville `\theta_d(x,k)`
-------------------------------------------------------------------------------

.. method:: math53.neville_theta_d(x, k)

    Returns the Neville theta function `\displaystyle \theta_d(x,k) = \frac{\theta_3(v,q(k))}{\theta_3(0,q(k))}, \quad v = \frac{\pi x}{2K(k)}, |k| \le  1`, and `q(k)` is the elliptic nome.

    See also: Wikipedia :cite:p:`WikipediaFun170a`, MathWorld :cite:p:`WolframFun170d`, :cite:t:`Ehrhardt2018` (3.2.15.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.neville_theta_d(0.01, 0.5)
        0.9999939746842494
        >>> math53.neville_theta_d(0.5, 0.9333)
        0.9602114827440184
        >>> math53.neville_theta_d(0.9333, 0.5)
        0.9594825353083286







Neville `\theta_n(x,k)`
-------------------------------------------------------------------------------

.. method:: math53.neville_theta_n(x, k)

    Returns the Neville theta function `\displaystyle \theta_n(x,k) = \frac{\theta_4(v,q(k))}{\theta_4(0,q(k))}, \quad v = \frac{\pi x}{2K(k)}, |k| \le  1`, and `q(k)` is the elliptic nome.

    See also: Wikipedia :cite:p:`WikipediaFun170a`, MathWorld :cite:p:`WolframFun170n`, :cite:t:`Ehrhardt2018` (3.2.15.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.neville_theta_n(0.01, 0.5)
        1.0000064743224766
        >>> math53.neville_theta_n(0.5, 0.9333)
        1.065460920528952
        >>> math53.neville_theta_n(0.9333, 0.5)
        1.0435380078392624




Neville `\theta_s(x,k)`
-------------------------------------------------------------------------------

.. method:: math53.neville_theta_s(x, k)

    Returns the Neville theta function `\displaystyle \theta_s(x,k) = \frac{2K(k)}{\pi} \frac{\theta_1(v,q(k))}{\theta'_1(0,q(k))}, \quad v = \frac{\pi x}{2K(k)}, |k| \le  1`, and `q(k)` is the elliptic nome.

    See also: Wikipedia :cite:p:`WikipediaFun170a`, MathWorld :cite:p:`WolframFun170s`, :cite:t:`Ehrhardt2018` (3.2.15.1).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.neville_theta_s(0.01, 0.5)
        0.009999856412344637
        >>> math53.neville_theta_s(0.5, 0.9333)
        0.4947356796971494
        >>> math53.neville_theta_s(0.9333, 0.5)
        0.8206456927162612





