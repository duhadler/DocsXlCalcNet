
.. |spacingstart| raw:: latex

   \begin{spacing}{1.5}


.. |spacingend| raw:: latex

   \end{spacing}


.. |newpage| raw:: latex

   \newpage



.. |br| raw:: html

   <br />



Basic arithmetic operations
===============================================================================



Matrix deep copy (unary plus)
-------------------------------------------------------------------------------

Returns the matrix multiplied with +1. This results in a deep copy of the matrix.


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
    >>> B = A
    >>> C = +A
    >>> A[1,1] = 99
    >>> B.show("B")
    B: 
    11, 12, 13, 14, 15, 16, 
    21, 99, 23, 24, 25, 26, 
    31, 32, 33, 34, 35, 36, 
    41, 42, 43, 44, 45, 46, 
    51, 52, 53, 54, 55, 56, 
    61, 62, 63, 64, 65, 66, 
    >>> C.show("C")
    C: 
    11, 12, 13, 14, 15, 16, 
    21, 22, 23, 24, 25, 26, 
    31, 32, 33, 34, 35, 36, 
    41, 42, 43, 44, 45, 46, 
    51, 52, 53, 54, 55, 56, 
    61, 62, 63, 64, 65, 66, 






Matrix negation (unary minus)
-------------------------------------------------------------------------------

Returns the matrix multiplied with -1.


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
    >>> B = -A
    >>> B.show("B")
    B: 
    -11, -12, -13, -14, -15, -16, 
    -21, -99, -23, -24, -25, -26, 
    -31, -32, -33, -34, -35, -36, 
    -41, -42, -43, -44, -45, -46, 
    -51, -52, -53, -54, -55, -56, 
    -61, -62, -63, -64, -65, -66, 






General matrix addition
-------------------------------------------------------------------------------

Returns the sum of matrix matA and matrix matB. matA and matB need to be of the same type and need to have the same dimensions. The returned matrix is of the same type as matA. Special rules apply for mixing real and complex matrices.


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
    >>> C = A + B; C.show("C")
    C: 
     922,  924,  926,  928,  930,  932, 
     942,  944,  946,  948,  950,  952, 
     962,  964,  966,  968,  970,  972, 
     982,  984,  986,  988,  990,  992, 
    1002, 1004, 1006, 1008, 1010, 1012, 
    1022, 1024, 1026, 1028, 1030, 1032, 





Matrix addition of a vector as diagonal matrix 
-------------------------------------------------------------------------------


Returns the matrix product of matrix matA and matrix matB. matA and matB need to be of the same type and need to have compatible dimensions. The returned matrix is of the same type as matA. Special rules apply for mixing real and complex matrices.


.. code-block:: pycon

    >>> from xlcalcnet import *
    >>> ctx = mp14.drf()
    >>> # read the first column from the matrix
    >>> d = ctx.read_from_sqlite(mp14.dbpath(), "DecTableB6x6", "").col(0); d.show("d")
    d: 
    911, 
    921, 
    931, 
    941, 
    951, 
    961, 

    >>> # creates a square matrix with the coefficents of d1 on the diagonal.
    >>> D = d.as_diagonal(); D.show("D")
    D: 
    911,   0,   0,   0,   0,   0, 
      0, 921,   0,   0,   0,   0, 
      0,   0, 931,   0,   0,   0, 
      0,   0,   0, 941,   0,   0, 
      0,   0,   0,   0, 951,   0, 
      0,   0,   0,   0,   0, 961, 

    >>> A = ctx.read_from_sqlite(mp14.dbpath(), "DecTableA6x6", ""); A.show("A")
    A: 
    11, 12, 13, 14, 15, 16, 
    21, 22, 23, 24, 25, 26, 
    31, 32, 33, 34, 35, 36, 
    41, 42, 43, 44, 45, 46, 
    51, 52, 53, 54, 55, 56, 
    61, 62, 63, 64, 65, 66, 

    >>> C = A + D; C.show("C")    # same as D + A()
    C: 
     922,   12,   13,   14,   15,   16, 
      21,  943,   23,   24,   25,   26, 
      31,   32,  964,   34,   35,   36, 
      41,   42,   43,  985,   45,   46, 
      51,   52,   53,   54, 1006,   56, 
      61,   62,   63,   64,   65, 1027, 

    >>> C = A + d.diagonal_view(); C.show("C")    # same as d.diagonal_view + A()
    C: 
     922,   12,   13,   14,   15,   16, 
      21,  943,   23,   24,   25,   26, 
      31,   32,  964,   34,   35,   36, 
      41,   42,   43,  985,   45,   46, 
      51,   52,   53,   54, 1006,   56, 
      61,   62,   63,   64,   65, 1027, 



