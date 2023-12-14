# Анализ данных в разработке игр [in GameDev]
Отчет по лабораторной работе #4 выполнил(а):
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
- Реализовать персептрон в Unity
- Сделать выводы о корректности его работы

## Задание 1
### В проекте Unity реализовать перцептрон, который умеет производить вычисления:
### - OR | дать комментарии о корректности работы
### - AND | дать комментарии о корректности работы
### - NAND | дать комментарии о корректности работы
### - XOR | дать комментарии о корректности работы
  
Ход работы:
- Создадим пустой 3D проект на Unity и добавим туда пустой объект
- Добавим к пустому объекту предложенный файл Perceptron.cs
- Запустим проект на разных тренировочных данных, используя 8 эпох обучения, и сделаем выводы
-   
![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб4.2.png)

Вывод OR:  
  - После тестов, сделал вывод, что 5 эпох для обучения персептрона вполне достаточно, но для уверенности можно использовать 6 эпох, чтобы он безошибочно выводил правильные результаты тестов. Ниже представлены скриншоты обучения персептрона на 1, 5 эпохах.  

    1 эпоха
      
    ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лабп1.png)  

    5 эпох
      
    ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лабп2.png)  
  
Вывод AND:  
  - После тестов, сделал вывод, что 8 и более эпох, для обучения персептрона вполне достаточно, чтобы он безошибочно выводил правильные результаты тестов. Ниже представлены скриншоты обучения персептрона на 1, 8 эпохах.     

    1 эпоха
       
    ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лабп3.png)  

    8 эпох: но иногда выдается неоднозначный результат, то есть больше 10 эпох будут выдавать правильные результаты с большей вероятностью
    
    ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лабп4.png)  
  
Вывод NAND:  
  - После тестов, сделал вывод, что 8 и более эпох для обучения персептрона достаточно, чтобы он безошибочно выводил правильные результаты тестов. Ниже представлены скриншоты обучения персептрона на 1, 8 эпохах.  

    1 эпоха
       
    ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лабп5.png)  

    8 эпох
    
    ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лабп6.png)   
  
Вывод XOR:  
 - После тестов, сделал вывод, что сколько бы эпох мы не проводили, он не выводит правильные результаты тестов, потому что XOR - это не линейная функция, а персептрон работает только с линейными. Ниже представлены скриншоты обучения персептрона на 1, 8 эпохах. Если запускать несколько раз, то можно заметить TOTAL ERROR либо максимальный после первой эпохи, либо увеличивается после каждой эпохи.  

   1 эпоха    

   ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лабп7.png)  

    8 эпох:    

   ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лабп8.png)  
  
## Задание 2
### Построить графики зависимости количества эпох от ошибки  обучения. Указать от чего зависит необходимое количество эпох обучения.
Необходимое число эпох обучения зависит от весов(weights) и смещения(bias). Более того также зависит от ошибки обучения, то есть мы должны подобрать такое число обучения, чтобы ошибка максимально минимизировалась,
и персептрон заканчивал свое обучение.  
  
Ссылка на таблицу   
https://docs.google.com/spreadsheets/d/1fI6StwFGVV5s0ctBkTc1QOcliWYPwLA_4dNtYZ2K0-Y/edit#gid=0  

OR:

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб4.1.png)

AND:

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб4.1.png)

NAND:

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб4.1.png)

XOR:

![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/лаб4.1.png)

Вывод:
- TOTAL ERROR(XOR) среднее с каждой эпохой увеличивается, достигает максимальной ошибки обучения и не меняется
- TOTAL ERROR(NAND) среднее c каждой эпохой уменьшается и достигиает значения 0 примерно к 9 эпохе. То есть персептрону будет достаточно обучения на 9 и более эпох, чтобы он уверенно выводил правильнык результаты.
При этом если мы уже видим, как на графике, что на 9 эпохе ошибка обучения равна нулю, то можно закончить обучение, иначе персептрон будет переобучаться
- TOTAL ERROR(AND) среднее c каждой эпохой уменьшается и достигиает значения 0 примерно к 10 эпохе. То есть персептрону будет достаточно обучения на 10 и более эпох, чтобы он уверенно выводил правильнык рзультаты. Также как и с AND если мы уже видим, как на графике, что на 10 эпохе ошибка обучния равна нулю, то можно закончить обучение, иначе персептрон будет переобучаться
- TOTAL ERROR(OR) среднее c каждой эпохой уменьшается и достигиает значения 0 примерно к 4 эпохе. То есть 10 эпох для OR слишком много, персептрон просто запоминает тренировочные данные, то есть переобучается. По моему мнению оптимальное количество эпох равно 4-6 для OR в зависимости от результатов обучения перспетрона

## Задание 3
### Построить визуальную модель работы перцептрона на сцене Unity.  
  Тесты OR, AND, NAND проходят одинаково хорошо, приведены на gif ниже
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/1.gif)  
  
  Один из тестов XOR показан на следующей gif
  
  ![Image alt](https://github.com/Vadichekk/UrFU-GameAnalysis/blob/main/github-screenshots/2.gif)
  
  Как мы видим, если персептрон успешно проходит тест, то платформа становятся зелёным цветом. Если же тест провален, то платформа становятся просто красным цветом.  
  Вот такой код я дописал в файле Perceptron.cs  
  ```cs
  	void Start () {
		Train(10);
		Debug.Log("Test 0 0: " + CalcOutput(0,0));
		Debug.Log("Test 0 1: " + CalcOutput(0,1));
		Debug.Log("Test 1 0: " + CalcOutput(1,0));
		Debug.Log("Test 1 1: " + CalcOutput(1,1));	
		if (CalcOutput(0, 0) == 0)
        {
            gameObject.GetComponent<Renderer>().material.color = Color.green;
        }
        else
        {
            gameObject.GetComponent<Renderer>().material.color = Color.red;
        }

        if (CalcOutput(0, 1) == 1)
        {
            gameObject.GetComponent<Renderer>().material.color = Color.green;
        }
        else
        {
            gameObject.GetComponent<Renderer>().material.color = Color.red;
        }


        if (CalcOutput(1, 0) == 1)
        {
            gameObject.GetComponent<Renderer>().material.color = Color.green;
        }
        else
        {
            gameObject.GetComponent<Renderer>().material.color = Color.red;
        }

        if (CalcOutput(1, 1) == 1)
        {
            gameObject.GetComponent<Renderer>().material.color = Color.green;
        }
        else
        {
            gameObject.GetComponent<Renderer>().material.color = Color.red;
        }	
	}
  ```

## Выводы

- Реализовал и визуализировал персептрон в Unity
- Сделал выводы о корректности его работы на примере функций OR, AND, NAND, XOR

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
