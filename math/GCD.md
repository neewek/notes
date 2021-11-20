[GCD](http://www-math.ucdenver.edu/~wcherowi/courses/m5410/exeucalg.html)

 The gcd of two integers can be found by repeated application of the division algorithm, this is known as the Euclidean Algorithm. You repeatedly divide the divisor by the remainder until the remainder is 0. The gcd is the last non-zero remainder in this algorithm. The following example shows the algorithm.

Finding the gcd of 81 and 57 by the Euclidean Algorithm:

```
81 = 1(57) + 24

57 = 2(24) + 9

24 = 2(9) + 6

9 = 1(6) + 3

6 = 2(3) + 0.
```

It is well known that if the gcd(a, b) = r then there exist integers p and s so that:
p(a) + s(b) = r.
By reversing the steps in the Euclidean Algorithm, it is possible to find these integers p and s. We shall do this with the above example:

Starting with the next to last line, we have:
From the line before that, we see that 6 = 24 - 2(9), so:
From the line before that, we have 9 = 57 - 2(24), so:
And, from the line before that 24 = 81 - 1(57), giving us:
So we have found p = -7 and s = 10.

```
3 = 9 -1(6)

3 = 9 - 1(24 - 2(9)) = 3(9) - 1(24).

3 = 3( 57 - 2(24)) - 1(24) = 3(57) - 7(24).

3 = 3(57) - 7( 81 - 1(57)) = 10(57) -7(81).
```
