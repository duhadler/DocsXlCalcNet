

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Struve functions
===============================================================================



        
Struve function `\mathbf{H}_0(x)`
-------------------------------------------------------------------------------

.. method:: math53.struve_h0(x)

    Returns the Struve function `H_0(x)`


    See also: :cite:t:`Ehrhardt2018` (3.1.9.1), Mpmath :cite:p:`MpmathFun1044`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.struve_h0(-4.333)
        -8.838923360249138e-05
        >>> math53.struve_h0(0.0)
        0.0
        >>> math53.struve_h0(4.333)
        8.838923360249138e-05








Struve function `\mathbf{H}_1(x)`
-------------------------------------------------------------------------------

.. method:: math53.struve_h1(x)

    Returns the Struve function `H_1(x)`

    See also: :cite:t:`Ehrhardt2018` (3.1.9.2), Mpmath :cite:p:`MpmathFun1044`.


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.struve_h1(-4.333)
        1.0083112254111042
        >>> math53.struve_h1(0.0)
        0.0
        >>> math53.struve_h1(4.333)
        1.0083112254111042






Struve function `\mathbf{L}_0(x)`
-------------------------------------------------------------------------------

.. method:: math53.struve_l0(x)

    Returns the Struve function `L_0(x)`

    See also: :cite:t:`Ehrhardt2018` (3.1.9.5). 


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.struve_l0(-4.333)
        -14.940909724356144
        >>> math53.struve_l0(0.0)
        0.0
        >>> math53.struve_l0(4.333)
        14.940909724356144







Struve function `\mathbf{L}_1(x)`
-------------------------------------------------------------------------------

.. method:: math53.struve_l1(x)

    Returns the Struve function `\mathbf{L}_1(x)`

    See also: :cite:t:`Ehrhardt2018` (3.1.9.6). 


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.struve_l1(-4.333)
        12.616306710713864
        >>> math53.struve_l1(0.0)
        0.0
        >>> math53.struve_l1(4.333)
        12.616306710713864




