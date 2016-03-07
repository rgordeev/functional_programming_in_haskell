Реализуйте класс типов ```Printable```, предоставляющий один метод ```toString```
— функцию одной переменной, которая преобразует значение типа, являющегося представителем ```Printable```,
в строковое представление.

Сделайте типы данных ```Bool``` и ```()``` представителями этого класса типов, обеспечив следующее поведение:
```
GHCi> toString True
"true"
GHCi> toString False
"false"
GHCi> toString ()
"unit type"
```

Answer:

```haskell
class Printable a where
  toString :: a -> String

instance Printable Bool where
  toString True = "true"
  toString False = "false"

instance Printable () where
  toString _ = "unit type"
```