# Coding Conventions
## 1. Quy tắc đặt tên biến trong lập trình

- **CamelCase**

Sử dụng camelCase để đặt tên biến trừ một số trường hợp đặc biệt như là hằng số,...
```javascript
// ❌ Không tốt
var MyVariable; // PascalCase
var totalamount = 0; // snackcase

// ✅ Tốt
var myVariable;
var totalAmount = 0;
```

- **Đặt Tên Rõ Ràng**

Đặt tên biến sao cho chúng mô tả rõ chức năng hoặc nội dung của biến.
```javascript
// ❌ Không tốt
let cn = "John Doe";
let tr = 1000;

// ✅ Tốt
let customerName = "John Doe";
let totalRevenue = 1000;
```

- **Tránh Tên Biến Ngắn Gọn**

Tránh sử dụng các tên biến ngắn gọn không mô tả đúng chức năng của chúng.
```javascript
// ❌ Không tốt
let num = 5;
let avg = 8.5;

// ✅ Tốt
let numberOfItems = 5;
let averageScore = 8.5;
```

- **Nhất Quán Trong Toàn Bộ Dự Án**

Duy trì sự nhất quán trong cách đặt tên biến để làm cho mã nguồn dễ đọc và bảo trì. Sử dụng quy tắc chung và tuân thủ chúng trong toàn bộ dự án.
```javascript
// ❌ Không tốt
let user_age = 25;
let totalCost = 50.5;

// ✅ Tốt
let userAge = 25;
let totalCost = 50.5;
```

- **Tránh Tên Giống Nhau Ở Nhiều Phạm Vi Khác Nhau**

Tránh đặt tên biến giống nhau ở nhiều phạm vi khác nhau để tránh nhầm lẫn và xung đột.
```javascript
// ❌ Không tốt
function calculateTotal() {
    let totalAmount = 0;
    //...
}

function printTotal() {
    let totalAmount = 100;
    //...
}

// ✅ Tốt
function calculateTotal() {
    let totalAmount = 0;
    //...
}

function printTotal() {
    let printedTotal = 100;
    //...
}
```

- **Đặt Tên Biến Hằng (Constant)**

Đặt tên biến hằng (constant) bằng chữ in hoa và sử dụng gạch dưới để phân cách các từ.
```javascript
// ❌ Không tốt
const maxvalue = 1000;
const piValue = 3.14;

// ✅ Tốt
const MAX_VALUE = 1000;
const PI = 3.14;
```

- **Không Sử Dụng Tên Biến Quá Dài**

Tránh sử dụng tên biến quá dài, giữ cho chúng ngắn gọn để tăng tính đọc hiểu và bảo trì.
```javascript
// ❌ Không tốt
let thisIsAnExcessivelyLongVariableName = "Too long!";

// ✅ Tốt
let shortName = "Better!";
```

- **Loại Bỏ Biến Không Cần Thiết**

Loại bỏ các biến không cần thiết để giảm kích thước mã nguồn và nguy cơ lỗi.
```javascript
// ❌ Không tốt
let unnecessaryVariable = "Unused";

// ✅ Tốt
// Biến không cần thiết đã được loại bỏ
```

- **Mô Tả Đúng Chức Năng**

Tên biến nên mô tả chính xác chức năng hoặc nội dung của biến để giúp người đọc hiểu được mục đích sử dụng của nó.
```javascript
// ❌ Không tốt
let ageVar;
let num;

// ✅ Tốt
let userAge;
let numberOfStudents;
```
