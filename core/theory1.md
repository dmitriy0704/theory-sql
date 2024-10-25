# РЕЛЯЦИОННЫЕ БАЗЫ ДАННЫХ

База данных - совокупность взаимосвязанных данных, организованных в соответствии
со схемой базы данных таким образом, чтобы с ними мог работать пользователь.

## Реляционная модель

_**Основные понятия:**_

- тип данных;
- домен - столбцы:
- атрибут - заголовок столбца;
- кортеж - строки таблицы;
- первичный ключ - id;
- отношение - таблица.


## Тип данных. Домен

Обычно в современных реляционных базах данных допускается хранение символьных
данных с фиксированной или переменной длиной, числовых данных, включая целые
числа различного размера, вещественные числа с плавающей или фиксированной
точностью, битовые данные, «темпоральные» данных (такие, как дата, время или
временной интервал). 

Кроме того, многие СУБД поддерживают хранение
пространственных и слабоструктурированных данных в формате XML или JSON.
Достаточно активно развивается подход к расширению возможностей реляционных
систем абстрактными типами данных. Например, в базе данных PostgreSQL
поддерживается хранение данных специального типа «деньги».

Типизация хранимых значений не просто указывает на размерность в байтах, которую
должна выделить система для размещения в памяти того или иного значения.
Типизация также определяет, какие операции могут быть осуществлены с теми или
иными данными.

Таким образом, понятие тип данных интегрирует в себе три компоненты:

- ограничение множества принадлежащих типу значений;
- определение применяемых к типу набора операций;
- определение способа отображения значений типа.

**_Домен_**

В самом общем виде домен определяется заданием некоторого базового типа данных,
к которому относятся элементы домена, и произвольного логического выражения,
применяемого к элементу типа данных. Если вычисление этого логического выражения
дает результат «истина>>, то элемент данных является элементом домена. Домен не
подменяет понятие типизации, а выступает в качестве дополнительного ограничителя
обрабатываемой в базе данных информации.

Наиболее правильной интуитивной трактовкой понятия домена является понимание
домена как допустимого потенциального **_множества значений данного типа_**. 
Например, домен «Имена» в примере с сотрудниками определен на базовом типе 
строк символов, но в число его значений могут входить только те строки, которые 
могут изображать имя (в частности, такие строки не могут начинаться с мягкого
знака).

## Отношение

Отношение R состоит из _**схемы**_ и _**тела**_.

**Схема** Н отношения R - конечное множество упорядоченных пар вида(Ai, Ti),
где Ai - имя атрибута, а Ti - имя домена, i = 1, ... , п. По определению
требуется, чтобы все имена атрибутов в заголовке отношения были
различными (уникальными).

Тело В отношения R - множество кортежей t.

Кортеж t, соответствующий схеме Н - множество упорядоченных пар вида (Ai, vi),
где vi - допустимое значение домена Ti.

Количество кортежей называют кардинальным числом отношения (кардинальностью),
или мощностью отношения. Количество атрибутов называют степенью, или «арностью»
отношения.

В классических реляционных базах данных после определения схемы изменяются
только отношения-экземпляры. В них могут появляться новые и удаляться или
модифицироваться существующие кортежи. Однако во многих реализациях допускается
и изменение схемы базы данных, т.е. определение новых и изменение существующих
схем отношения. Это принято называть эволюцией схемы базы данных.

Упрощенным представлением отношения является таблица, заголовком которой
является схема отношения, а строками - кортежи отношения-экземпляра; в этом
случае имена атрибутов именуют столбцы этой таблицы. Поэтому иногда говорят
«столбец таблицы», имея в виду «атрибут отношения».