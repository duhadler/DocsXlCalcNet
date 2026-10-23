

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Inverse Jacobi elliptic functions 
===============================================================================

The inverse Jacobi elliptic functions can be defined like the inverse trigonometric functions: e.g. if `\mathrm{sn}(y, k) = x` then `y = \mathrm{arcsn}(x, k)`; they are multivalued and their principal values are returned. The functions can be represented as elliptic integrals [30, §22.15(ii)] and they are computed with the incomplete elliptic integral `F(., k)` using the table from Abramowitz and Stegun [1, p.596].



Inverse Jacobi elliptic function `\mathrm{arcsn}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arcsn(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arcsn}(x, k)` for `|x| \le 1` and `|kx| \le 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.12.1).

    .. math::  \mathrm{arcsn}(x, k) = F(\mathrm{arcsin}(x), k).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arcsn(0.01, 0.5)
        0.010000208342552622
        >>> math53.jacobi_arcsn(0.5, 0.9333)
        0.5455929205316519
        >>> math53.jacobi_arcsn(0.9333, 0.5)
        1.2646631607926928








Inverse Jacobi elliptic function `\mathrm{arccn}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arccn(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arccn}(x, k)` for `|x| < 1` if `k \le 1`, and `x^2 > 1 - 1/k^2` if `k > 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018`  (3.2.12.2).

    .. math::  \mathrm{arccn}(x, k) = F(\mathrm{arccos}(x), k).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arccn(0.01, 0.5)
        1.6742032211210454
        >>> math53.jacobi_arccn(0.5, 0.9333)
        1.2569383151950466
        >>> math53.jacobi_arccn(0.9333, 0.5)
        0.3693405114569477







Inverse Jacobi elliptic function `\mathrm{arcdn}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arcdn(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arcdn}(x, k)` for `0 \le x \le 1` and `k^2 + x^2 > 1` if `|k| < 1`; and `|x| \le 1` if `|k| > 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018`  (3.2.12.3).

    .. math:: \mathrm{arcdn}(x, k) = F\left(\mathrm{arcsin}\left(\sqrt{\frac{1-x^2}{k^2}} \right), k \right).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arcdn(0.81, 0.85)
        0.818383723341855
        >>> math53.jacobi_arcdn(0.85, 0.9333)
        0.6333740262678361
        >>> math53.jacobi_arcdn(0.9333, 0.85)
        0.44639702745946724








Inverse Jacobi elliptic function `\mathrm{arccd}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arccd(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arccd}(x, k)` for `|x| \le 1` if `|k| < 1`; and `|x| \ge 1` if `|k| > 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.12.4).

    .. math:: \mathrm{arccd}(x, k) = F\left(\mathrm{arcsin}\left(\sqrt{\frac{1-x^2}{1-k^2 x^2}} \right), k \right).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arccd(0.01, 0.5)
        1.6757501464700435
        >>> math53.jacobi_arccd(0.5, 0.9333)
        1.9135135823272573
        >>> math53.jacobi_arccd(0.9333, 0.5)
        0.4210871940199031








Inverse Jacobi elliptic function `\mathrm{arcsd}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arcsd(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arcsd}(x, k)` for `x \in \mathbb{R}` if `|k| \ge 1` and `|x| < 1/\sqrt{1 - k^2}` otherwise. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018`  (3.2.12.5).

    .. math:: \mathrm{arcsd}(x, k) = F\left(\mathrm{arcsin}\left(\sqrt{\frac{x^2}{1+k^2 x^2}} \right), k \right).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arcsd(1.01, 1.5)
        0.01000008333708349
        >>> math53.jacobi_arcsd(1.5, 1.9333)
        0.48599631639488927
        >>> math53.jacobi_arcsd(1.9333, 1.5)
        1.0461374961953611








Inverse Jacobi elliptic function `\mathrm{arcnd}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arcnd(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arcnd}(x, k)` for `x \ge 1` and `x^2 \le k^2/(1 - k^2)` if `|k| < 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.12.6).

    .. math:: \mathrm{arcnd}(x, k) = F\left(\mathrm{arcsin}\left(\sqrt{\frac{x^2-1}{k^2 x^2}} \right), k \right).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arcnd(1.01, 1.5)
        0.09402852893196235
        >>> math53.jacobi_arcnd(1.5, 1.9333)
        0.44786848710680505
        >>> math53.jacobi_arcnd(1.9333, 1.5)
        0.7366908030186489






