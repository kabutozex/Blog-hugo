---
title: " Các câu trúc lệnh điều khiển trong Javascript"
date: 2024-12-28T00:00:00Z
draft: false
---

## Các cấu trúc lệnh điều khiển trong JavaScript

JavaScript cung cấp nhiều cấu trúc lệnh điều khiển giúp lập trình viên xử lý các luồng điều kiện và vòng lặp trong chương trình. Dưới đây là các cấu trúc phổ biến:

### 1. Cấu trúc điều kiện

#### If...Else
Câu lệnh `if...else` được sử dụng để kiểm tra một điều kiện và thực hiện các khối mã tương ứng:

```javascript
if (condition) {
    // Khối mã thực thi nếu điều kiện đúng
} else {
    // Khối mã thực thi nếu điều kiện sai
}
```

#### Switch...Case
Câu lệnh `switch` được sử dụng để thay thế nhiều câu lệnh `if...else` lồng nhau:

```javascript
switch (expression) {
    case value1:
        // Khối mã nếu biểu thức bằng value1
        break;
    case value2:
        // Khối mã nếu biểu thức bằng value2
        break;
    default:
        // Khối mã nếu không khớp với giá trị nào
}
```

### 2. Vòng lặp

#### For
Vòng lặp `for` được sử dụng khi biết trước số lần lặp:

```javascript
for (let i = 0; i < 10; i++) {
    console.log(i);
}
```

#### While
Vòng lặp `while` thực thi khối mã khi điều kiện còn đúng:

```javascript
let i = 0;
while (i < 10) {
    console.log(i);
    i++;
}
```

#### Do...While
Vòng lặp `do...while` luôn thực thi ít nhất một lần trước khi kiểm tra điều kiện:

```javascript
let i = 0;
do {
    console.log(i);
    i++;
} while (i < 10);
```

### 3. Câu lệnh nhảy

#### Break
Câu lệnh `break` dùng để thoát khỏi vòng lặp:

```javascript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;
    }
    console.log(i);
}
```

#### Continue
Câu lệnh `continue` bỏ qua lần lặp hiện tại và tiếp tục vòng lặp:

```javascript
for (let i = 0; i < 10; i++) {
    if (i % 2 === 0) {
        continue;
    }
    console.log(i);
}
```

## Cộng đồng và tài nguyên học tập

JavaScript có một cộng đồng lớn và thân thiện, với vô số tài liệu, khóa học, và diễn đàn hỗ trợ:

- [Mozilla Developer Network (MDN)](https://developer.mozilla.org/vi/): Một nguồn tài liệu chi tiết và đáng tin cậy.
- [W3Schools](https://www.w3schools.com/js/): Cung cấp các bài học cơ bản và thực hành.
- [FreeCodeCamp](https://www.freecodecamp.org/): Một nền tảng học lập trình miễn phí với nhiều bài tập thực tế.

## Kết luận

JavaScript là một công cụ mạnh mẽ và linh hoạt, phù hợp với cả người mới bắt đầu và các lập trình viên chuyên nghiệp. Việc nắm vững JavaScript không chỉ giúp bạn xây dựng các trang web đẹp mắt mà còn mở ra nhiều cơ hội trong lĩnh vực phát triển phần mềm.
