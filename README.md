# LR1_VectorSum
Сумма элементов вектора.
https://colab.research.google.com/drive/1pb1nHcKlzWRheca0ngT5vOVfqGeT6Y3_?usp=sharing

# Задание
Реализовать алгоритм сложения элементов вектора.
Язык: C++ или Python.
Входные данные: вектор размером от 1000..1 000 000 значений.
Выходные данные: сумма элементов вектора + время вычисления.
Реализация должна содержать 2 функции сложения элементов вектора: на CPU и на GPU с применением CUDA.

# Реализация
- Импорт библиотек, подключение CUDA devices.
- Функция сложение векторов на CPU.
- Сложение векторов на GPU:
- -функция сложения векторов, с применением numba @jit декоратором, непосредственно на CUDA devices,
- -функция копирования данных в пямять devices, предварительно задается размер блоков и количество нитей в блоке.
- Результаты. Визуализация данных.
  
# Результаты работы программы
В таблице приведены результаты времени выполнения суммирования элементов векторов и ускорение:
![image](https://github.com/Won20/LR1_VectorSum/assets/102918065/2dcfc5f2-86a3-417d-b4de-36705a172c29)  
![image](https://github.com/Won20/LR1_VectorSum/assets/102918065/499f7e36-933c-4884-b218-392cc018e7b3)

Графики зависимости времени и ускорения от размера вектора:
![image](https://github.com/Won20/LR1_VectorSum/assets/102918065/7df00bed-51ac-4f22-a412-466dc828d678)

Применение GPU не всегда оправданно, как можно видеть в таблицах. Это не трудно заметить в первой строке, где значение ускорения  не превышает 0,02. Данный результат можно обосновать тем, что были выделены сравнительно малый размер вектора и значительное время затрачиваемое на распараллеливание алгоритма. Однако с увеличением размерности массива, применение GPU становится оправданным, поскольку время затрачиваемое на распараллеливание и вычисления производимые на GPU становится меньшим посравнению со временем затрачиваемым CPU на работу последовательного алгоритма.

