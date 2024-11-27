## Mục Lục
1. [Template Literals](#template-literals)
2. [Tagged Template Literals](#tagged-template-literals)
3. [Arrow Function](#arrow-function)
4. [Giá trị mặc định của tham số hàm](#giá-trị-mặc-định-của-tham-số-hàm)
5. [Destructuring Object và Array](#destructuring-object-và-array)
6. [Tham số hàm](#tham-số-hàm)
7. [Array Methods: map, filter, reduce](#array-methods-map-filter-reduce)
8. [Spread Operator và Rest Operator](#spread-operator-và-rest-operator)
9. [Function Rest Parameter](#function-rest-parameter)
10. [Object Properties Spreading](#object-properties-spreading)
11. [Object Property Shorthand](#object-property-shorthand)

---

## Template Literals
**Template literals** là cách mới để tạo chuỗi trong JavaScript, giúp dễ dàng nhúng biến, biểu thức vào chuỗi. Sử dụng dấu backticks (`` ` ``) thay vì dấu nháy đơn (`'`) hoặc nháy kép (`"`).

### Cú pháp:
```javascript
const name = "Alice";
const message = `Hello, ${name}!`;
console.log(message); // "Hello, Alice!"
```

### Tính năng:
1. **Đa dòng (Multiline strings)**:
   ```javascript
   const text = `This is a
   multi-line string.`;
   console.log(text);
   ```
   
2. **Chèn biểu thức vào chuỗi**:
   ```javascript
   const x = 5;
   const y = 10;
   const result = `Sum of x and y is: ${x + y}`;
   console.log(result); // "Sum of x and y is: 15"
   ```

---

## Tagged Template Literals

**Tagged template literals** cho phép điều khiển cách chuỗi được xử lý, thay vì chỉ đơn giản là chèn các giá trị vào chuỗi. Hàm tag sẽ nhận các phần của chuỗi và các giá trị chèn vào (biểu thức trong `${}`) và xử lý chúng theo cách muốn.

### Cú pháp:
```javascript
tagFunction`template literal ${expression}`;
```

### Ví dụ cơ bản:
```javascript
function customTag(strings, ...expressions) {
  return strings.reduce((result, str, i) => result + str + (expressions[i] ? expressions[i].toUpperCase() : ''), '');
}

const name = "Alice";
const message = customTag`Hello, ${name}!`;
console.log(message); // "Hello, ALICE!"
```

---

## Arrow Function

**Arrow functions** là cách viết hàm ngắn gọn trong JavaScript, sử dụng cú pháp `() => {}`. Nó có nhiều ưu điểm, bao gồm không có `this` riêng và dễ dàng xử lý các hàm ngắn gọn.

### Cú pháp:
```javascript
const add = (a, b) => a + b;
console.log(add(2, 3)); // 5
```

---

## Giá trị mặc định của tham số hàm

JavaScript cho phép chỉ định giá trị mặc định cho tham số hàm nếu người dùng không truyền giá trị vào.

### Cú pháp:
```javascript
function greet(name = "Guest") {
  console.log(`Hello, ${name}`);
}

greet();      // "Hello, Guest"
greet("Alice"); // "Hello, Alice"
```

---

## Destructuring Object và Array

**Destructuring** giúp dễ dàng trích xuất các giá trị từ mảng hoặc đối tượng vào các biến riêng biệt.

### Destructuring Object:
```javascript
const person = { name: "Alice", age: 25 };
const { name, age } = person;
console.log(name, age); // Alice 25
```

### Destructuring Array:
```javascript
const numbers = [1, 2, 3];
const [a, b, c] = numbers;
console.log(a, b, c); // 1 2 3
```

---

## Tham số hàm

Trong JavaScript, có thể khai báo hàm với một hoặc nhiều tham số và có thể xử lý chúng trong thân hàm.

### Ví dụ:
```javascript
function greet(name, age) {
  console.log(`Hello, ${name}! You are ${age} years old.`);
}

greet("Alice", 25); // Hello, Alice! You are 25 years old.
```

---

## Array Methods: map, filter, reduce

1. **map**: Áp dụng một hàm cho từng phần tử của mảng và trả về mảng mới.
   ```javascript
   const numbers = [1, 2, 3];
   const doubled = numbers.map(num => num * 2);
   console.log(doubled); // [2, 4, 6]
   ```

2. **filter**: Lọc các phần tử của mảng thỏa mãn điều kiện.
   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   const even = numbers.filter(num => num % 2 === 0);
   console.log(even); // [2, 4]
   ```

3. **reduce**: Tính toán một giá trị duy nhất từ tất cả các phần tử của mảng.
   ```javascript
   const numbers = [1, 2, 3];
   const sum = numbers.reduce((acc, num) => acc + num, 0);
   console.log(sum); // 6
   ```

---

## Spread Operator và Rest Operator

- **Spread operator (`...`)** giúp "spread" (mở rộng) một mảng hoặc đối tượng thành các phần tử.
- **Rest operator (`...`)** dùng để gom nhóm các tham số lại thành một mảng.

### Spread operator:
```javascript
const arr1 = [1, 2];
const arr2 = [...arr1, 3, 4];
console.log(arr2); // [1, 2, 3, 4]
```

### Rest parameter:
```javascript
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3)); // 6
```

---

## Function Rest Parameter

Rest parameters (`...`) cho phép hàm nhận một số lượng tham số không xác định và gom chúng vào một mảng.

### Cú pháp:
```javascript
function greet(...names) {
  console.log(`Hello, ${names.join(", ")}`);
}

greet("Alice", "Bob", "Charlie"); // "Hello, Alice, Bob, Charlie"
```

---

## Object Properties Spreading

**Object properties spreading** cho phép sao chép hoặc kết hợp các thuộc tính của đối tượng này vào đối tượng khác.

### Ví dụ:
```javascript
const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 };
console.log(obj2); // { a: 1, b: 2, c: 3 }
```

---

## Object Property Shorthand

**Object property shorthand** giúp rút gọn cách khai báo thuộc tính của đối tượng khi tên thuộc tính và biến giống nhau.

### Ví dụ:
```javascript
const name = "Alice";
const age = 25;

const person = { name, age };
console.log(person); // { name: "Alice", age: 25 }
```

---
