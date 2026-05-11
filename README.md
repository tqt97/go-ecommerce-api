# 🚀 Go Ecommerce API - Học Golang Từ Con Số 0

![Go Version](https://img.shields.io/badge/Go-1.22+-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Status](https://img.shields.io/badge/Status-Developing-yellow?style=for-the-badge)

Chào mừng bạn đến với dự án **Go Ecommerce API**. Đây là hành trình bắt đầu học Golang một cách thực chiến thông qua việc xây dựng một hệ thống thương mại điện tử chuyên nghiệp.

---

## 🏗️ Cấu Trúc Thư Mục (Project Structure)

Dự án tuân thủ cấu trúc chuẩn của cộng đồng Go (`golang-standards/project-layout`), giúp code dễ bảo trì, mở rộng và kiểm thử.

```text
.
├── cmd/                   # Điểm khởi đầu của ứng dụng (Entry Points)
│   ├── cli/               # Các công cụ dòng lệnh (CLI tools)
│   ├── cronjob/           # Các tác vụ chạy định kỳ (Worker/Cron)
│   └── server/            # 🚀 Chạy Web Server chính (main.go)
├── config/                # Lưu trữ các file cấu hình (YAML, JSON, .env)
├── internal/              # Code nội bộ (Private code - Trái tim của dự án)
│   ├── controller/        # Xử lý Request/Response (Tầng giao diện người dùng)
│   ├── initialize/        # Khởi tạo DB, Redis, Logger, v.v.
│   ├── middlewares/       # Các bộ lọc trung gian (Auth, Log, Recovery)
│   ├── models/            # Định nghĩa cấu trúc dữ liệu (Entities/Schemas)
│   ├── repo/              # Tầng làm việc với Database (Repository Pattern)
│   ├── router/            # Định nghĩa các tuyến đường API (Routes)
│   └── service/           # Tầng xử lý Logic nghiệp vụ (Business Logic)
├── migrations/            # Quản lý các file migration của Database
├── pkg/                   # Các package dùng chung (Có thể tái sử dụng ở dự án khác)
│   ├── logger/            # Cấu hình ghi Log (Zap, Logrus)
│   ├── setting/           # Quản lý đọc file cấu hình
│   └── utils/             # Các hàm tiện ích bổ trợ
├── response/              # Định nghĩa mã lỗi và cấu trúc phản hồi API chuẩn
├── scripts/               # Các script hỗ trợ build, deploy (Makefile, Docker)
├── tests/                 # Các bài kiểm tra (Unit test, Integration test)
├── third_party/           # Cấu hình hoặc công cụ từ bên thứ ba
├── go.mod                 # Quản lý dependencies (giống package.json)
└── README.md              # Tài liệu hướng dẫn dự án
```

---

## 🔍 Giải Thích Chi Tiết Các Thành Phần

### 1. `cmd/`

Nơi chứa các file `main.go`. Mỗi thư mục con trong `cmd` sẽ tạo ra một file thực thi riêng. Ví dụ: `cmd/server` để chạy API, `cmd/cli` để chạy các lệnh quản trị.

### 2. `internal/`

Đây là thư mục quan trọng nhất. Trong Go, các code nằm trong `internal` sẽ **không** thể bị import bởi các dự án bên ngoài. Điều này giúp bảo vệ logic cốt lõi của ứng dụng.

- **Controller**: Tiếp nhận yêu cầu từ client, kiểm tra dữ liệu đầu vào.
- **Service**: Nơi tập trung toàn bộ "chất xám" của dự án, xử lý các phép tính và quy trình nghiệp vụ.
- **Repo (Repository)**: Chỉ tập trung vào việc truy vấn Database (SQL, NoSQL).

### 3. `pkg/`

Chứa các thư viện bổ trợ mà bạn viết ra và cảm thấy nó đủ tốt để có thể mang sang dự án khác dùng mà không cần sửa đổi gì nhiều.

### 4. `initialize/`

Giúp hàm `main` sạch sẽ hơn bằng cách gom toàn bộ logic kết nối database, khởi tạo cache, hoặc logger vào đây.

### 5. `response/`

Giúp đồng bộ hóa định dạng phản hồi API. Thay vì mỗi nơi trả về một kiểu, chúng ta quy định một chuẩn chung (Success/Error).

---

## 🛠️ Hướng Dẫn Bắt Đầu

### Yêu Cầu Hệ Thống

- Go version 1.22 hoặc mới hơn.
- Database (MySQL/PostgreSQL) - *Tùy chọn theo tiến độ học*.

### Cài Đặt

1. Clone dự án:

   ```bash
   git clone https://github.com/tqt97/go-ecommerce-api.git
   ```

2. Cài đặt các thư viện:

   ```bash
   go mod tidy
   ```

3. Chạy ứng dụng:

   ```bash
   go run cmd/server/main.go
   ```

---
⭐ **Nếu bạn thấy dự án này hữu ích, hãy tặng một Star nhé!**
