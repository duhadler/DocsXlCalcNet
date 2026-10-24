

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />






|newpage|

Synchrotron functions
==============================================================================================


First synchrotron function `F(x)`
-------------------------------------------------------------------------------

.. method:: math53.synchrotron_f(x)

    Returns the first synchrotron function `F(x)` for `x \ge 0`, `\displaystyle F(x) = x\int_x^{\infty} K_{5/3}(t) \mathrm{d}t.`

    See also: :cite:t:`Ehrhardt2018` (3.1.11.1). 



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.synchrotron_f(0.01)
        0.4449725041142106
        >>> math53.synchrotron_f(10.5)
        0.00011914762875805393
        >>> math53.synchrotron_f(20.9333)
        4.808211886821304e-09








Second synchrotron function `G(x)`
-------------------------------------------------------------------------------

.. method:: math53.synchrotron_g(x)

    Returns the second synchrotron function `G(x) = x K_{2/3}(x)` for `x \ge 0`.

    See also: :cite:t:`Ehrhardt2018` (3.1.11.2). 


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.synchrotron_g(0.01)
        0.2309807734222628
        >>> math53.synchrotron_g(10.5)
        0.0001128256550353819
        >>> math53.synchrotron_g(20.9333)
        4.669098611060105e-09




