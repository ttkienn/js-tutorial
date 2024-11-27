# **Destructuring trong JavaScript**

## **1. Destructuring với Object**

### **1.1. Cú pháp cơ bản**
```javascript
const obj = { name: "Alice", age: 25, job: "Developer" };
const { name, age } = obj;

console.log(name); // Alice
console.log(age);  // 25
```

- **`{ name, age }`**: tên các biến phải trùng với tên thuộc tính trong đối tượng.
- Các thuộc tính không được giải nén sẽ bị bỏ qua.

---

### **1.2. Đặt tên biến khác**
Có thể đặt tên biến khác với tên thuộc tính bằng cú pháp `: newName`.

```javascript
const obj = { name: "Alice", age: 25 };
const { name: fullName, age: yearsOld } = obj;

console.log(fullName); // Alice
console.log(yearsOld);  // 25
```

---

### **1.3. Giá trị mặc định**
Nếu thuộc tính không tồn tại, có thể đặt giá trị mặc định.

```javascript
const obj = { name: "Alice" };
const { name, age = 18 } = obj;

console.log(name); // Alice
console.log(age);  // 18 (giá trị mặc định)
```

---

### **1.4. Destructuring lồng nhau**
Nếu đối tượng có cấu trúc lồng nhau, có thể giải nén các thuộc tính bên trong.

```javascript
const obj = { person: { name: "Alice", age: 25 }, job: "Developer" };
const { person: { name, age }, job } = obj;

console.log(name); // Alice
console.log(age);  // 25
console.log(job);  // Developer
```

---

### **1.5. Sử dụng trong hàm**
Destructuring rất hữu ích khi làm việc với tham số của hàm.

```javascript
function displayInfo({ name, age }) {
  console.log(`Name: ${name}, Age: ${age}`);
}

const user = { name: "Alice", age: 25 };
displayInfo(user); // Name: Alice, Age: 25
```

---

## **2. Destructuring với Array**

### **2.1. Cú pháp cơ bản**
```javascript
const arr = [1, 2, 3];
const [first, second] = arr;

console.log(first);  // 1
console.log(second); // 2
```

- **`[first, second]`**: tên các biến tương ứng với giá trị theo thứ tự trong mảng.

---

### **2.2. Bỏ qua giá trị**

```javascript
const arr = [1, 2, 3];
const [, second, third] = arr;

console.log(second); // 2
console.log(third);  // 3
```

---

### **2.3. Giá trị mặc định**
Tương tự với object, bạn có thể đặt giá trị mặc định cho biến.

```javascript
const arr = [1];
const [first, second = 0] = arr;

console.log(first);  // 1
console.log(second); // 0 (giá trị mặc định)
```

---

### **2.4. Sử dụng với toán tử Rest**

```javascript
const arr = [1, 2, 3, 4];
const [first, ...rest] = arr;

console.log(first); // 1
console.log(rest);  // [2, 3, 4]
```

---

### **2.5. Destructuring lồng nhau**
Destructuring cũng hỗ trợ mảng lồng nhau.

```javascript
const arr = [1, [2, 3]];
const [first, [second, third]] = arr;

console.log(first);  // 1
console.log(second); // 2
console.log(third);  // 3
```

---

## **3. Ứng dụng thực tế**

### **3.1. Hoán đổi giá trị**
Destructuring giúp hoán đổi giá trị của hai biến dễ dàng.

```javascript
let a = 1, b = 2;
[a, b] = [b, a];

console.log(a); // 2
console.log(b); // 1
```

---

### **3.2. Lấy giá trị từ hàm trả về**
Destructuring rất hữu ích khi làm việc với các hàm trả về mảng hoặc đối tượng.

#### Ví dụ với mảng:
```javascript
function getCoordinates() {
  return [10, 20];
}

const [x, y] = getCoordinates();
console.log(x); // 10
console.log(y); // 20
```

#### Ví dụ với đối tượng:
```javascript
function getUser() {
  return { name: "Alice", age: 25 };
}

const { name, age } = getUser();
console.log(name); // Alice
console.log(age);  // 25
```

---

### **3.3. Lặp qua mảng hoặc đối tượng**
Destructuring có thể dùng trong vòng lặp để giải nén giá trị.

#### Với mảng:
```javascript
const arr = [[1, 2], [3, 4]];

for (const [a, b] of arr) {
  console.log(a, b);
}
// 1 2
// 3 4
```

#### Với đối tượng:
```javascript
const users = [{ name: "Alice", age: 25 }, { name: "Bob", age: 30 }];

for (const { name, age } of users) {
  console.log(name, age);
}
// Alice 25
// Bob 30
```

---

## **4. Kết hợp Destructuring Object và Array**

```javascript
const data = { items: [10, 20, 30], total: 60 };
const { items: [first, second], total } = data;

console.log(first);  // 10
console.log(second); // 20
console.log(total);  // 60
```

---

## **Kết luận**
- **Destructuring** giúp mã nguồn ngắn gọn, dễ đọc và tiện lợi hơn trong việc làm việc với dữ liệu phức tạp.
- Hãy sử dụng destructuring để cải thiện hiệu suất và sự rõ ràng trong code của ông!
