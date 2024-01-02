# Coding Conventions
## 1. Quy tắc đặt tên biến trong lập trình

- CamelCase

Sử dụng camelCase để đặt tên biến, bắt đầu mỗi từ bằng chữ in hoa, trừ từ đầu tiên.

```javascript
✅ var myVariable;
✅ var totalAmount = 0;
❌ let MyVariable;
❌ let totalAmount = 0;
```



- Đặt Tên Rõ Ràng

Đặt tên biến sao cho chúng mô tả rõ chức năng hoặc nội dung của biến. Ví dụ: `customerName` thay vì `cn`, `totalRevenue` thay vì `tr`.

- Tránh Tên Biến Ngắn Gọn

Tránh sử dụng các tên biến ngắn gọn không mô tả đúng chức năng của chúng. Ví dụ: `numberOfItems` thay vì `num`, `averageScore` thay vì `avg`.

- Nhất Quán Trong Toàn Bộ Dự Án

Duy trì sự nhất quán trong cách đặt tên biến để làm cho mã nguồn dễ đọc và bảo trì. Sử dụng quy tắc chung và tuân thủ chúng trong toàn bộ dự án.

 Tránh Tên Giống Nhau Ở Nhiều Phạm Vi Khác Nhau

Tránh đặt tên biến giống nhau ở nhiều phạm vi khác nhau để tránh nhầm lẫn và xung đột. Ví dụ: `totalAmount` không nên được sử dụng cho một biến khác ở một hàm khác.

- Đặt Tên Biến Hằng (Constant)
Đặt tên biến hằng (constant) bằng chữ in hoa và sử dụng gạch dưới để phân cách các từ. Ví dụ: `MAX_VALUE`, `PI`, `DEFAULT_TIMEOUT`.

- Không Sử Dụng Tên Biến Quá Dài

Tránh sử dụng tên biến quá dài, giữ cho chúng ngắn gọn để tăng tính đọc hiểu và bảo trì. Ví dụ: `thisIsAnExcessivelyLongVariableName` nên được viết ngắn gọn hơn.

- Loại Bỏ Biến Không Cần Thiết

Loại bỏ các biến không cần thiết để giảm kích thước mã nguồn và nguy cơ lỗi.

- Mô Tả Đúng Chức Năng

Tên biến nên mô tả chính xác chức năng hoặc nội dung của biến để giúp người đọc hiểu được mục đích sử dụng của nó. Ví dụ: `userAge` thay vì `ageVar`, `numberOfStudents` thay vì `num`.
