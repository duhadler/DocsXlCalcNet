

.. |spacingstart| raw:: latex

   \begin{spacing}{1.5}


.. |spacingend| raw:: latex

   \end{spacing}



.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />





|newpage|

Changing the shape of a matrix and/or the order of coefficients
===============================================================================


Sorting  a whole matrix
-------------------------------------------------------------------------------


.. method:: ctx.mat_sort(matA, sort_order=0, sort_criterion=1)

    Returns a sorted version of the matrix, sorted according to SortOrder and SortCriterion. 

    Writing ``matA.Sort(sort_order=0, sort_criterion=1)`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # returns a copy of the whole matrix in ascending order (SortOrder=0)
        >>> B = A.sorted(SortOrder=0); B.show("B")
        B: 
        11, 23, 41, 53, 
        12, 24, 42, 54, 
        13, 31, 43, 61, 
        14, 32, 44, 62, 
        21, 33, 51, 63, 
        22, 34, 52, 64, 

        >>> # sorts the whole matrix in descending order (SortOrder=1)
        >>> C = A.sorted(SortOrder=1); C.show("C")
        C: 
        64, 52, 34, 22, 
        63, 51, 33, 21, 
        62, 44, 32, 14, 
        61, 43, 31, 13, 
        54, 42, 24, 12, 
        53, 41, 23, 11, 




Sorting the rows of a matrix by a given column
-------------------------------------------------------------------------------

.. method:: ctx.mat_sort_rows_by_col(matA, column_to_sort_by=0, sort_order=0, sort_criterion=1)

    Returns a sorted version of the matrix, sorted by column ColumnToSortBy, according to SortOrder and SortCriterion.

    Writing ``matA.SortRowsByCol(column_to_sort_by=0, sort_order=0, sort_criterion=1)`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # sorts the whole matrix by column 0 in descending order (SortOrder=1)
        >>> B = A.sorted_rows_by_col(ColumnToSortBy=0, SortOrder=1); B.show("B")
        B: 
        61, 62, 63, 64, 
        51, 52, 53, 54, 
        41, 42, 43, 44, 
        31, 32, 33, 34, 
        21, 22, 23, 24, 
        11, 12, 13, 14, 

        >>> # sorts the whole matrix in descending order (SortOrder=0)
        >>> C = A.sorted_rows_by_col(ColumnToSortBy=0, SortOrder=0); C.show("C")
        C: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 





Resize a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_resize(matA, r, c)

    Resizes the matrix inplace, setting values of coefficients to zero.

    Writing ``matA.Resize(r, c)`` has the same effect

    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # resizes the matrix to 3 rows and 2 columns, setting values of coefficients to zero.
        >>> A.resize(3,2); A.show("A")
        A: 
        0, 0, 
        0, 0, 
        0, 0, 





Resize a matrix like another matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_resize_like(matA, matB)

    Resizes the matrix inplace, setting values of coefficients to zero.

    Writing ``matA.ResizeLike(matB)`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # resizes the matrix to 3 rows and 2 columns, setting values of coefficients to zero.
        >>> A.resize(3,2); A.show("A")
        A: 
        0, 0, 
        0, 0, 
        0, 0, 




Conservatively resize a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_conservative_resize(matA, r, c)

    Resizes the matrix inplace, retaining values of existing coefficients.

    Writing ``matA.ConservativeResize(r, c)`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # resizes the matrix to 3 rows and 6 columns, retaining values of existing coefficients.
        >>> A.conservative_resize(3,6); A.show("A")
        A: 
        11, 12, 13, 14,  0,  0, 
        21, 22, 23, 24,  0,  0, 
        31, 32, 33, 34,  0,  0, 






