### **Rest Parameter trong hàm**

**Mô tả:**  
Rest parameter cho phép gom **số lượng tham số không xác định** được truyền vào một hàm thành một **mảng**. Điều này rất hữu ích khi bạn muốn làm việc với các hàm nhận nhiều tham số mà không biết trước số lượng.

---

### **Cú pháp:**
```javascript
function functionName(...restParameter) {
  // restParameter là một mảng chứa các tham số còn lại
}
```

- **`...restParameter`** phải là **tham số cuối cùng** trong danh sách tham số.

---

### **Ví dụ cơ bản:**

1. **Tính tổng các số:**
```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
```

2. **In tất cả các tham số:**
```javascript
function logArguments(...args) {
  console.log(args);
}

logArguments("Alice", 25, true); // ["Alice", 25, true]
```

---

### **Kết hợp tham số thông thường và Rest:**

Bạn có thể kết hợp tham số thông thường với Rest parameter, nhưng Rest phải đặt cuối cùng.

```javascript
function greet(greeting, ...names) {
  console.log(`${greeting}, ${names.join(", ")}!`);
}

greet("Hello", "Alice", "Bob", "Charlie"); 
// Hello, Alice, Bob, Charlie!
```

---

### **Rest Parameter vs `arguments`:**

| **Rest Parameter**       | **`arguments`**                |
|--------------------------|--------------------------------|
| Chỉ chứa các tham số **còn lại**. | Chứa **tất cả** các tham số của hàm. |
| Là một mảng thực sự.     | Là một đối tượng giống mảng.   |
| Hoạt động trong **hàm thường** và **hàm mũi tên**. | Chỉ hoạt động trong **hàm thường**. |

#### Ví dụ:
```javascript
function showArguments(...args) {
  console.log(args); // Mảng
}

function showArgumentsOld() {
  console.log(arguments); // Đối tượng giống mảng
}

showArguments(1, 2, 3); // [1, 2, 3]
showArgumentsOld(1, 2, 3); // { '0': 1, '1': 2, '2': 3 }
```

---

### **Ứng dụng thực tế:**

1. **Gộp chuỗi động:**
```javascript
function concatenate(separator, ...words) {
  return words.join(separator);
}

console.log(concatenate("-", "JavaScript", "is", "fun")); 
// JavaScript-is-fun
```

2. **Xử lý tham số không xác định:**
```javascript
function findMax(...numbers) {
  return Math.max(...numbers);
}

console.log(findMax(3, 7, 1, 9)); // 9
```

---

### **Kết luận:**
- **Rest parameter** giúp viết hàm linh hoạt hơn, đặc biệt khi số lượng tham số không cố định.
- Thay thế hiệu quả cho **`arguments`** nhờ khả năng hoạt động như một mảng thực sự.
