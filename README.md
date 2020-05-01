# TypeScript style guide

## General rules

### General naming rules:
- Avoid contractions and acronyms if it's not common or well-known (e.g. `Event`)
- Identifiers should be meaningful (e.g. `vertexArray` or `loadedPage`, no `abc`, `number`)
- Use abbreviations for naming if it's possible and meaningful (e.g. `request` -> `req`)
	
### Variables, fields:
- Use `camelCase` for naming variables and fields
- Use `noun` for naming variables and fields (e.g. `projectName`, `userCoverUrl`)
- Use `question` for boolean fields and variables (`isDisposed`, `hasCar`, `areValid`)
- Use `const` and `let` for declaration variables
- Always use type for declaration
- Don't use underscore prefix `_` for declaration private fields

```typescript
let url: string = 'http://google.ru'

const initialSumValue: number = 0;
```

### Functions, methods
- Use `camelCase` for naming variables and fields
- Use `verb` for naming variables and fields (e.g. `getDescription`, `updateCar`)
- Use `question` for boolean functions and methods (`isDisposed`, `hasCar`, `areValid`)
- Always use type for declaration (exception only for cycle iterator anonymous functions)
- Always use type for arguments (exception only for cycle iterator anonymous functions)
- Don't use underscore prefix `_` for declaration private methods
- Use `function` declaration for separate functions. In case you need anonymous function or you need to pass callback use arrow function

```typescript
function sum(a: number, b: number): number {
  return a + b;
}

const a: number[] = [1, 2, 3].map(i => i * 2);
```

### Classes

- Use `PascalCase` for naming classes
- Use `noun` for naming variables and fields (e.g. `Car`, `CarResDto`)
- Use classes for:
    - Describing Entities
    - Describing DataTypeObjects (e.g. request bodies)
- Use such modifiers order:
    - private readonly fields
    - private fields
    - public fields
    - constructor
    - private methods
    - public methods
- Use readonly if possible

```typescript
class Bus {
    name: string;
    beep() { }
}
```

### Interfaces
- Use `PascalCase` for naming interfaces
- Don't use `I` prefix
- Use `noun` for naming variables and fields (e.g. `Car`)
- Use interfaces for:
    - Implementing classes
    
```typescript
interface Car {
    name: string;
    beep(): void;
} 

class Bus implements Car {
    name: string;
    beep() { console.log('something') }
}
```

### Types
- Use `PascalCase` for naming types
- Use `Type` postfix
- Use `noun` for naming variables and fields (e.g. `CarNameType`)
- Use types for:
    - Describing results of methods, functions or typing variables and fields
- Create reusable types for making union types

```typescript
type CarNameType = string | { name: string };
```

### Enums
- Use `PascalCase` for naming enums
- Use `Enum` postfix
- Use `noun` for naming variables and fields (e.g. `CarIdEnum`)
- Always set values for keys

```typescript
enum CarIdEnum {
    Audi = 1,
    BMW = 2,
}
```

### Namespaces

- Don't use it

### Array
- Always use `[]`
- Don't use `Array` directive
- If you need simple iterator use `for of` construction

```typescript
enum CarIdEnum {
    Audi = 1,
    BMW = 2,
}

type CarType = {
    id: CarIdEnum,
}

const cars: CarType[] = [{ id: CarIdEnum.Audi }];

for (const car of cars) {
    console.log(car.id);
}
```

### Formatting and other important rules

- Use `2 spaces` indentation
- Use single quotes `'` for all the strings (imports, variables, etc.)
- Max width of line is `80` symbols
- Use `;` at the end of line

### Filenames

- Use `camelCase` for naming files and folders
- Use `.` for describing type of file's content (e.g. `.interface.ts`, `.controller.ts`, `.dto.ts`):
    - interface
    - type
    - enum
    - dto
    - req, res
    - controller
    - service
    - module

```
auth.service.ts
carId.enum.ts
car.req.dto.ts
```


### Inspired by:

- https://github.com/phygitalism/c-sharp-style-guide
- https://github.com/basarat/typescript-book/blob/master/docs/styleguide/styleguide.md
- https://github.com/airbnb/javascript
- https://adidas.github.io/contributing/typescript-coding-guidelines/
