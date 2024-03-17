There are 2 problems in this code:

1. The word `entry` is reserved as a keyword in K&R C, but is no longer reserved since K&R2.
2. The digits 8 and 9 are permitted as octal digits in K&R C, but are forbidden in K&R2.

Since there is no C version in which this code is legal - the answer is no.
