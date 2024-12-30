---
title: "Number, String, Array và Object trong JavaScript"
date: 2024-12-28T10:00:00Z
draft: false
tags: ["JavaScript", "Event Loop", "Async Programming"]
categories: ["Lập Trình", "JavaScript"]
---
### Cái nhìn tổng quan về bốn kiểu dữ liệu cơ bản thường được sử dụng: Number, String, Array và Object.

### 1. Number
- **Mô tả:** Dùng để biểu diễn các số, bao gồm cả số nguyên và số thập phân.
- **Ví dụ:**
  ```javascript
  const a = 42; // Số nguyên
  const b = 3.14; // Số thập phân
  const c = NaN; // Giá trị "Not-a-Number"
  const d = Infinity; // Giá trị vô cực
  ```
- **Phương thức hữu ích:**
  ```javascript
  console.log(Number.isNaN(c)); // true
  console.log(Number.isFinite(d)); // false
  console.log(a.toFixed(2)); // "42.00"
  ```

### 2. String
- **Mô tả:** Đại diện cho chuỗi văn bản.
- **Ví dụ:**
  ```javascript
  const name = "John";
  const greeting = `Hello, ${name}!`;
  ```
- **Phương thức hữu ích:**
  ```javascript
  console.log(name.length); // 4
  console.log(name.toUpperCase()); // "JOHN"
  console.log(name.includes("oh")); // true
  ```

### 3. Array
- **Mô tả:** Cấu trúc dữ liệu lưu trữ danh sách các giá trị.
- **Ví dụ:**
  ```javascript
  const fruits = ["apple", "banana", "cherry"];
  ```
- **Phương thức hữu ích:**
  ```javascript
  fruits.push("date");
  console.log(fruits); // ["apple", "banana", "cherry", "date"]

  fruits.pop();
  console.log(fruits); // ["apple", "banana", "cherry"]

  console.log(fruits.indexOf("banana")); // 1
  ```

### 4. Object
- **Mô tả:** Lưu trữ dữ liệu dưới dạng cặp key-value.
- **Ví dụ:**
  ```javascript
  const person = {
    name: "Alice",
    age: 25,
    greet: function() {
      console.log(`Hello, my name is ${this.name}`);
    },
  };
  ```
- **Phương thức hữu ích:**
  ```javascript
  console.log(Object.keys(person)); // ["name", "age", "greet"]
  console.log(Object.values(person)); // ["Alice", 25, [Function: greet]]
  console.log(person.name); // "Alice"
  ```

---

## Kết luận về Number, String, Array và Object

Hiểu rõ cách sử dụng các kiểu dữ liệu này là nền tảng để phát triển ứng dụng JavaScript. Chúng giúp bạn tổ chức, xử lý và hiển thị dữ liệu một cách hiệu quả.
