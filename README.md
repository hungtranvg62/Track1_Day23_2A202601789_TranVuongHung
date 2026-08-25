# Track1 — Day 23 — Product Metrics: Core Action, Retention & Loop

> Một chuỗi quyết định cho VLearn Slide-Aware Copilot: hành vi nào chứng minh học viên thật sự nhận được giá trị → nhịp tự nhiên của hành vi đó → bộ metric và retention tính được → loop là giả thuyết → tracking đủ để kiểm chứng.

---

## 1. Thông tin cá nhân và nhóm

| Mục | Nội dung |
|---|---|
| MHV | 2A202601789 |
| Họ tên | Trần Vương Hưng |
| Nhóm | **JCungDuoc** |
| Ngày làm | 25/08/2026 |
| Dự án phân tích | **VLearn Slide-Aware Copilot** (Case C + A, nối tiếp Day 17–18) |

**Thành viên:**

| Họ tên | MHV |
|---|---|
| Trần Vương Hưng | 2A202601789 |
| Hồ Phạm Đức Linh | 2A202601533 |
| Lê Hoàng Việt | 2A202601543 |


---

## 2. Tệp trình bày của nhóm

| | |
|---|---|
| **Bản trong repo này** | [metrics-pack.html](metrics-pack.html) — mở trực tiếp bằng browser, không cần cài gì |
| **Link đã cấp quyền xem** | ⬜ **CẦN ĐIỀN** — dán link FigJam / Notion / Artifact tại đây sau khi upload và bật quyền xem cho người ngoài |

`metrics-pack.html` là một file HTML tự chứa (self-contained, 1336 dòng, không phụ thuộc CDN ngoài trừ Google Fonts). Cấu trúc đúng sáu mục theo yêu cầu của brief:

| Mục | Nội dung | Anchor |
|---|---|---|
| 00 | Dự án, persona, core job | `#phase-0` |
| 01 | Core Action Card + kết quả tự kiểm 5 tiêu chí | `#phase-1` |
| 02 | Action Nature Card + kết luận cadence | `#phase-2` |
| 03 | Metric System (activation / engagement / NSM / leading / counter) | `#phase-3` |
| 04 | Retention Definition (6 thành phần) | `#phase-4` |
| 05 | Product Loop (2 chu kỳ + metric hypothesis) | `#phase-5` |
| 06 | Tracking (8 events + 4 acceptance criteria) | `#phase-6` |
| ✓ | Tự soi 7 câu + Revision log | `#phase-selfcheck` |

---

## 3. Trạng thái bài làm — đọc trước khi chấm

**Bài này tôi làm một mình.** Phase 1–3 theo thiết kế của brief là thảo luận nhóm; buổi hôm nay tôi làm cá nhân, nên toàn bộ Metrics Pack hiện là **bản đề xuất của một người**, chưa đi qua tranh luận nhóm và chưa có ai trong nhóm ký duyệt.

Điều đó ảnh hưởng tới đúng ba chỗ, và tôi ghi ra để không ai đọc nhầm mức độ chắc chắn:

| Quyết định | Trạng thái |
|---|---|
| Core action | Tôi chốt. Đã tự phản biện bằng 5 tiêu chí và loại 3 ứng viên khác. ⬜ Chờ nhóm phản biện |
| Kết luận cadence | Tôi chốt. ⬜ Chờ nhóm phản biện |
| Metric hypothesis | Tôi chốt, nhưng **con số +15 điểm phần trăm chưa có baseline đo thật** — nó là ngưỡng tự ràng buộc, không phải kết quả |
| Retention 6 thành phần | Tôi chốt. Phần dễ cãi nhất là mẫu số "buổi đã tham dự" — xem §6 |

Cách dùng dữ liệu cũ: pack không bịa dự án mới. Mọi lý do "vì sao chọn thế này" đều truy ngược được về evidence có thật trong repo Day 17–18 (ba phiên phỏng vấn + ba phiên test prototype) và bộ eval Day 20–21.

