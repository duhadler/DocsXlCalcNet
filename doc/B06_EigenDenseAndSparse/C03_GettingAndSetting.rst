

.. |spacingstart| raw:: latex

   \begin{spacing}{1.5}


.. |spacingend| raw:: latex

   \end{spacing}



.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />





|newpage|

Accessing and setting parts of a matrix
===============================================================================


Getting and setting a matrix coefficient
-------------------------------------------------------------------------------

Individual coefficients of a matrix `A` are accessed using the ``A[row,col]`` syntax. Note that indexing starts at 0, so that the coefficient in the `4^{\text{th}}` row and `2^{\text{nd}}` column is accessed as ``A[3,1]``.  Examples:

.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> ctx = mp14.drf()
    >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
    A: 
    11,  12,  13,  14, 
    21,  22,  23,  24, 
    31,  32,  33,  34, 
    41,  42,  43,  44, 
    51,  52,  53,  54, 
    61,  62,  63,  64, 

    >>> # gets the coefficient in row number 3 and column number 1
    >>> print("A[3,1]: ", A[3,1])
    A[3,1]:  42

    >>> # sets the coefficient in row number 1 and column number 2 to the value of 99.
    >>> A[1,2] = 99; A.show("A")
    matA: 
    11,  12,  13,  14, 
    21,  22,  99,  24, 
    31,  32,  33,  34, 
    41,  42,  43,  44, 
    51,  52,  53,  54, 
    61,  62,  63,  64, 





Getting and setting a block
-------------------------------------------------------------------------------

.. method:: ctx.mat_get_block(matA, i, j, p, q)

    Gets a block of the matrix, starting at row `i` and column `j`, with `p` row elements and `q` column elements. Writing ``matA.get_Block(i, j, p, q)`` has the same effect

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11,  12,  13,  14, 
        21,  22,  23,  24, 
        31,  32,  33,  34, 
        41,  42,  43,  44, 
        51,  52,  53,  54, 
        61,  62,  63,  64, 

        >>> # gets a block, beginning at A[1, 1], stretching to A[1+3, 1+2]
        >>> b1 = A.block(1, 1, 3, 2); b1.show("b1")
        b1: 
        22,  23, 
        32,  33, 
        42,  43, 



.. method:: ctx.mat_set_block(matA, i, j, p, q, matB)

    Sets a block of the matrix to *matB*, starting at row `i` and column `j`, with `p` row elements and `q` column elements. Writing ``matA.set_Block(i, j, p, q, matB)`` has the same effect

    .. code-block:: pycon

            >>> # continued from above
            >>> # sets b1 into a block, beginning at A[0, 0], stretching to A[0+3, 0+2]
            >>> A.set_Block(0, 0, 3, 2, b1); ; A.show("A")
            A: 
            22,  23,  13,  14, 
            32,  33,  23,  24, 
            42,  43,  33,  34, 
            41,  42,  43,  44, 
            51,  52,  53,  54, 
            61,  62,  63,  64, 





Getting and setting a matrix row
-------------------------------------------------------------------------------

.. method:: ctx.mat_get_row(matA, i)

    Gets the `i^{\text{th}}` row. Writing ``matA.get_Row(i)`` has the same effect

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11,  12,  13,  14, 
        21,  22,  23,  24, 
        31,  32,  33,  34, 
        41,  42,  43,  44, 
        51,  52,  53,  54, 
        61,  62,  63,  64, 

        >>> # gets row number 2 (i.e. the 3rd row from the top)
        >>> r1 = A.row(2); r1.show("r1")
        r1: 
        31,  32,  33,  34, 



.. method:: ctx.mat_set_row(matA, i, matB)

    Sets the `i^{\text{th}}` row to *matB*. Writing ``matA.set_Row(i, matB)`` has the same effect


    .. code-block:: pycon

        >>> # continued from above
        >>> # sets the content of row number 5 to the content of row number 2
        >>> A.set_Row(5, A.get_Row(2)); A.show("A")
        A: 
        11,  12,  13,  14, 
        21,  22,  23,  24, 
        31,  32,  33,  34, 
        41,  42,  43,  44, 
        51,  52,  53,  54, 
        31,  32,  33,  34, 





