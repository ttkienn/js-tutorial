### **Object Properties Spreading**  

**Mô tả:**  
Object properties spreading (sử dụng `...`) cho phép sao chép hoặc gộp các thuộc tính của một đối tượng này vào đối tượng khác một cách dễ dàng và ngắn gọn.

---

### **Cách sử dụng:**

1. **Sao chép đối tượng (Shallow Copy):**
   ```javascript
   const obj = { a: 1, b: 2 };
   const copy = { ...obj };
   console.log(copy); // { a: 1, b: 2 }
   ```

2. **Gộp (Merge) các đối tượng:**
   ```javascript
   const obj1 = { a: 1, b: 2 };
   const obj2 = { b: 3, c: 4 };
   const merged = { ...obj1, ...obj2 };

   console.log(merged); // { a: 1, b: 3, c: 4 }
   // Lưu ý: Thuộc tính `b` từ `obj2` sẽ ghi đè thuộc tính `b` từ `obj1`.
   ```

3. **Thêm thuộc tính mới vào đối tượng:**
   ```javascript
   const obj = { a: 1, b: 2 };
   const extended = { ...obj, c: 3 };

   console.log(extended); // { a: 1, b: 2, c: 3 }
   ```

4. **Xóa một thuộc tính:**
   Sử dụng destructuring để loại bỏ thuộc tính không mong muốn.
   ```javascript
   const obj = { a: 1, b: 2, c: 3 };
   const { b, ...rest } = obj;

   console.log(rest); // { a: 1, c: 3 }
   ```

---

### **Ứng dụng thực tế:**

1. **Tạo đối tượng mới dựa trên đối tượng cũ:**
   - Thay đổi một số thuộc tính:
   ```javascript
   const user = { name: "Alice", age: 25, location: "NY" };
   const updatedUser = { ...user, location: "LA" };

   console.log(updatedUser); 
   // { name: "Alice", age: 25, location: "LA" }
   ```

2. **Kết hợp dữ liệu từ nhiều nguồn:**
   ```javascript
   const defaultSettings = { theme: "light", fontSize: 14 };
   const userSettings = { fontSize: 16 };
   const finalSettings = { ...defaultSettings, ...userSettings };

   console.log(finalSettings); 
   // { theme: "light", fontSize: 16 }
   ```

3. **Tạo bản sao đối tượng để tránh thay đổi gốc (immutability):**
   ```javascript
   const obj = { a: 1, b: 2 };
   const newObj = { ...obj };
   newObj.a = 10;

   console.log(obj);    // { a: 1, b: 2 }
   console.log(newObj); // { a: 10, b: 2 }
   ```

---

### **Hạn chế:**
- Object spreading chỉ thực hiện **sao chép nông** (shallow copy). Nếu đối tượng có thuộc tính lồng nhau (nested), các giá trị bên trong vẫn tham chiếu đến dữ liệu gốc.

#### Ví dụ:
```javascript
const obj = { a: 1, nested: { b: 2 } };
const copy = { ...obj };

copy.nested.b = 99;

console.log(obj.nested.b); // 99 (bị ảnh hưởng)
```

**Cách khắc phục:** Sử dụng **deep copy** (thư viện như `Lodash` hoặc JSON).  
```javascript
const deepCopy = JSON.parse(JSON.stringify(obj));
```

---
