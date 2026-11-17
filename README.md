# Wind Claude Certificate

Trang ôn luyện 3 chứng chỉ Claude (CCDV-F, CCAR-F, CCAR-P): 375 câu hỏi, flashcard, thi thử, học tủ, sổ câu sai, sổ từ vựng và thống kê.

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
- **↶ Hoàn tác lần nhập** đưa dữ liệu về trạng thái trước lần nhập gần nhất.
- File sao lưu gồm: tiến độ từng câu, lịch sử thi, câu đánh dấu, sổ câu sai, học tủ (hộp Leitner), sổ từ, nghĩa tự thêm, tiến độ học từ và điểm HUD.
