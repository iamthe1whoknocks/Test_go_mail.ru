# Test_go_mail.ru
Тестовое задание на позицию go developer в компанию Mail.ru Group


Процессу на stdin приходят строки, содержащие интересующие нас URL. Каждый такой URL нужно дернуть и посчитать кол-во вхождений строки "Go" в ответе. В конце работы приложение выводит на экран общее кол-во найденных строк "Go" во всех запросах, например:

```
$ echo -e 'https://golang.org\nhttps://golang.org\nhttps://golang.org' | go counter.go
Count for https://golang.org: 9
Count for https://golang.org: 9
Count for https://golang.org: 9
Total: 27
```

Введенный URL должен начать обрабатываться сразу после вычитывания и параллельно с вычитыванием следующего.
URL должны обрабатываться параллельно, но не более k=5 одновременно. Обработчики url-ов не должны порождать лишних горутин,
 т.е. если k=1000 а обрабатываемых URL-ов нет, не должно создаваться 1000 горутин.
Нужно обойтись без глобальных переменных и использовать только стандартные библиотеки.

Поддерживает ключи:
k - количество горутин обрабатывающих урлы (по дефолту 5)
q - поисковое слово (по дефлоту go)