Convert vector to diagonal matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_as_diagonal(matA)

    Returns the first column vector of a matrix as a diagonal matrix.

    Writing ``matA.AsDiagonal()`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> # read the first column from the matrix
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", "").col(0); A.show("A")
        A: 
        11, 
        21, 
        31, 
        41, 
        51, 
        61, 

        >>> # resizes the matrix to 3 rows and 6 columns, retaining values of existing coefficients.
        >>> B = A.as_diagonal(); B.show("B")
        B: 
        11,  0,  0,  0,  0,  0, 
         0, 21,  0,  0,  0,  0, 
         0,  0, 31,  0,  0,  0, 
         0,  0,  0, 41,  0,  0, 
         0,  0,  0,  0, 51,  0, 
         0,  0,  0,  0,  0, 61, 









Adjoint of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_adjoint(matA)


    Returns the adjoint matrix of the matrix.  Writing ``matA.Adjoint()`` has the same effect



    .. code-block:: pycon

        >>> from xlcalcnet import *

        >>> # example with a real matrix
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x6", ""); A.show("A")
        A: 
        11, 12, 13, 14, 15, 16, 
        21, 22, 23, 24, 25, 26, 
        31, 32, 33, 34, 35, 36, 
        41, 42, 43, 44, 45, 46, 
        51, 52, 53, 54, 55, 56, 
        61, 62, 63, 64, 65, 66, 


        >>> # returns the adjoint matrix of a real matrix, i.e. the transpose
        >>> B = A.adjoint(); B.show("B")
        B: 
        11, 21, 31, 41, 51, 61, 
        12, 22, 32, 42, 52, 62, 
        13, 23, 33, 43, 53, 63, 
        14, 24, 34, 44, 54, 64, 
        15, 25, 35, 45, 55, 65, 
        16, 26, 36, 46, 56, 66, 


        >>> # example with a complex matrix
        >>> ctx = mp14.dcf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecCplxTableA6x6", ""); A.show("A")
        A: 
        11 + 31j, 12 + 32j, 13 + 33j, 14 + 34j, 15 + 35j, 16 + 36j, 
        21 + 41j, 22 + 42j, 23 + 43j, 24 + 44j, 25 + 45j, 26 + 46j, 
        31 + 51j, 32 + 52j, 33 + 53j, 34 + 54j, 35 + 55j, 36 + 56j, 
        41 + 61j, 42 + 62j, 43 + 63j, 44 + 64j, 45 + 65j, 46 + 66j, 
        51 + 71j, 52 + 72j, 53 + 73j, 54 + 74j, 55 + 75j, 56 + 76j, 
        61 + 81j, 62 + 82j, 63 + 83j, 64 + 84j, 65 + 85j, 66 + 86j, 


        >>> # returns the adjoint matrix of a complex matrix, i.e. the conjugate of the transpose
        >>> B = A.adjoint(); B.show("B")
        B: 
        11 + -31j, 21 + -41j, 31 + -51j, 41 + -61j, 51 + -71j, 61 + -81j, 
        12 + -32j, 22 + -42j, 32 + -52j, 42 + -62j, 52 + -72j, 62 + -82j, 
        13 + -33j, 23 + -43j, 33 + -53j, 43 + -63j, 53 + -73j, 63 + -83j, 
        14 + -34j, 24 + -44j, 34 + -54j, 44 + -64j, 54 + -74j, 64 + -84j, 
        15 + -35j, 25 + -45j, 35 + -55j, 45 + -65j, 55 + -75j, 65 + -85j, 
        16 + -36j, 26 + -46j, 36 + -56j, 46 + -66j, 56 + -76j, 66 + -86j, 






Conjugate of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_conjugate(matA)

    Returns the conjugate matrix of matrix matA.  Writing ``matA.Conjugate()`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *

        >>> # example with a real matrix
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x6", ""); A.show("A")
        A: 
        11, 12, 13, 14, 15, 16, 
        21, 22, 23, 24, 25, 26, 
        31, 32, 33, 34, 35, 36, 
        41, 42, 43, 44, 45, 46, 
        51, 52, 53, 54, 55, 56, 
        61, 62, 63, 64, 65, 66, 


        >>> # returns the conjugate matrix of a real matrix, i.e. the matrix itself
        >>> B = A.conjugate(); B.show("B")
        B: 
        11, 12, 13, 14, 15, 16, 
        21, 22, 23, 24, 25, 26, 
        31, 32, 33, 34, 35, 36, 
        41, 42, 43, 44, 45, 46, 
        51, 52, 53, 54, 55, 56, 
        61, 62, 63, 64, 65, 66, 


        >>> # example with a complex matrix
        >>> ctx = mp14.dcf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecCplxTableA6x6", ""); A.show("A")
        A: 
        11 + 31j, 12 + 32j, 13 + 33j, 14 + 34j, 15 + 35j, 16 + 36j, 
        21 + 41j, 22 + 42j, 23 + 43j, 24 + 44j, 25 + 45j, 26 + 46j, 
        31 + 51j, 32 + 52j, 33 + 53j, 34 + 54j, 35 + 55j, 36 + 56j, 
        41 + 61j, 42 + 62j, 43 + 63j, 44 + 64j, 45 + 65j, 46 + 66j, 
        51 + 71j, 52 + 72j, 53 + 73j, 54 + 74j, 55 + 75j, 56 + 76j, 
        61 + 81j, 62 + 82j, 63 + 83j, 64 + 84j, 65 + 85j, 66 + 86j, 


        >>> # returns the conjugate matrix of a complex matrix
        >>> B = A.conjugate(); B.show("B")
        B: 
        11 + -31j, 12 + -32j, 13 + -33j, 14 + -34j, 15 + -35j, 16 + -36j, 
        21 + -41j, 22 + -42j, 23 + -43j, 24 + -44j, 25 + -45j, 26 + -46j, 
        31 + -51j, 32 + -52j, 33 + -53j, 34 + -54j, 35 + -55j, 36 + -56j, 
        41 + -61j, 42 + -62j, 43 + -63j, 44 + -64j, 45 + -65j, 46 + -66j, 
        51 + -71j, 52 + -72j, 53 + -73j, 54 + -74j, 55 + -75j, 56 + -76j, 
        61 + -81j, 62 + -82j, 63 + -83j, 64 + -84j, 65 + -85j, 66 + -86j, 





