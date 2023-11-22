# Анализ данных в разработке игр [in GameDev]
Отчет по лабораторной работе #3 выполнил(а):
- Зиновьев Вадим Алексеевич
- РИ220946
  
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
- Разработать оптимальный баланс для десяти уровней игры Dragon Picker

## Задание 1
### Предложите вариант изменения найденных переменных для 10 уровней в игре. Визуализируйте изменение уровня сложности в таблице.
Изучив прототип в игре, я заметил, что на движение дракона влияют скорость, диапазон значений в котором они движется и вероятность, что он поменяет направления, а на
сбрасывание яиц влияет время, которое проходит между сбрасыванием яиц. Следовательно, меняя эти перемнные, мы можем изменить уровень сложности игры.  
  
Например:  
  - Увеличить скорость дракона  
  - Уменьшить время между сбрасыванием яиц  
  - Увеличить диапазон значений в пределах, которых передвигается дракон  
  - Увеличить вероятнсть изменения направления дракона  

Ссылка на google таблицу
- https://docs.google.com/spreadsheets/d/1C_p_t8DMI9ykfdXev4fG-m8zrgQDCjDDhfvX2aHFw9s/edit#gid=0
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/lab3.1.png)

## Задание 2
### Создайте 10 сцен на Unity с изменяющимся уровнем сложности.
Ход работы:
- Скачаем проект DrakonPicker и добавим в Unity
- Будем добавлять новые сцена, меняя значения в них переменных
  
Так как у нас уже есть сцена №1(1 уровень), создадим еще 10 сцен или же 10 новых уровней  
  
Ссылка на DragonPickerWorkhop3 c новыми 10 уровнями
- https://


## Задание 3
### Заполнить google-таблицу данными из Python. В Python данные также должны быть визуализированы.
Ход работы:
- Откроем Anaconda Jupyter Notebook
- Напишим код для подключения к Google таблицы, заполним её и визуализируем полученные данные

```py
import gspread
import time
import numpy as np
import matplotlib.pyplot as plt
gc = gspread.service_account(filename='unitydatasience1-6bc7a0f73e8d.json')
sh = gc.open("UnityWorkshop3")
time.sleep(3)
speed = 4
time_egg_drops = 2
left_right_distance = 10
chance_direction = 0.01
l, l_speed, l_time, l_distance, l_chance = [],[],[],[],[]
n = [i for i in range(1,12)]
for i in range(11):
    sh.sheet1.update(('A' + str(i+2)), i+1)
    sh.sheet1.update(('B' + str(i+2)), speed)
    sh.sheet1.update(('C' + str(i+2)), time_egg_drops)
    sh.sheet1.update(('D' + str(i+2)), left_right_distance*2)
    sh.sheet1.update(('E' + str(i+2)), chance_direction)
    print([speed,time_egg_drops,left_right_distance,chance_direction])
    l.append([speed,time_egg_drops,left_right_distance,chance_direction])
    l_speed.append(speed)
    l_time.append(time_egg_drops)
    l_distance.append(left_right_distance*2)
    l_chance.append(chance_direction)
    speed += 1.5
    time_egg_drops -= 0.10
    left_right_distance += 1
    chance_direction += 0.002

plt.title('Скорость дракона', fontsize=20)
plt.plot(n,l_speed)
plt.xlabel("Уровень")
plt.xticks(n)
plt.show()
plt.title('Время между сбрасыванием яиц', fontsize=20)
plt.plot(n,l_time)
plt.xlabel("Уровень")
plt.xticks(n)
plt.show()
plt.title('Диапазон движения дракона', fontsize=20)
plt.plot(n,l_distance)
plt.xlabel("Уровень")
plt.xticks(n)
plt.show()
plt.title('Вероятность поменять направление', fontsize=20)
plt.plot(n,l_chance)
plt.xlabel("Уровень")
plt.xticks(n)
plt.show()
bw = 0.2
index = np.arange(1,12)
plt.title('Динамика изменений уровней сложности', fontsize=20)
plt.bar(index, l_time, bw, color='b')
plt.bar(index+bw, l_speed, bw,color='g')
plt.bar(index+2*bw, l_distance, bw, color='r')
plt.bar(index+3*bw, l_chance, bw, color='yellow')
plt.xticks(index+1.5*bw, np.arange(1,12))
plt.xlabel("Уровень")
plt.show()
```
Вывод программы
```py
[4, 2, 10, 0.01]
[5.5, 1.9, 11, 0.012]
[7.0, 1.7999999999999998, 12, 0.014]
[8.5, 1.6999999999999997, 13, 0.016]
[10.0, 1.5999999999999996, 14, 0.018000000000000002]
[11.5, 1.4999999999999996, 15, 0.020000000000000004]
[13.0, 1.3999999999999995, 16, 0.022000000000000006]
[14.5, 1.2999999999999994, 17, 0.024000000000000007]
[16.0, 1.1999999999999993, 18, 0.02600000000000001]
[17.5, 1.0999999999999992, 19, 0.02800000000000001]
[19.0, 0.9999999999999992, 20, 0.030000000000000013]
```
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/lab3.2.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/lab3.3.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/lab3.4.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/lab3.5.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/lab3.6.png)

## Выводы

- Изучил прототип игры, выявил изменяющие переменные
- Содал таблицу, где показал динамику изменений уровней сложности
- Разработал оптимальный баланс для десяти уровней игры Dragon Picker

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
