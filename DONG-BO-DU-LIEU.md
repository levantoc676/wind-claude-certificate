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

## Lần 5: 20/11/2026, thêm tab "Mẹo thi CCAR-P"

Nguồn: file *CCAR Exam Tips* (bạn tải lên), tổng hợp từ claudecertificationguide.com, Tutorials Dojo, aicertguides.com. Đây là nguồn bên thứ ba, không phải của Anthropic.

- Chỉ lấy phần **CCAR-P**: chiến lược chung, thông tin đề, cách loại đáp án, 7 domain (146 mẹo) và danh sách số liệu cần kiểm tra lại trước khi thi. Phần CCAR-F không đưa vào.
- Từ khóa tiếng Anh hay xuất hiện trong đề được giữ nguyên và có nghĩa tiếng Việt bên cạnh, ví dụ **least privilege** (quyền tối thiểu).
- Gắn mẹo với câu hỏi theo domain: D1→AP2, D2→AP6, D3→AP1, D4→AP3, D5→AP4, D6→AP5, D7→AP7. 104/146 mẹo có số câu đi kèm; 113/116 câu CCAR-P có ít nhất một mẹo. Việc gắn này do Claude đối chiếu nội dung đề và đáp án, nên có thể có chỗ chưa khớp.
- Ở Ôn tập câu hỏi, câu CCAR-P nào có mẹo gắn kèm thì panel Mẹo có thêm mục "Mẹo thi CCAR-P liên quan".
- Không đổi dữ liệu câu hỏi hay dữ liệu học của bạn.

## Lần 6: 20/11/2026, đánh số lại chủ đề CCAR-P theo domain của đề thi

Mã chủ đề AP của bộ CCAR-P (AP = **A**rchitect **P**rofessional) trước đây đánh số theo nguồn dữ liệu cũ, không khớp với thứ tự domain D1–D7 trong exam guide. Nay đổi để **APn = Dn**, kèm trọng số trong đề:

| Mới | Domain | Trọng số | Số câu | Mã cũ |
|---|---|---|---|---|
| AP1 | Solution Design & Architecture | 17% | 12 | AP2 |
| AP2 | Claude Models, Prompting & Context Engineering | 13% | 8 | AP6 |
| AP3 | Integration | 19% | 3 | AP1 |
| AP4 | Evaluation, Testing & Optimization | 16% | 20 | AP3 |
| AP5 | Governance, Safety & Risk | 14% | 32 | AP4 |
| AP6 | Stakeholder Communication & Lifecycle | 14% | 21 | AP5 |
| AP7 | Developer Productivity & Operational Enablement | 7% | 20 | AP7 |

- Chỉ đổi mã và tên chủ đề. Mã câu (`CCAR-P:ccarp-q…`), đề, đáp án và tiến độ học không đổi.
- Nếu trình duyệt đang lọc theo một chủ đề CCAR-P cũ, bộ lọc được tự chuyển sang mã mới (một lần).
- Tab Mẹo thi giờ ghi "D1 = AP1", "D2 = AP2"…

## Lần 7: 20/11/2026, thêm tab "Học tủ CCAR-P"

- Đủ 116/116 câu CCAR-P, xếp theo AP1–AP7. Mỗi câu một dòng: **key trong đề → key đáp án**. Câu nhiều đáp án có nhãn [Chọn 2].
- 12 câu AP1 lấy theo danh sách bạn gửi; 104 câu còn lại do Claude soạn theo cùng quy tắc.
- Đã kiểm tra bằng máy:
  - Mỗi key trong đề chỉ có ở đúng câu đó. Ngoại lệ là 3 cặp câu giống hệt nhau: #092/#108, #098/#105, #058/#109.
  - Mỗi key đáp án có trong đáp án đúng và không có trong đáp án sai. Ngoại lệ là các câu Yes/No và câu ghép thứ tự, nơi key chính là đáp án.
