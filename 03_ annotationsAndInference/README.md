Type Annotations (Аннотации Типов) - Подсказываем TypeScript тип данных для переменной
Type Inference - TypeScript - сам определяет тип данных

"Можно не писать типы данных" так как ts сам поймет тип данных если сразу задекларировать и инициализировать перемееную

TypeScript определил тип данных number(Для проверки можно навести на название перменной)

```typescript
let oranges = 5;
```

Если заделарировать , но не инициализировать переменную сразу, то ts не поймет тип данных и присвоет тип данных any

```typescript
let oranges;
oranges = 5;
```

---

Функции

```typescript
const logNumber: (i: number) => void = (i: number) => {
  console.log(i);
};
```

(: (i: number) => void) после названия функции(logNumber) - это аннотация которая говорит что входной параметр i будет типа number и фунция ничего не возвращает (void) , все что дальше , как в обычно arrow func В js

---

## Когда необходимо указывать тип данных

### 1)Function returns the 'any' type

JSON.parse - возвращает тип данных any (Любой тип данных)

```typescript
const json = '{"x": 10 , "y": 20}';
const coordinates = JSON.parse(json);
```

JSON.parse возвращал тип данных объекта , нужно добавить аннотацию

```typescript
const json = '{"x": 10 , "y": 20}';
const coordinates: { x: number; y: number } = JSON.parse(json);
```

---

### 2)When we declare a variable on one line and initialize it later

Отложенная инициализация

isTwo Будет с типом данных any , так как проинициализирвоана после декларации

```TypeScript
let words = ['one', 'two', 'three'];
let isTwo;

for (let i = 0; i < words.length; i++) {
  if (words[i] === 'two') {
    isTwo = true;
  }
}
```

TypeScript поймет тип данных если добавить аннотацию или присвоить булиновское значение false

```TypeScript
let isTwo: boolen;
//or
let isTWo = false
```

---

### 3)Variables whoes type can`t be inferred

positiveNumber хранит в себе значение false => имеет тип данных boolean

По заданию , если масииве есть нужное нам число , то нужно сохранить его в переменной positiveNumber (нельзя присвоить типу данных boolean значение типа данных number)

```TypeScript
let myNumbers = [-10, -1, 12];
let positiveNumber= false;

for (let i = 0; i < myNumbers.length; i++) {
  if (myNumbers[i] > 0) {
    positiveNumber = myNumbers[i];
  }
}
```

let positiveNumber: boolean | number; - у переменной может быть 2 типа данных -boolean и number

```typescript
let myNumbers = [-10, -1, 12];
let positiveNumber: boolean | number = false;

for (let i = 0; i < myNumbers.length; i++) {
  if (myNumbers[i] > 0) {
    positiveNumber = myNumbers[i];
  }
}
```
