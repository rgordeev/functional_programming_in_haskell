Реализуйте функцию seqA, находящую элементы следующей рекуррентной последовательности

a0=1;a1=2;a2=3;ak+3=ak+2+ak+1−2ak.

Попытайтесь найти эффективное решение.

GHCi> seqA 301
1276538859311178639666612897162414

Answer:

seqA :: Integer -> Integer
seqA n | n == 0 = 1
       | n == 1 = 2
       | n == 2 = 3
       | otherwise = h n 1 2 3

h :: Integer -> Integer -> Integer -> Integer -> Integer
h n a b c | n <= 2 = c
          | otherwise = h (n-1) b c (c + b - 2*a)
