Будем задавать точки на плоскости парами типа
```
(Double, Double).
```
Реализуйте функцию dist, которая возвращает расстояние между двумя точками, передаваемыми ей в качестве аргументов.

```haskell
dist :: (Double, Double) -> (Double, Double) -> Double
dist p1 p2 = ???
```

Answer:

```haskell
dist :: (Double, Double) -> (Double, Double) -> Double
dist x y = sqrt ((fst x - fst y)^2 + (snd x - snd y)^2)
```