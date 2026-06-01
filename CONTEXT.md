# TrollVNC Context

## Tổng quan dự án (Project Overview)
TrollVNC là một VNC server dành cho thiết bị iOS jailbroken, hỗ trợ điều khiển màn hình từ xa. Phiên bản hiện tại cần được tối ưu và xây dựng (build) để hoạt động ổn định trên môi trường jailbreak **RootHide** sử dụng **Dopamine 2** (iOS 15.0 - 16.x, ARM64e).

## Cấu trúc thư mục (Directory Structure)
- `src/`: Mã nguồn chính của VNC server daemon (`trollvncserver`) và manager (`trollvncmanager`).
- `prefs/`: Giao diện cài đặt TrollVNC (Preferences / Control Center).
- `app/`: Ứng dụng TrollVNC iOS (nếu build ở mode bootstrap).
- `devkit/`: Chứa các script tiện ích để chuyển đổi cấu hình build (rootless, roothide, bootstrap, simulator).
- `include/` và `lib/`: Các header và thư viện liên kết tĩnh (VNC, OpenSSL, libz, turbojpeg, png...).
- `layout/`: Cấu trúc thư mục đóng gói DEB.

## Trạng thái hiện tại & Mục tiêu
- **Mục tiêu**: Biên dịch thành công TrollVNC tương thích với RootHide (arm64e) trên Dopamine 2.
- **Trạng thái hiện tại**: Đang nghiên cứu cấu hình Theos cục bộ và SDK trên máy để thực hiện việc build cho `roothide`.

## Lịch sử thay đổi (Change Log)
- **2026-06-01**: Khởi tạo tài liệu `CONTEXT.md` và bắt đầu kế hoạch phân tích/build cho RootHide Dopamine 2.
