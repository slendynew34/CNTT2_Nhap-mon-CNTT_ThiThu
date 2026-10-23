# BÀI LÀM – THI THỬ HACKATHON 01

- **Mã đề:** Thi thử
- **Họ tên:** Phạm Vũ Tuấn Kiệt
- **Lớp:** CNTT2
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Window

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
Get-ChildItem -Recurse -Force
mv nhap_hang.txt docs/
mv "Logo Van Phong Pham.PNG" media/
cp media/"Logo Van Phong Pham.PNG" backup/
rm temp_131.tmp
cd logs
ls
cd ..

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Directory: C:\van-phong-pham-website

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         10/23/2026  9:12 AM                 backup
d-----         10/23/2026  9:12 AM                 data
d-----         10/23/2026  9:12 AM                 docs
d-----         10/23/2026  9:12 AM                 logs
d-----         10/23/2026  9:12 AM                 media
-a----         10/23/2026  9:12 AM                .env
-a----         10/23/2026  9:12 AM                Shop.log

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
Get-Content logs/shop.log | Select-String "ERROR" > logs/daily_report.txt
Get-Content logs/daily_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
[2026-10-01 08:15:22] [ERROR] Kết nối cơ sở dữ liệu thất bại.
[2026-10-01 08:20:45] [ERROR] Không tìm thấy tệp cấu hình hệ thống.

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\auto_report.ps1

```

### Nội dung file logs/auto_report.txt

```text
=== BAO CAO LOI ===
[2026-10-01 08:15:22] [ERROR] Kết nối cơ sở dữ liệu thất bại.
[2026-10-01 08:20:45] [ERROR] Không tìm thấy tệp cấu hình hệ thống.
[2026-10-01 09:10:11] [ERROR] Lỗi phân quyền truy cập thư mục logs.

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
(Get-Content logs/shop.log | Select-String "ERROR").Count

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
3

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
"=== TONG HOP LOG ===" > logs/tong_hop.txt
Get-Content logs/shop.log | Select-String "WARNING" >> logs/tong_hop.txt
(Get-Content logs/shop.log | Select-String "ERROR").Count >> logs/tong_hop.txt
Get-Content logs/tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG ===
[2026-10-01 08:25:10] [WARNING] Dung lượng ổ đĩa sắp đầy.
[2026-10-01 09:00:00] [WARNING] Phát hiện truy cập từ địa chỉ IP lạ.
3

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_ban_thang_10.xlsx`, không cần ghi vào đây.
