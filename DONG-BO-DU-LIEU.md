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

### Hạn chế của bộ CCAO-F lúc mới đồng bộ

- Chỉ có tiếng Anh, chưa có mẹo chọn đáp án. **Đã bổ sung ở Lần 2** (bên dưới).
- Chưa chia domain chi tiết: cả 119 câu nằm trong một chủ đề, và không có trong tab *Kiến thức thi* (tab này chỉ dành cho CCDV-F). *Vẫn còn.*

## Lần 2: 17/11/2026, bổ sung bản dịch và mẹo cho CCAO-F

Nguồn: tự biên soạn (không có trong dữ liệu gốc).

| Nội dung | Số lượng |
|---|---|
| Đề bài dịch tiếng Việt (`stem.vi`) | 119 câu |
| Đáp án dịch tiếng Việt (`options[].t.vi`) | 119 câu (tất cả phương án) |
| Mẹo chọn đáp án (`tip`, dạng "Thấy … → chọn …; loại …") | 119 câu |
| Sửa ký tự lỗi trong đề / đáp án tiếng Anh (`&#x27;` → `'`, `&quot;` → `"`) | 9 chuỗi, đều ở CCAO-F |

- Bản dịch viết lại cho tự nhiên, dễ đọc; giữ nguyên các thuật ngữ sản phẩm quen dùng: Project, custom instructions, Skill, Connector, Memory, Incognito, Artifact, Code Execution, Haiku / Sonnet / Opus, context window, prompt.
- Câu sắp xếp thứ tự: giữ nguyên dãy số trong đáp án (vd `5, 4, 1, 3, 2`), chỉ dịch các bước trong đề.
- Mẹo được viết dựa trên đáp án và phần giải thích có sẵn của từng câu. Mẹo hiện ở: panel *Mẹo chọn đáp án* (Học theo câu), *Học tủ* (dòng THẤY + mẹo), sau khi chấm ở *Học theo câu*.
- Không thay đổi đề, đáp án đúng hay giải thích của bất kỳ câu nào; 375 câu của CCAR-F, CCAR-P, CCDV-F giữ nguyên hoàn toàn.
- Bản dịch tiếng Nhật (JP) cho CCAO-F chưa có: khi chọn JP, đề CCAO-F sẽ hiện tiếng Anh.

## Lần 3: 18/11/2026, đưa bản Vercel lên link artifact

- Nguồn: repo công khai `github.com/levantoc676/wind-claude-certificate`, commit `8e9e571` (bản đang chạy ở https://wind-claude-certificate.vercel.app/).
- Link artifact https://claude.ai/artifact/1q3qpVrDmcKmeab5eSmgWb đã thay bằng đúng file `index.html` của repo, đổi tên thành "Wind Claude Certificate": 494 câu, 4 chứng chỉ, 2 theme Thường/Game, chuyển dữ liệu bằng mã `WCC1:…`.
- Phần lưu tiến độ lên tài khoản Claude (đồng bộ giữa các máy) vẫn hoạt động: đã kiểm tra lưu, tải lại ở máy khác và gộp dữ liệu hai máy.
- Lưu ý: trong link artifact, nút **↓ Sao lưu JSON** (tải file) không chạy vì khung artifact chặn tải file. Dùng **⇅ Copy / dán text** thay thế.
- Từ nay khi sửa web: sửa trên repo trước, rồi cập nhật artifact từ repo để hai bản luôn giống nhau.

## Lần 4: 20/11/2026, đánh dấu 13 câu "hay quên" kèm ghi nhớ

Nguồn: danh sách câu bạn gửi (file ghi chú). Cả 13 câu đều có sẵn trong bộ CCDV-F; dữ liệu câu hỏi, đáp án, giải thích không đổi. Mỗi câu được thêm trường `forget: true`; câu nào có ghi chú thì thêm trường `memo`.

| Câu | Chủ đề đề bài | Đáp án | Ghi nhớ của bạn |
|---|---|---|---|
| CCDV-F #048 | Tích hợp API trực tiếp hay qua lớp abstraction đa nhà cung cấp | D | Phải tích hợp trực tiếp qua SDK |
| CCDV-F #026 | Hợp đồng 50 trang: xử lý cả tài liệu hay chia nhỏ | B | Hợp đồng 50 trang → “Identify which property matters” |
| CCDV-F #086 | Chiến lược guardrail | A | Đề có guardrail → “Layer multiple guardrails” |
| CCDV-F #019 | Structured output làm sập code phía sau | D | Đề có crash → đáp án có “crash on” ở cuối câu |
| CCDV-F #015 | Roll out thay đổi prompt cho nhiều hệ thống phía sau | A | Đề có roll out → đáp án có “owners as needed” |
| CCDV-F #027 | Nhiều API call giờ hành chính, lo rate limit | C | API calls during business hours → “Identify the rate limits” |
| CCDV-F #021 | Lỗi validation đang bị coi là lỗi chặn | C | Đề lỗi validation → “Treat validation failures…” |
| CCDV-F #089 | Multi-agent: subagent gọi tool trùng, vượt token, mâu thuẫn | C | (chưa có ghi chú) |
| CCDV-F #035 | Văn bản người dùng có số tài khoản, mật khẩu | A | (chưa có ghi chú) |
| CCDV-F #097 | Thực thi content policy | D | (chưa có ghi chú) |
| CCDV-F #076 | Chuyển mục tiêu nghiệp vụ thành yêu cầu kỹ thuật | D | (chưa có ghi chú) |
| CCDV-F #018 | Chính thức hóa chiến lược kiểm thử | B | (chưa có ghi chú) |
| CCDV-F #045 | Đầu ra không nhất quán, cần gỡ lỗi có hệ thống | D | (chưa có ghi chú) |

Ghi chú được sửa nhẹ lỗi gõ khi đưa vào (vd “Identity property” → “Identify which property”, “mutiples” → “multiple”).

Ngoài 13 câu trên, bạn có thể tự bật/tắt 🧠 Hay quên cho bất kỳ câu nào; lựa chọn đó lưu trong trình duyệt (khóa `claude.study.atlas.forget.v1`) và đi kèm khi Sao lưu / Copy text dữ liệu.

- Bản trên Vercel (commit `1db4a6e`) đã có phần này. **Link artifact vẫn là bản Lần 3** (chưa có nút bỏ đánh dấu ★ hàng loạt và câu hay quên) cho tới khi được cập nhật lại từ repo.
