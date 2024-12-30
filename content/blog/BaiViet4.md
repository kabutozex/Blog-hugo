---
title: "Event Loop là gì? Cơ chế hoạt động của Event Loop trong JavaScript"
date: 2024-12-28T10:00:00Z
draft: false
tags: ["JavaScript", "Event Loop", "Async Programming"]
categories: ["Lập Trình", "JavaScript"]
---

## Event Loop là gì?

Event Loop là một cơ chế cốt lõi trong JavaScript, cho phép ngôn ngữ này xử lý các tác vụ bất đồng bộ (asynchronous). Đây là thành phần quan trọng giúp JavaScript, một ngôn ngữ đơn luồng (single-threaded), có thể thực hiện nhiều tác vụ đồng thời mà không bị chặn (non-blocking).

---

## Cơ chế hoạt động của Event Loop

Event Loop vận hành theo một quy trình cụ thể để xử lý các tác vụ đồng bộ và bất đồng bộ. Dưới đây là các bước chính trong cơ chế hoạt động:

1. **Call Stack (Ngăn xếp thực thi):**
   - Đây là nơi chứa các lệnh cần được thực thi. Mỗi khi một hàm được gọi, nó sẽ được đưa vào Call Stack. Khi hàm hoàn thành, nó sẽ bị loại bỏ khỏi Call Stack.

2. **Web APIs:**
   - Các tác vụ bất đồng bộ (như `setTimeout`, AJAX, hoặc sự kiện DOM) được gửi đến Web APIs. Sau khi hoàn tất, chúng sẽ đưa kết quả vào **Task Queue** hoặc **Microtask Queue**.

3. **Task Queue:**
   - Chứa các tác vụ như callback của `setTimeout`, `setInterval`, hoặc các sự kiện từ DOM.

4. **Microtask Queue:**
   - Chứa các tác vụ ưu tiên cao hơn, như `Promise` hoặc các hàm async/await. Các tác vụ này được thực hiện trước các tác vụ trong Task Queue.

5. **Event Loop:**
   - Event Loop liên tục kiểm tra Call Stack. Nếu Call Stack trống, nó sẽ lấy các tác vụ từ Microtask Queue hoặc Task Queue để xử lý.

---

## Ví dụ minh họa

```javascript
console.log("Start");

setTimeout(() => {
    console.log("Timeout");
}, 0);

Promise.resolve().then(() => {
    console.log("Promise");
});

console.log("End");
```

**Kết quả:**
```
Start
End
Promise
Timeout
```

### Giải thích:
1. `console.log("Start")` và `console.log("End")` là các lệnh đồng bộ, được thực thi ngay lập tức.
2. `setTimeout` được đưa vào Web APIs và sau đó vào Task Queue.
3. `Promise.resolve()` được đưa vào Microtask Queue.
4. Event Loop xử lý Microtask Queue trước, nên "Promise" được in ra trước "Timeout".

---

## Tại sao Event Loop quan trọng?

- **Xử lý bất đồng bộ:** Event Loop cho phép JavaScript thực hiện nhiều tác vụ mà không làm gián đoạn luồng chính.
- **Cải thiện hiệu suất:** Các tác vụ như đọc/ghi tệp, gọi API hoặc xử lý sự kiện đều không chặn luồng thực thi chính.
- **Phát triển ứng dụng web:** Hiểu rõ Event Loop giúp bạn viết mã hiệu quả và tối ưu hơn cho các ứng dụng hiện đại.

---

## Kết luận

Event Loop là chìa khóa giúp JavaScript xử lý hiệu quả các tác vụ đồng thời, đặc biệt là trong các ứng dụng web. Hiểu rõ cơ chế hoạt động của Event Loop sẽ giúp bạn viết mã JavaScript tốt hơn, giảm thiểu lỗi và tối ưu hiệu suất ứng dụng.

---
