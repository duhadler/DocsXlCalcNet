

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Jacobi theta functions  at `x=0` for `0 \le q <1`
===============================================================================




Jacobi theta function `\theta'_1(q)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_theta1p(q)  

    Returns the Jacobi theta function `\theta'_1(q) = \partial\theta_1(x,q)/\partial x` at `x=0` for `0 \le q <1`. See also Wikipedia :cite:p:`WikipediaFun170`, MathWorld :cite:p:`WolframFun170`,  MathWorld :cite:p:`WolframFun170a`, NIST :cite:p:`DLMFun170`, :cite:t:`Ehrhardt2018` (3.2.14.1).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_theta1p(0.01)
        0.632265795377228
        >>> math53.jacobi_theta1p(0.5)
        0.5489785325603408
        >>> math53.jacobi_theta1p(0.9333)
        1.8387255175389385e-13








Jacobi theta function `\theta_2(q)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_theta02(q)  

    Returns the Jacobi theta function `\theta_2(q) = \theta_2(0,q)` for `0 \le q <1`. See also Wikipedia :cite:p:`WikipediaFun170`, MathWorld :cite:p:`WolframFun170`, NIST :cite:p:`DLMFun170`, :cite:t:`Ehrhardt2018` (3.2.14.2).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_theta02(0.01)
        0.6325187775875117
        >>> math53.jacobi_theta02(0.5)
        2.128931250513028
        >>> math53.jacobi_theta02(0.9333)
        6.74621917080838







Jacobi theta function `\theta_3(q)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_theta03(q)  

    Returns the Jacobi theta function `\theta_3(q) = \theta_3(0,q)` for `0 \le q <1`. See also Wikipedia :cite:p:`WikipediaFun170`, MathWorld :cite:p:`WolframFun170`, NIST :cite:p:`DLMFun170`, :cite:t:`Ehrhardt2018` (3.2.14.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_theta03(0.01)
        1.0200000200000001
        >>> math53.jacobi_theta03(0.5)
        2.128936827211877
        >>> math53.jacobi_theta03(0.9333)
        6.74621917080838








Jacobi theta function `\theta_4(q)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_theta04(q)  

    Returns the Jacobi theta function `\theta_4(q) = \theta_4(0,q)` for `-1 < q <1`. See also Wikipedia :cite:p:`WikipediaFun170`, MathWorld :cite:p:`WolframFun170`, NIST :cite:p:`DLMFun170`, :cite:t:`Ehrhardt2018` (3.2.14.4).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_theta04(0.01)
        0.98000002
        >>> math53.jacobi_theta04(0.5)
        0.12112420800258053
        >>> math53.jacobi_theta04(0.9333)
        4.040136238779326e-15




