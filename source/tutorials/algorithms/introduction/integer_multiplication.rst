Integer Multiplication
======================

Integer Multiplication Algorithm
--------------------------------

Example:

::

  X : 5678
  Y : 1234

  X*Y     5678
        * 1234
  ------------
         22712 C[3320]
        17034- C[2220]
       11356-- C[1110]
       5678--- C[0000]
  ------------
       7006652 C[0011210]

Analysis
--------

**Basic Operation**

- Single Digit Multiplication

- MultiDigit Addition will be basic operation

**Total Basic Operation**

Size of Number : n=len(number) => n=4

======== =================== ============= =================
Line     #Max Multiplication #Max Addition #Total Operations
======== =================== ============= =================
A:5678*4 n ie.4              n ie. 4       2n * 1
B:5678*3 n ie.4              n ie. 4       2n * 2
C:5678*2 n ie.4              n ie. 4       2n * 3
D:5678*1 n ie.4              n ie. 4       2n * 4 i.e 2n*n
A+B+C+D  --                   n-1           2(n^2) + (n-1)
======== =================== ============= =================

Note:Addition of A+B+C+D will be successive.

Conclusion
----------

For Multiplication of **two n digit number** will take 2(n^2) + (n-1) operations.

Taking Upperbound : O(2(n^2) + (n-1)) => **O(n^2)**
