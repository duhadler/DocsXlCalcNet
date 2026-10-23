

.. |newpage| raw:: latex

   \newpage


.. |br| raw:: html

   <br />





|newpage|

Polylogarithm, and related functions
===============================================================================




Polylogarithm of integer order, `\mathrm{Li}_n(x)`
-------------------------------------------------------------------------------

.. method:: math53.polylog_i(n, x)


    Returns the polylogarithm  of integer order `n`, `\displaystyle \mathrm{Li}_n(x) = \sum_{k=1}^{\infty} \frac{x^k}{k^n}, \quad n \in \mathbb{Z}, |x|<1 \,`, or its analytic continuation; for `n>0`, `x>1` the real part of `\mathrm{Li}_n(x)` is returned.

    See also   Wikipedia :cite:p:`WikipediaFun173`, MathWorld :cite:p:`WolframFun173`, NIST :cite:p:`DLMFun173`, :cite:t:`Ehrhardt2018` (3.6.11).



    Returns the polylogarithm function of integer order `n`.

    This function returns the polylogarithm function of integer order `n`

    .. math :: \text{Li}_n(z)=\sum_{k=1}^\infty \frac{z^{k}}{k^n}, \quad n \in  \mathbb{Z},  |z|<1.

    or its analytic continuation; for `n>0` there is the arguments restriction `x\leq 1`.




    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.polylog_i(2, 0.01)
        0.010025111740139094
        >>> math53.polylog_i(3, 10.5)
        5.66534093854826
        >>> math53.polylog_i(4, 20.9333)
        13.767054582329026












Fermi-Dirac integrals of integer order, `F_n(x)`
-------------------------------------------------------------------------------

.. method:: math53.fermi_dirac_i(n, x)


    Returns the Fermi-Dirac integral of integer order `n`, `\displaystyle F_s(x) = \frac{1}{\Gamma(n+1)} \int_0^{\infty} \frac{t^n}{e^{t-x}+1} = -\text{Li}_{n+1}(-e^x) \,`.

    See also:  Wikipedia :cite:p:`WikipediaFun173c`, MathWorld :cite:p:`WolframFun173c`, :cite:t:`Ehrhardt2018` (3.6.8.2).




    This function returns the complete Fermi-Dirac integrals `F_n(x)` of integer order. They are defined for real orders `s>-1` by

    .. math :: F_s(x)=\frac{1}{\Gamma(s+1)} \int_0^\infty \frac{t^s}{e^{t-x}+1} \mathrm{d}t

    and by analytic continuation for `s \leq -1` using polylogarithms

    .. math :: F_s(x)=-\text{Li}_{s+1}(-e^x).



    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.fermi_dirac_i(2, 0.01)
        0.9098020885004644
        >>> math53.fermi_dirac_i(3, 10.5)
        599.031966057601
        >>> math53.fermi_dirac_i(4, 20.9333)
        36051.591345246416







Fermi-Dirac integral `F_{-1/2}(x)`
-------------------------------------------------------------------------------

