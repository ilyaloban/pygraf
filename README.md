# **Модуль PyGraF**

Данный модуль для Python позволяет очень просто строить графики.

-----

## **Установка**
Скачайте файл `pygraf.py` из релиза и переместите в папку с проектом. Модуль основан на библиотеке Turtle, так что следует импортировать и её:

```
import turtle
from pygraf import *
```

------

## **Оформление**
1. Координатная плоскость
>draw_coord( **size** - размер _(int)_ )

2. Настройка экрана

>screen_conf(title - название окна _(string)_,
height - высота _(int)_ ,
width - ширина _(int)_ )

>Чтобы окно не закрывалось после построения графика, используйте функцию screen_save()

-----
## _**y_plot** (y = ... x)_
(задаётся y, зависимый от x)
> y_plot(**equation**, - выражение _(string)_,
mult - читайте ниже,
 x_from, - миним. значение x _(int)_
 x_to - макс. значение x _(int)_ )

Пример:
```
urav = y_plot("y = 2 * x + 15", 1, -10, 70)
urav.draw("red")
```
* Параметр **mult** (доступен с версии 0.0.2) домножает Y на указанное значение _(int, float)_
```python
urav = y_plot("y = x ** 2", mult = 1)
urav.draw("green")
urav_m = y_plot("y = x ** 2", mult = 0.1)
urav_m.draw("red")
```
<img src="images/multip.jpg" alt="Сравнение" width="200"/>

> Функция draw(**color** - цвет _(string)_ ) может принимать такие значения, как "red", "yellow", "green", "blue" и так далее.


------

## **Пользовательские графики** 
#### ( _y_ равен каждому значению из списка)

> list_plot(data_array - список с данными _(int, float)_,
start_x - смещение по x _(int)_,
start_y - смещение по y _(int)_ )

>Пример кода с использованием библиотеки PyGraF:
```python
import turtle
from pygraf import *


screen_conf("Example", 500, 500)
draw_coord(200)

bidon = [0]
for i in range(101):
	k = bidon[ len(bidon) - 1 ] + i
	bidon.append( k )

cus = list_plot(bidon, -150, -200)
cus.draw("red")

urav = y_plot("y = 2 * x + 15", 1, -10, 70)
urav.draw("green")

screen_save()
```
<img src="images/pic_plot.jpg" alt="Скриншот примера" width="200"/>

_P.S. Мне 13 лет, и я только учусь в программировании, так что не судите строго_

