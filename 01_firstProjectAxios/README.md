Создание package.json Файла : npm init -y
Axios : npm install axios
Компиляция TypeScript кода : tsc index.ts

до tsc index.ts :

```typescript
import axios from 'axios';

const url = 'https://jsonplaceholder.typicode.com/todosts-/1';
axios.get(url).then((response) => {
  console.log(response.data);
});
```

после tsc index.ts , создался index.js файл :

```javascript
'use strict';
exports.__esModule = true;
var axios_1 = require('axios');
var url = 'https://jsonplaceholder.typicode.com/todos/1';
axios_1['default'].get(url).then(function (response) {
  console.log(response.data);
});
```

node index.js чтобы запустить код

---

Для компиляции и запуска ts кода без создания js файла : ts-node index.ts

---

interface

```TypeScript
const url = 'https://jsonplaceholder.typicode.com/todos/1';

//Указываем свойсво где хранятся название и тип данных переменной
interface Todo {
  id: number;
  title: string;
  completed: boolean;
}

axios.get(url).then((response) => {
  //response.data Объект типа Todo
  const todo = response.data as Todo;

  //если из todo берется свойство которого нету то ts покажет ошибку
  const id = todo.ID; // const id = todo.id;
  const title = todo.Title; //const title = todo.title;
  const finished = todo.completed; //const finished = todo.completed;
});
```

---

Отлов ошибок с типами данных

```TypeScript
const logTodo = (id: number, title: string, completed: boolean) => {
  console.log(`
    The todo with Id : ${id}
    Has a title of : ${title}
    Is it completed : ${completed}
  `);
```

Если при вызове функции приходят не те типы данных , подчекнется ошибка на месте вызова функции
