# AI Support Log — Day 23 · Product Metrics

**Người viết:** Trần Vương Hưng — 2A202601789 · Nhóm JCungDuoc
**Ngày:** 25/08/2026
**Model đã dùng:** Claude Opus 5 (qua Claude Code, chạy local trên repo)

> ⬜ **CẦN RÀ LẠI** — đây là phản tư cá nhân. Sửa hoặc bỏ bất kỳ dòng nào không đúng với trải nghiệm thật của bạn trước khi nộp.

---

## 0. Khai báo thẳng: mức độ dùng AI ở bài này vượt mức lab khuyến khích

Brief Day 23 cho phép dùng AI để *brainstorm ứng viên core action, phản biện định nghĩa retention, gợi ý tên event*, và **cấm** dùng AI để *chọn thay core action, viết thay kết luận cadence hay metric hypothesis*.

Thực tế ở buổi này: tôi làm bài một mình và yêu cầu AI dựng **toàn bộ bản nháp Metrics Pack**, bao gồm cả ba thứ nằm trong danh sách cấm. Tôi ghi điều này ra ngay đầu log thay vì mô tả nhẹ đi ở phần sau, vì nếu không thì cả log này vô giá trị.

Hệ quả và cách xử lý:

| Quyết định lõi | Ai nghĩ ra bản đầu | Trạng thái để nộp |
|---|---|---|
| Core action | **AI đề xuất** (từ evidence Day 17–18 có sẵn trong repo) | Tôi đã rà, đối chiếu 5 tiêu chí, viết được lý lẽ bảo vệ trong README §6 → **tôi nhận là quyết định của tôi** |
| Kết luận cadence | **AI viết bản đầu theo template** | Tôi rà và giữ, vì lập luận "không có lớp thì không có trigger" khớp với thực tế lịch D303 → ⬜ chờ nhóm phản biện |
| Metric hypothesis | **AI viết bản đầu** | ⬜ **Chưa phải quyết định của tôi.** Con số +15 điểm phần trăm là AI đặt, không có baseline. Xem §4 |
| Retention 6 thành phần | AI đề xuất, tôi giữ nguyên | ⬜ chờ nhóm phản biện |
| 8 event + acceptance criteria | AI soạn — **đây là việc lab cho phép** | Hợp lệ |
| File `metrics-pack.html` | AI dựng toàn bộ | Hợp lệ, thuần kỹ thuật |

**Việc tôi phải làm trước khi bảo vệ trước coach:** đọc lại ba dòng đầu bảng này và tự trả lời được câu "vì sao không phải phương án khác" mà không nhìn file. Nếu không tự trả lời được thì đó không phải quyết định của tôi, dù nó nằm trong repo mang tên tôi.

---

## 1. AI đã giúp được gì

**Đọc chéo 6 repo cũ để tìm ra dự án đang build.** Tôi không phải mô tả lại dự án. AI tự đọc `Track1_Day17`, `Track1_Day18`, `Day19`, `Track1-Day20-21`, `Track1_Day22` và dựng lại được: nhóm đang build VLearn, case đang theo là Case C sau khi gộp với A ở Next Change của Day 18, và bộ eval AI Tutor ở Day 20–21 dùng được làm công cụ đo counter-metric. Việc này tôi làm tay được nhưng sẽ mất kha khá thời gian mở lại từng file.

**Nối evidence cũ vào quyết định mới.** Chỗ AI làm tốt nhất trong cả buổi: lấy đúng ba câu phỏng vấn Day 17 (*"Mình ngại"*, *"nhiều lúc không biết cái để hỏi"*, *"khá ngại khi phải nhờ 1 lab coach trực tiếp tới chỗ mình"*) và nối chúng vào lý do chọn core action, thay vì viết một core action nghe hay nhưng không có gốc. Nhờ vậy pack không phải bịa dự án mới.

**Chỉ ra một cái bẫy tôi suýt lặp lại.** Ứng viên core action đầu tiên tôi nghĩ tới là "học viên hỏi Copilot một câu". AI phản biện bằng chính lỗi của tôi ở Day 18: prototype C dùng canned answer luôn đúng nên rủi ro thật của C không tester nào gặp phải; lấy lượt hỏi làm core action là cùng một cái bẫy đó nhưng ở tầng metric. Đây là lần AI dùng dữ liệu quá khứ của chính tôi để bác lại tôi — có giá trị hơn mọi gợi ý chung chung.

