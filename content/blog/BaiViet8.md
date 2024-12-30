---
title: "Window Object trong JavaScript"
date: 2024-12-28T10:00:00Z
draft: false
tags: ["JavaScript", "Window Object", "Browser API"]
categories: ["Lập Trình", "JavaScript"]
---

### Cái nhìn tổng quan về Window Object trong JavaScript

### 1. Giới thiệu về Window Object
- **Mô tả:** 
  `window` là đối tượng toàn cục (global object) trong môi trường trình duyệt. Tất cả các biến toàn cục, hàm, hoặc đối tượng được khai báo trong JavaScript đều trở thành thuộc tính hoặc phương thức của `window`.
- **Ví dụ:**
  ```javascript
  console.log(window); // Hiển thị toàn bộ đối tượng window
  console.log(window.document); // Truy cập vào DOM
  console.log(window.location); // Thông tin URL
  ```

### 2. Các thuộc tính phổ biến của Window Object
#### a. `window.location`
- **Mô tả:** Cung cấp thông tin URL hiện tại và hỗ trợ điều hướng.
- **Chi tiết:**
  - `window.location.href`: URL đầy đủ của trang hiện tại.
  - `window.location.hostname`: Tên miền của URL.
  - `window.location.pathname`: Đường dẫn sau tên miền.
  - `window.location.reload()`: Tải lại trang hiện tại.
- **Ví dụ:**
  ```javascript
  console.log(window.location.href); // URL hiện tại
  console.log(window.location.hostname); // Tên miền
  console.log(window.location.pathname); // Đường dẫn
  window.location.reload(); // Tải lại trang
  ```

#### b. `window.document`
- **Mô tả:** Truy cập và thao tác với DOM (Document Object Model).
- **Chi tiết:**
  - `window.document.title`: Trả về hoặc đặt tiêu đề trang.
  - `window.document.body`: Truy cập vào phần `<body>` của tài liệu.
  - `window.document.getElementById()`: Lấy phần tử HTML bằng ID.
- **Ví dụ:**
  ```javascript
  console.log(window.document.title); // Tiêu đề trang
  console.log(window.document.body); // Thẻ <body>
  const element = document.getElementById("myElement");
  console.log(element);
  ```

#### c. `window.navigator`
- **Mô tả:** Chứa thông tin về trình duyệt.
- **Chi tiết:**
  - `window.navigator.userAgent`: Chuỗi mô tả trình duyệt.
  - `window.navigator.language`: Ngôn ngữ hiện tại của trình duyệt.
  - `window.navigator.platform`: Nền tảng (hệ điều hành).
- **Ví dụ:**
  ```javascript
  console.log(window.navigator.userAgent); // Chuỗi thông tin trình duyệt
  console.log(window.navigator.language); // Ngôn ngữ trình duyệt
  console.log(window.navigator.platform); // Nền tảng trình duyệt
  ```

#### d. `window.history`
- **Mô tả:** Quản lý lịch sử duyệt web.
- **Chi tiết:**
  - `window.history.back()`: Quay lại trang trước đó.
  - `window.history.forward()`: Tiến tới trang tiếp theo.
  - `window.history.length`: Số mục trong lịch sử phiên làm việc.
- **Ví dụ:**
  ```javascript
  window.history.back(); // Quay lại trang trước
  window.history.forward(); // Tiến tới trang sau
  console.log(window.history.length); // Số lượng mục trong lịch sử
  ```

### 3. Các phương thức quan trọng của Window Object
#### a. `alert()`
- **Mô tả:** Hiển thị một hộp thoại cảnh báo.
- **Chi tiết:** Dùng để hiển thị thông báo cho người dùng.
- **Ví dụ:**
  ```javascript
  window.alert("Welcome to JavaScript!");
  ```

#### b. `confirm()`
- **Mô tả:** Hiển thị một hộp thoại xác nhận.
- **Chi tiết:** Hộp thoại này trả về `true` nếu người dùng chọn "OK" và `false` nếu chọn "Cancel".
- **Ví dụ:**
  ```javascript
  const result = window.confirm("Are you sure?");
  console.log(result); // true hoặc false
  ```

#### c. `prompt()`
- **Mô tả:** Hiển thị một hộp thoại yêu cầu nhập dữ liệu.
- **Chi tiết:** Hộp thoại trả về chuỗi mà người dùng nhập vào hoặc `null` nếu người dùng bấm "Cancel".
- **Ví dụ:**
  ```javascript
  const name = window.prompt("What is your name?");
  console.log(name); // Tên được nhập hoặc null
  ```

### 4. Các sự kiện phổ biến của Window Object
#### a. `window.onload`
- **Mô tả:** Kích hoạt khi trang web tải xong.
- **Ví dụ:**
  ```javascript
  window.onload = function() {
    console.log("Page is fully loaded.");
  };
  ```

#### b. `window.onresize`
- **Mô tả:** Kích hoạt khi kích thước cửa sổ thay đổi.
- **Ví dụ:**
  ```javascript
  window.onresize = function() {
    console.log("Window resized to: " + window.innerWidth + "x" + window.innerHeight);
  };
  ```

#### c. `window.onscroll`
- **Mô tả:** Kích hoạt khi trang được cuộn.
- **Ví dụ:**
  ```javascript
  window.onscroll = function() {
    console.log("Page scrolled. Scroll position: " + window.scrollY);
  };
  ```

### Kết luận
Window Object là nền tảng của việc tương tác với trình duyệt. Nắm vững các thuộc tính, phương thức, và sự kiện của `window` sẽ giúp bạn xây dựng ứng dụng web mạnh mẽ và linh hoạt hơn.
