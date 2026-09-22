# BizHome 🏠

Phần mềm quản lý kinh doanh nhẹ nhàng, tối ưu cho hoạt động offline-first, thay thế hoàn toàn Excel với giao diện hiện đại và tốc độ cao.

## 🚀 Tech Stack

* **Backend:** Go (`net/http` thuần, SQLite cục bộ, hỗ trợ đồng bộ Cloud DB)
* **Frontend:** React, TypeScript, Vite, Tailwindcss, RadixUi
* **Runtime & Package Manager:** Bun
* **Linter & Compiler:** Oxlint, React Compiler

---

## 📁 Cấu trúc thư mục

```text
bizhome/
├── cmd/
│   └── server/
│       └── main.go          # Điểm khởi chạy Backend Go
├── internal/
│   ├── database/            # Quản lý SQLite local & Cloud sync
│   └── handlers/            # Các API endpoints (CRUD)
├── view/                # Ứng dụng giao diện React
│   ├── src/                 # Mã nguồn React components & custom router
│   ├── vite.config.ts       # Cấu hình Vite + React Compiler
│   └── package.json         # Quản lý gói bằng Bun
├── data/                    # Thư mục chứa file cơ sở dữ liệu bizhome.db
├── static/                  # Thư mục chứa file tĩnh sau khi build (nếu cần)
├── .gitignore
├── go.mod
└── README.md

🛠️ Hướng dẫn cài đặt và chạy phát triển (Development)
Đảm bảo trên máy tính của bạn đã cài đặt sẵn Go và Bun.

1. Khởi chạy Backend (Go)
Mở một cửa sổ Terminal tại thư mục gốc của dự án (bizhome/):

Bash
go run cmd/server/main.go
Server sẽ khởi động và tự động tạo cơ sở dữ liệu SQLite tại thư mục data/.

2. Khởi chạy Frontend (React + Vite)
Mở một cửa sổ Terminal mới, di chuyển vào thư mục frontend và chạy môi trường phát triển:

Bash
cd frontend

# Cài đặt thư viện bằng Bun
bun install

# Chạy dev server
bun run dev
Trình duyệt sẽ tự động mở giao diện quản lý BizHome.

📦 Đóng gói ứng dụng (Production Build)
Khi hoàn thiện tính năng và muốn đóng gói thành phẩm:

Build giao diện React thành các file tĩnh:

Bash
cd frontend
bun run build
Biên dịch Go backend gộp chung để tạo file thực thi hoàn chỉnh chạy offline.