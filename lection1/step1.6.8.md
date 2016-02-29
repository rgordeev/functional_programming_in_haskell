Реализуйте функцию, находящую сумму и количество цифр заданного целого числа.

```haskell
sum'n'count :: Integer -> (Integer, Integer)
sum'n'count x = undefined
```

```
GHCi> sum'n'count (-39)
(12,2)
Time Limit: 5 seconds
Memory Limit: 256 MB
```

Answer:

```haskell
sum'n'count :: Integer -> (Integer, Integer)
sum'n'count n | n == 0 = (0,1)
              | n < 0  = sum'n'count (-n)
              | otherwise = h n 0 0 where
                 h n s k | n == 0 = (s,k)
                         | otherwise = h (div n 10) (s + mod n 10) (k+1)
```
