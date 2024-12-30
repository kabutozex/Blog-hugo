---
title: "Khai báo Biến, Scope và Hoisting trong JavaScript"
date: 2024-12-28T10:30:00Z
draft: false
tags: ["JavaScript", "Scope", "Hoisting", "Biến"]
categories: ["Lập Trình", "JavaScript"]
---

### 1. Giới thiệu về khai báo biến trong JavaScript
Trong JavaScript, bạn có thể khai báo biến bằng `var`, `let`, và `const`. Mỗi cách khai báo mang những đặc điểm và phạm vi sử dụng khác nhau.

### 2. Khai báo biến bằng `var`, `let`, và `const`

#### a. `var`
- **Đặc điểm:**
  - Có phạm vi hàm (function scope).
  - Có thể khai báo lại.
  - Không bị ràng buộc bởi block scope.
- **Ví dụ:**
  ```javascript
  function exampleVar() {
    if (true) {
      var x = 10;
    }
    console.log(x); // 10 (khả dụng ngoài block)
  }
  exampleVar();
  ```

#### b. `let`
- **Đặc điểm:**
  - Có phạm vi block (block scope).
  - Không thể khai báo lại trong cùng một phạm vi.
- **Ví dụ:**
  ```javascript
  function exampleLet() {
    if (true) {
      let y = 20;
      console.log(y); // 20
    }
    // console.log(y); // Lỗi: y không tồn tại ngoài block
  }
  exampleLet();
  ```

#### c. `const`
- **Đặc điểm:**
  - Tương tự `let` nhưng giá trị không thể thay đổi sau khi khai báo.
  - Phải được khởi tạo giá trị ngay khi khai báo.
- **Ví dụ:**
  ```javascript
  const z = 30;
  // z = 40; // Lỗi: Không thể thay đổi giá trị của z
  console.log(z); // 30
  ```

### 3. Scope (Phạm vi của biến)
Phạm vi của biến quyết định nơi biến có thể được truy cập và sử dụng.

#### a. Global Scope
- **Mô tả:** Biến được khai báo bên ngoài mọi hàm hoặc block, có phạm vi toàn cục.
- **Ví dụ:**
  ```javascript
  var globalVar = "Tôi là biến toàn cục";
  function accessGlobalVar() {
    console.log(globalVar); // "Tôi là biến toàn cục"
  }
  accessGlobalVar();
  ```

#### b. Function Scope
- **Mô tả:** Biến được khai báo bằng `var` bên trong hàm chỉ tồn tại trong hàm đó.
- **Ví dụ:**
  ```javascript
  function functionScopeExample() {
    var localVar = "Tôi chỉ tồn tại trong hàm này";
    console.log(localVar);
  }
  functionScopeExample();
  // console.log(localVar); // Lỗi: Không thể truy cập biến cục bộ
  ```

#### c. Block Scope
- **Mô tả:** Biến được khai báo bằng `let` hoặc `const` chỉ tồn tại trong block.
- **Ví dụ:**
  ```javascript
  if (true) {
    let blockScopedVar = "Tôi chỉ tồn tại trong block này";
    console.log(blockScopedVar); // "Tôi chỉ tồn tại trong block này"
  }
  // console.log(blockScopedVar); // Lỗi: Không thể truy cập ngoài block
  ```

### 4. Hoisting (Cơ chế nâng biến)
Hoisting là cơ chế của JavaScript "nâng" khai báo biến và hàm lên đầu phạm vi trước khi thực thi mã.

#### a. Hoisting với `var`
- **Đặc điểm:** Biến khai báo bằng `var` được nâng lên nhưng không gán giá trị ban đầu.
- **Ví dụ:**
  ```javascript
  console.log(a); // undefined
  var a = 10;
  console.log(a); // 10
  ```

#### b. Hoisting với `let` và `const`
- **Đặc điểm:** Không thể truy cập biến trước khi khai báo.
- **Ví dụ:**
  ```javascript
  // console.log(b); // Lỗi: Cannot access 'b' before initialization
  let b = 20;
  console.log(b); // 20
  ```

#### c. Hoisting với hàm
- **Đặc điểm:** Toàn bộ nội dung hàm được nâng lên đầu phạm vi.
- **Ví dụ:**
  ```javascript
  sayHello();
  function sayHello() {
    console.log("Hello, world!");
  }
  ```

### 5. Kết hợp Scope và Hoisting
- **Ví dụ tổng hợp:**
  ```javascript
  function testHoisting() {
    console.log(x); // undefined (hoisting với var)
    var x = 5;

    if (true) {
      let y = 10;
      console.log(y); // 10
    }
    // console.log(y); // Lỗi: y không tồn tại ngoài block
  }
  testHoisting();
  ```

### Kết luận
Hiểu rõ các khái niệm khai báo biến, scope và hoisting giúp bạn tránh những lỗi logic phổ biến và viết mã JavaScript một cách hiệu quả hơn.