- Sửa 2 chỗ so với danh sách bạn gửi:
  - #015: đề ghi "40 percent", không phải "40%".
  - #017 (BM25): đáp án đúng trong dữ liệu là Yes-Yes-Yes-No-No (5 phát biểu), không phải Yes-Yes-No-No.
- Có thêm mục "Mẹo câu Yes / No".
- Ở Ôn tập câu hỏi, câu CCAR-P có thêm dòng "✎ Học tủ" trong panel Mẹo.

## Lần 8: 20/11/2026, bỏ 5 câu trùng (494 → 489 câu)

Đã so cả 494 câu của 4 bộ, tính là trùng khi cùng đề, cùng các phương án và cùng đáp án đúng (không phân biệt hoa/thường, dấu câu). Có 5 câu trùng, đều trùng trong cùng một bộ. Giữ câu có số nhỏ hơn, bỏ câu sau:

| Bỏ | Giữ lại |
|---|---|
| CCAR-P #109 | CCAR-P #058 |
| CCAR-P #108 | CCAR-P #092 |
| CCAR-P #105 | CCAR-P #098 |
| CCDV-F #047 | CCDV-F #002 |
| CCDV-F #067 | CCDV-F #003 |

- Số câu mới: CCAR-F 162, CCAR-P 113, CCDV-F 95, CCAO-F 119, tổng 489. Số thứ tự (#) của các câu còn lại giữ nguyên, nên sẽ có chỗ nhảy số.
- Tiến độ học, sổ câu sai, ★, hay quên… của câu bị bỏ được tự chuyển sang câu giữ lại (một lần, khi mở web). Nếu câu giữ lại đã có dữ liệu riêng thì giữ dữ liệu đó.
- Tab Mẹo thi và Học tủ CCAR-P cũng bỏ 3 câu CCAR-P trùng (Học tủ còn 113 dòng).
- Mã dữ liệu cũ (WCC1:…) tạo trước lần này vẫn nhập được; câu bị bỏ trong mã đó sẽ được bỏ qua.

## Lần 9: 21/11/2026, đảo thứ tự nhận định ở câu Yes/No

- Áp dụng cho 5 câu CCAR-P có nhận định đánh số: #017, #020, #023, #037, #049.
- **Khi nào đảo:** khi chọn *Sắp xếp: Ngẫu nhiên* ở Ôn tập câu hỏi / Flashcards (mỗi lần chọn lại là một thứ tự mới), và trong mỗi lượt Thi thử.
- **Những gì đổi theo:**
  - Thứ tự (1)…(n) trong đề, cả tiếng Anh lẫn tiếng Việt.
  - Số trong phần ghi chú của đề, ví dụ "claims 4 and 5".
  - Chuỗi Yes/No của mọi phương án.
  - Key và đáp án Học tủ.
  - Phần giải thích có thêm dòng cho biết thứ tự mới ứng với thứ tự gốc.
- **Những gì giữ nguyên:**
  - Mã phương án (A–D) và đáp án đúng, nên tiến độ học không bị ảnh hưởng.
  - Dữ liệu gốc: bỏ chế độ Ngẫu nhiên thì đề về như cũ.
- **Câu không đảo được:** #036 không đánh số nhận định trong đề (chỉ ghi "five tools in total"), nên không đảo.

## Lần 10: 21/11/2026, đảo thứ tự cả câu ghép mục; sửa học tủ #066

- **Câu ghép mục (6 mục → 3 nhóm):** áp dụng cách đảo của Lần 9 cho #022 (chunking) và #112 (token-management). Khi đảo thì đổi theo cả thứ tự 6 mục trong đề (EN/VI), các phương án và đáp án Học tủ (vd "Code – Code – Short – Long – Short – Long").
- **#032 (pipeline hóa đơn) không đảo được:** đề không có danh sách 6 thành phần ("the specific list is not available").
- **Học tủ #066:** fixed steps → Câu chứa "steps". Chỉ đáp án đúng có chữ "steps" (số nhiều); đáp án A và C chỉ có "step".

## Lần 11: 21/11/2026, chế độ Ngẫu nhiên trộn cả phương án; nút 🔀 Ngẫu nhiên

- Khi chọn **Sắp xếp: Ngẫu nhiên** hoặc bấm nút **🔀 Ngẫu nhiên** mới thêm trong bộ lọc, mỗi lần bấm là một lần trộn mới. Áp dụng cho cả 489 câu ở Ôn tập câu hỏi và Flashcards.
- **Những gì đổi:**
  - Thứ tự câu hỏi.
  - Thứ tự phương án của mọi câu. Chữ cái A, B, C… được gán lại theo vị trí mới.
  - Câu Yes/No và câu ghép mục (#017, #020, #022, #023, #037, #049, #112): thêm đảo thứ tự (1)…(n) trong đề, như ở Lần 9–10.
- **Những gì đổi theo:** dòng "Đáp án đúng", phần giải thích (vd "<b>C.</b> …", "(trong đáp án C)"), Dịch ngắn gọn, phím tắt A–E và Copy câu hỏi đều theo chữ cái mới.
- **Những gì giữ nguyên:**
  - Tiến độ và lịch sử chọn vẫn lưu theo mã gốc, nên bỏ chế độ Ngẫu nhiên là mọi thứ về như cũ.
  - Thi thử giữ cách trộn phương án riêng của phòng thi, chỉ đảo thêm thứ tự (1)…(n).

## Lần 12: 25/11/2026, chia domain CCAO-F (AO1–AO7) và thêm Học tủ CCAO-F

- **Chia domain:** 119 câu CCAO-F trước đây chung một mục "Chủ đề 1", nay chia theo 7 domain của exam guide CCAO-F (bản 1.0, 07/2026). Đặt tên AOn = Dn, giống cách đánh số CCAR-P (APn = Dn).

  | Mã | Domain | Tỷ trọng đề | Số câu |
  |---|---|---|---|
  | AO1 | Prompting & Task Execution | 14% | 21 |
  | AO2 | Output Evaluation & Validation | 21% | 18 |
  | AO3 | Product & Model Selection | 12% | 12 |
  | AO4 | Workflow Integration & Solution Design | 16% | 14 |
  | AO5 | Configuration & Knowledge Management | 12% | 14 |
  | AO6 | Governance, Risk & Responsible Use | 15% | 21 |
  | AO7 | Troubleshooting & Optimization | 10% | 19 |

  - Nguồn đề không ghi domain, nên việc xếp câu vào domain do Claude tự phân loại theo nội dung. Quy ước cho 4 năng lực AI Fluency: Description → AO1, Discernment → AO2, Delegation → AO4, Diligence → AO6.
  - Chỉ thêm `category` / `categoryName` cho câu CCAO-F; nội dung câu, đáp án, mã câu và tiến độ học không đổi.
- **Học tủ CCAO-F:** khối dữ liệu mới `id="wcc-cramo"` (119 câu, cùng dạng `{ "<số câu>": { "k", "a" } }` như `wcc-cramp`).
  - Key đề được kiểm tra tự động: có trong đề và chỉ có ở đúng câu đó trong bộ CCAO-F. Nhóm key: `correct order | …` (câu xếp thứ tự), `BEFORE … | …`, `first | …`, `Description | …`, `Delegation | …`.
  - Đáp án tủ được kiểm tra tự động: khớp đáp án đúng và không là phần đầu của đáp án sai. Câu xếp thứ tự ghi đúng dãy số (vd `5, 4, 1, 3, 2`). Riêng #001 ghi theo ý (mọi phương án đều mở đầu bằng "Name Claude's role", đáp án đúng là phương án đủ cả 3 ý).
- **Bổ sung (25/11):** 13 câu xếp thứ tự của Học tủ CCAO-F ghi thêm chữ đầu của từng bước theo đúng thứ tự đáp án, ví dụ `5, 4, 1, 3, 2 (Read, Identify, Cross-check, Document, Decide)`. Nếu trong một câu có hai bước cùng chữ đầu thì ghi thêm chữ kế tiếp (vd `Identify audience`, `Identify data`).

## Lần 13: 26/11/2026, đảo thứ tự các bước ở câu xếp thứ tự CCAO-F

- Áp dụng cho 13 câu CCAO-F có các bước (1)…(5) và đáp án là dãy số: #003, #009, #017, #026, #030, #034, #041, #045, #059, #060, #075, #078, #100.
- **Khi nào đảo:** giống Lần 9–11, tức là khi chọn *Sắp xếp: Ngẫu nhiên* hoặc bấm 🔀 ở Ôn tập câu hỏi, và trong mỗi lượt Thi thử.
- **Những gì đổi theo:**
  - Số thứ tự các bước trong đề, cả tiếng Anh lẫn tiếng Việt.
  - Dãy số trong mọi phương án.
  - Dãy số trong mẹo chọn đáp án và trong đáp án Học tủ. Chữ đầu trong ngoặc giữ nguyên vì vẫn đúng thứ tự làm.
  - Phần giải thích có thêm dòng "Thứ tự các bước đã đảo: (1) = gốc (3)…", nội dung giải thích vẫn viết theo thứ tự gốc.
- **Những gì giữ nguyên:** mã phương án, đáp án đúng và tiến độ học. Bỏ chế độ Ngẫu nhiên thì đề về như cũ.
- Đã kiểm tra bằng máy cả 13 câu: đọc đáp án mới theo đề mới ra đúng trình tự các bước như đáp án gốc, ở cả tiếng Anh và tiếng Việt.

## Lần 14: 28/11/2026, thêm Học tủ CCAR-F; Thi thử lọc được "✓ Đã thuộc"

- **Học tủ CCAR-F:** khối dữ liệu mới `id="wcc-cramf"` (162 câu, cùng dạng `{ "<số câu>": { "k", "a" } }` như `wcc-cramo`). Tab Học tủ có thêm nút **CCAR-F** (giữa CCAO-F và CCAR-P), chia theo 5 domain sẵn có AR1–AR5.
  - Key đề do Claude chọn theo nội dung từng câu, ưu tiên cụm dễ nhớ (số liệu, tên tool, tình huống). Các câu giống nhau dùng key nhóm `X | Y` để nằm cạnh nhau khi xếp A–Z, ví dụ `yesterday | …` (resume / fork_session), `first 8 | …`, `invoices | 8% / 18% …`, `extract_metadata | …`, `delivery-specific | …`, `test generation | …`.
  - Đáp án tủ: chữ đầu của đáp án đúng nếu không trùng đáp án sai; nếu trùng thì thêm vài chữ, hoặc dạng `Chữ đầu … cụm phân biệt` (vd `Resume … fork_session`, `Use Grep … distinctive text`).
  - Đã kiểm tra bằng máy cả 162 câu: mọi phần của key có trong đề và tổ hợp key chỉ có ở đúng câu đó; đáp án tủ khớp đáp án đúng và không khớp đáp án sai nào.
  - 7 câu bất đồng đáp án (#044, #049, #057, #078, #082, #130, #134): đáp án tủ theo đáp án Exam Trainer (đáp án chấm điểm của web), có ghi chú "(đáp án bất đồng: Quizlet chọn …)".
  - Ôn tập: Sắp xếp "✎ Theo key Học tủ" và panel Học tủ nay dùng được cho cả CCAR-F.
- **Thi thử:** ô Trạng thái có thêm **✓ Đã thuộc** để thi lại riêng các câu đã bấm Đã thuộc.
- Không đổi đề, đáp án, giải thích hay tiến độ học.

