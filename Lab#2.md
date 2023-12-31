# Анализ данных в разработке игр  [in GameDev]
Отчет по лабораторной работе #2 выполнил(а):
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
Научиться передавать в Unity данные из Google Sheets с помощью Python.

## Задание 1
### Выберите одну из компьютерных игр, приведите скриншот её геймплея и краткое описание концепта игры. Выберите одну из игровых переменных в игре (ресурсы, внутри игровая валюта, здоровье персонажей и т.д.), опишите её роль в игре, условия изменения / появления и диапазон допустимых значений. Постройте схему экономической модели в игре и укажите место выбранного ресурса в ней.

Я выбрал игру Warframe. В ней в основном PVE режимы. Warframe — условно-бесплатный кооперативный экшен с видом от третьего лица для четырех игроков. В команде друзей предстоит сразиться за невероятно опасную инопланетную расу Тенно (Tenno). Нужно проходить квесты, разнообразные задания как в одиночном режиме, так и в кооперативе на четверых человек. Игра представляет из себя постоянный фарм различных ресурсов для крафта новых варфреймов, оружия, компаньонов и многого другого.

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/1варф.jpeg)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/2варф.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/3варф.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/4варф.png)

В игре существует множество варфреймов, я расскажу о его расходуемом ресурсе энергия.
Изначально колличество энергии зависит от выбраного варфрейма, а так же от модификаций этого варфрейма. Я выбрал варфрейма Висп, у меня в начале 150 энергии, но если собрать, например, сферу энергии, то она повышается на 25 единиц. Она расходуется на использование способностей варфрейма (они у всех варфреймов разные и стоимость использования тоже разная). Способности нужны для повышения силы, скорости передвижения, мгновенного урона и различных других механик игры.

Посмотрим на схему:
- У нас есть расходуемый ресурс, если мы применим, какую-то способность, мы потратим какое-то кол-во энергии. Если мы захотим повысить кол-во энергии, нам нужно выбить сферу энергии с вражеского противника.

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/5варф.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/6варф.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/7варф.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/8варф.png)
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/схема.png)

## Задание 2
### С помощью скрипта на языке Python заполнить google-таблицу данными, описывающими выбранную игровую переменную в выбранной игре и средствами google-sheets визуализировать данные в google-таблице (построить график, диаграмму и пр.) для наглядного представления выбранной игровой величины.  
Ход работы:  
- C помощью Anaconda  Jupiter Notebook напишем код, который подлючается к Google Sheets таблице и добавляет туда данные

```py
import gspread
import time
import numpy as np
gc = gspread.service_account(filename='unitydatasience1-6bc7a0f73e8d.json')
sh = gc.open("UnityWorkshop2")
l_skill = ["", "Источники 1","Источники 2", "Источники 3", "Блуждающий огонек", "Всплеск пробоя", "Врата солнца"]
l_amount = [25,25,25,50, 25, 100]
time.sleep(3)
rage = 0
price = np.random.randint(1, 6, 11)
print(price)
c = 1
f = True
for i in price:
    sh.sheet1.update(('A' + str(c)), c)
    
    if rage + l_amount[i] >= 0:
        rage += l_amount[i]
        if rage > 300:
            rage = 300
        if rage == 300:
            sh.sheet1.update(('E' + str(c)), "2")
        else:
            sh.sheet1.update(('E' + str(c)), "1")
    else:
        sh.sheet1.update(('E' + str(c)), "0")
        
    tempInf = rage
    
    sh.sheet1.update(('B' + str(c)), str(l_skill[i]))
    
    if l_amount[i] > 0:
        sh.sheet1.update(('C' + str(c)), "+" + str(l_amount[i]))
    else:
        sh.sheet1.update(('C' + str(c)), str(l_amount[i]))
    
    sh.sheet1.update(('D' + str(c)), tempInf)
    
    print(tempInf)
    c += 1
    
```
https://docs.google.com/spreadsheets/d/1Uvyy4eswiME31yU4pI0kL3c1mUNpog6fwocSV0HzHJY/edit#gid=0

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/таблица.png)
  
Также на скриншоте можно увидеть график зависимости энергии от затрачиваемости способности

## Задание 3
### Настроить на сцене Unity воспроизведение звуковых файлов, описывающих динамику изменения выбранной переменной.  
Ход работы:  
- Создать новый 3Д проект
- Написать скрипт на C#, с подключением Google Sheets таблице
- Записать звуковые файлы, которые описывают динамику изменений нашей переменной
- Добавим в скрипт звуковые файлы
- Создадим пустой 3Д обьект, добавим ему "Audio Sourse", чтобы обьект мог воспроизводит звуковые файлы
- Запустим наш проект и увидим в консоли, что все звуковые файлы воспроизводится в соответсвие с таблицей Google Sheets
  
Также я переделал звуковые эффекты, они соответствуют значениям ниже.  
0 - недостаточно энергии, 1 - достаточно энергии, 2 - энергия на максимум  
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/звуки.png)

## Выводы

- Описал игровую переменную, её роль, условия изменения
- Построил схему экономической модели
- На Python написал код с подключением Google Sheets  и визуализировал данные в виде графика
- На Unity в новом проекте с помощью скрипта на C# воспроизвёл звуковые файлы, которые описывают динамику изменений выбранной переменной

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
