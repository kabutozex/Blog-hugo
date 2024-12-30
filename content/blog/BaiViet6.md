---
title: "Higher-Order Functions (HOF) và Currying trong JavaScript"
date: 2024-12-28T12:00:00Z
draft: false
tags: ["JavaScript", "HOF", "Currying"]
categories: ["Lập Trình", "JavaScript"]
---

## Higher-Order Functions (HOF) trong JavaScript

### 1. Higher-Order Function là gì?
- **Định nghĩa:** Higher-Order Function (HOF) là các hàm nhận một hoặc nhiều hàm khác làm tham số, hoặc trả về một hàm khác.
- **Lợi ích:**
  - Giảm thiểu sự lặp lại mã (code duplication).
  - Tăng khả năng tái sử dụng và tổ chức mã tốt hơn.
  - Là nền tảng của lập trình hàm (functional programming).

### 2. Ví dụ về Higher-Order Functions

#### a. HOF nhận một hàm làm tham số
```javascript
function repeat(action, times) {
  for (let i = 0; i < times; i++) {
    action(i);
  }
}

repeat(console.log, 3);
// Output:
// 0
// 1
// 2
```

#### b. HOF trả về một hàm
```javascript
function multiplyBy(factor) {
  return function (value) {
    return value * factor;
  };
}

const double = multiplyBy(2);
console.log(double(5)); // 10
console.log(double(10)); // 20
```

### 3. HOF phổ biến trong JavaScript
- **`Array.map()`**:
  - Tạo một mảng mới bằng cách áp dụng hàm được cung cấp lên từng phần tử của mảng.
  ```javascript
  const numbers = [1, 2, 3, 4];
  const squared = numbers.map(n => n * n);
  console.log(squared); // [1, 4, 9, 16]
  ```

- **`Array.filter()`**:
  - Lọc các phần tử trong mảng dựa trên điều kiện hàm cung cấp.
  ```javascript
  const numbers = [1, 2, 3, 4];
  const even = numbers.filter(n => n % 2 === 0);
  console.log(even); // [2, 4]
  ```

- **`Array.reduce()`**:
  - Tổng hợp giá trị của mảng thành một giá trị duy nhất dựa trên hàm được cung cấp.
  ```javascript
  const numbers = [1, 2, 3, 4];
  const sum = numbers.reduce((acc, n) => acc + n, 0);
  console.log(sum); // 10
  ```

### 4. Kết hợp các HOF
```javascript
const numbers = [1, 2, 3, 4, 5];

const result = numbers
  .filter(n => n % 2 !== 0) // Lấy số lẻ
  .map(n => n * 2) // Nhân đôi các số lẻ
  .reduce((acc, n) => acc + n, 0); // Tính tổng

console.log(result); // 18
```

---

## Currying trong JavaScript

### 1. Currying là gì?
- **Định nghĩa:** Currying là kỹ thuật biến một hàm nhận nhiều tham số thành một chuỗi các hàm, mỗi hàm chỉ nhận một tham số.
- **Lợi ích:**
  - Tăng khả năng tái sử dụng và tính rõ ràng của mã.
  - Giúp tạo các hàm tùy biến một cách dễ dàng.

### 2. Cách hoạt động của Currying

#### a. Hàm thông thường
```javascript
function add(a, b) {
  return a + b;
}
console.log(add(2, 3)); // 5
```

#### b. Hàm curry
```javascript
function curryAdd(a) {
  return function(b) {
    return a + b;
  };
}

const addTwo = curryAdd(2);
console.log(addTwo(3)); // 5
console.log(addTwo(10)); // 12
```

### 3. Currying với arrow function
```javascript
const multiply = a => b => c => a * b * c;

const multiplyByTwo = multiply(2);
const multiplyByTwoAndThree = multiplyByTwo(3);
console.log(multiplyByTwoAndThree(4)); // 24
```

### 4. Currying trong thực tế

#### a. Cấu hình linh hoạt
```javascript
const greet = greeting => name => `${greeting}, ${name}!`;

const sayHello = greet("Hello");
console.log(sayHello("Alice")); // "Hello, Alice!"
console.log(sayHello("Bob"));   // "Hello, Bob!"
```

#### b. Kết hợp với HOF
```javascript
const products = [
  { name: "Laptop", price: 1000 },
  { name: "Phone", price: 500 },
  { name: "Tablet", price: 750 }
];

const applyDiscount = discount => product => ({
  ...product,
  price: product.price * (1 - discount)
});

const discountedProducts = products.map(applyDiscount(0.1));
console.log(discountedProducts);
```

#### c. Tái sử dụng logic
```javascript
const checkLength = min => max => str => str.length >= min && str.length <= max;

const isValidUsername = checkLength(3)(15);
console.log(isValidUsername("Alice")); // true
console.log(isValidUsername("A"));     // false
```

---

## Kết luận

Higher-Order Functions và Currying là hai khái niệm quan trọng trong lập trình JavaScript hiện đại. Chúng không chỉ làm cho mã ngắn gọn, dễ đọc mà còn giúp giải quyết các bài toán phức tạp một cách hiệu quả hơn. Hiểu và vận dụng tốt hai kỹ thuật này sẽ giúp bạn trở thành một lập trình viên JavaScript xuất sắc hơn.
