# Nhật ký đồng bộ dữ liệu câu hỏi

## Lần 1: 17/11/2026, từ Claude Study Atlas (494 câu, 4 chứng chỉ)

**Nguồn:** file `Claude Study Atlas · 494 câu hỏi · 4 chứng chỉ.html` (bản lưu của https://claude-study-atlas.vercel.app/). Đã đối chiếu với trang online: cùng 494 câu, 4 chứng chỉ.

### Kết quả so sánh

| Bộ | Trước | Sau | Thay đổi |
|---|---|---|---|
| CCAR-F · Architect Foundations | 162 | 162 | Không đổi (giống hệt từng trường) |
| CCAR-P · Architect Professional | 116 | 116 | Không đổi |
| CCDV-F · Developer Foundations | 97 | 97 | Không đổi |
| **CCAO-F · Associate Foundations** | 0 | **119** | **Bộ mới** |
| **Tổng** | **375** | **494** | **+119 câu** |

- 375 câu cũ: không câu nào bị sửa, xoá hay đổi đáp án. Mã câu (`id`) giữ nguyên nên **tiến độ học, Sổ câu sai, ghi chú… trên máy bạn không bị ảnh hưởng**.
- 119 câu CCAO-F mới: mã `CCAO-F:t1q1` đến `CCAO-F:t1q119`, gồm 86 câu chọn 1 đáp án và 33 câu chọn nhiều đáp án. Tất cả thuộc "Chủ đề 1" (Projects, Connectors, Prompting và quy trình Claude).

### Đã cập nhật trong web

- Dữ liệu câu hỏi (`DATA` trong `index.html`): thay bằng bộ 494 câu, kèm thông tin bộ CCAO-F.
- Tiêu đề trang, thanh bên, Tổng quan: "4 chứng chỉ · 494 câu", "4 bộ học, một hệ thống".
- Thêm bộ CCAO-F vào: danh sách Ngân hàng câu hỏi (ký hiệu **AsF**, màu đỏ), bộ lọc Bộ học, tên chứng chỉ khi copy câu hỏi cho AI ("Claude Certified Associate – Foundations (CCAO-F)").
- CCAO-F dùng được ở mọi tab: Ôn tập, Học theo câu, Flashcards, Học tủ, Sổ tay, Thi thử (kể cả Sổ câu sai), Thống kê.

### Hạn chế của bộ CCAO-F (do dữ liệu nguồn)

- Chỉ có **tiếng Anh**: chưa có bản dịch tiếng Việt cho đề và đáp án. Phần giải thích (phân tích đề, vì sao loại) có sẵn và viết bằng tiếng Việt.
- **Chưa có mẹo** ("Thấy … → chọn …"), nên panel *Mẹo chọn đáp án* và các thẻ Học tủ của CCAO-F không hiện mẹo.
- Chưa chia domain chi tiết: cả 119 câu nằm trong một chủ đề, và không có trong tab *Kiến thức thi* (tab này chỉ dành cho CCDV-F).