Matrix: addition of a scalar
-------------------------------------------------------------------------------

Returns the sum of matrix matA and scalar `b`, applied to each coefficient of matA. The coefficients of matA and `b` need to be of the same type. The returned matrix is of the same type as matA. Special rules apply for mixing real and complex matrices and real and complex scalars.


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
    >>> B = A + 15;  B.show("B")
    B: 
    26, 27, 28, 29, 30, 31, 
    36, 37, 38, 39, 40, 41, 
    46, 47, 48, 49, 50, 51, 
    56, 57, 58, 59, 60, 61, 
    66, 67, 68, 69, 70, 71, 
    76, 77, 78, 79, 80, 81, 




General matrix subtraction
-------------------------------------------------------------------------------


Returns the difference of matrix matA and matrix matB. matA and matB need to be of the same type and need to have the same dimensions. The returned matrix is of the same type as matA. Special rules apply for mixing real and complex matrices.


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
    >>> C = A - B; C.show("C")
    C: 
    -900, -900, -900, -900, -900, -900, 
    -900, -900, -900, -900, -900, -900, 
    -900, -900, -900, -900, -900, -900, 
    -900, -900, -900, -900, -900, -900, 
    -900, -900, -900, -900, -900, -900, 
    -900, -900, -900, -900, -900, -900, 





Matrix: subtraction of a scalar
-------------------------------------------------------------------------------


Returns the difference of matrix matA and scalar `b`, applied to each coefficient of matA. The coefficients of matA and `b` need to be of the same type. The returned matrix is of the same type as matA. Special rules apply for mixing real and complex matrices and real and complex scalars.


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
    >>> B = A - 15;  B.show("B")
    B: 
    -4, -3, -2, -1,  0,  1, 
     6,  7,  8,  9, 10, 11, 
    16, 17, 18, 19, 20, 21, 
    26, 27, 28, 29, 30, 31, 
    36, 37, 38, 39, 40, 41, 
    46, 47, 48, 49, 50, 51, 





General matrix multiplication ("gemm")
-------------------------------------------------------------------------------

See also Eigen :cite:p:`EigenMat100`.


In its general form, matrix multiplication takes the form `\boldsymbol{C} = \boldsymbol{A} \boldsymbol{B}`, where `\boldsymbol{A}` is a `m`-by-`k` matrix, `\boldsymbol{B}` is a `k`-by-`n` matrix, and `\boldsymbol{C}` is a `m`-by-`n` matrix. Also, the transposed or adjoined matrices of  `\boldsymbol{A}` and/or `\boldsymbol{B}` are often directly used.

In the general form, no information regarding special properties of `\boldsymbol{A}` and/or `\boldsymbol{B}` is used. If such information is available, specialized forms of multiplication are often signifantly faster:

* if `\boldsymbol{A}` or `\boldsymbol{B}` is a triangular or diagonal matrix, or 
* if the multiplication with the inverse of a square, triangular or diagonal matrix is desired, or
* if `\boldsymbol{B}` is the transpose of `\boldsymbol{A}`.


In the canonical FORTRAN package BLAS, the BLAS Level 3 function `\mathrm{?gemm}` and the BLAS Level 2 function `\mathrm{?gemv}` handle this kind of expression, with the scalars `\alpha` `\beta` and the indicator variables `\textsf{TransA}` and `\textsf{TransB}` as additional parameters:


