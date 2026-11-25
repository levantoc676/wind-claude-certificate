# Bàn giao: Wind Claude Certificate (để tiếp tục ở cuộc trò chuyện mới)

Cập nhật: 23/11/2026

## Dự án
- Web ôn thi chứng chỉ Claude, giao diện tiếng Việt. Toàn bộ web là một file `index.html` (khoảng 2,3 MB).
- Repo: `github.com/levantoc676/wind-claude-certificate`. Nhánh làm việc là `ninja-theme`, đẩy lên bằng `git push origin ninja-theme:main`. Vercel tự deploy từ `main`.
- Web: https://wind-claude-certificate.vercel.app. Mỗi tab có một URL riêng:
  - `#/on-tap`: Ôn tập câu hỏi
  - `#/meo-thi`: Mẹo thi CCAR-P
  - `#/hoc-tu`: Học tủ CCAR-P
  - `#/hoc-tu-moi`: Học từ mới
  - `#/thi-thu`: Thi thử
  - `#/thong-ke`: Thống kê
- **Tab Flashcards đã bỏ** (25/11): gỡ khỏi `VIEWS_ON`, thanh bên và `ROUTES`; mở `#/flashcards` sẽ về Ôn tập. Code render flashcard vẫn còn trong file nhưng không dùng.
- Link artifact (https://claude.ai/artifact/1q3qpVrDmcKmeab5eSmgWb) đang **cũ hơn repo nhiều**. Chỉ cập nhật được từ một chat mở ở chính trang artifact đó.
- Nhật ký đồng bộ dữ liệu: `DONG-BO-DU-LIEU.md` (trong repo, đã chép vào Project ở `claude/dong-bo-du-lieu.md`). Hiện tới **Lần 12**.

## Dữ liệu (nằm trong index.html)
- `<script type="application/json" id="wcc-data">`: **489 câu**.
  - CCAR-F 162, CCAR-P 113, CCDV-F 95, CCAO-F 119.
  - 5 câu trùng đã bị bỏ: CCAR-P #105, #108, #109 và CCDV-F #047, #067.
- `id="wcc-tips"`: tab Mẹo thi CCAR-P. Có 146 mẹo chia theo D1–D7, mỗi mẹo kèm số câu liên quan.
- `id="wcc-cramo"`: **Học tủ CCAO-F** (25/11), cùng dạng với `wcc-cramp`. Tab Học tủ có nút chọn bộ CCAR-P / CCAO-F (`UI.crBank`, ngữ cảnh `crCtx()` / biến `CX`). Mục Yes/No và 💡 Kinh nghiệm chỉ có ở CCAR-P.
- **Người dùng đang ôn CCAO-F** (25/11): CCAO-F đứng đầu mọi danh sách bộ học (sắp lại `META.banks` lúc chạy), Học tủ mặc định CCAO-F, và một lần duy nhất chọn sẵn Bộ học = CCAO-F (cờ `claude.study.atlas.aofirst.v1`).
- **Sắp xếp "✎ Theo key Học tủ"** (`UI.sort='key'`): chỉ hiện khi Bộ học = CCAO-F; xếp câu theo key Học tủ A–Z để câu cùng nhóm key nằm cạnh nhau, thẻ câu ở Ôn tập hiện nhãn key (`.lq-key`). Chọn bộ khác thì tự về Thứ tự gốc.
- CCAO-F chia 7 domain **AO1–AO7 = D1–D7** theo exam guide CCAO-F (Claude tự phân loại, xem Lần 12 trong DONG-BO-DU-LIEU.md).
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
  - Chọn được nhiều chủ đề (`UI.examTopics`). Từ 25/11 ô chọn nhiều chủ đề nằm ngay trong bộ lọc, thay ô "Chủ đề" (`examTopicPicker`, dạng dropdown có checkbox); chưa chọn = mọi chủ đề (bỏ qua `UI.topic`).
  - Trạng thái trong Thi thử chỉ còn: Tất cả, 🧠 Hay quên, Chưa học, Đã đánh dấu (`EX_STATUS`). Trạng thái khác (vd. Cần ôn lại) tự về Tất cả khi mở tab Thi thử. Các tab khác giữ đủ lựa chọn.
  - Nút "🧠 Thi riêng N câu hay quên" chỉ lấy câu hay quên của bộ học đang chọn (`forgetIdsBank()`); chọn Tất cả thì lấy mọi bộ.
  - Nút 🔀 Ngẫu nhiên: full-width chỉ ở cột lọc dọc (`.learn-side`), bộ lọc ngang thì nằm cạnh ô Sắp xếp.
  - Trên điện thoại có nút nổi "☰ Chọn câu khác" khi xem lại bài.
- **Panel Mẹo** ở Ôn tập, theo thứ tự: Học tủ (đóng khung, lên đầu), mẹo câu này, Dịch ngắn gọn, Mẹo cùng chủ đề (thu gọn), Mẹo thi CCAR-P liên quan.
- **Thanh bên trái** thu gọn và mở rộng được. Đã bỏ mục "Ngân hàng câu hỏi" (giữ `#bankNav` ẩn để JS không lỗi; chọn bộ đề bằng bộ lọc).
- **Kết quả Thi thử** (25/11): chỉ còn điểm + mục "✕ Câu sai" (nằm trong khung Tổng điểm `.result-panel`, thu gọn, chỉ câu sai/bỏ trống, có nút 🧠 Hay quên) + Sổ câu sai. Đã bỏ "Đối chiếu từng câu", "Xem lại bài thi" đầy đủ và nút "Ôn lại câu sai". Sổ câu sai chỉ hiện câu sai ≥ 3 lần (`WRONG_MIN`, `wrongBookIds()`), nút Thi lại dùng cùng danh sách. Mục thu gọn dùng lớp `xf-fold`. Trên mục Câu sai có "⚑ Câu đã đánh dấu" (`examFlagHTML`, lấy từ `EXAM.flags`, cả câu đúng lẫn sai). Mục lục "Câu sai" luôn cố định khi cuộn (sticky; `.result-panel` dùng `overflow:clip` thay vì hidden để sticky chạy; điện thoại dính trên cùng, cao tối đa 30vh).
- **Copy / dán text** có thêm phạm vi `forget` (🧠 Câu hay quên, key `claude.study.atlas.forget.v1`). Nút riêng ở tab Thống kê. Lưu ý: tab Dashboard đang tắt (`VIEWS_ON` không có `dashboard`).
- **Lịch sử thi:** chỉ ghi khi bấm Nộp bài (chọn "Không giới hạn" thì không tự nộp). Tab Thống kê báo bài đang làm dở (`examPendingHTML`); `save()` báo toast khi localStorage không ghi được. Lịch sử lưu theo từng trình duyệt.
- **Huỷ bài thi:** nút "✕ Huỷ bài thi" dưới nút Nộp bài và nút "✕ Huỷ bài" trong thông báo bài dở ở Thống kê (`data-action=cancelExam`): `EXAM=null`, không chấm, không ghi lịch sử, tiến độ hay Sổ câu sai. Hai nút nằm trong `.ex-btns`, luôn hiện: máy tính ở cuối khung Điều hướng bên phải (bảng số câu tự cuộn), điện thoại là 2 nút tròn nhỏ cố định góc phải dưới.

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
