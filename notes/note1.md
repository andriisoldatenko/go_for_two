Note #2

🐛Дебажим код написанный на Go


Да код на Go можно и нужно дебажить. Часто сталкиваюсь в разных командах, как разработчики, до сих пор в 2019 году! дебажат принтами :)

Delve - дебаггер который я обычно использую каждый день.  Если открыть документацию, она мягко говоря не идеальная.


Установить можно так: go get -u github.com/go-delve/delve/cmd/dlv
Чаще всего я использую `dlv debug <имя пакета>`. 

`dlv debug github.com/andriisoldatenko/go-blog`

Либо

dlv debug main.go
(dlv) breakpoint main.go:1
(dlv) continue

После того как установили breakpoint, можно нажать continue и программа остановится там где нужно и так далее. Также есть shortcuts (`b`, `c`, `l` и так далее).

Note # _ Дебажим тест/тесты:

dlv test -- -test.run NameOfYourTest

Те как вы заметили можно передавать параметры которые принимает go test в dlv test.