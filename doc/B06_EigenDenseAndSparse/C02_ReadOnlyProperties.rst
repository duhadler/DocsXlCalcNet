

.. |spacingstart| raw:: latex

   \begin{spacing}{1.5}


.. |spacingend| raw:: latex

   \end{spacing}



.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />





|newpage|

Read-only properties: information about a matrix
===============================================================================


Rows of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_rows(matA)


    Returns the number of rows of the matrix. Writing ``matA.rows`` has the same effect.


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> mpm.dps = 15;
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", "")
        >>> print("A.rows: ", A.rows)
        A.rows: 6





Columns of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_cols(matA)


    Returns the number of columns of the matrix. Writing ``matA.cols`` has the same effect,


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> mpm.dps = 15;
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", "")
        >>> print("A.cols: ", A.cols)
        A.cols: 4




Size of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_size(matA)

    Returns the size of the matrix. Writing ``matA.size`` has the same effect.



    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> mpm.dps = 15;
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", "")
        >>> print("A.size: ", A.size)
        A.cols: 24





