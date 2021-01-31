## JavaFraction
A wrapper module that handles fractions using `BigInteger`.

### Constructor
Constructs a `Fraction` instance. Takes either two `int` variables, two `BigInteger` instances, two `Fraction` instances, or a `BigDecimal` instance.
```java
// construct a new fraction using integers -> "1/2"
Fraction f1 = new Fraction(1, 2);
// construct a new fraction using BigIntegers -> "1/2"
Fraction f2 = new Fraction(BigInteger.valueOf(1), BigInteger.valueOf(2));
// construct a new fraction using Fractions -> "1/2"
Fraction f3 = new Fraction(new Fraction(1, 1), new Fraction(2, 1));
// construct a new fraction using BigDecimal -> "1/2"
Fraction f4 = new Fraction("0.5");
```

#### .multiply()
Returns a new `Fraction` instance that is the product of the multiplicand and the multiplier.
```java
Fraction f1 = new Fraction(1, 2); // -> 1/2
Fraction f2 = new Fraction(1, 5); // -> 1/5
Fraction product = f1.multiply(f2); // returns -> 1/10
```

#### .divide()
Returns a new `Fraction` instance that is the quotient of the dividend and the divisor.
```java
Fraction f1 = new Fraction(1, 2); // -> 1/2
Fraction f2 = new Fraction(1, 5); // -> 1/5
Fraction quotient = f1.divide(f2); // returns -> 5/2
```

#### .add()
Returns a new `Fraction` instance that is the sum of the two addends.
```java
Fraction f1 = new Fraction(1, 2); // -> 1/2
Fraction f2 = new Fraction(1, 5); // -> 1/5
Fraction sum = f1.add(f2); // returns -> 7/10
```

#### .subtract()
Returns a new `Fraction` instance that is the difference between the minuend and the subtrahend.
```java
Fraction f1 = new Fraction(1, 2); // -> 1/2
Fraction f2 = new Fraction(1, 5); // -> 1/5
Fraction difference = f1.subtract(f2); // returns -> 3/10
```

#### .getReciprocal()
Returns a new `Fraction` instance that is the reciprocal of the fraction.
```java
Fraction f1 = new Fraction(1, 2); // -> 2/3
Fraction reciprocal = f1.getReciprocal(f1); // returns -> 3/2
```

#### .getString()
Returns the fraction in `string` form.  If the denominator = 1, returns only the numerator.
```java
Fraction f1 = new Fraction(1, 2); // -> 1/2
Fraction s1 = f1.getString(); // returns -> "1/2"

Fraction f2 = new Fraction(5, 1); // -> 5/1
Fraction s2 = f2.getString(); // returns -> "5"
```

#### .getGCD()
Returns a `BigInteger` that is the greatest common denominator of 'a' and 'b' using Euclid's algorithm. Used by `.reduce()` to get the greatest common denominator between the numerator and denominator.
```java
Fraction f = new Fraction(1, 2);
BigInteger gcd = f.getGCD(10, 20); // -> returns 10
```

#### .reduce()
Reduces fraction to lowest terms. Used by the `Fraction` constructor to reduce reducible fractions.

#### .isEqualTo()
Checks if fractions are equal. Returns a boolean.

```java
Fraction f1 = new Fraction(1, 2);
Fraction f2 = new Fraction(1, 2);
Fraction f3 = new Fraction(1, 5);

f1.isEqualTo(f2); // -> returns true
f1.isEqualTo(f3); // -> returns false
```
