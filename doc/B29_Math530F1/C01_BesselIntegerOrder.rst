

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





Bessel functions of integer order
===============================================================================




Bessel function of the 1st kind, order `0, J_{0}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_j0(x)

    where ``ctx`` is ``math53`` or ``ctxcpp``.

    Returns `J_0(x)`, the Bessel function of the 1st kind, order zero.  See also Wikipedia :cite:p:`WikipediaFun84`, MathWorld :cite:p:`WolframFun84`, NIST :cite:p:`DLMFun84`,  BoostMath :cite:p:`BoostFun84`,  :cite:t:`Ehrhardt2018`  (3.1.1.1).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_j0(0.01)
        0.9999750001562496
        >>> math53.bessel_j0(10.5)
        -0.23664819446234708
        >>> math53.bessel_j0(20.9333)
        0.04792105881068816





Bessel function of the 1st kind, order `1, J_{1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_j1(x)

    where ``ctx`` is ``math53`` or ``ctxcpp``.


    Returns `J_1(x)`, the Bessel function of the 1st kind, order one. See also Wikipedia :cite:p:`WikipediaFun84`, MathWorld :cite:p:`WolframFun84`, NIST :cite:p:`DLMFun84`,  BoostMath :cite:p:`BoostFun84`,  :cite:t:`Ehrhardt2018`  (3.1.1.1).



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_j1(0.01)
        0.004999937500260415
        >>> math53.bessel_j1(10.5)
        -0.07885001422733144
        >>> math53.bessel_j1(20.9333)
        0.16884230112872245






Bessel function of the 1st kind, integer order `n, J_{n}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_jn(n, x)

    where ``ctx`` is ``math53`` or ``ctxcpp``.

    Returns `J_n(x)`, the Bessel function of the 1st kind, order `n`. See also Wikipedia :cite:p:`WikipediaFun84`, MathWorld :cite:p:`WolframFun84`, NIST :cite:p:`DLMFun84`,  BoostMath :cite:p:`BoostFun84`,  :cite:t:`Ehrhardt2018`  (3.1.1.1).



    .. math:: J_{n}(x)  = \left(\tfrac{1}{2}x\right)^{n}  \sum_{k=0}^\infty (-1)^k \frac{(x^2 / 4)^k}{k! \Gamma(n+k+1)}.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_jn(2, 0.01)
        1.2499895833658854e-05
        >>> math53.bessel_jn(3, 10.5)
        0.1632801643733625
        >>> math53.bessel_jn(4, 20.9333)
        -0.01834585303578947






Bessel function of the 2nd kind, order `0, Y_{0}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_y0(x)

    where ``ctx`` is ``math53`` or ``ctxcpp``.

    Returns `Y_0(x)`, the Bessel function of the 2nd kind, order zero, `x>0`. See also Wikipedia :cite:p:`WikipediaFun85`, MathWorld :cite:p:`WolframFun85`, NIST :cite:p:`DLMFun85`,  BoostMath :cite:p:`BoostFun84`,  :cite:t:`Ehrhardt2018`  (3.1.1.1).



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_y0(0.01)
        -3.005455637083646
        >>> math53.bessel_y0(10.5)
        -0.06753037249787641
        >>> math53.bessel_y0(20.9333)
        0.1676506814275376






Bessel function of the 2nd kind, order `1, Y_{1}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_y1(x)

    where ``ctx`` is ``math53`` or ``ctxcpp``.

    Returns `Y_1(x)`, the Bessel function of the 2nd kind, order one, `x>0`.  See also Wikipedia :cite:p:`WikipediaFun85`, MathWorld :cite:p:`WolframFun85`, NIST :cite:p:`DLMFun85`,  BoostMath :cite:p:`BoostFun84`,  :cite:t:`Ehrhardt2018`  (3.1.1.1).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_y1(0.01)
        -63.67859628206066
        >>> math53.bessel_y1(10.5)
        0.23370422835726862
        >>> math53.bessel_y1(20.9333)
        -0.04393254669288505








Bessel function of the 2nd kind, integer order `n, Y_{n}(x)`
-------------------------------------------------------------------------------

.. method:: math53.bessel_yn(x)

    where ``ctx`` is ``math53`` or ``ctxcpp``.

    Returns `Y_n(x)`, the Bessel function of the 2nd kind, order n, `x>0`.  See also Wikipedia :cite:p:`WikipediaFun85`, MathWorld :cite:p:`WolframFun85`, NIST :cite:p:`DLMFun85`,  BoostMath :cite:p:`BoostFun84`,  :cite:t:`Ehrhardt2018`  (3.1.1.1).


    .. math :: Y_{n}(z)=-{\frac {\left({\frac {z}{2}}\right)^{-n}}{\pi }}\sum _{k=0}^{n-1}{\frac {(n-k-1)!}{k!}}\left({\frac {z^{2}}{4}}\right)^{k}+{\frac {2}{\pi }}J_{n}(z)\log {\frac {z}{2}}-{\frac {\left({\frac {z}{2}}\right)^{n}}{\pi }}\sum _{k=0}^{\infty }(\psi (k+1)+\psi (n+k+1)){\frac {\left(-{\frac {z^{2}}{4}}\right)^{k}}{k!(n+k)!}}


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bessel_yn(2, 0.01)
        -12732.71380077505
        >>> math53.bessel_yn(3, 10.5)
        -0.19102024221877467
        >>> math53.bessel_yn(4, 20.9333)
        0.17502824733280994






