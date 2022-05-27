# Условие
### Задание 1
Написать приложение для копирования файлов с помощью `sendfile`.   
- Функцию `main` и функцию для копирования файла необходимо разместить в разных файлах. 
- Файл с функцией для копирования файла необходимо собрать в виде статической библиотеки.
- При сборке файла с функцией `main` необходимо слинковать его с ранее собранной библиотекой.
- Скопированный файл должен быть полной копией оригинала.

### Задание 2
1. Написать приложение которое открывает неименованный `пайп` и создает новый процесс с помощью системного вызова `fork`.  
2. После этого дочерний процес пишет в `пайп` сообщение "Hi daddy, I'm your child!" и завершается. 
3. Родительский процесс вычитывает сообщение из `пайпа` и дописывает в конец сообщения "Hi!". 
4. Получившийся текст родительский процесс записывает в файл и так же завершается.

# Требования
Для сборки в обоих заданиях использовать Makefile.

# Формат сдачи
Готовые файлы с кодом программы

# Обзор решения
### *Задание 1*
Проект содержит:
- `sendfile.h` header файл с подключением необходимых библиотек и сигнатурой функции для копирования файлов
- `sendfile.c` файл с реализацией функции копирования файлов
- `main.c` файл принимающий, как аргументы командной строки пути с названиями к файлам для копирования и для вставки копии. Так же, в качестве альтернативы при отсутствии аргументов, пути к файлам можно задать вручную.
- `Makefile` файл содержит инструкции компилятору по сборке исполняемого файла проекта

### *Сборка проекта*
Для сборки проекта в папке с его файлами необходимо открыть терминал и вызвать команду `make`. Результатом будет получение исполняемого файла с названием `send`  
![image_9_1](https://github.com/sotnikea/L_xTask9/raw/main/img/image_9_1.png)   

Существуют разные варианты использование полученного исполняемого файла.   
Введите в терминале './send' и через пробел путь и название файла для копирования, а так же путь и название файла, который должен быть создан  
![image_9_2](https://github.com/sotnikea/L_xTask9/raw/main/img/image_9_2.png) 

Так же достаточно просто ввести './send' без аргументов. Это вызовет возможность ввода путей и имен файлов в процессе выполнения программы  
![image_9_3](https://github.com/sotnikea/L_xTask9/raw/main/img/image_9_3.png) 

Отсутствие достаточно количества аргументов при вызове './send' так же приведет к предложению ввести необходимые пути и имена к файлам в процессе выполнения программы  
![image_9_4](https://github.com/sotnikea/L_xTask9/raw/main/img/image_9_4.png) 

Попытка указать несуществующий файл для копирования любым из способов исполнения программы приведет к отмене копирования и выводу сообщения об ошибке  
![image_9_5](https://github.com/sotnikea/L_xTask9/raw/main/img/image_9_5.png)  

### *Задание 2*
Проект содержит:
- `main.c` файл реализующий условие задания
- `Makefile` файл содержит инструкции компилятору по сборке исполняемого файла проекта

### *Сборка проекта*
Для сборки проекта в папке с его файлами необходимо открыть терминал и вызвать команду `make`. Результатом будет получение исполняемого файла с названием `start`  
![image_9_6](https://github.com/sotnikea/L_xTask9/raw/main/img/image_9_6.png)  

Для запуска исполняемого файла достаточно ввести в терминале `./start`. При успешном выполнении в терминал будет выведено соответствующее сообщение  
![image_9_7](https://github.com/sotnikea/L_xTask9/raw/main/img/image_9_7.png) 
а в папке проекта будет создан файл с соответствующим условию задания текстом  
![image_9_8](https://github.com/sotnikea/L_xTask9/raw/main/img/image_9_8.png) 

# Ссылки
- Установка образа Ubuntu в VirtualBox https://www.youtube.com/watch?v=vY9QNwX_IsY
- Установка gcc https://infoit.com.ua/linux/kak-ustanovit-gcc-na-ubuntu-20-04-lts/
