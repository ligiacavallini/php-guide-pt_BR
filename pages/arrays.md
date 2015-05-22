---
layout: page
title: "Arrays"
description: ""
---
{% include JB/setup %}

{% include menu/arrays.md %}

* * * 

## Fatos

* Chaves numéricas, tanto as definidas automaticamente como as definidas manualmente, são ótimas quando você não se importa com a forma na qual os dados serão indexados
* Frequentemente arrays associativos são utilizados com banco de dados, ou quando deve haver alguma associação chave=>valor
* Arrays multidimensionais (arrays de arrays) podem conter uma grande quantidade de dados, mas também podem ser complicados de serem acessados
* Chaves contendo apenas dígitos são convertidas implicitamente para inteiros
* Chaves de array são case-sensitive, mas não type-sensitive


* * *

## Iteração


* `foreach()` opera em uma cópia do array
* `foreach($array AS &$value) { … }`
* `end()` – move o ponteiro do array para o último elemento
* `key()` - obtém a chave da posição atual
* `next()` – avança o ponteiro do array em uma posição, e então retorna o valor atual
* `prev()` – volta o ponteiro do array em uma posição, e então retorna o valor atual
* `reset()` – redefine o ponteiro do array para o inicio do array
* `each()` – retorna a chave e o valor atual do array, então itera
* `current()`


* * *

## Ordenação


* `bool sort ( array &$array [, int $sort_flags = SORT_REGULAR ] )`
   * `SORT_REGULAR`
   * `SORT_NUMERIC`
   * `SORT_STRING`
* `rsort()`
* `ksort()`
* `asort()`
* `usort()`
* `bool natsort ( array &$array )`
* `bool shuffle ( array &$array )`


* * *

## Pilhas e Filas


* Pilha, implementando LIFO
   * `int array_push ( array &$array , mixed $var [, mixed $... ] )`
   * `mixed array_pop ( array &$array )`
* FIFO
   * `int array_unshift ( array &$array , mixed $var [, mixed $... ] )`
   * `mixed array_shift ( array &$array )`


* * *

## Funções


[http://php.net/array/](http://php.net/manual/pt_BR/language.types.array.php)

* `bool array_walk ( array &$array , callback $funcname [, mixed $userdata ] )`
* `bool array_walk_recursive ( array &$input , callback $funcname [, mixed $userdata ] )`
* `array array_keys ( array $input [, mixed $search_value [, bool $strict = false ]] )`
* `array array_values ( array $input )`
* `array array_change_key_case ( array $input [, int $case = CASE_LOWER ] )`
* `array array_merge ( array $array1 [, array $array2 [, array $... ]] )`
* `array array_merge_recursive ( array $array1 [, array $... ] )`
* `array array_splice ( array &$input , int $offset [, int $length = 0 [, mixed $replacement ]] )` - retira um pedaço de um array
* `bool array_key_exists ( mixed $key , array $search )`
* `array array_flip ( array $trans )`
* `array array_reverse ( array $array [, bool $preserve_keys = false ] )`
* `array array_combine ( array $keys , array $values )`
* `mixed array_rand ( array $input [, int $num_req = 1 ] )`
* `array array_diff ( array $array1 , array $array2 [, array $ ... ] )`
* `array array_intersect ( array $array1 , array $array2 [, array $ ... ] )`
* `bool in_array ( mixed $needle , array $haystack [, bool $strict ] )`
* `array list ( mixed $varname [, mixed $... ] )`
* `int count ( mixed $var [, int $mode = COUNT_NORMAL ] )`
* `int extract ( array $var_array [, int $extract_type = EXTR_OVERWRITE [, string $prefix ]] )`


* * *

## SPL, Objetos como arrays

* [http://www.php.net/manual/pt_BR/class.arrayobject.php](http://www.php.net/manual/pt_BR/class.arrayobject.php)
* [http://www.php.net/manual/pt_BR/class.arrayiterator.php](http://www.php.net/manual/pt_BR/class.arrayiterator.php)
* [http://www.php.net/manual/pt_BR/class.recursivearrayiterator.php](http://www.php.net/manual/pt_BR/class.recursivearrayiterator.php)

