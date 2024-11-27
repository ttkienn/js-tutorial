---

# Biến trong JavaScript

Biến trong JavaScript là những không gian lưu trữ dữ liệu. Bạn có thể sử dụng chúng để giữ giá trị và thay đổi giá trị đó trong suốt chương trình của mình. JavaScript cung cấp 3 cách khai báo biến, mỗi cách có một đặc điểm riêng.

## **1. `var`**
`var` là cách khai báo biến trong JavaScript trước đây. Tuy nhiên, hiện nay `var` không được khuyến khích sử dụng vì nó có một số vấn đề về phạm vi (scope) và tính linh hoạt. 

### Đặc điểm của `var`:
- **Phạm vi toàn cục hoặc phạm vi hàm**: Biến khai báo với `var` có thể bị ghi đè nếu khai báo cùng tên trong cùng một phạm vi, và nó có thể được truy cập từ bất kỳ đâu trong hàm hoặc toàn bộ chương trình.
- **Hoisting**: Biến khai báo bằng `var` sẽ được "hoisted" (nâng lên đầu phạm vi) dù không có giá trị, nghĩa là biến sẽ được khai báo ở đầu hàm hoặc chương trình dù bạn khai báo nó ở đâu.

### Ví dụ:
```javascript
function testVar() {
  console.log(a); // undefined, vì biến a đã được hoisted
  var a = 10;
  console.log(a); // 10
}
testVar();
```

---

## **2. `let`**
`let` là cách khai báo biến trong JavaScript hiện đại. Nó giúp khắc phục nhiều vấn đề của `var` và được khuyến khích sử dụng.

### Đặc điểm của `let`:
- **Phạm vi khối (block scope)**: Biến khai báo với `let` chỉ có thể được truy cập trong khối mã (block) nơi nó được khai báo, giúp tránh xung đột trong các vòng lặp hoặc cấu trúc điều kiện.
- **Hoisting**: Biến khai báo bằng `let` cũng được hoisted, nhưng không thể sử dụng trước khi khai báo. Điều này tạo ra một vùng "temporal dead zone" (TDZ), nơi biến chưa được khởi tạo không thể truy cập.

### Ví dụ:
```javascript
function testLet() {
  // console.log(a); // Lỗi: Cannot access 'a' before initialization
  let a = 10;
  console.log(a); // 10
}
testLet();
```

---

## **3. `const`**
`const` là cách khai báo biến không thay đổi, tức là bạn không thể gán lại giá trị cho biến này sau khi đã khai báo.

### Đặc điểm của `const`:
- **Phạm vi khối (block scope)**: Giống như `let`, biến khai báo với `const` có phạm vi trong khối mã.
- **Không thể thay đổi giá trị**: Một khi bạn gán giá trị cho một biến `const`, giá trị đó không thể thay đổi. Tuy nhiên, nếu biến là một đối tượng hoặc mảng, bạn có thể thay đổi các thuộc tính hoặc phần tử bên trong chúng.
- **Hoisting**: Giống như `let`, `const` cũng được hoisted, nhưng không thể sử dụng trước khi khai báo.

### Ví dụ:
```javascript
const pi = 3.14;
console.log(pi); // 3.14
// pi = 3.14159; // Lỗi: Assignment to constant variable.
```

### Ví dụ với mảng hoặc đối tượng:
```javascript
const person = { name: "Alice", age: 30 };
person.age = 31; // Được phép, vì thay đổi thuộc tính bên trong đối tượng
console.log(person.age); // 31
```

---

## **Sự khác biệt giữa `var`, `let`, và `const`**

| Tính năng                | `var`                          | `let`                         | `const`                        |
|--------------------------|--------------------------------|-------------------------------|-------------------------------|
| **Phạm vi**              | Toàn cục hoặc trong hàm       | Phạm vi khối (block scope)    | Phạm vi khối (block scope)     |
| **Hoisting**             | Biến được hoisted, nhưng có thể là `undefined` | Biến được hoisted, nhưng không thể truy cập trước khi khai báo | Biến được hoisted, nhưng không thể truy cập trước khi khai báo |
| **Thay đổi giá trị**     | Có thể thay đổi                | Có thể thay đổi                | Không thể thay đổi sau khi khai báo |
| **Khả năng bị ghi đè**   | Có thể bị ghi đè trong cùng phạm vi | Không bị ghi đè trong phạm vi | Không bị ghi đè, có giá trị không đổi |

---

## **Kết luận**
- **`var`** là cách khai báo cũ, không nên sử dụng nữa vì dễ gây lỗi và có phạm vi toàn cục.
- **`let`** là lựa chọn tốt hơn để khai báo biến khi bạn cần giá trị có thể thay đổi.
- **`const`** được dùng khi bạn chắc chắn giá trị của biến sẽ không thay đổi sau khi khai báo, đặc biệt là với đối tượng hoặc mảng.
---
