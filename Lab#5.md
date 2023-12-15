# Анализ данных в разработке игр [in GameDev]
Отчет по лабораторной работе #5 выполнил(а):
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
- Познакомиться с программными средствами для создания системы машинного обучения и ее интеграции в Unity

## Задание 1
### Найдите внутри C# скрипта “коэффициент корреляции ” и сделать выводы о том, как он влияет на обучение модели.  
Коэффицент корреляции в C# скрипте 

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.1.png)  

- при коэффиценте корреляции равным 5.0, средня награда всегда в диапазоне 0.75+ и до 1.0 и в среднем стандартное отклонение равно 0.512, а эло начинается около 1200 и немного уменьшается, но не слишком быстро
  
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.2.png)  

Вывод: коэффицент корреляции отвечает за точность обучения, также чем он меньше, тем дольше происходит обучение  

## Задание 2  
### Изменить параметры файла yaml-агента и определить какие параметры и как влияют на обучение модели. Привести описание не менее трех параметров.  
Настройки по умолчанию:  

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.2.png)

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.3.png)

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.4.png)

- network_settings:  
  - normalize: Нужно ли нормализировать входные данные. (true, false)  
  normalize = true

  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.11.png)
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.12.png)
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.13.png)
  
  Вывод:
    - Появляется ошибка обучения, которая в процессе, стремится к нулю. Дополнительные вознаграждения (Extrinsic Rewards) в начале растут, достигают максимума и уменьшаются. Оценка внешней ценности (Extrinsic value estimate) стабильно одинаковые данные, но с низкими показателями в сравнение со стартовыми настройками, где ценность со временем повышается. Энтропия(Entropy) стабильно растет.
    
  - hidden_units: (по умолчанию = 128) Количество узлов в скрытых слоях нейронной сети. То есть каждый скрытый слой нейронной сети имеет данное количество узлов. Если задача простая, то необходимости в большем количестве узлов в каждом слое нейронной сети не требуется.(64 - 256)
      
   hidden_units = 64
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.5.png)
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.6.png)
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.7.png)
  
   hidden_units = 256
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.8.png)
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.9.png)
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.10.png)
  
  Вывод:
    - В связи с тем, что узлов в каждом скрытом слое 64, время обучения уменьшается, но точность обучения из-за этого страдает. Очень сильно вылетает ошибка обучения (Value Loss), сильно не стабильно. Графики почти одинаковы. Но при 256 узлов в скрытом слое время обучения сильно увеличивается. На 20000 мы имеем Mean Rewards = -1.  Оценка внешней ценности (Extrinsic value estimate) начинает уменьшатьсяс 20000 в отличие от hidden_units = 64. (Extrinsic Rewards) растут экспотенциально.  
            
 - learning_rate: начальная скорость обучения для градиентного спуска. Как правило, этот показатель следует уменьшить, если обучение нестабильно, а вознаграждение постоянно не увеличивается.  
learning_rate = 0.03

  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.14.png)
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.15.png)
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб5.16.png)

  Вывод:
    - Так как всего один скрытый слой, то в начале ошибка обучения будет максимальной, процессе обучения ошибка будет уменьшаться. Время обучения не сильно сократилось. Точность немного уменьшилась,  что на 20000 шаге мы получаем mean rewards < 0. Дополнительные вознаграждения (Extrinsic Rewards) растут экспотенциально. Дополнительные вознаграждения (Extrinsic Rewards) не стабильны.
  
## Задание 3
### Приведите примеры, для каких игровых задачи и ситуаций могут использоваться примеры 1 и 2 с ML-Agent’ом. В каких случаях проще использовать ML-агент, а не писать программную реализацию решения?  
-  1 пример может использоваться для nps-врагов, которые находили бы путь до игрока,наводились на него и двигались к нему: "Need for speed" - соперники едут вплотную
-  2 пример может использоваться для nps, которые ходят только из одной точки в другую: "Clash of clans" - строить постройки, "World of Warcraft" - собирать золото
  
ML-агента проще использовать тогда, когда игрок совершает много действий и к ним требуется адаптация. Также проще использовать уже готовый алгоритм, а не писать новый, что существенно сократит время разработку игры. Но есть случаи, когда ML-агент вовсе не требуется, и использовать более простые алгоритмы будет гораздо правильнее и логичнее.
 

## Выводы
- Познакомился с программными средствами для создания системы машинного обучения и ее интеграции в Unity
- Научился создавать виртуальное пространство для ml-agenta и связывать ml-агента с Unity
- Использовал визуализацию на основне библиотеке tenseorflow

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