Getting and setting a matrix column
-------------------------------------------------------------------------------

.. method:: ctx.mat_get_col(matA, j)

    Gets the `j^{\text{th}}` column. Writing ``matA.get_Col(j)`` has the same effect

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11,  12,  13,  14, 
        21,  22,  23,  24, 
        31,  32,  33,  34, 
        41,  42,  43,  44, 
        51,  52,  53,  54, 
        61,  62,  63,  64, 

        >>> # gets column number 1 (i.e. the 2nd column from the left)
        >>> c1 = A.col(1); c1.show("c1")
        c1: 
        12, 
        22, 
        32, 
        42, 
        52, 
        62, 


.. method:: ctx.mat_set_col(matA, j, matB)


    Sets the `j^{\text{th}}` column to *matB*. Writing ``matA.set_Col(j, matB)`` has the same effect

    .. code-block:: pycon

        >>> # continued from above
        >>> # sets the content of column number 3 to the content of column number 1
        >>> A.set_Col(3, A.get_Col(1)); A.show("A")
        A: 
        11,  12,  13,  12, 
        21,  22,  23,  22, 
        31,  32,  33,  32, 
        41,  42,  43,  42, 
        51,  52,  53,  52, 
        61,  62,  63,  62, 



Getting and setting a diagonal
-------------------------------------------------------------------------------

.. method:: ctx.mat_get_diagonal(matA, q=0)

    Gets the diagonal or a subdiagonal of the matrix. Writing ``matA.get_Diagonal(q=0)`` has the same effect.

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11,  12,  13,  14, 
        21,  22,  23,  24, 
        31,  32,  33,  34, 
        41,  42,  43,  44, 
        51,  52,  53,  54, 
        61,  62,  63,  64, 

        >>> # gets the first lower subdiagonal
        >>> b1 = A.diagonal(-1); b1.show("b1")
        b1 = A.diagonal(-1): 
        21, 
        32, 
        43, 
        54, 



.. method:: ctx.mat_set_diagonal(matA, q, matB)

    Sets the diagonal or a subdiagonal of the matrix to *matB*. Writing ``matA.set_Diagonal(q, matB)`` has the same effect.

    .. code-block:: pycon

        >>> # continued from above
        >>> # sets the diagonal to the first lower subdiagonal
        >>> A.set_Diagonal(0, b1); A.show("A")
        A: 
        21,  12,  13,  14, 
        21,  32,  23,  24, 
        31,  32,  43,  34, 
        41,  42,  43,  54, 
        51,  52,  53,  54, 
        61,  62,  63,  64, 



Getting and setting a triangular view
-------------------------------------------------------------------------------

.. method:: ctx.mat_get_triangular_view(matA, view = 1)

    Gets the triangular view of the matrix. Writing ``matA.get_TriangularView(View = 1)`` has the same effect.


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11,  12,  13,  14, 
        21,  22,  23,  24, 
        31,  32,  33,  34, 
        41,  42,  43,  44, 
        51,  52,  53,  54, 
        61,  62,  63,  64, 

        >>> # gets the first lower subdiagonal
        >>> b1 = A.diagonal(-1); b1.show("b1")
        b1 = A.diagonal(-1): 
        21, 
        32, 
        43, 
        54, 



.. method:: ctx.mat_set_triangular_view(matA, view, matB)

    Sets the triangular view of the matrix to *matB*. Writing ``matA.set_TriangularView(View, matB)`` has the same effect.

    .. code-block:: pycon

        >>> # continued from above
        >>> # sets the diagonal to the first lower subdiagonal
        >>> A.set_Diagonal(0, b1); A.show("A")
        A: 
        21,  12,  13,  14, 
        21,  32,  23,  24, 
        31,  32,  43,  34, 
        41,  42,  43,  54, 
        51,  52,  53,  54, 
        61,  62,  63,  64, 






