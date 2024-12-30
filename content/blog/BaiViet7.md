---
title: "Tìm hiểu về this và Date trong JavaScript"
date: 2024-12-28T12:00:00Z
draft: false
tags: ["JavaScript", "this", "Date"]
categories: ["Lập Trình", "JavaScript"]
---

## `this` trong JavaScript

### 1. `this` là gì?
- **`this`** là một từ khóa trong JavaScript đại diện cho ngữ cảnh mà mã đang được thực thi.
- Giá trị của `this` thay đổi tùy thuộc vào cách mà hàm được gọi.

### 2. Các trường hợp sử dụng `this`

#### a. Trong global context (toàn cục)
```javascript
console.log(this);
// Trong trình duyệt: Window object
// Trong Node.js: {} (object global rỗng)
```

#### b. Trong một hàm
- `this` tham chiếu đến đối tượng global trong các hàm thông thường.
```javascript
function showThis() {
  console.log(this);
}

showThis();
// Trong trình duyệt: Window
// Trong Node.js: global object
```

#### c. Trong một đối tượng
- `this` tham chiếu đến đối tượng gọi hàm.
```javascript
const obj = {
  name: "JavaScript",
  getName() {
    return this.name;
  }
};

console.log(obj.getName()); // "JavaScript"
```

#### d. Với `class`
- Trong các phương thức của class, `this` đại diện cho đối tượng được tạo ra từ class.
```javascript
class Person {
  constructor(name) {
    this.name = name;
  }
  greet() {
    return `Hello, my name is ${this.name}`;
  }
}

const alice = new Person("Alice");
console.log(alice.greet()); // "Hello, my name is Alice"
```

#### e. Arrow function
- Arrow function không có `this` riêng, nó kế thừa `this` từ phạm vi nơi nó được định nghĩa.
```javascript
const obj = {
  name: "JavaScript",
  getName: function () {
    const arrow = () => this.name;
    return arrow();
  }
};

console.log(obj.getName()); // "JavaScript"
```

#### f. Khi sử dụng bind, call, apply
- `this` có thể được gán tường minh bằng các phương thức này.
```javascript
function greet(greeting) {
  console.log(`${greeting}, my name is ${this.name}`);
}

const person = { name: "Alice" };
greet.call(person, "Hello"); // "Hello, my name is Alice"
greet.apply(person, ["Hi"]); // "Hi, my name is Alice"

const boundGreet = greet.bind(person);
boundGreet("Hey"); // "Hey, my name is Alice"
```

---

## Date trong JavaScript

### 1. Khởi tạo đối tượng Date
- Sử dụng constructor `Date` để làm việc với thời gian.
```javascript
const now = new Date();
console.log(now); // Ngày giờ hiện tại

const specificDate = new Date("2024-01-01T00:00:00Z");
console.log(specificDate); // Ngày giờ cụ thể
```

### 2. Các phương thức của Date

#### a. Lấy thông tin ngày và giờ
```javascript
const now = new Date();
console.log(now.getFullYear()); // Năm hiện tại
console.log(now.getMonth());    // Tháng (0-11)
console.log(now.getDate());     // Ngày (1-31)
console.log(now.getDay());      // Thứ (0-6, Chủ nhật là 0)
console.log(now.getHours());    // Giờ (0-23)
console.log(now.getMinutes());  // Phút (0-59)
console.log(now.getSeconds());  // Giây (0-59)
console.log(now.getMilliseconds()); // Milli giây (0-999)
```

#### b. Đặt giá trị ngày giờ
```javascript
const date = new Date();
date.setFullYear(2025);
date.setMonth(6); // Tháng 7 (index từ 0)
date.setDate(15);
console.log(date);
```

#### c. Chuyển đổi ngày giờ thành chuỗi
```javascript
const now = new Date();
console.log(now.toISOString()); // Chuỗi ISO (UTC)
console.log(now.toDateString()); // Dạng ngày (e.g., "Mon Dec 28 2024")
console.log(now.toTimeString()); // Dạng giờ (e.g., "13:45:30 GMT+0000")
```

### 3. Tính toán thời gian
- Sử dụng timestamp (milliseconds từ 01/01/1970).
```javascript
const now = new Date();
const later = new Date(now.getTime() + 1000 * 60 * 60 * 24); // +1 ngày
console.log(later);

const difference = later - now; // Chênh lệch thời gian (ms)
console.log(difference / (1000 * 60 * 60)); // Chênh lệch giờ
```

### 4. Thư viện hỗ trợ
- **Moment.js:** Trước đây rất phổ biến nhưng hiện đã không được bảo trì.
- **date-fns:** Một thư viện hiện đại, gọn nhẹ.
- **Luxon:** Thay thế cho Moment.js, hỗ trợ tốt hơn các múi giờ.
```javascript
import { format } from "date-fns";

const now = new Date();
console.log(format(now, "yyyy-MM-dd HH:mm:ss"));
```

---

## Kết luận

`this` và Date là hai khái niệm quan trọng trong JavaScript. Hiểu rõ cách hoạt động của `this` giúp bạn tránh các lỗi phổ biến về ngữ cảnh. Đối với Date, sử dụng các phương thức có sẵn hoặc thư viện hỗ trợ để làm việc với thời gian hiệu quả hơn.
