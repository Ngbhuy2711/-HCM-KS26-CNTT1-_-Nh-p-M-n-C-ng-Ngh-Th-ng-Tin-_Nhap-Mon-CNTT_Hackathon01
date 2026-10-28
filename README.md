- **Mã đề:** 15
- **Họ tên:** Nguyễn Bảo Huy
- **Lớp:** KS26-HCM-CNTT1
- **Link repository:** https://github.com/Ngbhuy2711/-HCM-KS26-CNTT1-_-Nh-p-M-n-C-ng-Ngh-Th-ng-Tin-_Nhap-Mon-CNTT_Hackathon01
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```powershell
Get-ChildItem -Force
Get-ChildItem -Recurse -Force
Get-ChildItem -Recurse -Force | Where-Object { $_.FullName -notmatch '\\.git(\\|$)' } | Select-Object -ExpandProperty FullName
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
D:\starter-kit\data
D:\starter-kit\docs
D:\starter-kit\logs
D:\starter-kit\media
D:\starter-kit\scripts
D:\starter-kit\bai_lam.md
D:\starter-kit\README.md
D:\starter-kit\data\lich_chup_thang_5.xlsx
D:\starter-kit\docs\Bang Gia Goi.txt
D:\starter-kit\logs\daily_report.txt
D:\starter-kit\logs\Studio.log
D:\starter-kit\logs\tong_hop.txt
D:\starter-kit\media\Logo Studio Anh.PNG
D:\starter-kit\scripts\auto_report.ps1
```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```powershell
Get-Content .\logs\Studio.log | Select-String -Pattern '\[ERROR\]' | Set-Content .\logs\daily_report.txt -Encoding UTF8
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2026-05-28 07:29:30 [ERROR] Tai anh len may chu that bai
2026-05-28 07:44:30 [ERROR] Tai anh len may chu that bai
```

## 4.4. Thao tác với tài liệu Markdown (README.md)

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```powershell
.\scripts\auto_report.ps1
powershell.exe -NoProfile -ExecutionPolicy Bypass -File .\scripts\auto_report.ps1
```

### Kết quả hiển thị

```text
Lần gọi trực tiếp bị chặn bởi ExecutionPolicy của Windows.
Da tao bao cao: logs/daily_report.txt (7 dong loi)
Da tao bao cao tong hop: logs/tong_hop.txt
```

## 4.6. Đếm số dòng lỗi

### Lệnh

```powershell
(Select-String -Path .\logs\daily_report.txt -Pattern '\[ERROR\]').Count
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
7
```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File .\scripts\auto_report.ps1
Get-Content .\logs\tong_hop.txt
```

### Nội dung file logs/tong_hop.txt

```text
Bao cao tong hop
Tong so dong log: 20
INFO: 10
WARNING: 3
ERROR: 7
File loc loi: logs/daily_report.txt

## 4.8. Excel

> Đã kiểm tra file `data/lich_chup_thang_5.xlsx` (các sheet `LichChup` và `GoiChup`). Đề bài được cung cấp không nêu thao tác Excel cụ thể; phần này cần yêu cầu chi tiết để chỉnh sửa đúng.