.. method:: math53.fermi_dirac_m05(x)

    Returns the Fermi-Dirac integral `F_{-1/2}(x)`. See also:  Wikipedia :cite:p:`WikipediaFun173c`, MathWorld :cite:p:`WolframFun173c`, :cite:t:`Ehrhardt2018` (3.6.8.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.fermi_dirac_m05(0.01)
        0.608705610911171
        >>> math53.fermi_dirac_m05(10.5)
        3.6420723652672895
        >>> math53.fermi_dirac_m05(20.9333)
        5.157769932482041







Fermi-Dirac integral `F_{1/2}(x)`
-------------------------------------------------------------------------------

.. method:: math53.fermi_dirac_p05(x)

    Returns the Fermi-Dirac integral `F_{1/2}(x)`. See also:  Wikipedia :cite:p:`WikipediaFun173c`, MathWorld :cite:p:`WolframFun173c`, :cite:t:`Ehrhardt2018` (3.6.8.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.fermi_dirac_p05(0.01)
        0.7712150360437194
        >>> math53.fermi_dirac_p05(10.5)
        25.88346611317671
        >>> math53.fermi_dirac_p05(20.9333)
        72.25098647441794








Fermi-Dirac integral `F_{3/2}(x)`
-------------------------------------------------------------------------------

.. method:: math53.fermi_dirac_p15(x)

    Returns the Fermi-Dirac integral `F_{3/2}(x)`. See also:  Wikipedia :cite:p:`WikipediaFun173c`, MathWorld :cite:p:`WolframFun173c`, :cite:t:`Ehrhardt2018` (3.6.8.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.fermi_dirac_p15(0.01)
        0.874881667590789
        >>> math53.fermi_dirac_p15(10.5)
        113.49527140479812
        >>> math53.fermi_dirac_p15(20.9333)
        611.7653726268513







Fermi-Dirac integral `F_{5/2}(x)`
-------------------------------------------------------------------------------

.. method:: math53.fermi_dirac_p25(x, s)

    Returns the Fermi-Dirac integral `F_{5/2}(x)`. See also:  Wikipedia :cite:p:`WikipediaFun173c`, MathWorld :cite:p:`WolframFun173c`, :cite:t:`Ehrhardt2018` (3.6.8.3).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.fermi_dirac_p25(0.01)
        0.9362639349902176
        >>> math53.fermi_dirac_p25(10.5)
        364.9252593211593
        >>> math53.fermi_dirac_p25(20.9333)
        3726.9235556746216






Inverse tangent integral, `\mathrm{Ti}_2(x)`
-------------------------------------------------------------------------------

.. method:: math53.tangent_int_2(x)

    Returns the  inverse tangent integral `\displaystyle \mathrm{Ti}_2(x)  =  \int_0^x  \frac{\arctan(t)}{t} \, \mathrm{d}t`.

    See also:  Wikipedia :cite:p:`WikipediaFun173a`, MathWorld :cite:p:`WolframFun173a`, :cite:t:`Ehrhardt2018` (3.6.16).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.tangent_int_2(0.01)
        0.009999888892888685
        >>> math53.tangent_int_2(10.5)
        3.788674042119505
        >>> math53.tangent_int_2(20.9333)
        4.8250862474762








Lobachevsky's log-cos integral, `L(x)`
-------------------------------------------------------------------------------

.. method:: math53.lobachevsky_c(x)

    Returns Lobachevsky's log-cos integral `\displaystyle L(x) = \int_0^x \log|\cos(t)| \, \mathrm{d}t`. See also: :cite:t:`Ehrhardt2018` (3.6.18).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.lobachevsky_c(0.01)
        1.6666833336508016e-07
        >>> math53.lobachevsky_c(10.5)
        6.7712697858797855
        >>> math53.lobachevsky_c(20.9333)
        15.017229619310305







Lobachevsky's log-sin integral, `\Lambda(x)`
-------------------------------------------------------------------------------

.. method:: math53.lobachevsky_s(x, s)

    Returns Lobachevsky's log-sin integral `\displaystyle \Lambda(x) = \int_0^x \log|2\sin(t)| \, \mathrm{d}t`. See also: :cite:t:`Ehrhardt2018` (3.6.19).


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.lobachevsky_s(0.01)
        0.049120285609948126
        >>> math53.lobachevsky_s(10.5)
        0.3226979802070858
        >>> math53.lobachevsky_s(20.9333)
        -0.33243071505340765











Debye functions, `\mathrm{D}_n(x)`
-------------------------------------------------------------------------------

.. method:: math53.debye(n,x)

    Returns the Debye function `\displaystyle \mathrm{D}_n(x) = \frac{n}{x^n} \int_0^x \frac{t^n}{e^t-1} \, \mathrm{d}t,  \quad n>0, x \ge 0`.

    See also:  Wikipedia :cite:p:`WikipediaFun323`, MathWorld :cite:p:`WolframFun323`, :cite:t:`Abramowitz1970` section 27.1,  :cite:t:`Ehrhardt2018` (3.10.6),  :cite:t:`Dubinov2008`.


    This routine returns the Debye functions

    .. math:: \text{D}_n(x) = \frac{n}{x^n} \int_0^x \frac{t^n}{e^t-1} \mathrm{d}t \quad (n>0, x \geq 0).


    .. math:: \text{D}_n^{(1)}(x) = \int_0^x \frac{t^n}{e^t-1} \mathrm{d}t = n! \zeta(n+1)  - n! Z_{n+1}(z) .


    .. math:: \text{D}_n^{(2)}(x) = \int_x^{\infty} \frac{t^n}{e^t-1} \mathrm{d}t = n! Z_{n+1}(z).


    .. math:: \text{D}^{(2)}_n(x) = \Gamma(n+1)\zeta(n+1) - \text{D}^{(1)}_n(x).


    .. math:: \text{D}^{(1)}_n(x) = n! \zeta(n+1) - \text{D}^{(2)}_n(x).


    .. math:: Z_{n+1}(z)=\sum _{k=0}^{n}\mathrm{Li} _{n-k+1}(e^{-z}){z^{k} \over k!} \quad (n=1,2,3,\ldots ).



    In terms of the incomplete zeta functions or "Debye functions" (Abramowitz & Stegun 1972, § 27.1):

    .. math:: Z_{n}(z)={1 \over (n-1)!}\int _{z}^{\infty }{t^{n-1} \over e^{t}-1}\mathrm{d}t\qquad (n=1,2,3,\ldots ),

    the polylogarithm Lin(z) for positive integer n may be expressed as the finite sum (Wood 1992, § 16):

    .. math:: \mathrm {Li} _{n}(e^{\mu })=\sum _{k=0}^{n-1}Z_{n-k}(-\mu ){\mu ^{k} \over k!}\qquad (n=1,2,3,\ldots ).

    A remarkably similar expression relates the "Debye functions" Zn(z) to the polylogarithm:

    .. math:: Z_{n}(z)=\sum _{k=0}^{n-1}\mathrm{Li}_{n-k}(e^{-z}){z^{k} \over k!}\qquad (n=1,2,3,\ldots ).





    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.debye(2, 0.01)
        0.9966708333287038
        >>> math53.debye(3, 10.5)
        0.016717989806569248
        >>> math53.debye(4, 20.9333)
        0.0005184007550452067







Transport integral, `\mathrm{J}_n(x)`
-------------------------------------------------------------------------------

.. method:: math53.transport_jn(n,x)

    Returns the transport function `\displaystyle \mathrm{J}_n(x) =\int_0^x \frac{t^n e^t}{(e^t-1)^2} \, \mathrm{d}t,  \quad n \ge 2, x \ge 0`.

    See also: :cite:t:`Ehrhardt2018` (3.10.24).

    A.J. MacLeod, The numerical computation of transport integrals, 1992, Computer Physics Communications,
    69, pp. 229-234, https://doi.org/10.1016/0010-4655(92)90162-R,


    An example in Python

    .. code-block:: pycon

        >>> from xlcalcnet import math53
        >>> math53.transport_jn(2, 0.01)
        0.009999972222305555
        >>> math53.transport_jn(3, 10.5)
        7.169455825440913
        >>> math53.transport_jn(4, 20.9333)
        25.97556753445377







