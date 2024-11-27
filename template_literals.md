### **Template Literals (Literals chuỗi)**

**Mô tả:**  
Template literals là một cách mới trong JavaScript để tạo chuỗi, giúp mã dễ đọc và dễ bảo trì hơn. Thay vì dùng dấu nháy đơn (`'`) hoặc nháy kép (`"`), bạn sử dụng dấu backticks (`` ` ``). Template literals cho phép chèn biến, biểu thức vào chuỗi một cách trực quan và dễ dàng.

---

### **Cú pháp:**

1. **Tạo chuỗi đơn giản:**
   ```javascript
   const greeting = `Hello, world!`;
   console.log(greeting); // "Hello, world!"
   ```

2. **Chèn biến vào chuỗi:**
   - Dùng `${}` để chèn giá trị của biến vào trong chuỗi.
   ```javascript
   const name = "Alice";
   const message = `Hello, ${name}!`;
   console.log(message); // "Hello, Alice!"
   ```

3. **Chèn biểu thức vào chuỗi:**
   Bạn có thể sử dụng bất kỳ biểu thức nào trong `${}`.
   ```javascript
   const x = 5;
   const y = 10;
   const sum = `Sum of x and y is: ${x + y}`;
   console.log(sum); // "Sum of x and y is: 15"
   ```

---

### **Các tính năng của Template Literals:**

1. **Đa dòng (Multiline strings):**  
   Template literals cho phép viết chuỗi nhiều dòng mà không cần phải sử dụng ký tự đặc biệt như `\n`.

   ```javascript
   const multiline = `This is a string
   that spans multiple
   lines.`;
   console.log(multiline);
   ```

   Kết quả sẽ là:
   ```
   This is a string
   that spans multiple
   lines.
   ```

2. **Biểu thức trong Template Literals:**
   Bạn có thể sử dụng biểu thức phức tạp bên trong `${}`:
   ```javascript
   const x = 5;
   const y = 10;
   const result = `${x > y ? 'x is greater' : 'y is greater'}`;
   console.log(result); // "y is greater"
   ```

3. **Gọi hàm trong Template Literals:**
   ```javascript
   function greet(name) {
     return `Hello, ${name}!`;
   }

   const message = `The greeting is: ${greet("Alice")}`;
   console.log(message); // "The greeting is: Hello, Alice!"
   ```

4. **Chèn đối tượng hoặc mảng:**
   Khi chèn một đối tượng hoặc mảng vào trong template literal, JavaScript sẽ tự động chuyển nó thành chuỗi bằng phương thức `toString()`.
   
   ```javascript
   const arr = [1, 2, 3];
   const message = `The array is: ${arr}`;
   console.log(message); // "The array is: 1,2,3"
   ```

---

### **Ưu điểm của Template Literals:**

1. **Đọc và hiểu mã dễ dàng hơn**: Việc chèn biến và biểu thức vào chuỗi trở nên trực quan hơn với `${}`.
2. **Chịu đựng nhiều dòng (multiline)** mà không cần dùng ký tự `\n`.
3. **Dễ dàng thao tác với biểu thức phức tạp** trong chuỗi mà không cần phải tách chuỗi thành nhiều phần.

---
