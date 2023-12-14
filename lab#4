# Анализ данных в разработке игр [in GameDev]
Отчет по лабораторной работе #4 выполнил(а):
- Попов Василий Сергеевич
- РИ220948
  
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
- Запустим проект на разных тренировочных данных,используя 8 эпох обучения, и сделаем выводы    
![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/empty_object.png)

Вывод OR:  
  - Проведя тесты, я выяснил, что 5 эпох для обучения персептрона достаточно, но для еще большей уверенности можно использовать 6 эпох, чтобы он безошибочно выводил правильные результаты тестов. Ниже я прикрепил скриншоты обучения персептрона на 1, 3, 5 эпохах.  
    1 эпоха  
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/1epochOR.png)  
    3 эпохи  
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/3epochOR.png)  
    5 эпох  
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/5epochOR.png)  
  
Вывод AND:  
  - Проведя тесты, я выяснил, что 8 и более эпох, для обучения персептрона вполне достаточно, чтобы он безошибочно выводил правильные результаты тестов. Ниже я прикрепил скриншоты обучения персептрона на 1, 3, 8 эпохах.     
    1 эпоха   
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/1epochAND.png)  
    3 эпохи  
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/3epochAND.png)  
    8 эпох: но иногда выдается неоднозначный результат, то есть 10+ эпох будут выдавать правильные результаты с большей вероятностью
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/8epochAND.png)  
  
Вывод NAND:  
  - Проведя тесты, я выяснил, что 8 и более эпох для обучения персептрона достаточно, чтобы он безошибочно выводил правильные результаты тестов. Ниже я прикрепил скриншоты обучения персептрона на 1, 4, 6, 8 эпохах.  
    1 эпоха    
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/1epochNAND.png)  
    4 эпохи  
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/4epochNAND.png)  
    6 эпох: неоднозначный результат, требуется больше эпох    
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/6epochNAND.png)  
    8 эпох  
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/8epochNAND.png)   
  
Вывод XOR:  
 - Проведя тесты, я выяснил, что сколько бы эпох мы не ставили, он не будет выводит правильные результаты тестов, потому что XOR - это не линейная функция, а персептрон работает только с линейными. Ниже я прикрепил скриншоты обучения персептрона на 1, 4, 8 эпохах. Если запускать несколько раз, то можно заметить TOTAL ERROR либо максимальный после первой эпохи, либо увеличивается после каждой эпохи.  
    1 эпоха    
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/1epochXOR.png)  
    4 эпохи   
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/4epochXOR.png)  
    8 эпох:    
    ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/8epochXOR.png)  
  
## Задание 2
### Построить графики зависимости количества эпох от ошибки  обучения. Указать от чего зависит необходимое количество эпох обучения.
Необходимое число эпох обучения зависит от весов(weights) и смещения(bias). Более того также зависит от ошибки обучения, то есть мы должны подобрать такое число обучения, чтобы ошибка максимально минимизировалась,
и персептрон заканчивал свое обучение.  
  
Ссылка на таблицу   https://docs.google.com/spreadsheets/d/1NkxHI_CfUrCAs_nFhNSSOnMNH0bhel2zXnRblwwoRsY/edit#gid=0  
![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/epoch_gtable.png)
Вывод:
- TOTAL ERROR(XOR) среднее с каждой эпохой увеличивается, достигает максимальной ошибки обучения и не меняется
- TOTAL ERROR(NAND) среднее c каждой эпохой уменьшается и достигиает значения 0 примерно к 9 эпохе. То есть персептрону будет достаточно обучения на 9 и более эпох, чтобы он уверенно выводил правильнык результаты.
При этом если мы уже видим, как на графике, что на 9 эпохе ошибка обучения равна нулю, то можно закончить обучение, иначе персептрон будет переобучаться
- TOTAL ERROR(AND) среднее c каждой эпохой уменьшается и достигиает значения 0 примерно к 10 эпохе. То есть персептрону будет достаточно обучения на 10 и более эпох, чтобы он уверенно выводил правильнык рзультаты. Также как и с AND если мы уже видим, как на графике, что на 10 эпохе ошибка обучния равна нулю, то можно закончить обучение, иначе персептрон будет переобучаться
- TOTAL ERROR(OR) среднее c каждой эпохой уменьшается и достигиает значения 0 примерно к 4 эпохе. То есть 10 эпох для OR слишком много, персептрон просто запоминает тренировочные данные, то есть переобучается. По моему мнению оптимальное количество эпох равно 4-6 для OR в зависимости от результатов обучения перспетрона

