## Examples for eolang objects

Что есть:
- [arrtostdout](#arrtostdout) 
- [arrtostrarr](#arrtostrarr) 
- [between](#between) 
- [binarytree](#binarytree)
- [contains](#contains)
- [count](#count)
- [factorial](#factorial)
- [fibonacci](#fibonacci)
- [findcount](#findcount)
- [findindex](#findindex)
- [first](#first)
- [floatarrtostdout](#floatarrtostdout)
- [floatarrtostrarr](#floatarrtostrarr)
- [imax](#imax)
- [imin](#imin)
- [indexof](#indexof)
- [insert](#insert)
- [insertall](#insertall)
- [insertionsort](#insertionsort)
- [intarrtofloatarr](#intarrtofloatarr)
- [intarrtostdout](#intarrtostdout)
- [intarrtostrarr](#intarrtostrarr)
- [last](#last)
- [leaf](#leaf)
- [max](#max)
- [merge](#merge)
- [mergesort](#mergesort)
- [min](#min)
- [node](#node)
- [pi](#pi)
- [remove](#remove)
- [removeall](#removeall)
- [removeat](#removeat)
- [reverse](#reverse)
- [selectionsort](#selectionsort)
- [set](#set)
- [slice](#slice)
- [slicefrom](#slicefrom)
- [sliceto](#sliceto)
- [strarrtointarr](#strarrtointarr)
- [strarrtostdout](#strarrtostdout)
- [sum](#sum)
- [unique](#unique)

#### [arrtostdout](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/arrtostdout.eo)
Выводит заданный массив в указанном формате. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  arrtostdout > @
    (* 1 2 3)
    "%d"
  ```
*Результат: 1 2 3*

*Пример 2*
```
[args...] > app
  arrtostdout > @
    (* True False True)
    "%b"
```
*Результат: True False True*

#### [arrtostrarr](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/arrtostrarr.eo)
Преобразует заданный массив элементов в массив строк. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  arrtostdout > @
    arrtostrarr
      (* 1 2 3)
      "%d"
    "%s"
```
*Результат: 1 2 3*

#### [between](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/between.eo)
Определяет входит ли число в указанный диапозон. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%b"
      between
        2
        1
        3
```
*Результат: True*

*Пример 2*
```
[args...] > app
  stdout > @
    sprintf
      "%b"
      between
        5
        2
        3
```
*Результат: False*

#### [binarytree](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/binarytree.eo)
Основной объект для реализации бинарного дерева использует структуру их комбинации двух объектов [node](#node) и [leaf](#leaf). На данный объект умеет считать сумму всех узлов и их количество [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      sum.
        binarytree
          node
            1
            node
              2
              leaf
              leaf
            node
              3
              node
                4
                leaf
                leaf
              leaf
```
*Результат: 10*

#### [contains](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/contains.eo)
Определяет содержит ли данный массив указанный элемент. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%b"
      contains
        *
          1
          3
          5
        2 
```
*Результат: False*

*Пример 2*
```
[args...] > app
  stdout > @
    sprintf
      "%b"
      contains
        *
          1
          3
          5
        3
```
*Результат: True*

#### [count](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/count.eo)
Определяет количество вхождений заданного числа в массив. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      count
        *
          2
          1
          3
          3
          2
        3
```
*Результат: 2*

*Пример 2*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      count
        *
          2
          1
          3
          3
          2
        5
```
*Результат: 0*

#### [factorial](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/factorial.eo)
Возвращает факториал заданного числа. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      factorial
        5
```
*Результат: 120*

#### [fibonacci](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/fibonacci.eo)
Возвращает число, которое соответствует заданной позиции в последовательности [Фибоначчи](https://ru.wikipedia.org/wiki/Числа_Фибоначчи). [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      fibonacci
        10
```
*Результат: 55*

#### [findcount](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/findcount.eo)
Возвращает число элементов массива, которое соответствует заданному предикату. Главное условие для предиката - наличие атрибута "execute", возвращающее логическое значения. [Вернуться](#examples-for-eolang-objects)

*Пример 1. Предикат проверяет равенство заданного числа с элементами массива, то есть данный пример аналогичен вызову [count](#count)*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      findcount
        *
          1
          2
          3
        mypredicate
          2
      
[some] > mypredicate
  [current] > execute
    eq. > @
      some
      current
```
*Результат: 1*

*Пример 2. Предикат првоеряет меньше ли заданный элемент чем элемент массива*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      findcount
        *
          1
          2
          3
        mypredicate
          1
      
[some] > mypredicate
  [current] > execute
    less. > @
      some
      current
```
*Результат: 2*

#### [findindex](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/findindex.eo)
Возвращает номер первого элемента массива, который соответствует заданному предикату. Главное условие для предиката - наличие атрибута "execute", возвращающее логическое значения. [Вернуться](#examples-for-eolang-objects)

*Пример 1. Предикат провоеряет равенство заданного числа с элементами массива, то есть данный пример аналогичен вызову [indexof](#indexof)*
```
[args...] > app
  stdout > @
    sprint
      "%d"
      findindex
        *
          1
          2
          3
        mypredicate
          2
      
[some] > mypredicate
  [current] > execute
    eq. > @
      some
      current
```
*Результат: 1*

*Пример 2. Предикат првоеряет меньше ли заданный элемент чем элемент массива*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      findindex
        *
          1
          2
          3
        mypredicate
          4
      
[some] > mypredicate
  [current] > execute
    less. > @
      some
      current
```
*Результат: -1*

#### [first](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/first.eo)
Возвращает первый элемент массива и ошибку, если массив пустой. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      first
        *
          5
          2
          3
```
*Результат: 5*

#### [floatarrtostdout](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/floatarrtostdout.eo)
Выводит в консоль массив чисел с плавающей точкой. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  floatarrtostdout > @
    *
      5.0
      2.2
      3.1
```
*Результат: 5.0 2.2 3.1*

#### [floatarrtostrarr](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/floatarrtostrarr.eo)
Перводит массив чисел с плавающей точков в строковый массив. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  strarrtostdout > @
    floatarrtostrarr
      *
        5.0
        2.2
        3.1
```
*Результат: 5.0 2.2 3.1*

#### [imax](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/imax.eo)
Возвращает индекс максимального элемента массива и ошибку, если массив пустой. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      imax
        *
          5
          2
          3
```
*Результат: 0*

#### [imin](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/imin.eo)
Возвращает индекс минимального элемента массива и ошибку, если массив пустой. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      imin
        *
          5
          2
          3
```
*Результат: 1*

#### [indexof](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/indexof.eo)
Возвращает индекс первого элемента массива равного заданному, в противном случае возвращает -1. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      indexof
        *
          5
          2
          3
        3
```
*Результат: 2*

#### [insert](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/insert.eo)
Вставляет в массив указанный элемент на заданную позицию. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    insert
      *
        5
        2
        3
      7
      1
```
*Результат: 5 7 2 3*

#### [insertall](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/insertall.eo)
Вставляет в массив указанный массив на заданную позицию. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    insertall
      *
        1
        2
        3
      *
        4
        5
        6
      2
```
*Результат: 1 2 4 5 6 3*

#### [insertionsort](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/insertionsort.eo)
Сортирует массив при помощи сортировки вставками. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    insertionsort
      *
        5
        2
        3
```
*Результат: 2 3 5*

#### [intarrtofloatarr](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/intarrtofloatarr.eo)
Переводит массив целых чисел в массив чисел с плавающей точкой. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  floatarrtostdout > @
    intarrtofloatarr
      *
        5
        2
        3
```
*Результат: 5.0 2.0 3.0*

#### [intarrtostdout](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/intarrtostdout.eo)
Выводит в консоль массив целых чисел. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    *
      5
      2
      3
```
*Результат: 5 2 3*

#### [intarrtostrarr](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/intarrtostrarr.eo)
Переводит массив целых чисел в строковый массив. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  strarrtostdout > @
    intarrtostrarr
      *
        5
        2
        3
```
*Результат: 5 2 3*

#### [last](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/last.eo)
Возвращает последний элемент массива и ошибку, если массив пустой. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      last
        *
          5
          2
          4
```
*Результат: 4*

#### [leaf](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/leaf.eo)
Лист необходим для обозначения конца в дереве. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%b"
      leaf.empty
```
*Результат: True*

#### [max](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/max.eo)
Возвращает максимальный элемент массива и ошибку, если массив пустой. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      max
        *
          5
          2
          4
```
*Результат: 5*

#### [merge](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/merge.eo)
Возвращает массив, полученный в результате соединения двух заданных, массивы могут быть пустыми. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    merge
      *
        1
        2
      *
        3
        4
```
*Результат: 1 2 3 4*

#### [mergesort](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/mergesort.eo)
Сортирует массив при помощи сортировки слиянием. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    mergesort
      *
        5
        2
        3
```
*Результат: 2 3 5*

#### [min](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/min.eo)
Возвращает минимальный элемент массива и ошибку, если массив пустой. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      min
        *
          5
          2
          4
```
*Результат: 2*

#### [node](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/node.eo)
Узел дерева, содержащий некоторое значение и два других узла или листа. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      "%d"
      value.
        node
          5
          leaf
          leaf
```
*Результат: 5*

#### [pi](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/pi.eo)
Возвращет число пи, также может рассчитать более точный результат с помощью вызова атрибута. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    spritnf
      "%f"
      pi
```
*Результат: 3.1415926535*

*Пример 2*
```
[args...] > app
  stdout > @
    spritnf
      "%f"
      compute.
        pi
        1000
```
*Результат: TODO*

#### [remove](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/remove.eo)
Удаляет первое вхождение заданного элемента из массива, если такого элемента нет, то возвращает исходный массив. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    remove
      *
        1
        2
        3
      3
```
*Результат: 1 2*

#### [removeall](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/removeall.eo)
Удаляет первое вхождение заданных элементов из массива, если таких элементов нет, то возвращает исходный массив. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    removeall
      *
        1
        2
        3
        2
        4
        5
      *
        2
        2
        5
```
*Результат: 1 3 4*

#### [removeat](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/removeat.eo)
Удаляет элемент с заданным индексом из массива. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    removeat
      *
        1
        2
        3
        2
      2
```
*Результат: 1 2 2*

#### [reverse](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/reverse.eo)
Возвращает перевернутый массив. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    reverse
      *
        1
        2
        3
```
*Результат: 3 2 1*

#### [selectionsort](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/selectionsort.eo)
Сортирует массив при помощи сортировку выбором. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    selectionsort
      *
        3
        1
        2
```
*Результат: 1 2 3*

#### [set](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/set.eo)
Присваивает элементу массива с указанным индексом заданное значение. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    set
      *
        1
        2
        3
      2
      7
```
*Результат: 1 2 7*

#### [slice](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/slice.eo)
Возвращает срез массива в указанном диапозоне. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    slcie
      *
        5
        6
        7
        8
        9
      2
      4
```
*Результат: 7 8*

#### [slicefrom](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/slicefrom.eo)
Возвращает срез массива в c указанного начала и до его конца. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    slicefrom
      *
        5
        6
        7
        8
        9
      1
```
*Результат: 6 7 8 9*

#### [sliceto](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/sliceto.eo)
Возвращает срез массива в c начала и до указанного конца. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    slicefrom
      *
        5
        6
        7
        8
        9
      3
```
*Результат: 5 6 7*

#### [strarrtointarr](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/strarrtointarr.eo)
Переводит массив строк в массив целых чисел. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
      *
        "5"
        "3"
        "1"
```
*Результат: 5 3 1*

#### [strarrtostdout](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/strarrtostdout.eo)
Выводит в консоль массив строк. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  strarrtostdout > @
    *
      "some"
      "day"
      "today"
```
*Результат: some day today*

#### [sum](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/sum.eo)
Возвращает сумму элементов массива. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      sum
        *
          1
          2
          3
          4
      "%d"
```
*Результат: 10*

#### [unique](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/unique.eo)
Возвращает массив без дубликатов. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  intarrtostdout > @
    unique
      *
        2
        1
        2
        3
        4
        4
        7
        8
```
*Результат: 2 1 3 4 7 8*

<img src="https://www.yegor256.com/images/books/elegant-objects/cactus.svg" height="100px" />

[![Maven Central](https://img.shields.io/maven-central/v/org.eolang/eo-maven-plugin.svg)](https://maven-badges.herokuapp.com/maven-central/org.eolang/eo-maven-plugin)

You can play with EOLANG here, in a few simple steps:

First, clone this repo to your local machine and go
to the `sandbox` directory (you will need
[Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
installed):

```bash
$ git clone https://github.com/cqfn/eo.git
$ cd eo/sandbox
```

Then, compile the code (you will need
[Maven 3.3+](https://maven.apache.org/)
and [Java SDK 8+](https://www.java.com/en/download/) installed):

```bash
$ mvn compile
```

Intermediary `*.xml` files will be generated in the `target` directory (it will
be created). Also, there will be `*.java` and `*.class` files. Feel free to analyze
them: EO is parsed into XML, then translated to Java, and then compiled
by Java SDK to Java bytecode. Finally, just run the bytecode program through JRE:

```bash
$ ./run.sh 4 3 2
2 3 4
```

Should work.

Then, you can modify `*.eo` files, run `mvn compile` to compile them
again and `run.sh` to run it again.