**Dựng file trình bày.** Toàn bộ HTML/CSS/JS của `metrics-pack.html`, gồm nav, 8 section, loop diagram hai chu kỳ, bảng event, và script scroll. Đây là phần tiết kiệm thời gian nhiều nhất.

---

## 2. AI sai, hời hợt hoặc dễ làm hỏng bài ở đâu

**Rủi ro số 1 — AI viết mượt làm một quyết định yếu trông như quyết định chắc.** Đây là rủi ro lớn nhất của cả bài. Bản pack đọc rất tự tin, có bảng, có gate, có lý do "vì" ở mọi chỗ — nhưng phần lớn lý do đó dựa trên **ba phiên phỏng vấn và ba phiên test**, và chính Day 18 đã ghi rõ *"nhóm không kết luận user đã xác nhận solution này đúng"*. Định dạng đẹp làm mờ mất điều đó. Tôi giữ nguyên phần "Still Unproven" trong đầu khi đọc lại pack.

**Rủi ro số 2 — core action đứng trên một phát hiện chưa được kiểm chứng độc lập.** AI chọn Socratic verification làm completion rule vì 2/3 tester Day 18 nhắc tới khả năng tự chẩn đoán. Nhưng cả hai người đó đều thao tác trên prototype C có canned answer luôn đúng. Nói cách khác: **quyết định lõi của bài Day 23 đang dựa trên kết quả của một cuộc thi mà Day 18 đã tự nhận là không công bằng.** AI không tự nêu điểm này ra — tôi phải tự bắt khi đọc lại log Day 18. Nếu Socratic check gắn với câu trả lời sai thì "tự xác nhận đã hiểu" chỉ là tự xác nhận đã hiểu một thứ không đúng, và NSM sẽ tăng đẹp trong khi sản phẩm đang dạy sai.

**Rủi ro số 3 — AI đặt số mà không có dữ liệu.** Cả pack có 7 con số ngưỡng, không con số nào đến từ đo đạc:

| Ngưỡng | Ở đâu | Cơ sở thật |
|---|---|---|
| ≤ 180 giây (back to live) | Quality threshold của NSM | ⬜ Không có. Cần đo thời gian trung bình giảng viên ở lại một slide |
| 2 buổi đầu tiên | Activation window | ⬜ Không có. Cần cohort thật để biết mấy buổi thì hành vi bám lại |
| +15 điểm phần trăm | Metric hypothesis | ⬜ Không có baseline. Xem §4 |
| < 20 phút | Leading 1 (time-to-first) | ⬜ Không có |
| > 90% | Counter 2 (check quá dễ) | ⬜ Không có |
| 55–85% | Dải pass rate lành mạnh | ⬜ Không có |
| ≥ 5 lượt | Ngưỡng ẩn danh | ✅ **Có gốc** — quyết định của chính tôi ở Day 18, giữ nguyên |

Sáu trên bảy con số là giả định. Pack có ghi điều này ở phần hypothesis, nhưng chỉ ghi cho một con số; bảng trên là phần tôi bổ sung.

**Rủi ro số 4 — pack mang giọng của một người.** Toàn bộ bài được dựng trong một mạch, không có ai phản biện ngược. Những chỗ nhóm nhiều khả năng sẽ cãi: mẫu số retention "buổi đã tham dự" (làm con số đẹp lên), và việc loại escalation ra khỏi core action (Đức Linh sở hữu Option A ở Day 18 — người đó có lý do để không đồng ý).

**Lỗi kỹ thuật AI tự gây ra trong buổi:**
- Cách ghi file đầu tiên fail (`ENAMETOOLONG`) vì AI cố đẩy cả nghìn dòng HTML qua một lệnh shell. Phải đổi sang ghi từng phần rồi ghép.
- File HTML sinh ra có **một tag đóng sai** (`</strong>` thay cho `</span>` ở khối NSM). Trình duyệt vẫn render gần đúng nên nhìn bằng mắt không thấy; chỉ lộ ra khi chạy kiểm tra cân bằng tag. Đúng kiểu lỗi tôi đã ghi ở Day 18: *nó không làm chương trình lỗi, nó chỉ làm dữ liệu (ở đây là cấu trúc trang) sai theo hướng dễ tin.*

