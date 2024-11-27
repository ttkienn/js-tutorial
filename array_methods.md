# **1. Phương thức `map()`**

## **1.1. Mô tả**
- **`map()`** được dùng để **duyệt qua từng phần tử** của mảng và **trả về một mảng mới**, trong đó mỗi phần tử là kết quả của việc áp dụng một hàm lên phần tử tương ứng.

## **1.2. Cú pháp**
```javascript
array.map(callback(currentValue, index, array), thisArg);
```

- **`callback`**: Hàm được gọi cho mỗi phần tử trong mảng.
  - **`currentValue`**: Phần tử hiện tại.
  - **`index`** *(tùy chọn)*: Chỉ số của phần tử hiện tại.
  - **`array`** *(tùy chọn)*: Mảng gốc đang được duyệt.
- **`thisArg`** *(tùy chọn)*: Giá trị để làm `this` trong hàm `callback`.

---

## **1.3. Ví dụ**
```javascript
const numbers = [1, 2, 3, 4];
const squares = numbers.map(num => num * num);

console.log(squares); // [1, 4, 9, 16]
```

### **1.4. Ứng dụng**
- **Biến đổi dữ liệu**:
```javascript
const names = ["Alice", "Bob", "Charlie"];
const upperNames = names.map(name => name.toUpperCase());

console.log(upperNames); // ["ALICE", "BOB", "CHARLIE"]
```

---

# **2. Phương thức `filter()`**

## **2.1. Mô tả**
- **`filter()`** được dùng để **lọc các phần tử của mảng** dựa trên một điều kiện. Nó trả về một **mảng mới** chứa các phần tử thỏa mãn điều kiện.

---

## **2.2. Cú pháp**
```javascript
array.filter(callback(currentValue, index, array), thisArg);
```

- **`callback`**: Hàm kiểm tra từng phần tử.
  - Trả về `true` để giữ lại phần tử, `false` để loại bỏ.
- **`thisArg`** *(tùy chọn)*: Giá trị làm `this` trong hàm `callback`.

---

## **2.3. Ví dụ**
```javascript
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter(num => num % 2 === 0);

console.log(evenNumbers); // [2, 4]
```

### **2.4. Ứng dụng**
- **Lọc dữ liệu theo điều kiện**:
```javascript
const people = [
  { name: "Alice", age: 25 },
  { name: "Bob", age: 17 },
  { name: "Charlie", age: 19 }
];

const adults = people.filter(person => person.age >= 18);

console.log(adults);
// [{ name: "Alice", age: 25 }, { name: "Charlie", age: 19 }]
```

---

# **3. Phương thức `reduce()`**

## **3.1. Mô tả**
- **`reduce()`** dùng để **gộp các phần tử của mảng** thành một giá trị duy nhất bằng cách thực thi hàm `callback` trên từng phần tử.
- Nó linh hoạt hơn, có thể được sử dụng để **tính toán, gộp dữ liệu**, hoặc chuyển đổi dữ liệu.

---

## **3.2. Cú pháp**
```javascript
array.reduce(callback(accumulator, currentValue, index, array), initialValue);
```

- **`callback`**: Hàm xử lý từng phần tử.
  - **`accumulator`**: Giá trị tích lũy sau mỗi lần xử lý.
  - **`currentValue`**: Phần tử hiện tại.
  - **`index`** *(tùy chọn)*: Chỉ số của phần tử hiện tại.
  - **`array`** *(tùy chọn)*: Mảng gốc.
- **`initialValue`** *(tùy chọn)*: Giá trị khởi tạo cho `accumulator`.

---

## **3.3. Ví dụ**
### **Tính tổng các số**
```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((total, num) => total + num, 0);

console.log(sum); // 10
```

### **Chuyển đổi mảng thành đối tượng**
```javascript
const people = [
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" }
];

const peopleMap = people.reduce((map, person) => {
  map[person.id] = person.name;
  return map;
}, {});

console.log(peopleMap); // { 1: "Alice", 2: "Bob" }
```

---

## **4. So sánh `map()`, `filter()`, và `reduce()`**

| **Phương thức** | **Mục đích**                               | **Kết quả trả về**        | **Khi nào dùng**                       |
|-----------------|-------------------------------------------|--------------------------|----------------------------------------|
| **`map()`**     | Biến đổi từng phần tử trong mảng          | Mảng mới                 | Khi cần chuyển đổi giá trị từng phần tử|
| **`filter()`**  | Lọc các phần tử dựa trên điều kiện        | Mảng mới (phần tử phù hợp)| Khi cần chọn lọc dữ liệu từ mảng       |
| **`reduce()`**  | Gộp tất cả phần tử thành một giá trị       | Một giá trị duy nhất      | Khi cần tổng hợp hoặc gộp dữ liệu      |

---

## **5. Kết hợp cả 3 phương thức**
Bạn có thể kết hợp cả `map()`, `filter()`, và `reduce()` để xử lý dữ liệu phức tạp.

### Ví dụ:
Lấy tổng tuổi của những người trên 18:
```javascript
const people = [
  { name: "Alice", age: 25 },
  { name: "Bob", age: 17 },
  { name: "Charlie", age: 19 }
];

const totalAge = people
  .filter(person => person.age >= 18) // Lọc người lớn
  .map(person => person.age)         // Lấy tuổi
  .reduce((sum, age) => sum + age, 0); // Tính tổng

console.log(totalAge); // 44
```

---

## **Kết luận**
- **`map()`**: Dùng để chuyển đổi dữ liệu.
- **`filter()`**: Dùng để lọc dữ liệu.
- **`reduce()`**: Dùng để gộp dữ liệu.
