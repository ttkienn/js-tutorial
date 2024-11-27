### **Spread Operator** (`...`)

**Mô tả:**  
Spread operator được dùng để "trải" (spread) các phần tử của một mảng hoặc các thuộc tính của một đối tượng. Nó giúp sao chép, nối, hoặc truyền dữ liệu dễ dàng.

---

#### **Cách sử dụng:**

1. **Với mảng**  
   - **Gộp (merge):**
   ```javascript
   const arr1 = [1, 2];
   const arr2 = [3, 4];
   const combined = [...arr1, ...arr2];
   console.log(combined); // [1, 2, 3, 4]
   ```

   - **Sao chép (copy):**
   ```javascript
   const original = [1, 2, 3];
   const copy = [...original];
   console.log(copy); // [1, 2, 3]
   ```

2. **Với đối tượng**  
   - **Gộp (merge):**
   ```javascript
   const obj1 = { a: 1 };
   const obj2 = { b: 2 };
   const combined = { ...obj1, ...obj2 };
   console.log(combined); // { a: 1, b: 2 }
   ```

   - **Sao chép (copy):**
   ```javascript
   const original = { x: 10, y: 20 };
   const copy = { ...original };
   console.log(copy); // { x: 10, y: 20 }
   ```

3. **Truyền tham số vào hàm:**
   ```javascript
   const nums = [1, 2, 3];
   console.log(Math.max(...nums)); // 3
   ```

---

### **Rest Operator** (`...`)

**Mô tả:**  
Rest operator gom các giá trị còn lại thành **một mảng** hoặc **một đối tượng**. Nó giúp làm việc với số lượng tham số hoặc thuộc tính không xác định.

---

#### **Cách sử dụng:**

1. **Trong hàm:**
   - Gom tất cả tham số còn lại thành mảng:
   ```javascript
   function sum(...numbers) {
     return numbers.reduce((total, num) => total + num, 0);
   }
   console.log(sum(1, 2, 3)); // 6
   ```

2. **Trong destructuring:**
   - **Với mảng:**
   ```javascript
   const [first, ...rest] = [1, 2, 3, 4];
   console.log(first); // 1
   console.log(rest);  // [2, 3, 4]
   ```

   - **Với đối tượng:**
   ```javascript
   const { a, ...others } = { a: 1, b: 2, c: 3 };
   console.log(a);      // 1
   console.log(others); // { b: 2, c: 3 }
   ```

---

### **Tóm tắt:**
- **Spread (`...`)**: Trải phần tử ra (sao chép, gộp, truyền dữ liệu).
- **Rest (`...`)**: Gom phần tử lại (xử lý số lượng không xác định).  

Cùng một ký hiệu nhưng mục đích khác nhau tùy theo ngữ cảnh!