---

## 4. Chuỗi quyết định — bản tóm tắt

| Bước | Chốt là gì | Vì sao không phải lựa chọn quen thuộc |
|---|---|---|
| **Core action** | Đóng một `stuck_point`: mở trên slide đang chiếu → nhận trả lời bám ngữ cảnh → **vượt câu Socratic check** | "Hỏi AI" là thao tác giao diện; "Copilot trả lời xong" là output hệ thống. Hỏi xong mà vẫn không hiểu thì value bằng 0 |
| **Cadence** | **Per attended lab session**, cuộn theo tuần khóa học | Trigger là giảng viên chuyển slide → không có lớp thì không có nhu cầu. DAU sẽ đo thời khóa biểu chứ không đo sản phẩm |
| **Activation** | ≥1 stuck point resolved ở **mỗi buổi trong 2 buổi tham dự đầu tiên** | Đăng nhập / xem hết onboarding / gửi một câu hỏi đều xảy ra **trước** khi có bất kỳ giá trị nào |
| **NSM** | **VCPS** = stuck point resolved có `socratic_passed` **và** quay lại slide đang chiếu ≤180s, mỗi buổi đã tham dự | "Số lượt hỏi AI" là số lượng thuần — nó còn tăng lên khi câu trả lời của AI **tệ đi**, vì user phải hỏi lại |
| **Retention** | Window **session-based S+1 / S+2 / S+3**, mẫu số là buổi learner **thực sự có mặt** | D7 rơi trúng hay trượt buổi học là chuyện ngẫu nhiên của lịch 2 buổi/tuần; hai lớp lịch khác nhau ra hai con số không so được |
| **Loop** | Event-response trong chu kỳ lịch học; saved state là **Gap Map cá nhân** | Reason to return không phải notification: lịch lab là trigger nằm ngoài sản phẩm, cộng bằng chứng lần trước gỡ được mà không lộ danh tính |
| **Tracking** | 8 event, mỗi event map về ít nhất một metric | `copilot_answer_delivered` được giữ lại nhưng ghi rõ **không phải core value event** — nó chỉ phục vụ counter-metric |

---

## 5. Đóng góp của tôi

Bài làm cá nhân nên phần này là toàn bộ nội dung pack. Ghi theo việc, không ghi theo phase:

**Chốt phạm vi.** Chọn use case "gỡ vướng ngay trong buổi lab" thay vì phân tích cả sản phẩm VLearn, và chọn **một** persona là học viên — không lấy giảng viên hay Lab Coach, vì Day 17 đã hạ hai vai này xuống actor phụ sau khi phỏng vấn Lab Coach D302.

**Chốt core action và loại ba ứng viên.** Loại "hỏi AI" (thao tác giao diện), "Copilot trả lời xong" (output hệ thống), "gửi escalation cho Lab Coach" (cả ba tester Day 18 đều né việc có người tới tận bàn — nên nó là counter-metric, không phải core action). Đặt completion rule dạng chuyển trạng thái `open → resolved` trên một object có ID để hành vi quan sát được chính xác tới từng giây.

**Đưa Socratic check vào completion rule.** Đây là chỗ tôi dùng lại đúng phát hiện bất ngờ nhất của Day 18: nhóm thiết kế C như công cụ trả lời nhanh, nhưng 2/3 tester lại nhắc tới khả năng **tự chẩn đoán** (*"hiểu được sự thiếu hụt kiến thức bản thân của mình ở đâu"*, *"tự hỏi và tự kiểm tra câu trả lời của mình"*). Nếu value nằm ở tự xác nhận thì metric phải đo tự xác nhận, không đo lượt hỏi.

**Chốt cadence per-session và bác bỏ DAU/D7.** Lập luận đi từ Action Nature Card: trigger là sự kiện bên ngoài, dependency là lịch lớp, nên đơn vị đo phải là buổi. Viết rõ trong pack lý do loại từng nhịp đo quen thuộc thay vì chỉ chọn cái mình thích.