Transpose of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_transpose(matA)

    Returns the transposed matrix of matrix matA.  Writing ``matA.Transpose()`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # returns the transpose matrix of a real matrix
        >>> B = A.transpose(); B.show("B")
        B: 
        11, 21, 31, 41, 51, 61, 
        12, 22, 32, 42, 52, 62, 
        13, 23, 33, 43, 53, 63, 
        14, 24, 34, 44, 54, 64, 






Full Reverse of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_reverse_full(matA)

    Returns the full reverse of matrix matA.  Writing ``matA.ReverseFull()`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # returns the full reverse  of the matrix
        >>> B = A.reverse_full(); B.show("B")
        B: 
        64, 63, 62, 61, 
        54, 53, 52, 51, 
        44, 43, 42, 41, 
        34, 33, 32, 31, 
        24, 23, 22, 21, 
        14, 13, 12, 11, 






Row-wise Reverse of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_reverse_row_wise(matA)


    Returns the row-wise reverse of matrix matA.  Writing ``matA.ReverseRowwise()`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # returns the row-wise reverse of the matrix
        >>> B = A.reverse_rowwise(); B.show("B")
        14, 13, 12, 11, 
        24, 23, 22, 21, 
        34, 33, 32, 31, 
        44, 43, 42, 41, 
        54, 53, 52, 51, 
        64, 63, 62, 61, 




Column-wise Reverse of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_reverse_col_wise(matA)

    Returns the column-wise reverse of matrix matA.  Writing ``matA.ReverseColwise()`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # returns the column-wise reverse of the matrix
        >>> B = A.reverse_colwise(); B.show("B")
        B: 
        61, 62, 63, 64, 
        51, 52, 53, 54, 
        41, 42, 43, 44, 
        31, 32, 33, 34, 
        21, 22, 23, 24, 
        11, 12, 13, 14, 





Full Replication of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_replicate_full(matA, vertical, horizontal)

    Returns a full replication of matrix matA.  Writing ``matA.ReplicateFull(vertical, horizontal)`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # returns a full replication (Vertical=2, Horizontal=3) of the matrix
        >>> B = A.replicate_full(2, 3); B.show("B")
        B: 
        11, 12, 13, 14, 11, 12, 13, 14, 11, 12, 13, 14, 
        21, 22, 23, 24, 21, 22, 23, 24, 21, 22, 23, 24, 
        31, 32, 33, 34, 31, 32, 33, 34, 31, 32, 33, 34, 
        41, 42, 43, 44, 41, 42, 43, 44, 41, 42, 43, 44, 
        51, 52, 53, 54, 51, 52, 53, 54, 51, 52, 53, 54, 
        61, 62, 63, 64, 61, 62, 63, 64, 61, 62, 63, 64, 
        11, 12, 13, 14, 11, 12, 13, 14, 11, 12, 13, 14, 
        21, 22, 23, 24, 21, 22, 23, 24, 21, 22, 23, 24, 
        31, 32, 33, 34, 31, 32, 33, 34, 31, 32, 33, 34, 
        41, 42, 43, 44, 41, 42, 43, 44, 41, 42, 43, 44, 
        51, 52, 53, 54, 51, 52, 53, 54, 51, 52, 53, 54, 
        61, 62, 63, 64, 61, 62, 63, 64, 61, 62, 63, 64, 






Row-wise Replication of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_replicate_row_wise(matA, horizontal)

    Returns a row-wise replication of matrix matA.  Writing ``matA.ReplicateRowwise(horizontal)`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # returns a row-wise replication (Horizontal=4) of the matrix
        >>> B = A.replicate_rowwise(4); B.show("B")
        B: 
        11, 12, 13, 14, 11, 12, 13, 14, 11, 12, 13, 14, 11, 12, 13, 14, 
        21, 22, 23, 24, 21, 22, 23, 24, 21, 22, 23, 24, 21, 22, 23, 24, 
        31, 32, 33, 34, 31, 32, 33, 34, 31, 32, 33, 34, 31, 32, 33, 34, 
        41, 42, 43, 44, 41, 42, 43, 44, 41, 42, 43, 44, 41, 42, 43, 44, 
        51, 52, 53, 54, 51, 52, 53, 54, 51, 52, 53, 54, 51, 52, 53, 54, 
        61, 62, 63, 64, 61, 62, 63, 64, 61, 62, 63, 64, 61, 62, 63, 64, 






