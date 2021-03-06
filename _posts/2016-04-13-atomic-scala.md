---
layout: post
title:  "Книга Atomic Scala и наивные впечатления от языка"
permalink: /atomic-scala
categories: scala books
---

![cover](/assets/static/atomic-scala.jpg)

Прочитал книжку [о Скале][book], заодно немного поковырял язык. Это
первая книжка, прочитанная мной на [Киндле](/kindle).

[book]: http://www.atomicscala.com/

Понравилась структура. Примерно 30 глав -- атомов -- по разным
аспектам языка. Автор -- плюсовик со стажем, по ходу действия дает
полезные советы, объясняет ООП-паттерны, затрагивает ФП.

Ближе к концу серия глав о монадах. Описаны `Either`, `Maybe
(Option)`, `Try`. Понравилось, что автор ни разу не употребил термин
"монада". Это камень в огород Хаскела, где монады начинаются с
аппликативных функторов.

К книжке прилагается набор примеров с тестами, доками. Все добротно и
на совесть, [лежит на Гитхабе][github]. Автор очень ответственно
подошел к делу. По сути, у него не просто книга, а сообщество вокруг
нее. Покупка книги -- своего рода членский билет.

[github]: https://github.com/AtomicScala

Я немного повозился с языком и могу сказать следующее. Прошу прощения
за дилетантский взгляд, все пункты ниже могут оказаться ложью и
провокацией.

- Сперва язык кажется очень простым, вроде Гоу или Питона, только с
  типизацией. Примерно к середине книги понимаешь, что все не так
  просто.

- Некоторые элементы дизайна очень странны. Например, составные
  объекты, когда объявлены класс и объект с одинаковыми именами. Я
  долго ломал голову, пока наконец понял, что таким образом
  формируется метакласс. Можно было сделать удобнее.

- Избыточные модификаторы вроде `sealed`, `implict`. Мне кажется, их
  впихнули задним числом, получилось не очень. Скала вроде стремится в
  минимализму, а получается опять Джава.

- Самая жесть с параметрическими трейтами. Напоминает Хаскел, но очень
  неуклюже. В книге есть пример как построить модель рецепта
  мороженного. 100 строк на декларацию трейтов, затем дикий микс из
  них. В конце автор пишет, что вот как хорошо получилось. Я бы убился
  поддерживать это мороженное.

- Скала все-таки ООП-язык, хоть и с функциональным уклоном. Насколько
  я понял, в экосистеме Скалы не поощрается процедурно-модульное
  программирование. Получается `yet another oop language`.

![picture](http://41.media.tumblr.com/393d852bf9be9b339e76e4bc393aad34/tumblr_o56sc7ASY31ugyavxo1_1280.jpg)

~~~

Hieronymus Bosch “A visual guide to the Scala language” oil on oak
panels, 1490-1510.

The left panel shows the functional features, the main one describes
the type system, and the right the object oriented parts.

~~~

Все же, интерес к языку у меня возник, и при случае был бы рад принять
участие в проекте на нем.

Выборочные цитаты из книги с моим вольным переводом.

О ручной итерации:

> Notice that `map` and `reduce` take care of the iteration code that
> you normally write by hand. Although managing the iteration yourself
> might not seem like much effort, it’s one more error-prone detail,
> one more place to make a mistake (and since they’re so “obvious,”
> such mistakes are particularly hard to find).

*Обратите внимание, `map` и `reduce` сами заботятся об итерации. В
императивном подходе итерация ложится на ваши плечи. Это кажется
пустяком, но увеличивает код и вероятность ошибки. Баг в ручной
итерации замечаешь в последнюю очередь.*

О комментариях:

> Comments should add new information that isn’t obvious from reading
> the code. If the comments just repeat what the code says, it becomes
> annoying (and people start ignoring your comments). When the code
> changes, programmers often forget to update comments, so it’s a good
> practice to use comments judiciously, mainly for highlighting tricky
> aspects of your code.

*Комментарии должны дополнять код, объяснять неочевидные моменты.
Раздражает, когда комментарий повторяет в точности то, что делает
код. Люди проигнорируют их. Когда код меняется, программист часто
забывает обновить комментарий. Комментируйте вдумчиво, в основном
чтобы объяснить неочевидные приемы в коде.*

О паттерн-матчинге:

> Notice that pattern matching can overlap with the functionality of
> if statements. Because pattern matching is more flexible and
> powerful, we prefer it over if statements when there’s a choice.

*Замечу, что паттер-матчинг похож на условное выражение. Первый более
гибок, поэтому будем использовать его вместо условия при удобном
случае.*

В целом, книжка зачет, не жалею потраченного времени.
