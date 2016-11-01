# Свойства
## display: flex | inline-flex;
> Применяется к: родительскому элементу flex-контейнера.

    display: other values | flex | inline-flex;

* CSS-столбцы columns не работают с flex-контейнером
* float, clear и vertical-align не работают с flex-элементами

## flex-direction

> Применяется к: родительскому элементу flex-контейнера.

    flex-direction: row | row-reverse | column | column-reverse

* row (по умолчанию): слева направо для ltr, справа налево для rtl;
* row-reverse: справа налево для ltr, слева направо для rtl;
* column: аналогично row, сверху вниз;
* column-reverse: аналогично row-reverse, снизу вверх.

## flex-wrap

> Применяется к: родительскому элементу flex-контейнера/.

    flex-wrap: nowrap | wrap | wrap-reverse

* nowrap (по умолчанию): однострочный / слева направо для ltr, справа налево для rtl;
* wrap: многострочный / слева направо для ltr, справа налево для rtl;
* wrap-reverse: многострочный / справа налево для ltr, слева направо для rtl.

## flex-flow

> Применяется к: родительскому элементу flex-контейнера.

    flex-flow: <'flex-direction'> || <'flex-wrap'>

## justify-content

> Применяется к: родительскому элементу flex-контейнера.


    justify-content: flex-start | flex-end | center | space-between | space-around

* flex-start (по умолчанию): элементы сдвигаются к началу строки;
* flex-end: элементы сдвигаются к концу строки;
* center: элементы выравниваются по центру строки;
* space-between: элементы распределяются равномерно (первый элемент в начале строки, последний — в конце);
* space-around: элементы распределяются равномерно с равным расстоянием между собой и границами строки.

## align-items

> Применяется к: родительскому элементу flex-контейнера.

    align-items: flex-start | flex-end | center | baseline | stretch

* flex-start: граница cross-start для элементов располагается на позиции cross-start;
* flex-end: граница cross-end для элементов располагается на позиции cross-end;
* center: элементы выравниваются по центру поперечной оси;
* baseline: элементы выравниваются по своей базовой линии;
stretch (по умолчанию): элементы растягиваютcя, заполняя контейнер (с учётом  min-width/max-width).
