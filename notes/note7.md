Note #7  О стилистике Decode//UnMarshal 🐣

Недавно в твиттере возник вопрос, что лучше писать:


```
// Option A
var v T
v.Decode(someData)
```

Или так:
```
Option B
func (t *T) Decode(data []byte) {
  // decode data into *t
}
```


На самом деле все зависит от контекста, а именно вариант В) или использование метода вместо функции - позволяет типам удовлетворять интерфейсам, т.е другими словами, если у вас есть где-то ` type Decoder interface{ Decode([]byte) error }`,
Если такого типа нет, оба варианта подойдут и как все знают на вкус и цвет фломастеры разные, хотя второй вариант более универсальный кмк.

Пару ссылок:
- Интересный [gist](https://gist.github.com/egonelbre/7aebdfdf9d8f5483b6064b175b7b673b) о том как можно приводить типы между источниками
- Дока о том, что Decode - это обычно выражает Unmarshal  [BinaryUnmarshaler](https://golang.org/pkg/encoding/#BinaryUnmarshaler)
