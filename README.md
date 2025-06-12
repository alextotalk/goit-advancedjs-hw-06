# TypeScript Advanced Homework - Базові типи та Generics

Це домашнє завдання з розширеного TypeScript, яке включає роботу з базовими типами та generics. Всі завдання виконано з правильними типізаціями.


## 🔧 Базові типи - Рішення

### Завдання 1: Типізація змінних
```typescript
let age: number = 50;
let name: string = 'Max';
let toggle: boolean = true;
let empty: null = null;
let notInitialize: undefined;
let callback = (a: number): number => { return 100 + a };
```

### Завдання 2: Тип any
```typescript
let anything: any = -20;
anything = 'Text';
anything = {};
```

### Завдання 3: Unknown тип з перевіркою
```typescript
let some: unknown;
some = 'Text';
let str: string;

if (typeof some === 'string') {
  str = some;
}
```

### Завдання 4: Кортежі (Tuples)
```typescript
let person: [string, number] = ['Max', 21];
```

### Завдання 5: Union та Literal типи
```typescript
let union: string | number;
let literal: 'enable' | 'disable';
```

### Завдання 6: Типізація функцій
```typescript
function showMessage(message: string): void {
  console.log(message);
}

function calc(num1: number, num2: number): number {
  return num1 + num2;
}

function customError(): never {
  throw new Error('Error');
}
```

### Завдання 7: Enum та функції
```typescript
enum DaysOfWeek {
  Monday,
  Tuesday,
  Wednesday,
  Thursday,
  Friday,
  Saturday,
  Sunday
}

function isWeekend(day: DaysOfWeek): boolean {
  return day === DaysOfWeek.Saturday || day === DaysOfWeek.Sunday;
}
```

### Завдання 8: Union типи
```typescript
type Gender = "male" | "female";
const myGender: Gender = "male";
```

### Завдання 9: Типи об'єктів
```typescript
type Page = {
  title: string;
  likes: number;
  accounts: string[];
  status: 'open' | 'close';
  details?: {
    createAt: Date;
    updateAt: Date;
  };
};
```

## 🚀 Generics - Рішення

### Завдання 1: Generic Promise
```typescript
function getPromise(): Promise<[string, number]> {
  return new Promise((resolve) => {
    resolve(['Text', 50]);
  });
}
```

### Завдання 2: Pick utility type
```typescript
function compare(top: Pick<AllType, 'name' | 'color'>, bottom: Pick<AllType, 'position' | 'weight'>): AllType {
  return {
    name: top.name,
    color: top.color,
    position: bottom.position,
    weight: bottom.weight,
  }
}
```

### Завдання 3: Generic функції
```typescript
function merge<T, U>(objA: T, objB: U): T & U {
  return { ...objA, ...objB };
}
```

### Завдання 4: Generic класи
```typescript
interface PageProps {
  title: string;
}

class Component<T> {
  constructor (public props: T) {

  }
}

class Page extends Component<PageProps> {
  pageInfo () {
    console.log(this.props.title);
  }
}
```

### Завдання 5: Generic інтерфейси
```typescript
interface KeyValuePair<K, V> {
  key: K;
  value: V;
}
```

### Завдання 6: Partial utility type
```typescript
function createOrUpdateUser(initialValues: Partial<User>) {
  // Оновлення користувача
}
```

### Завдання 7: Record utility type
```typescript
const RoleDescription: Record<UserRole, string> = {
  admin: 'Admin User',
  editor: 'Editor User',
  guest: 'Guest User',
};
```

### Завдання 8: Omit utility type
```typescript
type Params = Omit<Form, 'errors'>;
```

## 📚 Використані концепції

### Базові типи:
- `number`, `string`, `boolean`, `null`, `undefined`
- `any` - для максимальної гнучкості
- `unknown` - безпечна альтернатива any з перевіркою типів
- `void` - для функцій, що не повертають значення
- `never` - для функцій, що ніколи не завершуються
- Tuples `[string, number]` - масиви з фіксованою структурою
- Union types `string | number` - об'єднання типів
- Literal types `'enable' | 'disable'` - конкретні значення
- Enum - перелічення констант

### Utility Types:
- `Pick<T, K>` - вибір конкретних полів з типу
- `Partial<T>` - робить всі поля опціональними
- `Record<K, V>` - створює об'єкт з ключами K і значеннями V
- `Omit<T, K>` - виключає поля K з типу T

### Generics:
- Generic функції `<T, U>`
- Generic класи `class Component<T>`
- Generic інтерфейси `interface KeyValuePair<K, V>`
- Intersection types `T & U`
- Promise типізація `Promise<[string, number]>`

## 🛠️ Запуск проекту

```bash
npm install
npx tsc --noEmit  # Перевірка типів без компіляції
```

Всі файли типізовані правильно та проходять перевірку TypeScript компілятора без помилок.