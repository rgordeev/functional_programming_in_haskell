Что произойдет при попытке загрузить данный модуль в GHCi?
```haskell
module Test where
import Data.List hiding (union)
import Data.Set

myUnion [] ys = ys
myUnion xs ys = union xs ys
```

Answer:

```
Произойдет ошибка из-за неопределенности при выборе функции
* Произойдет ошибка из-за несовпадения типа аргумента и ожидаемого типа функции
Все пройдет нормально
```