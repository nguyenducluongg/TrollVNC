# TrollVNC Context

## Tổng quan dự án (Project Overview)
TrollVNC là một VNC server dành cho thiết bị iOS jailbroken, hỗ trợ điều khiển màn hình từ xa. Phiên bản này đã được tối ưu và xây dựng (build) thành công để hoạt động ổn định trên môi trường jailbreak **RootHide** sử dụng **Dopamine 2** (iOS 15.0 - 16.x, ARM64/ARM64e).

## Cấu trúc thư mục (Directory Structure)
- `src/`: Mã nguồn chính của VNC server daemon (`trollvncserver`) và manager (`trollvncmanager`).
- `prefs/`: Giao diện cài đặt TrollVNC (Preferences / Control Center).
- `app/`: Ứng dụng TrollVNC iOS (nếu build ở mode bootstrap).
- `devkit/`: Chứa các script tiện ích để chuyển đổi cấu hình build (rootless, roothide, bootstrap, simulator).
- `include/` và `lib/`: Các header và thư viện liên kết tĩnh (VNC, OpenSSL, libz, turbojpeg, png...).
- `layout/`: Cấu trúc thư mục đóng gói DEB.

## Trạng thái hiện tại & Mục tiêu
- **Mục tiêu**: Đã biên dịch đóng gói và phát hành gói cài đặt `.deb` tương thích hoàn toàn với kiến trúc RootHide (arm64/arm64e) trên Dopamine 2.
- **Tính năng mới**:
  - **Tối ưu Web UI**: Nút **Connect/Disconnect** thủ công để tự khởi tạo/ngắt capture luồng VNC giúp tối ưu tài nguyên thiết bị và lưu lượng truyền tải.
  - **Telemetry Stats Overlay**: Hiển thị thời gian thực chỉ số CPU, RAM, Disk qua WebSocket/HTTP (`stats.json`) dưới dạng biểu đồ màu sắc trực quan (Glassmorphism).
  - **Cài đặt đa ngôn ngữ độc lập**: Tuỳ chọn chọn ngôn ngữ (tiếng Việt, tiếng Anh, tiếng Trung) tự chuyển đổi động ngay trong Preference Bundle.
  - **Dọn dẹp nhật ký (Log Management)**: Tự động thu gọn log files (`trollvnc-stdout.log` và `trollvnc-stderr.log`) về 0 khi dung lượng vượt quá 5MB để tránh tràn bộ nhớ. Đồng thời kích hoạt tính năng xoá log thủ công.

## Lịch sử thay đổi (Change Log)
- **2026-06-01**: Khởi tạo tài liệu `CONTEXT.md` và bắt đầu kế hoạch phân tích/build cho RootHide Dopamine 2.
- **2026-06-01 (Tiếp tục)**: Triển khai hoàn tất việc sửa đúp Theos-Roothide, Việt hoá giao diện và nâng cấp Web UI (Connect button, telemetry, log limit, manual language settings bundle control), đóng gói thành công tệp deb kiểm thử tại `./packages/com.82flex.trollvnc_3.2-272_iphoneos-arm64e.deb`.