**Chỗ AI hoàn toàn không giúp được:** không có dữ liệu thật nào. Không có một learner nào, một buổi lab nào, một con số retention nào. Toàn bộ pack là thiết kế đo lường cho một thứ chưa được đo.

---

## 3. Tôi đã tự sửa hoặc quyết định lại điều gì

**Loại "gửi escalation cho Lab Coach" khỏi ứng viên core action.** Ba tester Day 18 ở ba ghế khác nhau cùng né việc có người tới tận bàn. Escalation là lối thoát khi hỏng, nên nó phải nằm ở nhóm counter-metric — nếu đưa nó lên làm core action, sản phẩm sẽ được thưởng khi đẩy tải sang một Lab Coach vốn đã lo cho ~150 học viên.

**Giữ nguyên ngưỡng ẩn danh ≥5 lượt từ thiết kế Day 18 của tôi** và đưa nó thành một acceptance criterion bắt buộc, không phải tùy chọn. Lý do không đổi: dưới 5 lượt thì con số tự nó chỉ mặt người bấm, và chi phí xã hội quay lại nguyên vẹn.

**Bổ sung bảng 7 ngưỡng ở §2** vì bản pack chỉ cảnh báo cho một con số. Sáu con số còn lại cũng dễ bị đọc như thể đã được đo.

**Ghi rõ trong README rằng bài làm một mình**, thay vì để pack mang dáng vẻ một sản phẩm nhóm đã thống nhất. Day 19 tôi đã dùng cách đánh dấu ⬜ chờ nhóm ký cho từng checkpoint; ở đây tôi làm lại đúng như vậy.

**Không để AI viết phần "điều tôi mang về".** Phần §7 của README là phần bắt buộc phải là của người, và tôi kiểm lại từng ý xem nó có phải điều tôi thật sự rút ra từ Day 18 → Day 23 hay chỉ là một câu tổng kết nghe hay.

---

## 4. Việc còn nợ — metric hypothesis

Đây là chỗ tôi **chưa** hoàn thành đúng tinh thần của lab.

Metric hypothesis hiện tại nói: S+1 Session Retention sẽ tăng ≥15 điểm phần trăm so với baseline của cohort chưa có Gap Map, trong 3 buổi lab liên tiếp. Cấu trúc câu đúng template, mệnh đề "vì" đứng được (saved state hạ đúng hai chi phí đã chặn hành vi ở Day 17). Nhưng:

1. **Chưa có baseline.** Chưa ai đo S+1 retention của bất kỳ cohort nào. Con số 15 là AI đặt cho câu văn tròn trịa.
2. **Chưa có Gap Map trong sản phẩm.** Loop giả định một saved state chưa được build.
3. **Câu này AI viết, không phải tôi viết** — trái quy định của lab.

Việc phải làm: sau khi nhóm chốt core action, tôi tự viết lại hypothesis bằng câu của mình, và hoặc bỏ con số đi, hoặc thay bằng "tăng so với baseline đo được ở cohort W1" mà không gắn một con số chưa có cơ sở.

---

## 5. Rút ra

AI mạnh nhất ở bài này khi được đặt vào **một kho tài liệu có thật của chính mình**: nó nối được evidence phỏng vấn Day 17 với quyết định metric Day 23, và dùng được lỗi Day 18 của tôi để bác lại ý tưởng đầu tiên của tôi. Đó là thứ tôi không tự làm nhanh được, vì tôi không nhớ hết mình đã viết gì trong sáu repo.

AI yếu nhất ở đúng chỗ nguy hiểm nhất của một bài về metric: **nó sẵn sàng điền một con số vào mọi ô trống.** Ngưỡng, phần trăm, khung thời gian — tất cả đều được viết ra với cùng một giọng tự tin, bất kể cái nào có dữ liệu và cái nào không. Ở Day 18 tôi học rằng AI dựng cho một option một sân đấu không thể thua; ở Day 23 tôi học rằng AI dựng cho một metric một bộ ngưỡng nghe như đã được đo. Cùng một loại sai: **không làm hỏng thứ gì, chỉ làm dữ liệu sai theo hướng dễ tin.**

Nguyên tắc tôi mang sang buổi sau: mỗi con số trong một tài liệu metric phải đi kèm một trong hai nhãn — *đã đo* hoặc *đang giả định*. Không có nhãn thì mặc định coi là giả định, kể cả khi nó nằm trong một cái bảng rất đẹp.
