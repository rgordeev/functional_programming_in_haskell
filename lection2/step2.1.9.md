Реализуйте функцию on3, имеющую семантику, схожую с on, но принимающую в качестве первого аргумента трехместную функцию:

```haskell
on3 :: (b -> b -> b -> c) -> (a -> b) -> a -> a -> a -> c
on3 op f x y z = undefined
```

Например, сумма квадратов трех чисел может быть записана с использованием on3 так

```
GHCi> let sum3squares = (\x y z -> x+y+z) `on3` (^2)
GHCi> sum3squares 1 2 3
14
```

Answer:

```haskell
on3 :: (b -> b -> b -> c) -> (a -> b) -> a -> a -> a -> c
on3 op f x y z = op (f x) (f y) (f z)
```