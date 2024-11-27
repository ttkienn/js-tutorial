
# **Giá trị mặc định của tham số hàm trong JavaScript**

## **1. Cách sử dụng giá trị mặc định**
Cú pháp cơ bản để đặt giá trị mặc định:

```javascript
function functionName(parameter = defaultValue) {
  // Thân hàm
}
```

- **`parameter`**: tên tham số.
- **`defaultValue`**: giá trị mặc định được gán nếu tham số không được truyền hoặc được truyền là `undefined`.

### Ví dụ:
```javascript
function greet(name = "Stranger") {
  console.log(`Hello, ${name}!`);
}

greet(); // Hello, Stranger!
greet("Kien"); // Hello, Kien!
```

---

## **2. Kết hợp nhiều tham số**

### Ví dụ:
```javascript
function multiply(a = 1, b = 1) {
  return a * b;
}

console.log(multiply()); // 1 (vì cả `a` và `b` đều có giá trị mặc định là 1)
console.log(multiply(5)); // 5 (vì `b` sử dụng giá trị mặc định là 1)
console.log(multiply(5, 3)); // 15
```

---

## **3. Sử dụng biểu thức trong giá trị mặc định**
Giá trị mặc định có thể là một biểu thức phức tạp, không chỉ là một giá trị đơn giản:

### Ví dụ:
```javascript
function calculateArea(length = 1, width = length * 2) {
  return length * width;
}

console.log(calculateArea()); // 2 (length = 1, width = 2)
console.log(calculateArea(3)); // 18 (length = 3, width = 6)
console.log(calculateArea(3, 4)); // 12 (length = 3, width = 4)
```

---

## **4. Phân biệt với `undefined`**
Giá trị mặc định chỉ được sử dụng khi tham số **không được truyền** hoặc **truyền giá trị là `undefined`**.

### Ví dụ:
```javascript
function test(param = "Default") {
  console.log(param);
}

test(); // Default (tham số không được truyền)
test(undefined); // Default (tham số là undefined)
test(null); // null (tham số có giá trị cụ thể là null)
```

---

## **5. Giá trị mặc định với hàm và đối tượng**

### Ví dụ với hàm:
```javascript
function sayHello(callback = () => console.log("Default Hello!")) {
  callback();
}

sayHello(); // Default Hello!
sayHello(() => console.log("Custom Hello!")); // Custom Hello!
```

### Ví dụ với mảng và đối tượng:
```javascript
function processArray(arr = [1, 2, 3]) {
  console.log(arr);
}

processArray(); // [1, 2, 3]
processArray([10, 20]); // [10, 20]

function processObject(obj = { name: "Alice", age: 25 }) {
  console.log(obj);
}

processObject(); // { name: "Alice", age: 25 }
processObject({ name: "Bob" }); // { name: "Bob" }
```

---

## **6. Thứ tự tham số có giá trị mặc định**
Khi sử dụng các tham số có giá trị mặc định, chúng thường được đặt **sau các tham số không có giá trị mặc định**. Điều này giúp tránh việc truyền nhầm lẫn.

### Ví dụ tốt:
```javascript
function logMessage(message, level = "INFO") {
  console.log(`[${level}] ${message}`);
}

logMessage("System started"); // [INFO] System started
logMessage("System error", "ERROR"); // [ERROR] System error
```

### Ví dụ không tốt:
```javascript
function logMessage(level = "INFO", message) {
  console.log(`[${level}] ${message}`);
}

logMessage("System started"); // [INFO] undefined
```

---

## **7. So sánh với cách cũ**
Trước ES6, bạn phải sử dụng logic kiểm tra thủ công để đặt giá trị mặc định:

### Cách cũ:
```javascript
function oldWay(a, b) {
  a = a || 1;
  b = b || 1;
  return a + b;
}

console.log(oldWay()); // 2
```

### Cách mới với ES6:
```javascript
function newWay(a = 1, b = 1) {
  return a + b;
}

console.log(newWay()); // 2
```

Cách mới ngắn gọn, dễ đọc hơn và tránh lỗi khi giá trị truyền vào là `0` (vì `0 || 1` sẽ trả về `1` trong cách cũ).