.. math:: 
    \mathrm{?gemm}=\begin{cases}
        \alpha \boldsymbol{A} \boldsymbol{B} + \beta \boldsymbol{C}, & \text{for } \textsf{TransA = 'N', TransB = 'N'},\\
        \alpha \boldsymbol{A} \boldsymbol{B}^T + \beta \boldsymbol{C}, & \text{for } \textsf{TransA = 'N', TransB = 'T'},\\        
        \alpha \boldsymbol{A} \boldsymbol{B}^H + \beta \boldsymbol{C}, & \text{for } \textsf{TransA = 'N', TransB = 'C'},\\
        \alpha \boldsymbol{A}^T \boldsymbol{B} + \beta \boldsymbol{C}, & \text{for } \textsf{TransA = 'T', TransB = 'N'},\\
        \alpha \boldsymbol{A}^T \boldsymbol{B}^T + \beta \boldsymbol{C}, & \text{for } \textsf{TransA = 'T', TransB = 'T'},\\
        \alpha \boldsymbol{A}^T \boldsymbol{B}^H + \beta \boldsymbol{C}, & \text{for } \textsf{TransA = 'T', TransB = 'C'},\\
        \alpha \boldsymbol{A}^H \boldsymbol{B} + \beta \boldsymbol{C}, & \text{for } \textsf{TransA = 'C', TransB = 'N'},\\
        \alpha \boldsymbol{A}^H \boldsymbol{B}^T + \beta \boldsymbol{C}, & \text{for } \textsf{TransA = 'C', TransB = 'T'},\\
        \alpha \boldsymbol{A}^H \boldsymbol{B}^H + \beta \boldsymbol{C}, & \text{for } \textsf{TransA = 'C', TransB = 'C'},\\
    \end{cases}


.. math:: 
    \mathrm{?gemv}=\begin{cases}
        \alpha \boldsymbol{A} \boldsymbol{x} + \beta \boldsymbol{y}, & \text{for } \textsf{TransA = 'N'},\\
        \alpha \boldsymbol{A}^T \boldsymbol{x} + \beta \boldsymbol{y}, & \text{for } \textsf{TransA = 'T'},\\
        \alpha \boldsymbol{A}^H \boldsymbol{x} + \beta \boldsymbol{y}, & \text{for } \textsf{TransA = 'C'}.
    \end{cases}


We use the ``transpose()`` and ``adjoint()`` properties to compute these expressions efficiently.
Here are some examples with real matrices:

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
    >>> C = A * B; C.show("C")
    C: 
     75991,  76072,  76153,  76234,  76315,  76396, 
    132151, 132292, 132433, 132574, 132715, 132856, 
    188311, 188512, 188713, 188914, 189115, 189316, 
    244471, 244732, 244993, 245254, 245515, 245776, 
    300631, 300952, 301273, 301594, 301915, 302236, 
    356791, 357172, 357553, 357934, 358315, 358696, 

    >>> C = A.transpose() * B;  C.show("C")
    C: 
    203926, 204142, 204358, 204574, 204790, 205006, 
    209542, 209764, 209986, 210208, 210430, 210652, 
    215158, 215386, 215614, 215842, 216070, 216298, 
    220774, 221008, 221242, 221476, 221710, 221944, 
    226390, 226630, 226870, 227110, 227350, 227590, 
    232006, 232252, 232498, 232744, 232990, 233236, 

    >>> C = A * B.transpose();  C.show("C")
    C: 
     74011,  74821,  75631,  76441,  77251,  78061, 
    128821, 130231, 131641, 133051, 134461, 135871, 
    183631, 185641, 187651, 189661, 191671, 193681, 
    238441, 241051, 243661, 246271, 248881, 251491, 
    293251, 296461, 299671, 302881, 306091, 309301, 
    348061, 351871, 355681, 359491, 363301, 367111, 



Here are some examples with complex matrices:

