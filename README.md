Это шаблон для проектов написанных на go

# Структура проекта
Если приложение является малым, то разрешается использовать плоскую стрктуру,
т. е. такую, при которой все файлы лежат в корне проекта. Типично для микросервисов.

Если приложение имеет средние размеры, то лучше всего использовать иерархическую структуру,
пример которой приведен в данном репозитории.

/*
Также данный шаблон подразумевает что проект находится в папке `GOPATH/src/github.com/`.
Это удобнее всего с точки зрения интеграции с IDE.

Пути импорта пишутся полными, относительно `GOPATH/src`, как показано в `main.go`.
*/

С версии go 1.16 GOPATH отрубили, теперь проект должен использовать модули, для этого необходимо
включить в goland интеграцию с модулями и ввести в консоли в корне проекта следующее:
- go mod init - инициализирует файл модуля
- go mod tidy - заполняет его используемыми зависимостями

В файле go.mod на первой строке указывается название проекта, оно должно быть:
github.com/user_name/repo_name

Не должно быть никаких папок `src` и смежных с ним

Названия пакетов должны быть:
- короткими и что-то значащими (избегать названий вроде `utils`)
- в единственном числе `httputils` -> `httputil`

# Что можно настроить в goland ide
Для того чтобы проще кодилось, можно поднастроить следующие фишки:
- gofmt при сохранении. https://www.jetbrains.com/help/go/integration-with-go-tools.html#gofmt
- goimports при сохранении. https://www.jetbrains.com/help/go/integration-with-go-tools.html#goimports
