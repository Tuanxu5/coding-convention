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
```Cpp
// ❌ Không tốt
class Product {
    constructor(name, price, category, manufacturer, weight, quantity) {
        //...
    }
}

// ✅ Tốt
class Product {
    constructor(name, price, category) {
        //...
    }
}
```

- **Sử dụng kế thừa và giao tiếp một cách chín chắn**

Tận dụng kế thừa khi có mối quan hệ "is-a" (là một), và sử dụng giao tiếp (interface) khi có mối quan hệ "has-a" (có một).
```Cpp
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
```Cpp
// ❌ Không tốt
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

// ✅ Tốt
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

## 5. Cách clean code khi sử dụng struct

- **Sử dụng Tên Mô Tả**

Tên của struct nên mô tả chính xác mục đích hoặc chức năng của nó.

```Cpp
// ❌ Không tốt
struct Data {
    //...
};

// ✅ Tốt
struct UserData {
    //...
};

```

- **Áp Dụng Nguyên Tắc Single Responsibility**

Struct nên thực hiện một nhiệm vụ cụ thể và không nên chịu trách nhiệm quá mức.
```Cpp
// ❌ Không tốt
struct FileData {
    readFromFile() {
        //...
    }

    writeToFile() {
        //...
    }
};

// ✅ Tốt
struct FileReader {
    readFromFile() {
        //...
    }
};

struct FileWriter {
    writeToFile() {
        //...
    }
};

```

- **Không Sử Dụng Cấu Trúc Như Class**

Struct thường được sử dụng cho các cấu trúc dữ liệu đơn giản và nên tránh sử dụng chúng giống như class.
```Cpp
// ❌ Không tốt
struct Point {
    int x;
    int y;
    void move(int newX, int newY) {
        x = newX;
        y = newY;
    }
};

// ✅ Tốt
struct Point {
    int x;
    int y;
};
void movePoint(Point& point, int newX, int newY) {
    point.x = newX;
    point.y = newY;
}

```

- **Đặt Các Thuộc Tính ở Đầu**

Đặt các thuộc tính của struct ở đầu giúp dễ đọc và hiểu cấu trúc.
```Cpp
// ✅ Tốt
struct UserData {
    void printData() {
        //...
    }
    int age;
    std::string name;
};

// Tốt
struct UserData {
    int age;
    std::string name;
    void printData() {
        //...
    }
};
```

- **Dùng Tính Chất Bất Biến Nếu Có Thể**

Nếu có thể, hãy sử dụng tính chất bất biến để đảm bảo rằng dữ liệu trong struct không thay đổi sau khi được khởi tạo.
```Cpp
// Bất biến
struct Point {
    const int x;
    const int y;
    Point(int x, int y) : x(x), y(y) {}
};
```

- **Đảm Bảo Cấu Trúc Thực Hiện Một Nhiệm Vụ Cụ Thể**

Mỗi struct nên thực hiện một nhiệm vụ cụ thể, và không nên có quá nhiều chức năng.
```Cpp
// ❌ Không tốt
struct File {
    std::string name;
    int size;
    void readFromFile() {
        //...
    }
    void writeToFile() {
        //...
    }
};

// ✅ Tốt
struct FileInfo {
    std::string name;
    int size;
};

struct FileReader {
    void readFromFile(FileInfo& file) {
        //...
    }
};

struct FileWriter {
    void writeToFile(FileInfo& file) {
        //...
    }
};
```

## 6. Cách clean code khi sử dụng component

- **Chia Components Thành Các Phần Nhỏ (Atomic Components)**

Chia components thành các phần nhỏ giúp giảm độ phức tạp của mỗi component và làm cho chúng dễ bảo trì và tái sử dụng hơn.

- **Tránh Sự Phụ Thuộc Lẫn Nhau (Interdependence)**

Phụ thuộc lẫn nhau có thể tạo ra vấn đề khi bạn cố gắng tái sử dụng components hoặc khi cần thay đổi một phần nhỏ mà phải cập nhật nhiều components liên quan.

- **Dùng Stateless Components Khi Có Thể**

Stateless components không quản lý trạng thái và thường ít phức tạp hơn, làm cho chúng dễ hiểu và dễ tái sử dụng.

- **Tuân Thủ Quy ước (Conventions)**

Tuân thủ quy ước giúp đảm bảo rằng mã nguồn của bạn sẽ được đồng nhất với các dự án khác và dễ hiểu hơn đối với cả bạn và đồng đội.

- **Nguyên Tắc Single Responsibility**

Mỗi component chỉ nên đảm nhận một trách nhiệm duy nhất, giúp giữ cho code dễ hiểu và tái sử dụng.