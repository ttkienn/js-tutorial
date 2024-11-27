## Cài Đặt IDE

### 1. **Visual Studio Code (VS Code)**

Visual Studio Code (VS Code) là một trong những IDE phổ biến nhất cho JavaScript vì tính năng mạnh mẽ và hỗ trợ nhiều tiện ích mở rộng.

- **Cài đặt:**
  1. Tải về Visual Studio Code tại: [https://code.visualstudio.com/](https://code.visualstudio.com/).
  2. Cài đặt và mở VS Code.

- **Cài đặt tiện ích mở rộng (Extension) cho JavaScript:**
  1. Mở VS Code và vào phần Extensions (hoặc nhấn `Ctrl+Shift+X`).
  2. Tìm kiếm và cài đặt các tiện ích như `ESLint`, `Prettier`, hoặc `JavaScript (ES6)` để hỗ trợ viết mã dễ dàng hơn.

### 2. **WebStorm**

WebStorm là một IDE mạnh mẽ của JetBrains dành cho phát triển JavaScript, với nhiều tính năng hữu ích như gợi ý mã, kiểm tra lỗi và hỗ trợ framework.

- **Cài đặt:**
  1. Tải về WebStorm tại: [https://www.jetbrains.com/webstorm/](https://www.jetbrains.com/webstorm/).
  2. Cài đặt và mở WebStorm.

### 3. **Sublime Text**

Sublime Text là một trình soạn thảo mã nhẹ và mạnh mẽ, hỗ trợ nhiều ngôn ngữ lập trình, bao gồm JavaScript.

- **Cài đặt:**
  1. Tải về Sublime Text tại: [https://www.sublimetext.com/](https://www.sublimetext.com/).
  2. Cài đặt và mở Sublime Text.

## Cách Chạy Code JavaScript

Để chạy mã JavaScript, có thể làm theo các phương pháp sau:

### 1. **Sử dụng Trình Duyệt (Browser)**

JavaScript được hỗ trợ trực tiếp trong các trình duyệt web, vì vậy có thể chạy mã JavaScript ngay trên trình duyệt của mình.

- **Cách thực hiện:**
  1. Mở trình duyệt (Chrome, Firefox, Safari, v.v.).
  2. Mở DevTools bằng cách nhấn `F12` hoặc `Ctrl+Shift+I`.
  3. Chuyển đến tab **Console**.
  4. Nhập mã JavaScript và nhấn `Enter` để chạy.

### 2. **Sử dụng Node.js**

Node.js cho phép chạy mã JavaScript ngoài trình duyệt, rất hữu ích khi phát triển ứng dụng server-side.

- **Cài đặt Node.js:**
  1. Tải và cài đặt Node.js tại: [https://nodejs.org/](https://nodejs.org/).
  2. Sau khi cài đặt xong, mở Command Prompt (Windows) hoặc Terminal (Mac/Linux).
  3. Kiểm tra cài đặt Node.js bằng cách gõ lệnh `node -v` để kiểm tra phiên bản Node.js.

- **Chạy mã JavaScript:**
  1. Mở một trình soạn thảo mã như VS Code.
  2. Tạo một file JavaScript mới, ví dụ: `app.js`.
  3. Viết mã JavaScript trong file này.
  4. Mở Terminal hoặc Command Prompt và chạy lệnh:
     ```
     node app.js
     ```

---

## Mục Lục
1. [Variables](https://github.com/ttkienn/js-tutorial/blob/main/variable.md)
2. [Template Literals](https://github.com/ttkienn/js-tutorial/blob/main/template_literals.md)
3. [Arrow Function](https://github.com/ttkienn/js-tutorial/blob/main/arrow_function.md)
4. [Giá trị mặc định của tham số hàm](https://github.com/ttkienn/js-tutorial/blob/main/default_parametor.md)
5. [Destructuring Object và Array](https://github.com/ttkienn/js-tutorial/blob/main/destructuring_object_and_array.md)
6. [Tham số hàm](https://github.com/ttkienn/js-tutorial/blob/main/function_rest_parametor.md)
7. [Array Methods: map, filter, reduce](https://github.com/ttkienn/js-tutorial/blob/main/array_methods.md)
8. [Spread Operator và Rest Operator](https://github.com/ttkienn/js-tutorial/blob/main/spread_operator_and_rest_operator.md)
9. [Function Rest Parameter](https://github.com/ttkienn/js-tutorial/blob/main/function_rest_parametor.md)
10. [Object Properties Spreading](https://github.com/ttkienn/js-tutorial/blob/main/object_properties_spreading.md)
11. [Object Property Shorthand](https://github.com/ttkienn/js-tutorial/blob/main/object_property_shorthand.md)

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
   const numbers = [1, 2, 3

, 4, 5];
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
