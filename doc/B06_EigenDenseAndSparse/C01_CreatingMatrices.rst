

.. |spacingstart| raw:: latex

   \begin{spacing}{1.5}


.. |spacingend| raw:: latex

   \end{spacing}



.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />



Creating scalars and matrices
===============================================================================





Creating a matrix, and converting from compatible data types
-------------------------------------------------------------------------------

.. method:: ctx.mat_t(x)


    Converts from a real scalar of type dreal





Creating a matrix of zeros
-------------------------------------------------------------------------------

.. method:: ctx.mat_zeros(n, m)


    Creates a `n \times m` matrix of the indicated type and sets all entries to zero.


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx.dps = 15; n = 4; m = 4
        >>> matA = ctx.mat_zeros(n, m, eigen=True)
        >>> matA.show("matA, mat_zeros(n, m) :")
        matA, mat_zeros(n, m) :
         0,  0,  0,  0, 
         0,  0,  0,  0, 
         0,  0,  0,  0, 
         0,  0,  0,  0, 



Creating a matrix of ones
-------------------------------------------------------------------------------

.. method:: ctx.mat_ones(n, m)


    Creates a `n \times m` matrix of the indicated type and sets all entries to one.


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx.dps = 15; n = 4; m = 4
        >>> matA = ctx.mat_ones(n, m)
        >>> matA.show("matA, mat_ones(n, m) :")
        matA, mat_ones(n, m) :
         1,  1,  1,  1, 
         1,  1,  1,  1, 
         1,  1,  1,  1, 
         1,  1,  1,  1, 





Creating an identity matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_identity(n, m)


    Creates a `n \times m` identity matrix of the indicated type.


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx.dps = 15; n = 4; m = 4
        >>> matA = ctx.mat_identity(n, m)
        >>> matA.show("matA, mat_identity(n, m) :")
        matA, mat_identity(n, m) :
         1,  0,  0,  0, 
         0,  1,  0,  0, 
         0,  0,  1,  0, 
         0,  0,  0,  1, 








Creating a general random matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_random(n, m)


    Creates a `n \times m` matrix of the indicated type and sets all entries to random values.



    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx.dps = 15; n = 4; m = 4
        >>> matA = ctx.mat_random(n, m)
        >>> matA.show("matA, mat_random(n, m) :")
        matA, mat_random(n, m) :
         0.35029145176550,  0.17410809656056,  0.30399487289041,  0.14731284524064, 
         0.89596240119633,  0.85894344920194,  0.014984588152715,  0.16589861751152, 
         0.82284005249184,  0.71050141911069,  0.091402935880612,  0.98852504043703, 
         0.74660481582080,  0.51353495895260,  0.36445204016236,  0.44569231238746, 





Creating a symmetric random matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_random_symmetric(n)


    Creates a `n \times n` symmetric matrix of the indicated type and sets all entries to random values.



    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx.dps = 15; n = 4; m = 4
        >>> matA = ctx.mat_random_symmetric(n)
        >>> matA.show("matA, mat_random_symmetric(n) :")
        matA, mat_random_symmetric(n) :
         0.23816644795068,  0.53633228553118,  0.17514572588275,  0.43491927854244, 
         0.53633228553118,  1.1423688467055,  1.2648091067232,  1.2148503067110, 
         0.17514572588275,  1.2648091067232,  0.90157780693990,  1.1354411450545, 
         0.43491927854244,  1.2148503067110,  1.1354411450545,  1.6052125614185, 





Creating a self-adjoint random matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_random_selfadjoint(n, complex=False, eigen=False)


    Creates a `n \times n` selfadjoint matrix of the indicated type and sets all entries to random values.



    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx.dps = 15; n = 4; m = 4
        >>> matA = ctx.mat_random_sa(n)
        >>> matA.show("matA, mat_random_sa(n) :")
        matA, mat_random_sym(n) :
         0.23816644795068,  0.53633228553118,  0.17514572588275,  0.43491927854244, 
         0.53633228553118,  1.1423688467055,  1.2648091067232,  1.2148503067110, 
         0.17514572588275,  1.2648091067232,  0.90157780693990,  1.1354411450545, 
         0.43491927854244,  1.2148503067110,  1.1354411450545,  1.6052125614185, 






Creating a positive definite self-adjoint matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_random_selfadjoint_posdef(n, complex=False, eigen=False)


    Creates a `n \times n` positive definite random matrix of the indicated type.



    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx.dps = 15; n = 4; m = 4
        >>> matA = ctx.mat_random_sa_posdef(n)
        >>> matA.show("matA, mat_random_sa_posdef(n)")
        matA, mat_random_sa_posdef(n)
         1.6144949159812,  0.37328104299787,  0.64671931578811,  1.0725029543798, 
         0.37328104299787,  0.23220359390837,  0.27432857744706,  0.35913470470614, 
         0.64671931578811,  0.27432857744706,  0.55785829596540,  0.52838216584663, 
         1.0725029543798,  0.35913470470614,  0.52838216584663,  1.4188647561723, 






Creating a matrix with linearly increasing values
-------------------------------------------------------------------------------

.. method:: ctx.mat_fill_linear(n, m, x)


    Creates a `n \times m` matrix of the indicated type and sets all entries to increasing values.


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx.dps = 15; n = 4; m = 4
        >>> matA = ctx.mat_linspace(n, m, x)
        >>> matA.show("matA, mat_linspace(n, m, x) :")
        matA, mat_linspace(n, m, x) :
         0,  0,  0,  0, 
         0,  0,  0,  0, 
         0,  0,  0,  0, 
         0,  0,  0,  0, 



