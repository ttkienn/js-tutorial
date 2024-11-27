### **Object Property Shorthand**  

---

### **Cú pháp:**

1. **Cách khai báo thông thường:**
   ```javascript
   const name = "Alice";
   const age = 25;

   const person = {
     name: name,
     age: age
   };

   console.log(person); // { name: "Alice", age: 25 }
   ```

2. **Sử dụng Object Property Shorthand:**
   ```javascript
   const name = "Alice";
   const age = 25;

   const person = {
     name, // Tự động lấy giá trị từ biến `name`
     age   // Tự động lấy giá trị từ biến `age`
   };

   console.log(person); // { name: "Alice", age: 25 }
   ```

---

### **Ứng dụng thực tế:**

1. **Khi muốn tạo đối tượng từ các biến:**
   ```javascript
   const name = "Bob";
   const job = "Developer";

   const person = { name, job };

   console.log(person); // { name: "Bob", job: "Developer" }
   ```

2. **Khi sử dụng trong hàm:**
   - Bạn có thể dùng **shorthand** khi truyền tham số là đối tượng:
   ```javascript
   function createPerson(name, age) {
     return { name, age };
   }

   const person = createPerson("Charlie", 30);
   console.log(person); // { name: "Charlie", age: 30 }
   ```

---

### **Lợi ích:**
- Giúp code ngắn gọn và dễ đọc hơn.
- Hữu ích khi bạn có rất nhiều thuộc tính với tên giống tên biến.

---

### **Lưu ý:**
- **Object Property Shorthand** chỉ có hiệu lực khi **tên thuộc tính và tên biến giống nhau**. Nếu không, bạn phải dùng cách khai báo thông thường để chỉ rõ tên thuộc tính.

---

### **Ví dụ nâng cao:**

1. **Sử dụng trong hàm constructor:**
   ```javascript
   function createCar(model, year) {
     return { model, year };
   }

   const car = createCar("Tesla", 2024);
   console.log(car); // { model: "Tesla", year: 2024 }
   ```

2. **Kết hợp với Rest Parameter:**
   ```javascript
   const firstName = "John";
   const lastName = "Doe";

   const fullName = { firstName, lastName, ...otherInfo };
   ```

---