Inverse Jacobi elliptic function `\mathrm{arcdc}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arcdc(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arcdc}(x, k)` for `|x| \ge 1` if `|k| < 1`; and `|x| \le 1` if `|k| > 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.12.7).

    .. math:: \mathrm{arcdc}(x, k) = F\left(\mathrm{arcsin}\left(\sqrt{\frac{1-x^2-1}{k^2 - x^2}} \right), k \right).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arcdc(0.01, 1.5)
        1.1997781698230954
        >>> math53.jacobi_arcdc(0.5, 1.9333)
        0.602871393168387
        >>> math53.jacobi_arcdc(0.9333, 1.5)
        0.3230254324880706







Inverse Jacobi elliptic function `\mathrm{arcnc}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arcnc(x, k)

    Returns the inverse Jacobi elliptic function  `\mathrm{arcnc}(x, k)` for `x \ge 1`, and `x^2 \le k^2/(k^2 - 1)` for `|k| > 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.12.8).

    .. math:: \mathrm{arcnc}(x, k) = F(\mathrm{arcsec}(x), k).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arcnc(1.01, 0.5)
        0.1409520642226382
        >>> math53.jacobi_arcnc(1.5, 0.9333)
        0.9408474060083183
        >>> math53.jacobi_arcnc(1.9333, 0.5)
        1.0673523684807162








Inverse Jacobi elliptic function `\mathrm{arcsc}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arcsc(x, k)

    Returns the inverse Jacobi elliptic function  `\mathrm{arcsc}(x, k)` for `x \in \mathbb{R}` if `|k| \le 1` and `|x| \le 1/\sqrt{
    k^2 - 1}` if `|k| > 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.12.9).

    .. math:: \mathrm{arcsc}(x, k) = F(\mathrm{arctan}(x), k).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arcsc(0.01, 0.5)
        0.009999708348801099
        >>> math53.jacobi_arcsc(0.5, 0.9333)
        0.4787388167314662
        >>> math53.jacobi_arcsc(0.9333, 0.5)
        0.7675883759164223









Inverse Jacobi elliptic function `\mathrm{arcns}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arcns(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arcns}(x, k)` for `|x| \ge 1` if `|k| < 1` and `|x| \ge |k|` if `|k| > 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.12.10).

    .. math:: \mathrm{arcns}(x, k) = F(\mathrm{arccsc}(x), k).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arcns(1.01, 0.5)
        1.523305059639121
        >>> math53.jacobi_arcns(1.5, 0.9333)
        0.7925159210200553
        >>> math53.jacobi_arcns(1.9333, 0.5)
        0.5501460517169048









Inverse Jacobi elliptic function `\mathrm{arcds}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arcds(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arcds}(x, k)` for `x \in \mathbb{R}` if `|k| > 1` and `|x| \ge \sqrt{ 1 - k^2}` if `|k| < 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.12.11).

    .. math:: \mathrm{arcds}(x, k) = F\left(\mathrm{arcsin}\left(\sqrt{\frac{1}{k^2 + x^2}} \right), k \right).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arcds(0.01, 1.5)
        1.2004822727201372
        >>> math53.jacobi_arcds(0.5, 1.9333)
        0.7245630486544666
        >>> math53.jacobi_arcds(0.9333, 1.5)
        0.7261996704910932








Inverse Jacobi elliptic function `\mathrm{arccs}(x, k)`
-------------------------------------------------------------------------------

.. method:: math53.jacobi_arccs(x, k)

    Returns the inverse Jacobi elliptic function `\mathrm{arccs}(x, k)` for `x \in \mathbb{R}` if `|k| < 1` and `|x| \ge \sqrt{k^2 - 1}` if `|k| > 1`. See also NIST :cite:p:`DLMFun155`, :cite:t:`Ehrhardt2018` (3.2.12.12).

    .. math:: \mathrm{arccs}(x, k) = F(\mathrm{arccot}(x), k).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.jacobi_arccs(0.01, 0.5)
        1.6742037984472615
        >>> math53.jacobi_arccs(0.5, 0.9333)
        1.3622156081449894
        >>> math53.jacobi_arccs(0.9333, 0.5)
        0.8413253980268582







