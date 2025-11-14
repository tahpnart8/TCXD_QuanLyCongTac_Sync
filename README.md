# 🚀 Sync - Phần mềm Quản lý Công tác (Đồ án OOP)

Đây là đồ án môn học Lập trình Hướng đối tượng, xây dựng một ứng dụng WinForms (.NET Framework) mô phỏng hệ thống quản lý công việc và quy trình nội bộ cho một tổ chức (ví dụ: một Ban trong Đoàn Thanh niên - Hội Sinh viên).

## 🎯 Bối cảnh & Mục tiêu

Dự án được xây dựng nhằm giải quyết các vấn đề thực tiễn trong quản lý công việc nhóm: thông tin phân tán, quy trình thủ công, và khó khăn trong việc theo dõi tiến độ. Mục tiêu là số hóa toàn bộ vòng đời của một công tác – từ khởi tạo, phân công, thực thi, cho đến khi được xét duyệt và lưu trữ – trên một nền tảng tập trung.

## ✨ Tính năng nổi bật

-   🔐 **Đăng nhập & Phân quyền:** Hệ thống phân chia quyền hạn rõ ràng cho các vai trò: Trưởng ban (Admin), Quản lý (Manager), và Thành viên (Member).
-   📋 **Quản lý Công tác Toàn diện:** Giao diện quản lý tổng quan theo dạng bảng Kanban, cho phép Trưởng ban thêm/xóa các "Mảng công tác".
-   👤 **Không gian làm việc cá nhân:** Mỗi người dùng có một trang "My Tasks" để theo dõi các công việc được giao cho riêng mình.
-   ✅ **Quy trình Xét duyệt:** Các công tác sau khi hoàn thành có thể được gửi đi để cấp trên (Trưởng ban) xét duyệt hoặc từ chối.
-   🔔 **Hệ thống Thông báo:** Tự động tạo thông báo khi người dùng được giao việc, công tác sắp hết hạn, hoặc công tác được duyệt/từ chối.
-   👥 **Quản lý Người dùng:** Trưởng ban có quyền thêm, chỉnh sửa, và vô hiệu hóa tài khoản người dùng.
-   📂 **Thư viện Tài liệu:** Cho phép người dùng tải lên và tải về các tài liệu liên quan đến công việc.
-   📊 **Xuất Báo cáo:** Chức năng xuất báo cáo tổng quan về tình hình công tác ra file CSV.

## 🏗️ Kiến trúc & Kỹ thuật Lập trình

Dự án được xây dựng với mục tiêu tuân thủ nghiêm ngặt các nguyên tắc thiết kế phần mềm hiện đại.

#### 1. Ngôn ngữ & Nền tảng
-   **Ngôn ngữ:** C#
-   **Nền tảng:** .NET Framework
-   **Giao diện:** Windows Forms

#### 2. Kiến trúc 3 lớp (3-Layer Architecture)
Ứng dụng được phân tách rõ ràng thành các lớp logic độc lập:
-   `GUI (Presentation Layer)`: Chịu trách nhiệm hiển thị giao diện và tương tác với người dùng.
-   `BLL (Business Logic Layer)`: Là "bộ não" của ứng dụng, xử lý toàn bộ các quy tắc nghiệp vụ.
-   `DAL (Data Access Layer)`: Đảm nhiệm việc truy xuất dữ liệu từ file `data.json` thông qua kỹ thuật Serialization/Deserialization.
-   `DOMAIN`: Lớp lõi, định nghĩa các thực thể và đối tượng giá trị của bài toán (User, Task, Department...). Đây là lớp độc lập, không phụ thuộc vào bất kỳ tầng nào khác.
#### 3. Các nguyên lý Lập trình Hướng đối tượng (OOP)
Dự án áp dụng triệt để 4 tính chất trụ cột của OOP:
-   **Tính Đóng gói (Encapsulation):** Dữ liệu được bảo vệ thông qua `private fields` và truy cập qua `public properties`.
-   **Tính Kế thừa (Inheritance):** Xây dựng hệ thống phân cấp lớp (ví dụ: `User`, `Task` kế thừa từ `BaseEntity`).
-   **Tính Đa hình (Polymorphism):** Thể hiện qua việc `override` các phương thức `virtual` từ lớp cha.
-   **Tính Trừu tượng (Abstraction):** Sử dụng các `abstract class` và `interface` để tạo ra các hợp đồng, giảm sự phụ thuộc giữa các thành phần.

#### 4. Design Patterns
Một số mẫu thiết kế đã được áp dụng để giải quyết các vấn đề cụ thể:
-   **Singleton Pattern:** Đảm bảo lớp `DataManager` chỉ có một thể hiện duy nhất trong toàn bộ ứng dụng, quản lý việc đọc/ghi file tập trung.
-   **Repository Pattern:** Tạo một lớp trừu tượng giữa BLL và nguồn dữ liệu, giúp BLL không cần biết dữ liệu được lưu ở đâu và như thế nào.
-   **Factory Pattern:** Sử dụng lớp `NotificationFactory` để tạo ra các đối tượng `Notification` một cách nhất quán và che giấu logic khởi tạo phức tạp.

## 🛠️ Hướng dẫn Cài đặt & Chạy thử

1.  **Tải file .rar** này về máy của bạn:
2.  Mở file `TCXD_QuanlyCongtac.sln` bằng **Visual Studio** (phiên bản 2019 trở lên).
3.  **Build Solution** (F6 hoặc `Ctrl + Shift + B`) để Visual Studio tải về các tài nguyên cần thiết.
4.  Nhấn **F5** để chạy chương trình.
5.  Sử dụng tài khoản quản trị viên mặc định để đăng nhập và trải nghiệm đầy đủ tính năng:
    -   **Username:** `admin`
    -   **Password:** `admin`

---
*Đây là sản phẩm của đồ án môn học Lập trình Hướng đối tượng.*
