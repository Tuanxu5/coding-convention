# Coding Conventions

## 1. Cách clean code khi sử dụng biến

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

## 2. Cách clean code khi sử dụng function

- **Tên hàm phải mô tả đúng chức năng và rõ ràng**

Tên của hàm nên mô tả chính xác công việc mà hàm thực hiện. Điều này giúp đọc mã nguồn dễ hiểu và giảm khả năng hiểu lầm.

```javascript
// ❌ Không tốt
function process(data) {
  //...
}

// ✅ Tốt
function calculateTotalPrice(cartItems) {
  //...
}
```

- **Thứ tự thực hiện hàm phải đúng thứ tự**

Các bước thực hiện trong hàm nên được sắp xếp một cách hợp lý và dễ đọc. Điều này giúp mọi người đọc mã hiểu rõ quá trình thực hiện.

```javascript
// ❌ Không tốt
function processData(data) {
  cleanData(data);
  transformData(data);
  analyzeData(data);
}

// ✅ Tốt
function processData(data) {
  analyzeData(data);
  transformData(data);
  cleanData(data);
}
```

- **Tham số truyền vào phải rõ ràng và không nên truyền quá nhiều tham số**

Số lượng tham số nên được giữ ở mức tối thiểu và phải được đặt tên mô tả rõ mục đích của chúng.

```javascript
// ❌ Không tốt
function calculateTotal(a, b, c, d) {
  //...
}

// ✅ Tốt
function calculateTotal(price, quantity) {
  //...
}
```

- **Hạn chế sử dụng side effects**

Các hàm nên tập trung vào việc thực hiện một công việc cụ thể và trả về kết quả thay vì thay đổi trạng thái bên ngoài (side effects).

```javascript
// ❌ Không tốt
let totalPrice = 0;

function calculateTotal(cartItems) {
  for (let item of cartItems) {
    totalPrice += item.price;
  }
}

// ✅ Tốt
function calculateTotal(cartItems) {
  let totalPrice = 0;
  for (let item of cartItems) {
    totalPrice += item.price;
  }
  return totalPrice;
}
```

- **Xử lý lỗi tốt**

Hàm cần xử lý các trường hợp lỗi một cách tốt, không để lỗi lan toả ra ngoài mà không được báo cáo.

```javascript
// ❌ Không tốt
function divide(a, b) {
  return a / b;
}

// ✅ Tốt
function divide(a, b) {
  if (b === 0) {
    throw new Error("Cannot divide by zero");
  }
  return a / b;
}
```

## 3. Cách clean code khi sử dụng comment

- **Chỉ comment những chỗ khó hiểu và quan trọng**

Comments nên tập trung vào giải thích những điều khó hiểu hoặc quan trọng mà không thể hiểu được từ mã nguồn mà không cần comment.

- **Ngắn gọn rõ ràng và nên sử dụng bằng tiếng Anh**

Comments nên được viết ngắn gọn và rõ ràng để dễ đọc. Sử dụng tiếng Anh để giữ tính nhất quán trong mã nguồn.

```javascript
// ❌ Không tốt
// Loop through the array to find the maximum value
for (let i = 0; i < array.length; i++) {
  //...
}

// ✅ Tốt
// Find the maximum value by iterating through the array
for (let i = 0; i < array.length; i++) {
  //...
}
```

- **Luôn cập nhật khi thay đổi code**

Comments nên được cập nhật khi có sự thay đổi trong mã nguồn để đảm bảo tính đồng bộ giữa comment và mã nguồn.

- **Dùng để giải thích tại sao chứ không phải làm gì**

Comments nên giải thích tại sao một phần mã nguồn được thực hiện như vậy thay vì mô tả nó làm gì.

## 4. Cách clean code khi sử dụng class

- **Nguyên tắc SOLID**

Cố gắng tuân thủ nguyên tắc SOLID (Single Responsibility Principle, Open/Closed Principle, Liskov Substitution Principle, Interface Segregation Principle, Dependency Inversion Principle).

- **Tránh quá nhiều tham số trong hàm tạo**

Hạn chế số lượng tham số trong hàm tạo để giữ nó ngắn gọn và dễ hiểu.
```javascript
// Không tốt
class Product {
    constructor(name, price, category, manufacturer, weight, quantity) {
        //...
    }
}

// Tốt
class Product {
    constructor(name, price, category) {
        //...
    }
}
```

- **Sử dụng kế thừa và giao tiếp một cách chín chắn**

Tận dụng kế thừa khi có mối quan hệ "is-a" (là một), và sử dụng giao tiếp (interface) khi có mối quan hệ "has-a" (có một).
```javascript
// Kế thừa (is-a)
class Shape {
    //...
}

class Circle extends Shape {
    //...
}

// Giao tiếp (has-a)
class Engine {
    //...
}

class Car {
    constructor(engine) {
        this.engine = engine;
    }
}
```

- **Ngắn gọn và chỉ thực hiện một nhiệm vụ**

Mỗi class nên có một mục đích cụ thể và thực hiện duy nhất một nhiệm vụ. Tránh "god class" có quá nhiều trách nhiệm.
```javascript
// Không tốt
class OrderProcessing {
    processOrder() {
        //...
    }

    generateInvoice() {
        //...
    }

    sendConfirmationEmail() {
        //...
    }
}

// Tốt
class OrderProcessor {
    processOrder() {
        //...
    }
}

class InvoiceGenerator {
    generateInvoice() {
        //...
    }
}

class EmailSender {
    sendConfirmationEmail() {
        //...
    }
}
```