**Đặt mẫu số retention là "buổi đã tham dự".** Đây là quyết định tôi tự thấy đáng bảo vệ nhất — xem §6.

**Thiết kế 4 counter-metric, trong đó có một cái canh chính team.** Quality threshold của NSM (`socratic_passed`) nằm trong tay team, nên team có thể tự nới nó để đẩy NSM lên. Counter 2 (Socratic first-attempt pass rate, cảnh báo nếu >90%) tồn tại để chặn đúng đường đó.

**Viết acceptance criteria theo hai bẫy phổ biến nhất** — idempotency của `stuck_point_resolved`, và cấm bắn event tại thời điểm `copilot_answer_delivered` — cộng thêm ràng buộc ẩn danh ≥5 lượt lấy từ thiết kế Option B của chính tôi ở Day 18.

**Dựng file trình bày** `metrics-pack.html` và ghi Revision log 4 mục kèm lý do thay đổi.

**Dùng AI thế nào:** khai báo đầy đủ, không cắt xén, trong [ai-support-log.md](ai-support-log.md). Có phần AI làm nhiều hơn mức lab khuyến khích và tôi ghi rõ điều đó ở đó.

---

## 6. Quyết định tôi sẵn sàng bảo vệ trước coach

Coach sẽ hỏi ngẫu nhiên một người bảo vệ core action, một thành phần retention, hoặc một event bất kỳ. Ba câu tôi chuẩn bị sẵn:

**"Vì sao core action không phải là *hỏi AI*?"**
Vì hỏi là chi phí, không phải giá trị. Một học viên hỏi xong, đọc câu trả lời, vẫn không hiểu, rồi tắt panel — hành vi đó đã xảy ra nhưng job của họ ("theo kịp bài") thất bại hoàn toàn. Nếu lấy lượt hỏi làm core action thì sản phẩm sẽ được thưởng cho đúng lần thất bại đó. Completion rule của tôi bắt buộc học viên phải tự phát biểu lại được hiểu biết của mình thì stuck point mới đóng.

**"Vì sao mẫu số retention là buổi đã tham dự, không phải toàn bộ learner theo lịch?"**
Vì nếu lấy mẫu số theo ngày hoặc theo toàn bộ lịch, sản phẩm bị trừ điểm cho những thứ nó không điều khiển: học viên nghỉ ốm, lớp đổi lịch, tuần nghỉ giữa khóa. Retention khi đó trộn hai câu hỏi khác nhau — "sản phẩm có giữ được người" và "trường có giữ được người đi học" — và team sẽ đi sửa nhầm vấn đề. Câu tôi muốn retention trả lời là: **khi cơ hội quay lại thực sự tồn tại, learner có quay lại và nhận value nữa không.** Attendance được theo dõi riêng, không trộn vào.
*Điểm yếu đã biết của lựa chọn này:* nó làm retention trông đẹp hơn so với cách tính theo lịch, nên khi báo cáo ra ngoài bắt buộc phải ghi kèm mẫu số, nếu không sẽ thành một con số dễ gây hiểu nhầm.

**"`copilot_answer_delivered` để làm gì nếu nó không tính vào metric chính?"**
Nó là bằng chứng cho counter-metric, không phải bằng chứng cho value. Nó cho tôi latency, cost và danh sách nguồn để (1) lấy mẫu chấm grounded-answer rate bằng bộ eval Day 20–21, (2) tính chi phí model trên mỗi stuck point được đóng. Tôi giữ nó trong bảng chính xác vì nếu bỏ ra, sẽ không có cách nào phát hiện kịch bản xấu nhất: VCPS tăng nhờ AI trả lời trôi chảy nhưng sai.

---

## 7. Điều tôi mang về áp dụng cho dự án thật

