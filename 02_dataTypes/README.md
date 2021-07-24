# Типы данных

## Примитивные типы :

-number
-boolean
-void/undefined
-string
-symbol
-null

## Объектные типы :

-functions
-classes
-arrays
-objects

---

Плюсы Типизации При объявлении типа данных у переменной то при дальнейшей работе с кодом , ts будет подсказывать функции этого типа данных или показывать что такого метода нету

```TypeScript
//Принадлежит типу данных Date(Класса Date)
const today = new Date()

today.getDate()

today.sadsadsad() // error



class Color {

}
//Принадлежит типу данных color(Класса color)
const red = new Color()
```
