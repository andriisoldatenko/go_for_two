Note #9 Когда лучше использовать именнованые параметры в функциях, определеных в интерфейсах?

Ели нам попадается такой код, то не совсем понятно что такое `str` или `int` O_O:

```
type runner interface {
 run(context.Context, string, int)
}
```

Сразу же последует PR с чем-то вроде такого:

```
2c2
<  run(context.Context, string, int)
---
>  run(ctx context.Context, service string, instances int)
4d3
<
```
Так намного лучше :)

Но иногда есть более спорный кейс, в котором называть не объязательно:
```
type Enroller interface {
  Enroll(*User, *Course) error
}
```

```
// P.S.
func main(){println("не забываем, что код пишется, еще и для наших коллеги, а не только для того, чтобы его можно было запустить на проде!")}
```
🍺