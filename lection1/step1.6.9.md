Реализуйте функцию, находящую значение определённого интеграла от заданной функции ff на заданном интервале [a,b][a,b] методом трапеций. (Используйте равномерную сетку; достаточно 1000 элементарных отрезков.)

integration :: (Double -> Double) -> Double -> Double -> Double
integration f a b = undefined
GHCi> integration sin pi 0
-2.0
Результат может отличаться от -2.0, но не более чем на 1e-4.

Answer:

integration :: (Double -> Double) -> Double -> Double -> Double
integration f a b | a == b = 0
                  | a > b = -integration f b a
                  | otherwise = h * (((f a) + (f b))/2 + sum f a b h) where
                  	h = (b - a) / 1000
                        sum f a b h = if (a + h) < b - h/2 then f (a + h) + sum f (a + h) b h else 0
