
# **Tham số hàm trong JavaScript**


## **1. Các loại tham số cơ bản**

### **1.1. Tham số cơ bản**

```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}

greet("Alice"); // Hello, Alice!
```

- **`name`** là tham số.
- **`"Alice"`** là đối số (giá trị truyền vào tham số).

---

### **1.2. Giá trị mặc định của tham số**
Giá trị mặc định sẽ được sử dụng nếu không truyền tham số hoặc tham số truyền vào là `undefined`.

```javascript
function greet(name = "Stranger") {
  console.log(`Hello, ${name}!`);
}

greet(); // Hello, Stranger!
greet("Bob"); // Hello, Bob!
```

---

### **1.3. Số lượng tham số linh hoạt**
JavaScript không yêu cầu số lượng tham số trong lời gọi hàm phải khớp với số tham số được khai báo.

#### Nếu truyền thiếu tham số:
Các tham số không được truyền sẽ có giá trị là `undefined`.

```javascript
function add(a, b) {
  console.log(a, b);
}

add(5); // 5 undefined
```

#### Nếu truyền thừa tham số:
Các tham số dư sẽ bị bỏ qua, nhưng bạn có thể truy cập chúng bằng **`arguments`** (dành cho hàm thường) hoặc **toán tử rest**.

```javascript
function add(a, b) {
  console.log(a + b);
}

add(5, 3, 7); // 8 (chỉ sử dụng 5 và 3)
```

---

## **2. Các kỹ thuật nâng cao**

### **2.1. Toán tử Rest (`...`)**
Sử dụng Rest để gom các đối số còn lại vào một mảng.

```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
```

- **Rest** hữu ích khi bạn không biết trước số lượng đối số.

---

### **2.2. Sử dụng `arguments` (trong hàm thường)**
`arguments` là một đối tượng giống mảng chứa tất cả các đối số được truyền vào hàm.

```javascript
function showArgs() {
  console.log(arguments);
}

showArgs(1, 2, 3); // [1, 2, 3]
```

- **Lưu ý**: `arguments` không hoạt động trong hàm mũi tên.

---

### **2.3. Destructuring trong tham số**

#### Với Object:
```javascript
function displayUser({ name, age }) {
  console.log(`Name: ${name}, Age: ${age}`);
}

displayUser({ name: "Alice", age: 25 }); // Name: Alice, Age: 25
```

#### Với Array:
```javascript
function displayNumbers([first, second]) {
  console.log(first, second);
}

displayNumbers([10, 20]); // 10 20
```

---

### **2.4. Tham số lồng nhau**
Hàm có thể nhận đối tượng hoặc mảng lồng nhau làm tham số.

```javascript
function displayData({ user: { name, age }, location: { city } }) {
  console.log(`Name: ${name}, Age: ${age}, City: ${city}`);
}

const data = { user: { name: "Alice", age: 25 }, location: { city: "Paris" } };
displayData(data); // Name: Alice, Age: 25, City: Paris
```

---

## **3. Phạm vi và biến liên quan**

### **3.1. Phạm vi tham số**
- Tham số của hàm chỉ tồn tại trong **phạm vi cục bộ** của hàm đó.
- Ngoài phạm vi hàm, tham số sẽ không được truy cập.

```javascript
function greet(name) {
  console.log(name); // Alice
}
console.log(name); // ReferenceError
```

---

### **3.2. Tham chiếu và tham trị**
- **Tham trị**: Dữ liệu kiểu **primitive** (như `number`, `string`) được truyền theo giá trị. Thay đổi trong hàm không ảnh hưởng đến giá trị gốc.
- **Tham chiếu**: Dữ liệu kiểu **object** (như `array`, `object`) được truyền theo tham chiếu. Thay đổi bên trong hàm sẽ ảnh hưởng đến đối tượng gốc.

#### Ví dụ:
```javascript
function modifyValue(num, obj) {
  num = 10;
  obj.name = "Modified";
}

let number = 5;
let person = { name: "Original" };

modifyValue(number, person);
console.log(number); // 5 (không thay đổi)
console.log(person); // { name: "Modified" } (bị thay đổi)
```

---

## **4. Ứng dụng thực tế**

### **4.1. Tham số mặc định và Rest**
```javascript
function createUser(name = "Anonymous", ...roles) {
  return { name, roles };
}

console.log(createUser("Alice", "Admin", "Editor"));
// { name: "Alice", roles: ["Admin", "Editor"] }
```

---

### **4.2. Destructuring tham số**
```javascript
function getFullName({ firstName, lastName }) {
  return `${firstName} ${lastName}`;
}

console.log(getFullName({ firstName: "Alice", lastName: "Doe" }));
// Alice Doe
```

---

### **4.3. Kết hợp Destructuring và giá trị mặc định**
```javascript
function showUser({ name = "Guest", age = 18 } = {}) {
  console.log(`Name: ${name}, Age: ${age}`);
}

showUser(); // Name: Guest, Age: 18
showUser({ name: "Alice" }); // Name: Alice, Age: 18
```

---

## **Kết luận**
- **Tham số hàm** giúp truyền dữ liệu và kiểm soát hành vi của hàm.
- Sử dụng các kỹ thuật như giá trị mặc định, destructuring, và Rest để viết mã ngắn gọn, linh hoạt hơn.