Column-wise Replication of a matrix
-------------------------------------------------------------------------------

.. method:: ctx.mat_replicate_col_wise(matA, vertical)

    Returns a column-wise replication of matrix matA.  Writing ``matA.ReplicateColwise(vertical)`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x4", ""); A.show("A")
        A: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 

        >>> # returns a column-wise replication (Vertical=2) of the matrix
        >>> B = A.replicate_colwise(2); B.show("B")
        B: 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 
        11, 12, 13, 14, 
        21, 22, 23, 24, 
        31, 32, 33, 34, 
        41, 42, 43, 44, 
        51, 52, 53, 54, 
        61, 62, 63, 64, 




Horizontal concatenation of two matrices
-------------------------------------------------------------------------------

.. method:: ctx.mat_concat_horizontal(matA, matB)

    Returns the horizontal concatenation of matrix matA with matrix matB.  Writing ``matA.ConcatHorizontal(matB)`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x6", ""); A.show("A")
        A: 
        11, 12, 13, 14, 15, 16, 
        21, 22, 23, 24, 25, 26, 
        31, 32, 33, 34, 35, 36, 
        41, 42, 43, 44, 45, 46, 
        51, 52, 53, 54, 55, 56, 
        61, 62, 63, 64, 65, 66, 

        >>> B = ctx.read_from_sqlite(mp14.dbpath(), "DecTableB6x6", ""); B.show("B")
        B: 
        911, 912, 913, 914, 915, 916, 
        921, 922, 923, 924, 925, 926, 
        931, 932, 933, 934, 935, 936, 
        941, 942, 943, 944, 945, 946, 
        951, 952, 953, 954, 955, 956, 
        961, 962, 963, 964, 965, 966, 

        >>> # returns a column-wise replication (Vertical=2) of the matrix
        >>> C = A.concat_horizontal(B); C.show("C")
        C: 
         11,  12,  13,  14,  15,  16, 911, 912, 913, 914, 915, 916, 
         21,  22,  23,  24,  25,  26, 921, 922, 923, 924, 925, 926, 
         31,  32,  33,  34,  35,  36, 931, 932, 933, 934, 935, 936, 
         41,  42,  43,  44,  45,  46, 941, 942, 943, 944, 945, 946, 
         51,  52,  53,  54,  55,  56, 951, 952, 953, 954, 955, 956, 
         61,  62,  63,  64,  65,  66, 961, 962, 963, 964, 965, 966, 






Vertical concatenation of two matrices
-------------------------------------------------------------------------------

.. method:: ctx.mat_concat_vertical(matA, matB)


    Returns the vertical concatenation of matrix matA with matrix matB.  
    
    Writing ``matA.ConcatVertical(matB)`` has the same effect


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> ctx = mp14.drf()
        >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x6", ""); A.show("A")
        A: 
        11, 12, 13, 14, 15, 16, 
        21, 22, 23, 24, 25, 26, 
        31, 32, 33, 34, 35, 36, 
        41, 42, 43, 44, 45, 46, 
        51, 52, 53, 54, 55, 56, 
        61, 62, 63, 64, 65, 66, 

        >>> B = ctx.read_from_sqlite(mp14.dbpath(), "DecTableB6x6", ""); B.show("B")
        B: 
        911, 912, 913, 914, 915, 916, 
        921, 922, 923, 924, 925, 926, 
        931, 932, 933, 934, 935, 936, 
        941, 942, 943, 944, 945, 946, 
        951, 952, 953, 954, 955, 956, 
        961, 962, 963, 964, 965, 966, 

        >>> # returns a column-wise replication (Vertical=2) of the matrix
        >>> C = A.concat_vertical(B); C.show("C")
        C: 
         11,  12,  13,  14,  15,  16, 
         21,  22,  23,  24,  25,  26, 
         31,  32,  33,  34,  35,  36, 
         41,  42,  43,  44,  45,  46, 
         51,  52,  53,  54,  55,  56, 
         61,  62,  63,  64,  65,  66, 
        911, 912, 913, 914, 915, 916, 
        921, 922, 923, 924, 925, 926, 
        931, 932, 933, 934, 935, 936, 
        941, 942, 943, 944, 945, 946, 
        951, 952, 953, 954, 955, 956, 
        961, 962, 963, 964, 965, 966, 




