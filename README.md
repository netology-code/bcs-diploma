# Дипломный проект по курсу «Basic C#»

Работа выполняется и сдается в [repl.it](https://repl.it)

---

Необходимо разработать консольное приложение для создания и управления заметками.

Заметка представляет из себя объект с тремя полями:

- текст заметки
- дата и время создания заметки
- дата и время последнего изменения заметки

Команды, которые должно уметь выполнять приложение:

- `help` - **Показать справку** - вывести список всех доступных команд на экран
- `print` - **Вывести заметки на экран** - вывести все заметки на экран
- `add` - **Добавить заметку** - добавить новую заметку
- `edit` - **Изменить текст заметки** - изменить текст выбранной заметки
- `delete` - **Удалить заметку** - удалить выбранную заметку
- `save` - **Сохранить заметки в файл** - сохранить все текущие заметки в файл
- `quit` - **Выход** - закончить работу с программой

При запуске программы должна производиться попытка загрузки заметок из файла (этот файл появляется в момент сохранения с помощью команды `save`).

 **Проверьте, что приложение работает корректно в следующих ситуациях:**

- ввели недопустимую команду.
- ввели команду `edit` и затем любое слово.
- ввели команду `edit` и затем отрицательное число.
- ввели команду `edit` и затем 0.
- ввели команду `edit` и затем положительное число, большее количества заметок.
- ввели команду `delete` и затем любое слово.
- ввели команду `delete` и затем отрицательное число.
- ввели команду `delete` и затем 0.
- ввели команду `delete` и затем положительное число, большее количества заметок.
- ввели команду `save`.
- запустили программу без файла с заметками.
- запустили программу, а в файлах с заметками "поломанные" данные.

### Пример "поломанных" данных:

```
fdgdjf
1234234|123
```

---

## Примеры работы программы:

### Пример 1

```
Загрузка данных...
Ошибка: файл с данными не найден
Добро пожаловать в лучший сервис заметок!
help   - Показать справку
print  - Вывести заметки на экран
add    - Добавить заметку
edit   - Изменить текст заметки
delete - Удалить заметку
save   - Сохранить заметки в файл
quit   - Выход

Введите команду: add
Введите текст заметки: Test

Введите команду: save
Сохранение успешно выполнено

Введите команду: add
Введите текст заметки: Some note

Введите команду: print
№   | Время создания                        | Последнее обновление                  | Текст
1   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:43 PM    | Test
2   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:43 PM    | Some note

Введите команду: save
Сохранение успешно выполнено

Введите команду: edit
№   | Время создания                        | Последнее обновление                  | Текст
1   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:43 PM    | Test
2   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:43 PM    | Some note
Введите номер заметки, которую необходимо изменить: 1
Введите новый текст заметки: Test -> Test 2

Введите команду: print
№   | Время создания                        | Последнее обновление                  | Текст
1   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:44 PM    | Test -> Test 2
2   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:43 PM    | Some note

Введите команду: save
Сохранение успешно выполнено

Введите команду: quit
Приходите ещё ;)
```

### Пример 2

```
Загрузка данных...
Данные загружены успешно
Добро пожаловать в лучший сервис заметок!
help   - Показать справку
print  - Вывести заметки на экран
add    - Добавить заметку
edit   - Изменить текст заметки
delete - Удалить заметку
save   - Сохранить заметки в файл
quit   - Выход

Введите команду: print
№   | Время создания                        | Последнее обновление                  | Текст
1   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:44 PM    | Test -> Test 2
2   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:43 PM    | Some note

Введите команду: edit
№   | Время создания                        | Последнее обновление                  | Текст
1   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:44 PM    | Test -> Test 2
2   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:43 PM    | Some note
Введите номер заметки, которую необходимо изменить: 2
Введите новый текст заметки: New text in note

Введите команду: print
№   | Время создания                        | Последнее обновление                  | Текст
1   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:44 PM    | Test -> Test 2
2   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 2:28 PM    | New text in note

Введите команду: delete
№   | Время создания                        | Последнее обновление                  | Текст
1   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 1:44 PM    | Test -> Test 2
2   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 2:28 PM    | New text in note
Введите номер заметки, которую необходимо удалить: 1

Введите команду: print
№   | Время создания                        | Последнее обновление                  | Текст
1   | Tuesday, September 8, 2020 1:43 PM    | Tuesday, September 8, 2020 2:28 PM    | New text in note

Введите команду: exit
Неопознанная команда!

Введите команду: quit
Приходите ещё ;)
```

## Советы

1. Удобно сделать заметку классом.
2. При создании заметки удобно заполнять поле _дата и время создания заметки_
3. При изменении текста заметки удобно обновлять поле _дата и время последнего изменения заметки_
4. При сохранении заметок рекомендуется вести запись через разделитель, например `|`, в одну строку:

```cs
$"{CreatedAt.Ticks}|{UpdatedAt.Ticks}|{Text}"
```

поля создания и обновления удобно хранить в виде "тиков" - количество тактов от 1 января 2000 года. Каждый такт равен 100 наносекундам ([документация](https://docs.microsoft.com/ru-ru/dotnet/api/system.datetime.ticks?view=netcore-3.1)). Чтобы обратно из "тиков" получить `DateTime` - достаточно просто сконструировать объект:

```cs
long ticks = Convert.ToInt64(Console.ReadLine());
DateTime dt = new DateTime(ticks);
```

5. Путь к файлу, в который сохраняются заметки и из которого загружаются, удобно сделать в виде переменной класса `Program`:

```cs
class Program
{
  static string filename = "notes.txt";
  // ...
}
```

## Как правильно задавать вопросы дипломному руководителю?

**Что следует делать, чтобы все получилось:**

- Попробовать найти ответ сначала самому в интернете. Ведь именно этот скилл поиска ответов пригодится тебе на первой работе. И только после этого спрашивать дипломного руководителя.
- В одном вопросе должна быть заложена одна проблема.
- По возможности, прикреплять к вопросу скриншоты и стрелочкой показывать где не получается. Программу для этого можно скачать здесь https://app.prntscr.com/ru/.
- По возможности, задавать вопросы в комментариях к коду.
- Начинать работу над дипломом как можно раньше! Чтобы было больше времени на правки.
- Делать диплом по-частям, а не все сразу. Иначе, есть шанс, что нужно будет все переделывать :)

**Что следует делать, чтобы ничего не получилось:**

- Писать вопросы вида "Ничего не работает. Не запускается. Всё сломалось...".
- Откладывать диплом на потом.
- Ждать ответ на свой вопрос моментально. Дипломные руководители - работающие разработчики, которые занимаются, кроме преподавания, своими проектами. Их время ограничено, поэтому постарайтесь задавать правильные вопросы, чтобы получать быстрые ответы!