**Một, "AI trả lời xong" chưa bao giờ là bằng chứng của giá trị.** Đây là lỗi tôi đã mắc thật ở Day 18 chứ không phải lỗi lý thuyết: prototype C dùng canned answer luôn đúng, 2/3 tester chọn C, và tôi không tách được bao nhiêu phần kết quả đó đến từ cơ chế C, bao nhiêu phần đến từ việc C được dựng cho một sân đấu không thể thua. Cùng một cái bẫy, ở tầng metric, có tên là "lấy output hệ thống làm core value event". Từ giờ mọi metric của VLearn phải đo được **hành vi xác nhận của người dùng**, không đo phản hồi của model.

**Hai, nhịp đo phải lấy từ lịch của người dùng, không lấy từ thói quen dashboard.** VLearn là sản phẩm chạy trong lớp học có thời khóa biểu. Mọi lần trước khi ai đó trong nhóm nhắc tới DAU hay D7, câu hỏi cần hỏi lại là: *ngày không có lớp thì hành vi này còn lý do tồn tại không?* Với sản phẩm của nhóm, câu trả lời là không — nên đơn vị đo là buổi.

**Ba, metric nào cũng phải có một counter-metric canh chính người đặt ra nó.** Bài học cụ thể: ngưỡng chất lượng của NSM (độ khó câu Socratic check) do team viết, nên team có thể nới nó để NSM đẹp lên mà không ai vi phạm quy trình nào cả. Counter-metric không chỉ để canh user game hệ thống — nó để canh chính team.

**Bốn, một loop chỉ đứng được khi xóa hết notification mà nó vẫn chạy.** Kiểm tra này rẻ và tàn nhẫn. Loop của Copilot qua được vì trigger nằm ngoài sản phẩm (lịch lab) và saved state là tài sản của người học (Gap Map). Nếu bản thiết kế nào của nhóm không qua được bài kiểm tra này, nó đang là một cơ chế nhắc nhở, không phải một product loop.

**Năm, viết acceptance criteria cùng lúc với việc đặt metric, không để sau.** Hai bẫy tôi gặp ngay khi ngồi viết bảng event — bắn event lúc bấm nút thay vì lúc hoàn tất, và reload trang tạo event trùng — đều đủ sức làm sai toàn bộ NSM mà không làm hỏng bất cứ dòng code nào. Đây đúng kiểu lỗi Day 18 đã dạy: **nó không làm chương trình lỗi, nó chỉ làm dữ liệu thu về sai, và sai theo hướng dễ tin.**

---

## 8. Đối chiếu 5 gate

| Gate | Yêu cầu | Ở đâu trong pack |
|---|---|---|
| 1. Core Action | Có actor / object / completion rule, qua 5 tiêu chí tự kiểm | Mục 01 — Core Action Card + checklist 5/5 |
| 2. Cadence | Kết luận theo template, nhịp từ nature | Mục 02 — Cadence conclusion + bảng ba nhịp đo đã loại |
| 3. Metric & Retention | Retention đủ 6 thành phần, NSM đúng công thức, có counter-metric | Mục 03 (NSM 3 thành phần + 4 counter) và mục 04 (6 thành phần) |
| 4. Loop | ≥2 chu kỳ, hypothesis nối metric | Mục 05 — 2 chu kỳ + hypothesis trỏ về S+1 Session Retention ở mục 04 |
| 5. Tracking | 4–8 event map metric, ≥2 acceptance criteria | Mục 06 — 8 event + 4 acceptance criteria |

---

## Cấu trúc repo

```
Track1_Day23_2A202601789_TranVuongHung/
├── README.md            # file này — thông tin cá nhân, link tệp nhóm, đóng góp, điều mang về
├── metrics-pack.html    # tệp trình bày: 6 mục 00–06 + tự soi + revision log
└── ai-support-log.md    # khai báo dùng AI của chính người nộp
```
