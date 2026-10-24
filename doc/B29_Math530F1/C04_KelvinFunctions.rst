

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />




|newpage|


Kelvin functions of order 0
===============================================================================




.. _rst_mpm_ber0: 

Kelvin function `\mathrm{ber0}(x)`
-------------------------------------------------------------------------------

.. method:: math53.kelvin_ber0(x)


    Returns the Kelvin function ber. See also  Wikipedia :cite:p:`WikipediaFun1040`, MathWorld :cite:p:`WolframFun1040`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1040`.


    Returns the Kelvin function `\mathrm{ber}_0(x)`, defined as

    .. math::  \mathrm{ber}_0(x) = \sum_{k=0}^\infty (-1)^k \frac{\left(\tfrac{1}{4}x^2\right)^{2k}}{((2k)!)^2}.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.kelvin_ber0(0.01)
        0.99999999984375
        >>> math53.kelvin_ber0(10.5)
        153.76858196600045
        >>> math53.kelvin_ber0(20.9333)
        -62152.363191785866






.. _rst_mpm_bei0: 

Kelvin function `\mathrm{bei0}(x)`
-------------------------------------------------------------------------------

.. method:: math53.kelvin_bei0(x)



    Returns the Kelvin function bei.  See also  Wikipedia :cite:p:`WikipediaFun1041`, MathWorld :cite:p:`WolframFun1041`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1041`.

    Returns the Kelvin function `\mathrm{bei}_0(x)` is defined as

    .. math::  \mathrm{bei}_0(x) = \sum_{k=0}^\infty (-1)^k \frac{\left(\tfrac{1}{4}x^2\right)^{2k+1}}{((2k+1)!)^2}.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.kelvin_bei0(0.01)
        2.4999999999565975e-05
        >>> math53.kelvin_bei0(10.5)
        140.32375216623805
        >>> math53.kelvin_bei0(20.9333)
        226472.54726414903






.. _rst_mpm_ker0: 

Kelvin function `\mathrm{ker0}(x)`
-------------------------------------------------------------------------------

.. method:: math53.kelvin_ker0(x)



    Returns the Kelvin function ker.  See also  Wikipedia :cite:p:`WikipediaFun1042`, MathWorld :cite:p:`WolframFun1042`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1042`.

    The Kelvin function `\mathrm{ker}_0(x)` is defined as

    .. math::  \mathrm{ker}_0(x) = -\log \left(\tfrac{1}{2}x \right) \mathrm{ber}_0(x) +\tfrac{1}{4}\pi \; \mathrm{bei}_0(x) + \sum_{k=0}^\infty (-1)^k \frac{\psi(2k+1) \left(\tfrac{1}{4}x^2\right)^{2k}}{((2k)!)^2}.



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.kelvin_ker0(0.01)
        4.721121335628541
        >>> math53.kelvin_ker0(10.5)
        1.0187520004406006e-05
        >>> math53.kelvin_ker0(20.9333)
        -8.840038229293252e-08








.. _rst_mpm_kei0: 

Kelvin function `\mathrm{kei0}(x)`
-------------------------------------------------------------------------------

.. method:: math53.kelvin_kei0(x)


    Returns the Kelvin function kei. See also  Wikipedia :cite:p:`WikipediaFun1043`, MathWorld :cite:p:`WolframFun1043`, NIST :cite:p:`DLMFun1040`, Mpmath :cite:p:`MpmathFun1043`.

    The Kelvin function `\mathrm{kei}_0(x)` is defined as

    .. math::  \mathrm{kei}_0(x) = -\log \left(\tfrac{1}{2}x \right) \mathrm{bei}_0(x) -\tfrac{1}{4}\pi \; \mathrm{ber}_0(x) + \sum_{k=0}^\infty (-1)^k \frac{\psi(2k+2) \left(\tfrac{1}{4}x^2\right)^{2k+1}}{((2k+1)!)^2}



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.kelvin_kei0(0.01)
        -0.7852551357321914
        >>> math53.kelvin_kei0(10.5)
        -0.0002285179865986644
        >>> math53.kelvin_kei0(20.9333)
        -5.029479901091146e-08









First derivative of the Kelvin function `\mathrm{ber0}, \mathrm{ber0}'(x)`
------------------------------------------------------------------------------------

.. method:: math53.kelvin_ber_prime0(x)



    Returns the Kelvin function ber'(x), x >= 0

    See also: :cite:t:`Ehrhardt2018` (3.1.8.8). 



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.kelvin_ber_prime0(0.01)
        -6.249999999945747e-08
        >>> math53.kelvin_ber_prime0(10.5)
        1.9344188906856528
        >>> math53.kelvin_ber_prime0(20.9333)
        -202640.54055889626








First derivative of the Kelvin function `\mathrm{bei0}, \mathrm{bei0}'(x)`
------------------------------------------------------------------------------------

.. method:: math53.kelvin_bei_prime0(x)


    Returns the Kelvin function bei'(x), x >= 0

    See also: :cite:t:`Ehrhardt2018` (3.1.8.9). 



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.kelvin_bei_prime0(0.01)
        0.004999999999739583
        >>> math53.kelvin_bei_prime0(10.5)
        201.30360248165368
        >>> math53.kelvin_bei_prime0(20.9333)
        110723.61094753428







First derivative of the Kelvin function `\mathrm{ker0}, \mathrm{ker0}'(\nu, x)`
------------------------------------------------------------------------------------

.. method:: math53.kelvin_ker_prime0(x)


    Returns the Kelvin function ker'(x), x > 0


    See also: :cite:t:`Ehrhardt2018` (3.1.8.10). 



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.kelvin_ker_prime0(0.01)
        -99.99607338237708
        >>> math53.kelvin_ker_prime0(10.5)
        -0.00016942836391713252
        >>> math53.kelvin_ker_prime0(20.9333)
        2.902892305874749e-08





First derivative of the Kelvin function `\mathrm{kei0}, \mathrm{kei0}'(x)`
------------------------------------------------------------------------------------

.. method:: math53.kelvin_kei_prime0(x)


    Returns the Kelvin function kei'(x), x >= 0

    See also: :cite:t:`Ehrhardt2018` (3.1.8.11). 



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.kelvin_kei_prime0(0.01)
        0.02610555759395425
        >>> math53.kelvin_kei_prime0(10.5)
        0.0001650763656284745
        >>> math53.kelvin_kei_prime0(20.9333)
        9.928019000907199e-08








