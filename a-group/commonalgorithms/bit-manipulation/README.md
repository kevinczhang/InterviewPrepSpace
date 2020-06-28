# Bit Manipulation

## **Bitwise Operators**

### **Basic operations**

$$N = 5 = (101)_2, A = 5 = (101)_2 $$ and$$B = 3 = (011)_2$$ 

#### **NOT \( ~ \)**

Bitwise NOT is an unary operator that flips the bits of the number i.e., if the ith bit is 0, it will change it to 1 and vice versa.

 $$\sim N = \sim 5 = \sim (101)_2 = (010)_2$$

 **AND \( & \)**

Bitwise AND is a binary operator that operates on two equal-length bit patterns. If both bits in the compared position of the bit patterns are 1, the bit in the resulting bit pattern is 1, otherwise 0.

$$
A\  \& \ B = (101)_2 \ \& \ (011)_2 = (001)_2 = 1
$$

 **OR \( \| \)**

**I**f both bits in the compared position of the bit patterns are 0, the bit in the resulting bit pattern is 0, otherwise 1.

$$
A | B = (101)_2 | (011)_2 = (111)_2 = 7
$$

 **XOR \( ^ \)**

Bitwise XOR also takes two equal-length bit patterns. If both bits in the compared position of the bit patterns are 0 or 1, the bit in the resulting bit pattern is 0, otherwise 1.

$$
A\ ^ {\wedge} \ B = (101)_2 \ ^ {\wedge} \  (011)_2=(110)_2 = 6
$$

### Arithmetic vs. Logical Right Shift

#### Logical right shift

Shift the bits and put a 0 in the most significant bit which is the sign bit. It is indicated with &gt;&gt;&gt; operator.

$$
-75 >>> 1 = (10110101)_2  >>> 1 = (01011010) = 90
$$

#### Arithmetic right shift

Shift values to the right but fill in the new bits with the value of the sign bit. This has the effect of \(roughly\) dividing by two. It is indicated by a &gt; &gt; operator.

$$
-75 >> 1 = (10110101)_2  >> 1 = (11011010) = -38
$$

