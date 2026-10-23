

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Riemann zeta, and related functions
===============================================================================




Riemann `\zeta(n)` for integer arguments
-------------------------------------------------------------------------------

.. method:: math53.zeta_i(n)

    Returns the Riemann zeta function `\zeta(n)` for integer arguments `n \ne 1`. For
    `n > 63` the result is `1`, for `0 \le n \le 63` the value is taken from a table, otherwise the Bernoulli
    numbers are used: `\zeta(n) = B_{1-n}/(n - 1)` for `n < 0`.

    See also   Wikipedia :cite:p:`WikipediaFun171`, MathWorld :cite:p:`WolframFun171`, NIST :cite:p:`DLMFun171`,  BoostMath :cite:p:`BoostFun171`, :cite:t:`Ehrhardt2018` (3.6.1.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.zeta_i(2)
        1.6449340668482264
        >>> math53.zeta_i(3)
        1.2020569031595942
        >>> math53.zeta_i(4)
        1.0823232337111381







Riemann `\zeta(1+x)`
-------------------------------------------------------------------------------

.. method:: math53.zeta1p(x) 

    Returns the Riemann zeta function `\zeta(1+x)` for `x \ne 0`. Normally used with `|x| \ll 1` for increased accuracy near the pole of `\zeta(s)` at `s = 1`.

    See also   Wikipedia :cite:p:`WikipediaFun171`, MathWorld :cite:p:`WolframFun171`, NIST :cite:p:`DLMFun171`,  BoostMath :cite:p:`BoostFun171`, :cite:t:`Ehrhardt2018` (3.6.1.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.zeta1p(0.01)
        100.57794333849687
        >>> math53.zeta1p(10.5)
        1.0003486558834918
        >>> math53.zeta1p(20.9333)
        1.0000002497344977








Dirichlet eta function for integer argument,  `\eta(n)`
-------------------------------------------------------------------------------

.. method:: math53.dirichlet_eta_i(n) 

    Returns the Dirichlet eta function `\eta(n)` for integer arguments. For
    `n > 64` the result is `1`, for `0 \le n \le 64` the value is taken from a table, otherwise for `n<0` the Bernoulli
    numbers are used: `\eta(n) = (2^{1-n}-1) B_{1-n}/(1-n)`.

    See also: MathWorld :cite:p:`WolframFun1008`, :cite:t:`Ehrhardt2018` (3.6.3.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.dirichlet_eta_i(2)
        0.8224670334241132
        >>> math53.dirichlet_eta_i(3)
        0.9015426773696957
        >>> math53.dirichlet_eta_i(4)
        0.9470328294972459





Prime zeta function
-------------------------------------------------------------------------------

.. method:: math53.primezeta(s)

    Returns for `x > 0.2` the prime zeta function `\displaystyle P(x) = \sum_{p \text{ prime}} p^{-x}`,  or its real part for `x<1`.

    See also :cite:t:`Ehrhardt2018` (3.6.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.primezeta(2.01)
        0.4473533160988981
        >>> math53.primezeta(10.5)
        0.0006898729399747471
        >>> math53.primezeta(20.9333)
        4.995031614994917e-07





Riemann prime counting function, `R(x)`
-------------------------------------------------------------------------------

.. method:: math53.riemann_r(x)

    Returns `\displaystyle R(x) =  \sum_{n=1}^{\infty} \frac{\mu(n)}{n} \text{li}(x^{1/n})  1 + \sum_{k=1}^{\infty} \frac{\log^k x}{k k! \zeta(k+1)}, \,` the Riemann prime counting  function, for `x>0`.

    See also   Wikipedia :cite:p:`WikipediaFun122`,  Wikipedia :cite:p:`WikipediaFun124`, MathWorld :cite:p:`WolframFun122`,  Wikipedia :cite:p:`WikipediaFun123`, MathWorld :cite:p:`WolframFun123`, :cite:t:`Ehrhardt2018` (3.10.20).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.riemann_r(2.01)
        1.5459341840849095
        >>> math53.riemann_r(10.5)
        4.725293716386582
        >>> math53.riemann_r(220.9333)
        48.32330658563835









Inverse of the Riemann prime counting function, `R^{-1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.riemann_r_inv(x)

    Returns the functional inverse of the Riemann prime counting function, i.e. `R(R^{-1}(x))= x`, for `x \ge 1.125`.

    See also :cite:t:`Ehrhardt2018` (3.10.21).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.riemann_r_inv(2.01)
        3.0121183149089292
        >>> math53.riemann_r_inv(10.5)
        31.308893414099234
        >>> math53.riemann_r_inv(220.9333)
        1378.8514211496115







Rogers-Ramanujan continued fraction
-------------------------------------------------------------------------------

.. method:: math53.rogers_ramanujan_cf(q)

    Returns `\displaystyle R(q) = \frac{q^{1/5}}{1+} \frac{q}{1+} \frac{q^2}{1+} \frac{q^3}{1+} \frac{q^5}{1+}`, the Rogers-Ramanujan continued fraction, for `|q| < 1`.

    See also :cite:t:`Ehrhardt2018` (3.10.22).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.rogers_ramanujan_cf(0.01)
        0.3941659056233625
        >>> math53.rogers_ramanujan_cf(0.5)
        0.6180183781955219
        >>> math53.rogers_ramanujan_cf(0.9333)
        0.6180339887498949






Moebius function, `\mu(n)`
-------------------------------------------------------------------------------

.. method:: math53.moebius(n) 

    Returns `\mu(n)`, the Möbius function.

    For integer `n`, the Moebius `\mu` function `\mu(n)` equals 0 if `n` has repeated integer factors. Otherwise, if `n` is the product of `k` distinct primes, the Moebius `\mu` function `\mu(n)` equals `(-1)^k`.


    https://en.wikipedia.org/wiki/M%C3%B6bius_function



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.moebius(21)
        1
        >>> math53.moebius(30)
        -1
        >>> math53.moebius(40)
        0









q-Pochhammer Euler function, `(q)_{\infty}`
-------------------------------------------------------------------------------

.. method:: math53.euler_q(n,x) 

    Returns `\displaystyle \phi(q) = (q)_{\infty} = \prod_{k=1}^{\infty} \left(1-q^k\right)`, the q-Pochhammer Euler function, for `-1 \le q \le 1`.

    See also: MathWorld :cite:p:`WolframFun1031`,  Wikipedia :cite:p:`WikipediaFun1031`, :cite:t:`Ehrhardt2018` (3.10.19).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.euler_q(0.01)
        0.98990000010001
        >>> math53.euler_q(0.5)
        0.2887880950866024
        >>> math53.euler_q(0.9333)
        4.2824759927091205e-10




