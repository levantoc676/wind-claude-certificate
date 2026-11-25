# Bàn giao: Wind Claude Certificate (để tiếp tục ở cuộc trò chuyện mới)

Cập nhật: 23/11/2026

## Dự án
- Web ôn thi chứng chỉ Claude, giao diện tiếng Việt. Toàn bộ web là một file `index.html` (khoảng 2,3 MB).
- Repo: `github.com/levantoc676/wind-claude-certificate`. Nhánh làm việc là `ninja-theme`, đẩy lên bằng `git push origin ninja-theme:main`. Vercel tự deploy từ `main`.
- Web: https://wind-claude-certificate.vercel.app. Mỗi tab có một URL riêng:
  - `#/on-tap`: Ôn tập câu hỏi
  - `#/meo-thi`: Mẹo thi CCAR-P
  - `#/hoc-tu`: Học tủ CCAR-P
  - `#/flashcards`
  - `#/hoc-tu-moi`: Học từ mới
  - `#/thi-thu`: Thi thử
  - `#/thong-ke`: Thống kê
- Link artifact (https://claude.ai/artifact/1q3qpVrDmcKmeab5eSmgWb) đang **cũ hơn repo nhiều**. Chỉ cập nhật được từ một chat mở ở chính trang artifact đó.
- Nhật ký đồng bộ dữ liệu: `DONG-BO-DU-LIEU.md` (trong repo, đã chép vào Project ở `claude/dong-bo-du-lieu.md`). Hiện tới **Lần 11**.

## Dữ liệu (nằm trong index.html)
- `<script type="application/json" id="wcc-data">`: **489 câu**.
  - CCAR-F 162, CCAR-P 113, CCDV-F 95, CCAO-F 119.
  - 5 câu trùng đã bị bỏ: CCAR-P #105, #108, #109 và CCDV-F #047, #067.
- `id="wcc-tips"`: tab Mẹo thi CCAR-P. Có 146 mẹo chia theo D1–D7, mỗi mẹo kèm số câu liên quan.
- `id="wcc-cramp"`: **Học tủ CCAR-P**. Dạng `{ "<số câu>": { "k": "key trong đề", "a": "đáp án tủ" } }`.
  - Key dạng nhóm viết `phần1 | phần2`, ví dụ `BEFORE running | selecting a model`, `guardrail | tactics`, `HTTP | data-exfiltration`, `Trenova Systems | p95`, `Diligence | actions`.
  - Phần trong ngoặc tiếng Việt tự hiện màu đỏ.
- Khi sửa dữ liệu JSON: dùng Python đọc rồi ghi lại khối JSON, nhớ thay `</` thành `<\/`. Sau khi sửa phải chạy `node --check` cho từng `<script>`.
- Chủ đề CCAR-P đã đánh số lại để **APn = Dn** theo exam guide:
  - AP1 = Design (17%)
  - AP2 = Models (13%)
  - AP3 = Integration (19%, chỉ có 3 câu)
  - AP4 = Eval (16%)
  - AP5 = Governance (14%)
  - AP6 = Stakeholder (14%)
  - AP7 = DevProd (7%)

## Quy ước khi sửa Học tủ (theo ý người dùng)
- **Key đề:** ưu tiên cụm từ ở 1–2 dòng đầu, hoặc con số đáng nhớ, hoặc nhóm `X | Y` để các câu giống nhau nằm cạnh nhau khi xếp A–Z. Key phải có trong đề và **chỉ có ở đúng câu đó**.
- **Đáp án tủ:** ưu tiên **chữ đầu** của đáp án đúng nếu chữ đó không trùng với đáp án sai. Câu chọn 2 thì viết theo thứ tự xuất hiện, ví dụ `Enable + Cache`.
- **Câu Yes/No và câu ghép mục:** ghi theo **nội dung** (ví dụ `No = Replacing a vector index + sub-50-millisecond`), không ghi theo vị trí, vì chế độ Ngẫu nhiên sẽ đảo thứ tự.
- **Luôn kiểm tra trước khi sửa:** key có trong đề hay không, đáp án tủ có khớp đúng đáp án đúng hay không. Nếu người dùng nhớ nhầm (ví dụ #024 muốn ghi "Rotate" nhưng đó là đáp án sai) thì báo lại cho người dùng, không ghi đáp án sai.
- Tab Học tủ có 3 chế độ: Theo chủ đề AP, Theo key đề bài (A–Z), Chữ đầu chắc đúng / chắc sai. Chế độ thứ ba gồm:
  - Chữ đầu 100% đúng
  - Đúng ở 1 câu (thu gọn được, dạng bảng theo chữ cái)
  - Cụm từ 100% đúng
  - Chữ đầu chưa lần nào đúng
  - 💡 Kinh nghiệm: BEFORE running, BEFORE piloting, Diligence, Trenova, HTTP, guardrail

## Tính năng đã có (gần đây)
- **Chế độ Ngẫu nhiên** (chọn trong Sắp xếp, hoặc nút 🔀 trong bộ lọc):
  - Trộn câu và trộn phương án; chữ cái A–E được gán lại theo vị trí mới.
  - Đảo thứ tự (1)…(n) trong 7 câu: #017, #020, #022, #023, #037, #049, #112.
  - Lịch sử chọn vẫn lưu theo mã gốc.
  - Code nằm trong khối `SH` / `shApply`.
- **Thi thử:**
  - Chọn được nhiều chủ đề (`UI.examTopics`).
  - Trên điện thoại có nút nổi "☰ Chọn câu khác" khi xem lại bài.
- **Panel Mẹo** ở Ôn tập, theo thứ tự: Học tủ (đóng khung, lên đầu), mẹo câu này, Dịch ngắn gọn, Mẹo cùng chủ đề (thu gọn), Mẹo thi CCAR-P liên quan.
- **Thanh bên trái** thu gọn và mở rộng được.
- **Kết quả Thi thử:** Đối chiếu từng câu, Xem lại bài thi, Sổ câu sai thu gọn mặc định (lớp `xf-fold`, trạng thái mở không lưu, nộp bài mới thì thu gọn lại).
- **Copy / dán text** có thêm phạm vi `forget` (🧠 Câu hay quên, key `claude.study.atlas.forget.v1`). Nút riêng ở tab Thống kê. Lưu ý: tab Dashboard đang tắt (`VIEWS_ON` không có `dashboard`).
- **Lịch sử thi:** chỉ ghi khi bấm Nộp bài (chọn "Không giới hạn" thì không tự nộp). Tab Thống kê báo bài đang làm dở (`examPendingHTML`); `save()` báo toast khi localStorage không ghi được. Lịch sử lưu theo từng trình duyệt.

## Quyết định đã chốt (23/11/2026)
- **Không sửa** đề 5 câu CCAR-P có ghi chú lộ đáp án (#017, #023, #032, #036, #037). Giữ nguyên, đừng đề xuất lại.
- **Không thêm** mục "⚠ Chữ đầu lúc đúng lúc sai" vào tab Học tủ.

## Việc còn treo
1. **Để sau:** thêm câu "Each correct answer presents part of / a complete solution" vào 45 câu CCAR-P chọn 2. Cần người dùng gửi lại file CCAR-P-Trainer.
2. **Để sau:** viết memo Học tủ cho 6 câu hay quên. Chờ người dùng gửi số câu.
3. Cập nhật link artifact theo repo (phải làm từ chat mở ở trang artifact).

## Lưu ý về nhánh
- Nhánh `ninja-theme` trên GitHub đã cũ. `main` mới là bản đầy đủ. Khi bắt đầu, chạy `git checkout -B ninja-theme origin/main` rồi mới làm, đẩy bằng `git push origin ninja-theme:main`.

## Cách kiểm tra trước khi đẩy
- Dùng Playwright với Chrome (`/usr/bin/google-chrome`), chạy file `index.html` local.
- Thử ở hai khung 1440px và 390px. Kiểm tra không có `pageerror`.
- Chụp ảnh màn hình gửi người dùng khi có thay đổi giao diện.
- Cuối mỗi commit thêm các dòng attribution theo hướng dẫn của phiên.