## Задание 3
### Построить визуальную модель работы перцептрона на сцене Unity.  
  Тесты OR, AND, NAND проходят одинаково хорошо, поэтому всего одна gif для них
  ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/gifOR-AND-NAND.gif)  
  Один из тестов XOR показан на второй gif  
  ![Image alt](https://github.com/prepref/UrFU-GameAnalysis/raw/main/github-screenshots/workshop4/gifXOR.gif)  
  Как мы видим, если персептрон успешно проходит тест, то шарик и куб становятся зелёным цветом, и кубик разрушается. Если же
  тест провален, то шарик и кубик становятся просто красным цветом.  
  Вот такой код я дописал в файле Perceptron.cs  
  ```cs
  private void OnCollisionEnter(Collision collision)
	{	
        var test = CalcOutput(0, 0);
		if (test == 0 && collision.gameObject.tag != "Floor" && collision.gameObject.tag == "sphere4")
		{	
			collision.gameObject.GetComponent<Renderer>().material.color = Color.green;
			gameObject.GetComponent<Renderer>().material.color = Color.green;
            Destroy(collision.gameObject,1);
		}
		else if(collision.gameObject.tag != "Floor" && collision.gameObject.tag == "sphere4")
		{
            collision.gameObject.GetComponent<Renderer>().material.color = Color.red;
            gameObject.GetComponent<Renderer>().material.color = Color.red;
        };
        test = CalcOutput(0,1);
        if (test == 1 && collision.gameObject.tag != "Floor" && collision.gameObject.tag == "sphere3")
        {
            collision.gameObject.GetComponent<Renderer>().material.color = Color.green;
            gameObject.GetComponent<Renderer>().material.color = Color.green;
            Destroy(collision.gameObject,1);
        }
        else if (collision.gameObject.tag != "Floor" && collision.gameObject.tag == "sphere3")
        {
            collision.gameObject.GetComponent<Renderer>().material.color = Color.red;
            gameObject.GetComponent<Renderer>().material.color = Color.red;
        };
        test = CalcOutput(1, 0);
        if (test == 1 && collision.gameObject.tag != "Floor" && collision.gameObject.tag == "sphere2")
        {
            collision.gameObject.GetComponent<Renderer>().material.color = Color.green;
            gameObject.GetComponent<Renderer>().material.color = Color.green;
            Destroy(collision.gameObject,1);
        }
        else if (collision.gameObject.tag != "Floor" && collision.gameObject.tag == "sphere2")
        {
            collision.gameObject.GetComponent<Renderer>().material.color = Color.red;
            gameObject.GetComponent<Renderer>().material.color = Color.red;
        };
        test = CalcOutput(1, 1);
        if (test == 0 && collision.gameObject.tag != "Floor" && collision.gameObject.tag == "sphere1")
        {
            collision.gameObject.GetComponent<Renderer>().material.color = Color.green;
            gameObject.GetComponent<Renderer>().material.color = Color.green;
            Destroy(collision.gameObject,1);
        }
        else if (collision.gameObject.tag != "Floor" && collision.gameObject.tag == "sphere1")
        {
            collision.gameObject.GetComponent<Renderer>().material.color = Color.red;
            gameObject.GetComponent<Renderer>().material.color = Color.red;
        };
    }
  ```
В каждом условие значение test мы меняем в зависимости от того, для какой функции мы проводим тесты. В данном случаче значение test представлено для функции XOR.

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
