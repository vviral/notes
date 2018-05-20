Karatsuba Multiplication
========================

Existing Problem
----------------

- Standard Multiplication Algorithm is Time Consuming **O(n^2)**

- Standard Algoritm is **Complex for larger length numbers** (n>10)

Karatsuba Algorithm
-------------------

**Initial Values**::

  n := 4(digit)
  x := 5678
  y := 1234

  lets divide numbers in a,b,c,d i.e

  x := a[56]b[78]
  y := c[12]d[34]

  x := (10^(n/2))a + b
  y := (10^(n/2))c + d

**Formula**::

  x*y = ((10^(n/2))a + b) * ((10^(n/2))c + d)
      = ((10^n)ac) + ((10^(n/2))ad) + ((10^(n/2))bc) + bd
      = ((10^n)ac) + ((10^(n/2))( ad + bc )) + bd

There are 4 multiplication we need to search i.e **ac, ad, bc, bd**, We can compute ad + bc by following formula

::

  (a + b)(c + d) = ac + ad + bc + bd
  ad + bc = ((a + b)(c + d)) - ac - bd

So Finally we need max 3 multiplication for finding actual result
i.e **((a + b)(c + d)), ac and bd**

**Final Formula**::

  x*y = ((10^n)ac) + ((10^(n/2))(((a + b)(c + d)) - ac - bd)) + bd


Example
-------

**Initial Values**::

  n := 4(digit)
  x := 5678
  y := 1234

  lets divide numbers in a,b,c,d i.e

  x := a[56]b[78]
  y := c[12]d[34]
  x = 5600 + 78 (a=56, b=78)
  y = 1200 + 34 (c=12, d=34)

**Terms**::

  (a + b)(c + d) = (56 + 78) * (12 + 34) = 134 * 46 = 6164
  ac = 56 * 12 = 672
  bd = 78 * 34 = 2652


**Result**::

  x*y = ((10^n)ac) + ((10^(n/2))(((a + b)(c + d)) - ac - bd)) + bd
      = (10^4)672 + (10^2)(6164 - 672 - 2652) + 2652
      = 6720000 + 284000 + 2652
      = 7006652

Analysis
--------

Advantages
----------

Conclusion
----------

References
----------
[1] Karatsuba Algorithm
