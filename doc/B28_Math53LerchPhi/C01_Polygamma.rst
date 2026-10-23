

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





Polygamma, and related functions
===============================================================================




Pentagamma function `\psi'''(x)`
-------------------------------------------------------------------------------

.. method:: math53.pentagamma(x) 

    Returns the pentagamma function `\psi'''(x), \quad x \ne 0, -1, -2, \ldots` The function returns the Hurwitz zeta value `6\zeta(4,x)` if `x` is positive; for `x<0` it returns `\psi'''(x) = -2\pi^4\left(1+ 4\cot^2(\pi x)+3\cot^4(\pi x)\right) - 6\zeta(4,1-x)`.

    See also   Wikipedia :cite:p:`WikipediaFun83`, MathWorld :cite:p:`WolframFun83`, NIST :cite:p:`DLMFun83`,  BoostMath :cite:p:`BoostFun83`, :cite:t:`Ehrhardt2018` (3.5.6.5).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.pentagamma(0.01)
        600000006.2510617
        >>> math53.pentagamma(10.5)
        0.001990086237144355
        >>> math53.pentagamma(20.9333)
        0.00023415053202383002






Tetragamma function, `\psi''(x)`
-------------------------------------------------------------------------------

.. method:: math53.tetragamma(x) 

    Returns the tetragamma function `\psi''(x), \quad x \ne 0, -1, -2, \ldots` The function returns the Hurwitz zeta value `-2\zeta(3,x)` if `x` is positive; for `x<0` it returns `\psi''(x) = -2\pi^3 \cot(\pi x)\left(1+\cot^2(\pi x)\right) - 2\zeta(3,1-x)`.

    See also   Wikipedia :cite:p:`WikipediaFun83`, MathWorld :cite:p:`WolframFun83`, NIST :cite:p:`DLMFun83`,  BoostMath :cite:p:`BoostFun83`, :cite:t:`Ehrhardt2018` (3.5.6.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.tetragamma(0.01)
        -2000002.3403986772
        >>> math53.tetragamma(10.5)
        -0.009975144247715168
        >>> math53.tetragamma(20.9333)
        -0.0023936641630670093






Auxiliary function `\psi^{*}(x)`
-------------------------------------------------------------------------------

.. method:: math53.psistar(x)  

    Returns `\psi^{*}(x) = \psi(x) - \log(x), x > 0`. The function is useful when computing differences of `\psi` functions, because it can avoid cancellation for larger `x` values. See also :cite:t:`Ehrhardt2018` (3.5.6.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.psistar(0.01)
        -95.95571527188056
        >>> math53.psistar(10.5)
        -0.04837422286579131
        >>> math53.psistar(20.9333)
        -0.024075515594002023








Inverse digamma function `\psi^{-1}(y)`
-------------------------------------------------------------------------------

.. method:: math53.psi_inv(y)

    Returns `\psi^{-1}(y)`, the functional inverse of of the digamma function, i.e. it returns `x` with `\psi(x) = y`.

    See also  Wikipedia :cite:p:`WikipediaFun125`, MathWorld :cite:p:`WolframFun125`, NIST :cite:p:`DLMFun83`,  BoostMath :cite:p:`BoostFun125`, :cite:t:`Ehrhardt2018` (3.5.6.7).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.psi_inv(0.01)
        1.4720152539294011
        >>> math53.psi_inv(10.5)
        36316.00267309933
        >>> math53.psi_inv(20.9333)
        1233720207.3863456






Bateman function `G(x)`
-------------------------------------------------------------------------------

.. method:: math53.bateman_g(x)

    Returns the Bateman function `G(x) = \psi((x+1)/2) - \psi(x/2); x \ne 0,-1,-2,\ldots` See also :cite:t:`Ehrhardt2018` (3.5.6.8).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.bateman_g(0.01)
        198.6299765458315
        >>> math53.bateman_g(10.5)
        0.09975303466039102
        >>> math53.bateman_g(20.9333)
        0.048910504209268506