.. code-block:: pycon


    >>> TName = "DecCplxTableA6x6"; Query = "where row<4 and col<4"
    >>> A = ctx.read_from_sqlite(mp14.dbpath(), TName, Query); A.show("A")
    A: 
    11 + 31j, 12 + 32j, 13 + 33j, 14 + 34j, 
    21 + 41j, 22 + 42j, 23 + 43j, 24 + 44j, 
    31 + 51j, 32 + 52j, 33 + 53j, 34 + 54j, 
    41 + 61j, 42 + 62j, 43 + 63j, 44 + 64j, 


    >>> TName = "DecCplxTableB6x6"; Query = "where row<4 and col<4"
    >>> B = ctx.read_from_sqlite(mp14.dbpath(), TName, Query); B.show("B")
    B: 
    45 + 7.5j, 2.9 + 36j,  11 + 13j,  37 + 37j, 
     13 + 29j,  38 + 41j,  22 + 44j,  28 + 20j, 
    32 + 9.0j,  42 + 49j,  47 + 11j,  32 + 49j, 
     34 + 42j, 6.0 + 16j,  20 + 38j,  22 + 17j, 

    >>> C = A.adjoint() * B;  C.show("C")
    C: 
    7596.5 - 2941.5j,  8649.9 - 723.9j,     7946 - 1894j,     8392 - 2226j, 
    7808.0 - 2978.0j,  8880.8 - 670.8j,     8152 - 1888j,     8634 - 2222j, 
    8019.5 - 3014.5j,  9111.7 - 617.7j,     8358 - 1882j,     8876 - 2218j, 
    8231.0 - 3051.0j,  9342.6 - 564.6j,     8564 - 1876j,     9118 - 2214j, 

    >>> C = B.adjoint() * A;  C.show("C")
    C: 
    7596.5 + 2941.5j, 7808.0 + 2978.0j, 8019.5 + 3014.5j, 8231.0 + 3051.0j, 
     8649.9 + 723.9j,  8880.8 + 670.8j,  9111.7 + 617.7j,  9342.6 + 564.6j, 
        7946 + 1894j,     8152 + 1888j,     8358 + 1882j,     8564 + 1876j, 
        8392 + 2226j,     8634 + 2222j,     8876 + 2218j,     9118 + 2214j, 


    >>> C = A * B.adjoint();  C.show("C")
    C: 
     4262.3 + 1907.3j,      5620 + 1634j,  5791.0 + 3459.0j,  4660.0 + 1268.0j, 
     6156.3 + 1931.3j,      7970 + 1304j,  8501.0 + 3809.0j,   6610.0 + 958.0j, 
     8050.3 + 1955.3j,      10320 + 974j, 11211.0 + 4159.0j,   8560.0 + 648.0j, 
     9944.3 + 1979.3j,      12670 + 644j, 13921.0 + 4509.0j,  10510.0 + 338.0j, 

    >>> C = B * A.adjoint();  C.show("C")
    C: 
     4262.3 - 1907.3j,  6156.3 - 1931.3j,  8050.3 - 1955.3j,  9944.3 - 1979.3j, 
         5620 - 1634j,      7970 - 1304j,      10320 - 974j,      12670 - 644j, 
     5791.0 - 3459.0j,  8501.0 - 3809.0j, 11211.0 - 4159.0j, 13921.0 - 4509.0j, 
     4660.0 - 1268.0j,   6610.0 - 958.0j,   8560.0 - 648.0j,  10510.0 - 338.0j, 








Arithmetic comparisons with a scalar or a matrix
-------------------------------------------------------------------------------


.. method:: ctx.mat_count(matA, query, comparator)


    Returns the number of coefficients in matrix matA which are greater than the corresponding coefficients in matrix matB.

    Writing ``matA.count(query, comparator)`` has the same effect.

    Queries are: ">, <, >=, <=, !=, ==", For complex matrices, the absolute values are compared 


    .. code-block:: pycon

        >>> from xlcalcnet import *
        >>> mpm.dps = 40;
        >>> A = mp14.xrf().read_from_sqlite(mp14.dbpath(), "MpfrTableA4x4", "")
        >>> B = mp14.xrf().read_from_sqlite(mp14.dbpath(), "MpfrTableB4x4", "")


