# .NET Core Web Service – MongoDB

## Mô tả dự án
Dự án này phát triển một dịch vụ web API sử dụng **.NET Core** và **MongoDB** để quản lý thông tin sách. API hỗ trợ các thao tác CRUD (Create, Read, Update, Delete) và tích hợp Swagger UI để kiểm tra và thử nghiệm trực tiếp các endpoint.

### **Tính năng chính**
- **GET**: Lấy danh sách tất cả các sách hoặc chi tiết một cuốn sách theo ID.
- **POST**: Thêm một cuốn sách mới vào cơ sở dữ liệu.
- **PUT**: Cập nhật thông tin một cuốn sách dựa trên ID.
- **DELETE**: Xóa một cuốn sách khỏi cơ sở dữ liệu bằng ID.

---

## Các thành phần chính

### 1. Mô hình dữ liệu (Model)
#### **Book**
Lớp đại diện cho một cuốn sách, bao gồm các thuộc tính sau:
- **Id**: Định danh duy nhất của cuốn sách (kiểu ObjectId của MongoDB).
- **BookName**: Tên cuốn sách.
- **Price**: Giá tiền của cuốn sách.
- **Category**: Thể loại của cuốn sách.
- **Author**: Tác giả của cuốn sách.

#### **BookStoreDatabaseSettings**
Lớp chứa thông tin cấu hình kết nối MongoDB:
- **ConnectionString**: URL kết nối đến máy chủ MongoDB.
- **DatabaseName**: Tên của cơ sở dữ liệu.
- **BooksCollectionName**: Tên của bộ sưu tập nơi lưu trữ thông tin sách.

---

### 2. Bộ điều khiển (Controller)
#### **BooksController**
Đây là lớp xử lý các API để tương tác với dữ liệu sách. Các phương thức chính:
- **GET**:
  - Lấy toàn bộ sách từ cơ sở dữ liệu.
  - Truy vấn chi tiết một cuốn sách dựa trên ID.
- **POST**: Thêm một cuốn sách mới.
- **PUT**: Cập nhật thông tin của một cuốn sách.
- **DELETE**: Xóa một cuốn sách dựa trên ID.

---

### 3. Dịch vụ (Service)
#### **BooksService**
Lớp xử lý logic liên quan đến MongoDB, cung cấp các chức năng chính:
- **GetAsync**: Truy xuất danh sách toàn bộ sách hoặc chi tiết sách theo ID.
- **CreateAsync**: Thêm một cuốn sách mới.
- **UpdateAsync**: Cập nhật thông tin sách đã tồn tại.
- **RemoveAsync**: Xóa một cuốn sách.

---

### 4. **Cấu hình MongoDB** trong `appsettings.json`

- Cấu hình kết nối MongoDB và tên cơ sở dữ liệu được lưu trữ trong `appsettings.json`:
  ```json
  "BookStoreDatabase": {
    "ConnectionString": "mongodb://localhost:27017",
    "DatabaseName": "BookStore",
    "BooksCollectionName": "Books"
  }
## Kết quả

API quản lý sách đã được triển khai thành công với các chức năng chính. Các endpoint hoạt động như mong đợi và kết nối ổn định với MongoDB. Dưới đây là kết quả thử nghiệm:

- **API hoạt động đúng**: Các phương thức GET, POST, PUT, DELETE đều thực hiện đúng chức năng với dữ liệu trong cơ sở dữ liệu MongoDB.
- **Swagger UI**: Được tích hợp để thử nghiệm các API trực tiếp trên trình duyệt, hỗ trợ kiểm tra và phát triển dễ dàng hơn.
- **Tương tác cơ sở dữ liệu**: API kết nối thành công với MongoDB, thực hiện đầy đủ các thao tác CRUD.

---

### **1. GET: Lấy danh sách toàn bộ sách**
<img width="1182" alt="Image" src="https://github.com/user-attachments/assets/b6c66839-aae3-4a7e-8343-76b971bcdc87" />

---

### **2. POST: Thêm sách mới**
<img width="1133" alt="Image" src="https://github.com/user-attachments/assets/6f0aedd7-6533-4df3-9ce5-b003baf5bffb" />

---

### **3. GET: Lấy thông tin chi tiết một cuốn sách**
<img width="1180" alt="Image" src="https://github.com/user-attachments/assets/27944dfa-e07a-45e1-94f8-8332203a42d2" />

---

### **4. PUT: Cập nhật thông tin sách**
<img width="1167" alt="Image" src="https://github.com/user-attachments/assets/ddc95544-a31b-4c16-8c07-7c944d8c7284" />

---

### **5. DELETE: Xóa một cuốn sách**
<img width="1193" alt="Image" src="https://github.com/user-attachments/assets/a40412fa-bc02-4073-9b7f-365e84468998" />

---

- **Tương tác cơ sở dữ liệu**: API đã kết nối thành công với MongoDB, thực hiện đầy đủ các thao tác CRUD một cách hiệu quả.
- **Swagger**: Hỗ trợ thử nghiệm API trực tiếp trên trình duyệt, giúp quá trình kiểm tra và phát triển trở nên thuận tiện hơn cho người dùng.

