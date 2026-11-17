# Wind Claude Certificate

Trang ôn luyện 4 chứng chỉ Claude (CCAR-F, CCAR-P, CCDV-F, CCAO-F): 494 câu hỏi, flashcard, thi thử, học tủ, sổ câu sai, sổ từ vựng và thống kê.

## Giao diện

- **Theme Thường**: font dễ đọc (Inter), dùng mặc định.
- **Theme Game**: font pixel monospace, khung vuông, có HP, Combo, Level, EXP. Bấm nút ✨/🎮 trên thanh trên cùng để đổi.
- Nút ☀ đổi giữa chế độ sáng và tối, dùng được với cả hai theme.

## Lịch sử đồng bộ dữ liệu

Xem [DONG-BO-DU-LIEU.md](DONG-BO-DU-LIEU.md) để biết mỗi lần đồng bộ đã thêm hoặc sửa những gì.

## Cấu trúc

Toàn bộ ứng dụng nằm trong một file tĩnh `index.html`: không cần build, không cần server.

## Chạy thử ở máy

Mở trực tiếp `index.html` bằng trình duyệt.

## Deploy lên Vercel

1. Vercel → **Add New → Project** → **Import** repo này.
2. Framework Preset: **Other**. Không cần Build Command, Output Directory để mặc định.
3. Bấm **Deploy**. Mỗi lần push lên `main`, Vercel tự deploy lại.

## Dữ liệu học

- Tiến độ được lưu trong `localStorage` của từng trình duyệt.
- Để chuyển sang máy khác: vào phần **Quản lý dữ liệu học**, bấm **↓ Sao lưu JSON** để tải file. Trên máy mới, bấm **↑ Khôi phục JSON** (gộp với dữ liệu đang có) hoặc **↑ Khôi phục (ghi đè)**.
- **⇅ Copy / dán text** (ở Sổ câu sai, Học từ mới, Thống kê): tạo một mã `WCC1:…` để gửi qua Zalo/Messenger/email rồi dán vào máy khác. Chọn Sổ câu sai, Sổ từ vựng hoặc Toàn bộ dữ liệu. Muốn máy mới giống hệt thì chọn **Toàn bộ dữ liệu**.
- **↶ Hoàn tác lần nhập** đưa dữ liệu về trạng thái trước lần nhập gần nhất.
- File sao lưu gồm: tiến độ từng câu, lịch sử thi, câu đánh dấu, sổ câu sai, học tủ (hộp Leitner), sổ từ, nghĩa tự thêm, tiến độ học từ và điểm HUD.
