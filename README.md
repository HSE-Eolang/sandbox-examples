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
- [findindex](#findindex) TODO
- [first](#first)
- [floatarrtostdout](#floatarrtostdout) TODO
- [floatarrtostrarr](#floatarrtostrarr) TODO
- [imax](#imax) TODO
- [imin](#imin) TODO
- [indexof](#indexof) TODO
- [insert](#insert) TODO
- [insertall](#insertall) TODO
- [insertionsort](#insertionsort) TODO
- [intarrtofloatarr](#intarrtofloatarr) TODO
- [intarrtostdout](#intarrtostdout) TODO
- [intarrtostrarr](#intarrtostrarr) TODO
- [last](#last) TODO
- [leaf](#leaf)
- [max](#max) TODO
- [merge](#merge) TODO
- [mergesort](#mergesort) TODO
- [min](#min) TODO
- [node](#node)
- [pi](#pi) TODO
- [remove](#remove) TODO
- [removeall](#removeall) TODO
- [removeat](#removeat) TODO
- [reverse](#reverse) TODO
- [selectionsort](#selectionsort) TODO
- [set](#set) TODO
- [slice](#slice) TODO
- [slicefrom](#slicefrom) TODO
- [sliceto](#sliceto) TODO
- [strarrtointarr](#strarrtointarr) TODO
- [strarrtostdout](#strarrtostdout) TODO
- [sum](#sum) TODO
- [unique](#unique) TODO

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
      between
        2
        1
        3
      "%b"
```
*Результат: True*

*Пример 2*
```
[args...] > app
  stdout > @
    sprintf
      between
        5
        2
        3
      "%b"
```
*Результат: False*

#### [binarytree](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/binarytree.eo)
Основной объект для реализации бинарного дерева использует структуру их комбинации двух объектов [node](#node) и [leaf](#leaf). На данный объект умеет считать сумму всех узлов и их количество [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
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
      "%d"
```
*Результат: 10*

#### [contains](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/contains.eo)
Определяет содержит ли данный массив указанный элемент. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      contains
        *
          1
          3
          5
        2 
      "%b"
```
*Результат: False*

*Пример 2*
```
[args...] > app
  stdout > @
    sprintf
      contains
        *
          1
          3
          5
        3 
      "%b"
```
*Результат: True*

#### [count](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/count.eo)
Определяет количество вхождений заданного числа в массив. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      count
        *
          2
          1
          3
          3
          2
        3
      "%d"
```
*Результат: 2*

*Пример 2*
```
[args...] > app
  stdout > @
    sprintf
      count
        *
          2
          1
          3
          3
          2
        5
      "%d"
```
*Результат: 0*

#### [factorial](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/factorial.eo)
Возвращает факториал заданного числа. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      factorial
        5
      "%d"
```
*Результат: 120*

#### [fibonacci](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/fibonacci.eo)
Возвращает число, которое соотвествует заданной позиции в последовательности [Фибоначчи](https://ru.wikipedia.org/wiki/Числа_Фибоначчи). [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      fibonacci
        10
      "%d"
```
*Результат: 55*

#### [findcount](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/findcount.eo)
Возвращает число элементов массива, которое соотвествует заданному предикату. Главное условие для предиката - наличие атрибута "execute", возвращающее логическое значения. [Вернуться](#examples-for-eolang-objects)

*Пример 1. Предикат првоеряет равенство заданного числа с элементами массива, то есть данный пример аналогичен вызову [count](#count)*
```
[args...] > app
  stdout > @
    sprintf
      findcount
        *
          1
          2
          3
        mypredicate
          2
      "%d"
      
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
      findcount
        *
          1
          2
          3
        mypredicate
          1
      "%d"
      
[some] > mypredicate
  [current] > execute
    less. > @
      some
      current
```
*Результат: 2*

#### [first](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/first.eo)
Возвращает первый элемент массива и ошибку, если массив пустой. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      first
        *
          5
          2
          3
      "%d"
```
*Результат: 5*

#### [leaf](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/leaf.eo)
Лист необходим для обозначения конца в дереве. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      leaf.empty
      "%b"
```
*Результат: True*

#### [node](https://github.com/HSE-Eolang/sandbox-examples/blob/main/eo/node.eo)
Узел дерева, содержащий некоторое значение и два других узла или листа. [Вернуться](#examples-for-eolang-objects)

*Пример 1*
```
[args...] > app
  stdout > @
    sprintf
      value.
        node
          5
          leaf
          leaf
      "%d"
```
*Результат: 5*

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
