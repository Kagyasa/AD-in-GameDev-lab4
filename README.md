# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Иванова Ивана Варкравтовна
- РИ000024
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
Работа с перцептроном.

## Задание 1
#### в проекте Unity реализовать перцептрон, который умеет производить вычисления: OR, AND, NAND, XOR

Я реализовала перцептрон для вычислений OR, AND, NAND, XOR и результаты занесла в таблицу. В ячейках внесены значения TotalError для соответствующей эпохи и выда вычисления
![image](https://github.com/user-attachments/assets/2d4de94b-a3ca-4323-83f2-e82b0e550092)

Перцептрон получилось успешно обучть для вычислений OR, AND, NAND, а вот XOR реализовать не получилось, так как если задача линейно разделима (например, логическая операция AND или OR), перцептрон может быстро обучиться и достичь нулевой ошибки, но если задача не линейно разделима (например, XOR), перцептрон не сможет достичь нулевой ошибки, так как это выходит за пределы его возможностей.

Ссылка на таблицу: https://docs.google.com/spreadsheets/d/12OzVTgGi5T1EE5V_gfD7UTot7J3LSi_hU-QRPQcL48I/edit?gid=0#gid=0



## Задание 2
### Построить графики зависимости количества эпох от ошибки  обучения. Указать от чего зависит необходимое количество эпох обучения.
Ссылка на таблицу с графиками: https://docs.google.com/spreadsheets/d/12OzVTgGi5T1EE5V_gfD7UTot7J3LSi_hU-QRPQcL48I/edit?gid=0#gid=0

## Задание 3
### Построить визуальную модель работы перцептрона на сцене Unity.
Я добавила в скрипт с перцетроном следующий код:


```
private int isWhite(Color color) => color == Color.green ? 1 : 0;

void OnTriggerEnter(Collider other)
{
    var firstCube = isWhite(this.gameObject.GetComponent<Renderer>().material.color);

    var secondCube = isWhite(other.gameObject.GetComponent<Renderer>().material.color);

	Debug.Log("first cube: " + firstCube);
    Debug.Log("first cube: " + this.gameObject.GetComponent<Renderer>().material.color);
    Debug.Log("first cube: " + Color.green);

    Debug.Log("second cube: " + secondCube);
    Debug.Log("second cube: " + this.gameObject.GetComponent<Renderer>().material.color);
    Debug.Log("second cube: " + Color.white);

    var outputColor = CalcOutput(firstCube, secondCube) > 0 ? Color.green : Color.white;

    this.gameObject.GetComponent<Renderer>().material.color = outputColor;
    Destroy(other.gameObject);
}
```.
для верхних кубов добавила компонент rigidbody, а к нижним применила скрипт перцептрона и в boxCollider включила Is Trigger

Результаты:

OR
[OR.webm](https://github.com/user-attachments/assets/413cf988-f233-4b7d-9d44-47e086fde2f5)

AND
[AND.webm](https://github.com/user-attachments/assets/2879c994-19ee-4087-a32b-7f896dfefdaa)

NAND
[NAND.webm](https://github.com/user-attachments/assets/281a78c0-45a8-433d-8262-53bb53f07a20)

Для XOR видео я не сняла, так как всё равно результат был бы неправильным, так как для этого вида вычислений обучить правильно перцептрон нельзя.




## Выводы

Я узнала как работает перцптрон, как его подключать и визуализировать. Также я узнала, как отслеживать столкновение объектов в Unity и реагировать на этот триггер.
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
