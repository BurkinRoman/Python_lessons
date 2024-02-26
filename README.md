# Уроки Python
*Данный readme содержит шпаргалки по языку Python*

***Содержание***

0. [Введение](#0-введение)
1. [Комментарии](#1-комментарии)
2. [Типы данных](#2-типы-данных)
3. [Интерполяция или f-строки](#3-интерполяция-или-f-строки)
4. [Консольный ввод и вывод данных](#4-консольный-ввод-и-вывод-данных)
5. [Приведение типов](#5-приведение-типов)
6. [Математические операторы и функции](#6-математические-операторы-и-функции)
7. [Логические операторы](#7-логические-операции)
8. [Условные конструкции (ветвление)](#8-условные-конструкции-ветвление)
9. [Циклы](#9-циклы)
10. [Строки](#10-строки)
11. [Списки](#11-списки)
12. [Кортежи](#12-кортежи)
13. [Словари](#13-словари)
14. [Множества](#14-множества)
15. [Функции](#15-функции)
16. [Работа с файлами](#16-работа-с-файлами)
17. [Модуль ОС](#17-модуль-ос)
18. [Модуль shutil](#18-модуль-shutil)
99. [Распространенные ошибки](#распространенные-ошибки)

## 0. Введение 
Разрешение файла ".py" \
Язык Python требователен к отступам (по умолчанию 4) не рекомендовано менять\
Полезные плагины для VSCode:
1. Python (Microsoft)
2. 


## 1. Комментарии
\# - однострочный комментарий

""" """ - многострочный комментрий

## 2. Типы данных
* int - Натуральные числа
* float - вещественные числа
* bool - булев тип (True, False) - С большой буквы
* str - строка (в одинарных '' или двойных "" ковычках)
* list - список (упорядоченный конечный набор элементов)
* tuple - кортеж (неизменяемый список. Работает быстрее, защищает данные)
* dict - словарь (неупорядоченные коллекции произвольных объектов с доступом по
ключу)
* set - множества
* Проверка типа данных `type()`

***Для присвоения пустого значения используется:*** `None`
Например `num = None`

## 3. Интерполяция или f-строки
Синтаксис: `print(f"{a} - {b} - {c}")` \
Альтернатива: \
`print("{} - {} - {}".format(a,b,c))`

## 4. Консольный ввод и вывод данных
`input("Можно использовать запрос тут")` - получает сроку в качестве ответа \
`print()` - можно писать через запятую много переменных

Использование функции print() вместе с оператором ‘ * ‘ \
Для вывода элементов списка без скобок.

## 5. Приведение типов
Пишем названия типа данных и в скобки вставляем значение для преобразования (может быть или значение или переменная):
```python
a = '5'
b = int(a)
```
## 6. Математические операторы и функции
```
+	сложение
—	вычитание
*	умножение
/	деление
%	остаток от деления
**	возведение в степень
//	целочисленное деление
```

```python
round([arg], ['кол-во символов после запятой']) # Округление
ads(-5) # Модуль числа

```
## 7. Логические операции
```
==	равно
!=	не равно
>	больше
<	меньше
>=	больше или равно
<=	меньше или равно
and	логическое И
or	логическое ИЛИ
not	логическое НЕ
```
## 8. Условные конструкции (ветвление)
Проверка работает до первого совпадения. Т.е. в преведенном примере ниже если a > b, то код в elif и в else не выполняется. \
<span style="color: red">Не забываем про отступы и двоеточия!</span>

```python
if a > b:
    print(a)
elif a == 0:
    print(0)
else:
    print(b)
```

## 9. Циклы
***While*** - данный цикл удобен при работе только со внешним флагом (внешней переменной). \
<span style="color: yellow">Так же именно его используют когда нужен бесконечный цикл, но с бесконечными ***будь аккуратен, можно повесить среду разработки***</span>

```python
flag = True
i = 2 
while flag:
    if n % i == 0: #если остаток при делении числа n на і равен 0
        flag = False
        print (i)
    elif i › n // 2: # делить числа не может превышать введенное число, деленное на 2
        print(n)
        flag = False
    i += 1
```
***for*** - Более универсальный цикл. Отлично подходит когда мы знаем количество итерируемых элементов. 
```python
for i in 3, 6, -10, 345, 24:
    #Действия для каждой итерации. В данном случае i принимает значения из списка
```
***Часто используется с функцией `range`***
```python
range(['Старт=0'], ['Конец не включая'], ['Шаг=1'])
```

## 10. Строки
По логике строка - это аналог списка символов, а значит можно использовать такой же подход в работе с ними. \
<span style="color: yellow">Не все возможности списков будут доступны в строках</span>

```python
Можно обращаться как к элементам массива `str[0]`
len(str) # Длина строки
print('ещё' in text) # Поиск "еще" в переменной text
print(text.lower()) # Преобразование к нижнему регистру
print(text.upper()) # Преобразование к верхнему регистру
print(text.replace("ещё', 'ЕЩЁ")) # Замена строки на другую
print("12, 21, 54, 34".split(", ")) # Преобразование в список


#####################################################
                        Срез
#####################################################
[:] - Срез. Может принимат от 1 до 3 аргументов, например:
text = "Hello"
print(text[:]) # Выведет все
print(text[:2]) # Выведет начиная с 0 индекса до 2 (не включая 2)
print(text[2:]) # Выведет начиная с 2 индекса до последнего
print(text[2:4]) # Выведет начиная с 2 индекса до 4 (не включая 4)
print(text[::6 ]) # Каждый 6 с 0 до последнего
```

## 11. Списки

Список - это упорядоченный конечный набор элементов. Давайте разбираться, по сути список - это тот же самый массив, в котором можно хранить элементы любых типов данных.
```python
list_1 = [] # Пустой список
list_2 = list() # Пустой список
list_3 = [7, 9, 11, 13, 15, 171]
print(list_3) # [7, 9, 11, 13, 15, 171]
print(*list_3) # 7 9 11 13 15 171
print(len(list_1)) # Длина списка

list_3.append(9) # Добавление в конец списка нового элемента
list_3.pop() # Извлекает (возвращает) последний элемент списка
list_3.pop(['индекс удаляемого элемента']) # Извлекает (возвращает) выбранный по индексу элемент списка
list_3.insert(['Индекс позиции для вставки'], ['элемент для вставки']) # Добавление элементов в массив
list_3[2:] # Срез, работает так же как и в сроках (см. работа со строками)
``` 
***List comprehension*** — это упрощенный подход к созданию списка, который задействует цикл for, а также инструкции if-else для определения того, что в итоге окажется в финальном списке.

```python
list_1 = [exp for item in iterable] # Простая ситуация—список
list_1 = [exp for item in iterable (if conditional)] # Выборка по заданному условию

# Создать список чисел от 1 до 100
list_1 = []
for i in range(1, 101):
list_1.append(i) print(list_1) # [1, 2, 3,..., 100]
# Альтернатива:
list_1 = [i for i in range(1, 101)] # [1, 2, 3,..., 100]

# Добавить условие (только чётные числа)
list_1 = [i for i in range(1, 101) if i % 2 == 0] # [2, 4, 6,..., 100]

# Также можно умножать, делить, прибавлять, вычитать. Например, умножить значение на 2.
list_1 = [i * 2 for i in range(10) if i % 2 == 0] print(list_1) # [0, 4, 8, 12, 16]
```

## 12. Кортежи
Кортеж — это неизменяемый список. \
В случае защиты каких-либо данных от изменений (намеренных или случайных). Кортеж занимает меньше места в памяти и работают быстрее, по сравнению со списками
```python
cort_1 = () # Пустой кортеж
cort_2 = (1,2,3,4,5)
# Можно распаковать кортеж в независимые переменные:
t = tuple(['red', 'green', 'blue'])
red, green, blue = t
print('r:{} g:{} b:{}'.format(red, green, blue)) # r:red g:green b:blue
```

## 13. Словари
Словари — неупорядоченные коллекции произвольных объектов с доступом по ключу. \
<span style="color: yellow">В других языках назвается объектом</span> \
В списках в качестве ключа используется индекс элемента. В словаре для определения элемента используется значение ключа (строка, число).

```python
dictionary = {} # Пусто словарь
dictionary ={ # Запись в столбец делает код более читабельным.
    'up': '↑',
    'left': '←',
    'down': '↓',
    'right': '→'}

# Поиск ключа по значению, используя понимание списка
students = {
    "Alice": "A",
    "Bob": "B",
    "Charlie": "C",
    "Dave": "B",
    "Eve": "A"
}

target_grade = "B"

keys = [key for key in students if students[key] == target_grade]
print("Keys with target grade:", keys)

# Поиск ключа по значению с помощью list.index()
students = {
    "Alice": "A",
    "Bob": "B",
    "Charlie": "C",
    "Dave": "B",
    "Eve": "A"
}

target_grade = "B"

keys = list(students.keys())
index = list(students.values()).index(target_grade)
key = keys[index]

print("Key with target grade:", key)

# Поиск ключа по значению с помощью dict.item()
students = {
    "Alice": "A",
    "Bob": "B",
    "Charlie": "C",
    "Dave": "B",
    "Eve": "A"
}

target_grade = "B"

keys = [key for key, value in students.items() if value == target_grade]

print("Keys with target grade:", keys)

# Поиск ключа по значению с помощью лямбда-выражения и filter()
students = {
    "Alice": "A",
    "Bob": "B",
    "Charlie": "C",
    "Dave": "B",
    "Eve": "A"
}

target_grade = "B"

keys = list(filter(lambda key: students[key] == target_grade, students))

print("Keys with target grade:", keys)

# Поиск ключа по значению с помощью модуля re
import re

# Заданный входной словарь с оценками студентов
students = {
    "Alice": "A",
    "Bob": "B",
    "Charlie": "A+",
    "David": "B+",
    "Eve": "C"
}

# Значение для поиска
value = "B"

# Создание регулярного выражения для точного совпадения значения
pattern = re.compile(r'\b' + re.escape(value) + r'\b')

# Поиск ключа по значению с использованием модуля re
key = next((k for k, v in students.items() if pattern.search(v)), None)

# Вывод результата
if key:
    print("Ключ по значению", value, "найден:", key)
else:
    print("Ключ по значению", value, "не найден")

```
## 14. Множества
Множества содержат в себе уникальные элементы, не обязательно упорядоченные. \
Одно множество может содержать значения любых типов. Если у Вас есть два множества, Вы можете совершать над ними любые стандартные операции, например, объединение, пересечение и разность.

***Пример работы:***

```python
colors = {'red', 'green', 'blue'}
print(colors) # {'red', 'green', 'blue'}
colors.add('red')
print(colors) # {'red', 'green', 'blue'}
colors.add('gray')
print(colors) # {'red', 'green', 'blue','gray'}
colors.remove('red')
print(colors) # {'green', 'blue','gray'}
colors.remove('red') # KeyError: 'red'
colors.discard('red') # ok
print(colors) # {'green', 'blue','gray'} 
colors.clear() # { }
print(colors) # set()
```

***Операции со множествами***

```python
a = {1, 2, 3, 5, 8}
b = {2, 5, 8, 13, 21}
c = a.copy()
u = a.union(b)
i = a.intersection(b)
dl = a.difference(b)
dr = b.difference(a) q=a.union(b).difference(a.intersection(b)) # {1, 21, 3, 13}
# Проверка на уникальность элементов множеств
my_set_1 = set([1, 2, 3, 4, 5])
my_set_2 = set([5, 6, 7, 8, 9])
my_set_1.intersection(my_set_2)  # {5}
my_set_1 & my_set_2  # {5} делат то же самое только короче
```

***Неизменяемое или замороженное множество(frozenset)*** — множество, с которым не будут работать методы удаления и добавления.

```python
a = {1, 2, 3, 5, 8}
b = frozenset(a)
print(b) # frozenset({1, 2, 3, 5, 8})
```

## 15. Функции
***Функция*** — это фрагмент программы, используемый многократно.

```python
# def - служебное слово для создания функции
def add(x, y):  # x, y - параметры
    return x + y # return - возвращает значение указанное справа от return в место вызова функции

# Безымянные или Лямда функции
foo = lambda a,b: a+b

# Пример применения
def select(f, col):
    return [f(x) for x in col]
def where(f, col):
    return [x for x in col if f(x)]

data = [1, 2, 3, 5, 8, 15, 23, 38]
res = select(int, data)
print (res)
res = where (lambda x: x % 2 == 0, res)
print(res)
res = list(select(lambda x: (x, x**2), res))
print (res)

# Возможность передачи неограниченного количества аргументов
def concatenatio(*params): 
    res = ""
    for item in params: 
        res += item
    return res


# Встроенные функции в язук Python
filter(f, data) # проверяет соответствие каждого из перебераемых элементов data, если проверка - True, возвращает этот элемент.
map(f, data) # Примерняет функцию для каждого из элементов data, возвращает новое значение
zip([1,2,3], ['q', 'w', 'e'], [3,2,1]) # Возвращает список кортежей из соответствующих индексов [(1, 'q', 3), (2, 'w', 2), (3, 'e', 1)]
#################################################
# В примере выше стоит учитывать длину всех списков
# Если один из списков - короче, то и итоговый будет длиной 
# соответствующей самому короткому списку
#################################################
# Функция enumerate0 позволяет пронумеровать набор данных.
users = ['userl', 'user2', 'user3']
data = list (enumerate (users))
print (data) # [(0, 'user1'), (1, 'user2'), (2, 'user3))]

sorted(iterable,key=None,reverse=False) #Сортировка строк осуществляется по ASCII-значениям
# iterable: строка, список, кортеж, множество, словарь
# key (необязательный параметр): если указать ключ, то сортировка будет выполнена по функции этого ключа.
# reverse (необязательный параметр): по умолчанию сортировка выполняется по возрастанию. Если указать reverse=True, то можно отсортировать по убыванию.
```
Зачастую функции описываются в одном файле, а используются в другом. Для этого необходимо:
1. Создать файл с функциями
2. Импортировать 
3. обратиться к названию файла и через "." обратиться к функции:
```python
import modul
modul.some_foo()
# так же можно переименовать длинное название например так:
import modul as m
m.some_foo()
# или импортировать саму функцию так:
from modul import some_foo
# или импортировать все функции из файла так:
from modul import *

```

***Alias (псевдоним)*** — альтернативное имя, которое даётся функции при её импорте из файла (смотри пример выше во 2м импорте)

***Рекурсия*** — это функция, вызывающая сама себя.

Пример применения: Необходимо вывести n - первых членов последовательности Фибоначчи.
```python
def fib(n):
    if n in [1, 2]:
        return 1
    return fib(n - 1) + fib(n - 2)
```

## 16. Работа с файлами
При работе с файлами необходимо соблюдать некоторую последовательность операций:

Открытие файла с помощью метода open() \
Чтение файла с помощью метода read() или запись в файл посредством метода write() \
Закрытие файла методом close()

Так же файл можно переименовать
* rename(src,dest) - переименовать
    * src - файл который нужно переименовать
    * dest - новое имя файла


***Методы файла в Python***
```python
file.close() # закрывает открытый файл
file.fileno() # возвращает целочисленный дескриптор файла
file.flush() # очищает внутренний буфер
file.isatty() # возвращает True, если файл привязан к терминалу
file.next() # возвращает следующую строку файла
file.read(n) # чтение первых n символов файла
file.readline() # читает одну строчку строки или файла
file.readlines() # читает и возвращает список всех строк в файле
file.seek(offset[,whene]) # устанавливает текущую позицию в файле
file.seekable() # проверяет, поддерживает ли файл случайный доступ. Возвращает True, если да
file.tell() # возвращает текущую позицию в файле
file.truncate(n) # уменьшает размер файл. Если n указала, то файл обрезается до n байт, если нет — до текущей позиции
file.write(str) # добавляет строку str в файл
file.writelines(sequence) # добавляет последовательность строк в файл
```


Варианты режима (мод): \
`a` - открыть для добавления данных
* Можно дописать в уже существующий файл
* Если такого файла нет - создаст и запишет

`r` - открыть для чтения
* позволяет прочитать данные из файла
* Если такого файла нет - выдаст ошибку

`w` - открытие для записи данных
* Позволяет записывать данные и создавать файл если его не существует.
* если файл существовал все данные будут перезаписаны

`w+` - открыть для записи и чтения
* Позволяет открыть для записи и чтения из файла
* Если файла не существует - создаст

`r+` - Позволяет открыть файл для чтения и записывать в него
* Позволяет открыть файл для чтения и дописать в него
* Если файла не существует - выдаст ошибку

Чтобы добавить запись обращаемся к переменной сохраненной в data:
```python
colors = ['red', 'green', 'yellow']
data = open('file_name.txt', 'a') # Открытие файла для добавления данных
data.writelines(colors) # Добавляем запись 
data.close() # После работы с файлом не забудь закрыть его чтобы не забыть лучше использовать такой подход:

# Рекомендовано к использованию
with open('file_name.txt', 'w') as data:
    data.write('line 1\n')
    data.write('line 2\n')

# Для чтения:
path = 'file.txt'
data = open( 'file.txt', 'r')
for line in data:
    print(line)
data.close()
```
При открытии файла или в процессе работы с ним мы можем столкнуться с различными исключениями, например, к нему нет доступа и т.д. В этом случае программа выпадет в ошибку, а ее выполнение не дойдет до вызова метода close, и соответственно файл не будет закрыт.

В этом случае мы можем обрабатывать исключения:
```python
try:
    myfile = open("hello.txt", "w")
    try:
        print("Работа с файлом")
    finally:
        myfile.close()
except Exception as ex:
    print(ex)
```
Или же так же работаем с конструкцией `with`

## 17. Модуль ОС
Модуль `os` предоставляет множество функций для работы с операционной системой, причем их поведение, как правило, не зависит от ОС, поэтому программы остаются переносимыми.
Для того, чтобы начать работать с данным модулем необходимо его импортировать в свою программу:
```python
import os
os.chdir('C:/Users/79190/PycharmProjects/GB') # смена текущей директории.
print(os.getcwd()) # текущая рабочая директория 'C:\Users\79190\PycharmProjects\webproject'
print(os.path.basename('C:/Users/79190/PycharmProjects/webproject/main.py')) # базовое имя пути 'main.py'
print(os.path.abspath('main.py')) # возвращает нормализованный абсолютный путь. 'C:/Users/79190/PycharmProjects/webproject/main.py'

``` 
## 18. Модуль shutil
Модуль shutil содержит набор функций высокого уровня для обработки файлов, групп файлов, и папок. В частности, доступные здесь функции позволяют копировать, перемещать и удалять файлы и папки. Часто используется вместе с модулем os.
Для того, чтобы начать работать с данным модулем необходимо его импортировать в свою программу:
```python
import shutil
shutil.copyfile(src, dst) # копирует содержимое (но не метаданные) файла src в файл dst.
shutil.copy(src, dst) # копирует содержимое файла src в файл или папку dst.
shutil.rmtree(path) # Удаляет текущую директорию и все поддиректории; path должен указывать на директорию, а не на символическую ссылку.
```

## Распространенные ошибки
Тут указаны самые распространенные ошибки при написании кода:
1. Отсутствие ":" во всех языковых конструкциях (if, while, for и т.д.)
2. Отсутствие отступов во вложенных конструкциях 
3. Сложение строк и чисел
4. Деление на 0
5. Отсутсвие вводимого ключа или переменной
6. Преобразование типов при невозможности (Например: int("Hello"))