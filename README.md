# Track1_Day17_2A202601633_NguyenDucDat

**Từ Solution Directive đến Problem Hypothesis — Case C: AI Support Radar (VLearn)**

---

## 1. Thông tin cá nhân và nhóm

| | |
|---|---|
| **Họ tên** | Nguyễn Đức Đạt |
| **MHV** | 2A202601633 |
| **Track / Day** | Track 1 — Day 17 |
| **Nhóm** | **Mái Ấm Gia Đình** |
| **Case đã chọn** | **Case C — AI Support Radar** |

**Thành viên nhóm**

| # | Họ tên | MHV |
|---|---|---|
| 1 | Nguyễn Đức Đạt | 2A202601633 |
| 2 | La Thế Quyền | 2A202601699 |
| 3 | Bùi Hoàng Vương | 2A202601553 |

**Cấu trúc repo**

```
Track1_Day17_2A202601633_NguyenDucDat/
├── README.md                                              ← file này
├── interview/
│   ├── notes.md                                           ← Chặng 3: Interview Record đã điền
│   ├── transcript.md                                      ← transcript bản ghi (bóc offline)
│   └── Phỏng Vấn Day17.m4a                                ← bản ghi 4'35" ⚠️ xem lưu ý consent
└── .gitignore
```

> **Ghi chú:** ba file nháp — `GUIDE.md` (đề bài gốc), `LAB_Day17_...md` (bản làm chi tiết Chặng 1–2) và `CONVERSATION_GUIDE_...md` (guide đầy đủ v1) — được **để ở máy cá nhân, không đưa vào repo** (xem `.gitignore`). **Toàn bộ nội dung cần cho bài nộp đã được tổng hợp vào README này**, nên repo vẫn đọc được độc lập.

---

## 2. Problem Hypothesis Brief — kết quả Chặng 1 của nhóm

### 2.1. Solution → Capability trung tính

**Solution directive (nguyên bản):** *Sau mỗi phiên học, AI phân tích hành vi học tập và tạo một Support Queue, cho biết học viên nào cần hỗ trợ, nội dung họ gặp khó khăn, các tín hiệu liên quan và hành động đề xuất để giảng viên xem xét.*

Các thành phần mang tính **giải pháp cụ thể**: AI phân tích hành vi · Support Radar · Support Queue · xếp mức ưu tiên · đề xuất hành động cho giảng viên.

> **Capability trung tính:** *Nhận diện và tổng hợp kịp thời các dấu hiệu cho thấy học viên có thể đang gặp khó khăn, giúp người phụ trách xác định trường hợp cần theo dõi hoặc hỗ trợ.*

Capability này **không mặc định** rằng: nhất thiết phải dùng AI · phải có một Support Queue · chỉ giảng viên mới có thể hỗ trợ · hệ thống phải tự động đề xuất hành động.

### 2.2. Change — chuỗi thay đổi được kỳ vọng

```
Hệ thống tổng hợp dấu hiệu học tập
  → người phụ trách nhận biết học viên có thể đang gặp khó khăn
  → hiểu học viên gặp khó ở nội dung nào và vì sao
  → ưu tiên đúng trường hợp cần quan tâm
  → quyết định có can thiệp hay không
  → học viên nhận được hỗ trợ sớm và phù hợp hơn
  → khó khăn hoặc hiểu sai được xử lý
  → học viên tiếp tục học hiệu quả hơn
```

| | Nội dung |
|---|---|
| **Output** (team tạo ra) | Danh sách học viên có thể cần hỗ trợ · các tín hiệu dẫn đến nhận định · nội dung học viên có thể gặp khó · gợi ý hành động |
| **Thay đổi hành vi phải xảy ra** | Giảng viên/coach **phải xem** danh sách → **phải tin** tín hiệu đủ hữu ích → **phải quyết định** can thiệp → **phải có thời gian** và khả năng hỗ trợ → học viên **phải tiếp nhận và phản hồi** |
| **Outcome** (chỉ ảnh hưởng được) | Học viên được hỗ trợ sớm hơn · ít trường hợp bị bỏ sót · khó khăn được giải quyết trước khi nghiêm trọng · học viên tiến bộ / hoàn thành tốt hơn |

**Giả định trong chuỗi — chuỗi chỉ đúng nếu:**

1. Hành vi như dừng lâu, xem lại, đổi câu trả lời **thực sự liên quan** đến khó khăn.
2. Giảng viên **hiện chưa dễ dàng** phát hiện các trường hợp đó.
3. Việc phát hiện sớm **dẫn tới hành động** hỗ trợ.
4. Giảng viên **có đủ nguồn lực** để can thiệp.
5. Hành động can thiệp **thực sự giúp** học viên.

> ⚠️ **Điểm gãy lớn nhất:** chuỗi đòi hỏi **hai actor khác nhau** (giảng viên **và** học viên) cùng thay đổi hành vi một cách tự nguyện. Xác suất sống sót của chuỗi = tích của hai xác suất đó.

### 2.3. Actor

| Actor | Họ đang làm gì? | Pain hoặc hậu quả có thể có | Họ hưởng lợi thế nào? |
|---|---|---|---|
| **Học viên** | Học, xem slide, ghi chú, trả lời câu hỏi, dùng AI Chat | Có thể gặp khó nhưng không nhận biết hoặc không chủ động yêu cầu giúp đỡ | Nhận hỗ trợ sớm và đúng nội dung |
| **Giảng viên** | Theo dõi nhiều học viên, quyết định ai cần hỗ trợ | Khó quan sát đầy đủ, phải xem nhiều dữ liệu, có thể bỏ sót | Biết nên ưu tiên ai và vì sao |
| **Coach** | Trực tiếp trao đổi và hỗ trợ học viên | Thiếu bối cảnh về vấn đề cụ thể của từng học viên | Chuẩn bị và hỗ trợ đúng trọng tâm hơn |
| **Người thiết kế khóa học** | Đánh giá chất lượng nội dung | Khó nhận ra nội dung nào khiến nhiều học viên gặp khó | Phát hiện nội dung cần điều chỉnh |
| **Quản lý chương trình** | Theo dõi chất lượng và kết quả đào tạo | Học viên chậm tiến độ hoặc bỏ học mà không được phát hiện sớm | Cải thiện tỉ lệ tiến bộ và hoàn thành |

- **Actor trực tiếp sử dụng:** Giảng viên / Quản lý học vụ
- **Actor phải thay đổi hành vi:** Giảng viên và Quản lý — phải xem tín hiệu, đánh giá và thực hiện hỗ trợ
- **Actor trực tiếp chịu hậu quả cuối cùng:** Học viên

> **Điểm cần lưu ý của nhóm:** người nhận Support Queue là giảng viên, nhưng **người sở hữu pain cuối cùng có thể là học viên**. Vì vậy phải nghiên cứu **cả hai phía**, không chỉ phỏng vấn người sử dụng giao diện.

### 2.4. Situation & Job

**Phía giảng viên** — Khi một phiên học kết thúc, giảng viên cần xác định học viên nào đang gặp khó khăn và nội dung nào cần được hỗ trợ, bằng cách xem xét các tín hiệu học tập đang nằm ở nhiều hoạt động khác nhau.

> **JTBD:** Khi học viên vừa hoàn thành một phiên học, tôi muốn nhanh chóng xác định ai thực sự cần hỗ trợ và họ đang vướng ở đâu, để tôi có thể ưu tiên can thiệp trước khi khó khăn trở nên nghiêm trọng.

**Phía học viên** — Khi đang học một nội dung khó, học viên cần nhận biết mình chưa hiểu và tìm được sự hỗ trợ phù hợp để tiếp tục việc học.

> **JTBD:** Khi tôi gặp khó khăn trong một phiên học nhưng chưa biết cách giải quyết, tôi muốn nhận được sự hỗ trợ đúng lúc và đúng nội dung để có thể tiếp tục học mà không bị mắc kẹt.

### 2.5. Pain — các giả thuyết cạnh tranh

| | Giả thuyết | Nếu đúng thì sao |
|---|---|---|
| 🅰️ | **Thiếu khả năng quan sát** — Khi một phiên học kết thúc, giảng viên gặp khó trong việc xác định học viên nào thực sự cần hỗ trợ vì các tín hiệu học tập **phân tán, gián tiếp và mất thời gian để xem xét**, dẫn đến hỗ trợ bị chậm hoặc bỏ sót. | Vấn đề nằm ở **khả năng nhìn thấy** → capability tổng hợp tín hiệu là đúng hướng |
| 🅱️ | **Thiếu năng lực can thiệp** — Khi nhiều học viên cùng gặp khó, giảng viên không hỗ trợ kịp vì **không đủ thời gian hoặc nguồn lực**, dẫn đến một số học viên không được hỗ trợ **dù giảng viên đã biết** họ đang gặp vấn đề. | Vấn đề nằm ở **phía cung** → thêm một danh sách nữa **không tạo ra outcome** |
| 🅲 | **Niềm tin vào hệ thống** — Khi hệ thống có vài trường hợp dự đoán sai, người dùng có xu hướng ngừng sử dụng. | Đây là giả thuyết về **độ tin cậy của giải pháp**, không phải về pain |

**Các cách giải thích cạnh tranh khác nhóm giữ lại:** học viên chỉ đang suy nghĩ kỹ chứ không gặp khó · dừng lâu / xem lại không phản ánh mức độ hiểu bài · giảng viên đã biết ai cần hỗ trợ qua bài kiểm tra hoặc trao đổi trực tiếp · học viên tự giải quyết được ở phiên sau · học viên không muốn nhận can thiệp chủ động · vấn đề nằm ở chất lượng nội dung khóa học · giảng viên có đủ thông tin nhưng không biết cách hỗ trợ phù hợp.

**Giả thuyết điều tra trước: 🅰️.** Lý do: đây là giả định trực tiếp nhất đứng sau Support Radar; nếu giảng viên vốn đã dễ dàng nhận biết học viên cần hỗ trợ thì solution không tạo thêm giá trị; và giả thuyết này kiểm được bằng tình huống và hành vi đã xảy ra. **Sau đó phải kiểm 🅱️**, vì phát hiện đúng nhưng không có khả năng can thiệp thì outcome vẫn không xảy ra.

> **Ghi chú PM của cá nhân tôi về 🅲:** giả thuyết này **không kiểm được trong problem interview** — hỏi về độ chính xác của dự đoán là làm lộ solution. Nó thuộc về vòng **prototype / concierge test** sau khi pain đã được xác nhận, nên tôi **park lại**, không đưa vào Conversation Guide.

### 2.6. Evidence — bằng chứng cần tìm

| Cần kiểm tra | Evidence làm nhóm **tin hơn** | Evidence khiến nhóm **nghi ngờ hoặc bác bỏ** |
|---|---|---|
| **Situation có thật** | Giảng viên kể được lần gần nhất phải rà soát nhiều học viên sau phiên học | Giảng viên không thực hiện việc rà soát, hoặc không xem đây là trách nhiệm của mình |
| **Pain có ý nghĩa** | Việc xác định mất nhiều thời gian, gây căng thẳng hoặc thường xuyên bị bỏ sót | Việc xác định rất nhanh, hiếm khi sai, không tạo ảnh hưởng đáng kể |
| **Workaround tồn tại** | Giảng viên dùng bảng tính, tin nhắn, quiz, báo cáo hoặc nhờ coach kiểm tra | Không có workaround vì giảng viên không thấy cần giải quyết |
| **Consequence tồn tại** | Học viên từng bị hỗ trợ chậm, lặp lại lỗi, tụt tiến độ hoặc bỏ học | Phát hiện muộn không tạo khác biệt đáng kể với kết quả học tập |
| **Pattern có lặp** | Vấn đề xuất hiện ở nhiều phiên học và với nhiều học viên | Chỉ xuất hiện trong một trường hợp đặc biệt |
| **Tín hiệu có giá trị** | Dừng lâu / xem lại / đổi đáp án có liên hệ với khó khăn **được học viên xác nhận** | Các hành vi này xuất hiện cả khi học viên đã hiểu bài hoặc chỉ đang khám phá |
| **Can thiệp tạo giá trị** | Học viên được hỗ trợ sớm giải quyết khó khăn nhanh hơn | Hỗ trợ chủ động làm gián đoạn, gây khó chịu hoặc không cải thiện kết quả |

### 2.7. Problem Hypothesis chốt lại

> **Khi một phiên học kết thúc, giảng viên hoặc coach gặp khó khăn trong việc xác định học viên nào thực sự cần hỗ trợ và họ đang vướng ở đâu, vì các tín hiệu học tập phân tán, gián tiếp và mất thời gian để kiểm tra, dẫn đến việc hỗ trợ có thể bị chậm hoặc bỏ sót.**

**AI Support Radar được "park" cho đến khi có bằng chứng rằng:**
1. Vấn đề nhận diện thực sự tồn tại và lặp lại.
2. Vấn đề tạo ra hậu quả đáng kể.
3. Các tín hiệu được phân tích có liên quan đến khó khăn thật.
4. Giảng viên có khả năng và động lực hành động sau khi nhận thông tin.

### 2.8. Solution Parking Lot

> Solution directive gốc trở thành **một** phương án ngang hàng, không phải mặc định.

| # | Hướng giải quyết | AI / Không AI | Nhắm vào mắt xích nào |
|---|---|---|---|
| 1 | Nút **"Tôi đang mắc ở đây"** ngay trên slide → tạo yêu cầu hỗ trợ kèm ngữ cảnh | **Không AI** | Hạ chi phí của việc hỏi; giữ nguyên ngữ cảnh |
| 2 | **Office hours cố định** + đặt lịch một chạm ngay trong bài học | **Không AI** | Tạo cửa sổ hỗ trợ dự đoán được; giải quyết mandate |
| 3 | **Thảo luận gắn theo từng slide** — thấy người khác cũng mắc đúng chỗ đó | **Không AI** | Xoá nỗi ngại hỏi; câu trả lời có sẵn = độ trễ bằng 0 |
| 4 | **Heatmap cấp lớp theo khái niệm** → sửa nội dung / dạy lại 10 phút đầu buổi sau | **Không AI** | Tránh đòi hỏi thay đổi hành vi 1-1; sửa nguyên nhân ở nội dung |
| 5 | **AI Chat có ngữ cảnh slide + tự escalate** cho người thật khi hỏi lại lần thứ 3 | AI | Gỡ ngay trong phiên; chỉ dùng người khi máy đã thất bại |
| 6 | **Digest gửi cho chính học viên** sau phiên: "3 điểm bạn nên xem lại" + link tới đúng slide | AI | Bỏ hẳn mắt xích giảng viên — chỉ cần **một** thay đổi hành vi |
| 7 | **AI Support Radar (directive gốc)** — Support Queue ưu tiên cho giảng viên | AI | Việc giảng viên không nhìn thấy ai đang gặp khó |

### 2.9. Hai lớp nội dung trong repo này — ghi rõ để không lẫn

| | Nội dung | Actor điều tra trước | Ở đâu |
|---|---|---|---|
| **Bản của nhóm** (mục 2 ở trên) | Pain 🅰️ = giảng viên thiếu khả năng quan sát | **Giảng viên / Quản lý học vụ** | README này |
| **Phần mở rộng cá nhân của tôi** | Pain 🅰️ = chi phí & độ trễ của việc **xin** trợ giúp phía học viên | **Học viên** | §3.4 + bản nháp cá nhân |

**Vì sao tôi giữ cả hai:** chính nhóm đã ghi *"người nhận Support Queue là giảng viên, nhưng người sở hữu pain cuối cùng có thể là học viên — cần nghiên cứu cả hai phía"* (mục 2.3). Bản mở rộng cá nhân là việc thực hiện đúng ghi chú đó, **không phải thay thế** kết luận của nhóm. Conversation Guide cuối cùng vì vậy có **hai phần**: Phần I cho học viên, Phần II cho giảng viên/coach.

---

## 3. Conversation Guide — phiên bản cuối (v2)

> **Đây là bản v2 — bản chạy thật trong 15 phút** của Chặng 3, và là **phiên bản cuối được nộp**.
> Bản v1 đầy đủ (289 dòng, ngân sách 20–25 phút) giữ ở máy cá nhân; lý do cắt xuống v2 ghi ở mục 3.8.

### 3.1. Ba quy tắc bắt buộc

1. **Solution vẫn bị park.** Không từ nào được phép xuất hiện: *AI, phân tích, tín hiệu, danh sách, hàng đợi, ưu tiên, cảnh báo, hệ thống phát hiện, gợi ý*.
2. **Chỉ hỏi quá khứ đã xảy ra.** Không hỏi *"bạn có muốn…", "bạn nghĩ sao nếu…", "bạn sẽ dùng chứ…"*. Mọi câu neo vào **"lần gần nhất"**.
3. **Mục tiêu là tìm cách bác bỏ giả thuyết, không phải xác nhận nó.** Mỗi guide có ít nhất một 🔥 câu có thể giết chết case.

### 3.2. Tiêu chí tuyển người

> **Học viên:** người đã **tự học ít nhất một phiên một mình, ngoài giờ làm, và có ít nhất một lần phải xem lại / làm lại một phần nội dung** trong **14 ngày** gần đây.
> **Giảng viên / coach:** đang phụ trách ít nhất một lớp **đang chạy** trong **30 ngày** gần đây.

**Recruitment check** *(tuyển người — không tính là evidence)*: *"Trong hai tuần gần đây, bạn có buổi nào ngồi học online một mình mà phải quay lại xem lại một phần nội dung không? Buổi gần nhất rơi vào khoảng ngày nào?"*
→ Đạt = **có** + **mốc thời gian cụ thể**. Không đạt → báo giảng viên đổi cặp.

### 3.3. Consent + lời mở đầu

> *"Trước khi bắt đầu, mình xin phép ghi âm buổi này. Bản ghi chỉ dùng để mình nghe lại, bóc transcript và phục vụ bài học — không chia sẻ công khai. Bạn có thể yêu cầu dừng ghi hoặc xoá bất cứ lúc nào. Bạn đồng ý chứ?"*
>
> *"Hôm nay mình **không giới thiệu hay demo gì cả**, và **không có câu trả lời đúng hay sai**. Mình muốn hiểu **một buổi tự học thực tế diễn ra như thế nào** — bạn ngồi xuống lúc nào, gặp chuyện gì, xoay xở ra sao. Mình sẽ hỏi nhiều về *'lần gần nhất'* thay vì *'bạn thường'*; không nhớ chính xác thì cứ nói không nhớ."*

### 3.4. PHẦN I — Guide HỌC VIÊN · 15 phút · 8 câu bắt buộc

| Phút | Câu hỏi | Kiểm điều gì |
|---|---|---|
| 0–1.5 | *Consent · lời mở đầu · recruitment check* | — |
| 1.5–4.5 | **L1 (opener):** "Kể mình nghe về **lần gần nhất** bạn ngồi học một mình mà gặp một phần bạn không hiểu được ngay — hôm đó diễn ra như thế nào?"<br>*Neo:* "Tối trong tuần hay cuối tuần? Mấy giờ? Module nào? Trước đó bạn vừa làm gì xong?" | Situation có thật |
| 4.5–8 | **L2:** "Từ lúc nhận ra mình chưa hiểu, bạn đã làm những gì? **Kể theo thứ tự**, từ việc đầu tiên đến lúc bạn dừng."<br>**L3:** "Lúc đó bạn mở thêm những gì — tab nào, ứng dụng nào, sổ nào?"<br>**L4:** "Trong lần đó bạn **có hỏi ai không?**" → *[Có]* "Hỏi ai, kênh nào, **bao lâu sau** thì có trả lời? Có gỡ được không?" → *[Không]* "**Điều gì khiến bạn không hỏi?**" | 🅰️ độ trễ + chi phí xã hội |
| 8–11 | 🔥 **L5:** "Khoảng bao lâu thì bạn dừng lại — và **ngay lúc dừng, chuyện gì đang diễn ra với bạn?**"<br>🔥 **L6:** "Lúc đóng máy tối đó, bạn nghĩ về chỗ đó là **'mình chưa hiểu'** hay **'chắc ổn rồi, mai tính'**?"<br>**L7:** "Có phần nào bạn **cố tình đọc lại vì thấy quan trọng**, dù đã hiểu rồi không?" | 🅱️ ngắt quãng · 🅲 ảo giác đã hiểu · **A2 false positive** |
| 11–14 | **L8:** "Sau buổi đó, chỗ chưa hiểu ấy về sau ra sao — nó có quay lại làm khó bạn ở bài nào không?"<br>🔥 **L9:** "Có bao giờ giảng viên hoặc trợ giảng **chủ động nhắn cho bạn trước** không? Lần đó bạn **đã làm gì**?" → "Tin nhắn đến vào lúc nào so với lúc bạn đang học?" | Consequence · **A3 + A6** |
| 14–15 | **L10:** "Lần gần nhất **trước đó** bạn gặp chuyện tương tự là khi nào?" · "Có chuyện gì mình chưa hỏi tới mà bạn thấy đáng kể không?" | Pattern có lặp |

### 3.5. PHẦN II — Guide GIẢNG VIÊN / COACH · 15 phút · 8 câu bắt buộc

| Phút | Câu hỏi | Kiểm điều gì |
|---|---|---|
| 0–1.5 | *Consent · mở đầu · screener (mấy lớp, bao nhiêu học viên, buổi gần nhất hôm nào)* | — |
| 1.5–4 | **I1 (opener):** "Kể em nghe về **buổi gần nhất** anh/chị phụ trách — sau khi buổi đó kết thúc, **việc tiếp theo** anh/chị làm là gì?"<br>**I2:** "Tuần vừa rồi tổng thời gian cho lớp này khoảng bao nhiêu tiếng? Bao nhiêu trong đó là **ngoài giờ dạy**?" | Situation phía cung có thật |
| 4–7.5 | **I3:** "**Lần gần nhất** anh/chị phát hiện một học viên đang gặp khó — biết được **qua đâu**?" → "Từ lúc bạn ấy bắt đầu gặp khó tới lúc anh/chị biết, khoảng **bao lâu**?"<br>**I4:** "Có trường hợp nào anh/chị chỉ biết khi bạn ấy **đã nghỉ hẳn** không?"<br>**I5:** "Anh/chị có tự ghi chép riêng về học viên ở đâu không — file, sổ, nhóm chat?" | 🅰️ độ trễ phát hiện · **workaround** |
| 7.5–12 | 🔥 **I6:** "**Lần gần nhất anh/chị có trong tay một danh sách học viên điểm thấp hoặc chậm tiến độ — anh/chị đã làm gì với nó?**" → "Liên hệ được mấy người? Còn lại thì sao?"<br>🔥 **I7:** "Việc liên hệ học viên ngoài giờ **có nằm trong phần được tính công** không? **Ai kỳ vọng** anh/chị làm việc đó?"<br>**I8:** "Một tuần bình thường anh/chị nhắn riêng được cho **khoảng bao nhiêu** học viên? **Tuần vừa rồi cụ thể là mấy người?**" | 🅱️ · **A1 mandate** · **A5 trần năng lực** |
| 12–14.5 | **I9:** "Lần gần nhất anh/chị liên hệ một học viên đang gặp khó — bạn ấy **có trả lời không**? Sau đó có **quay lại học** phần đó không?"<br>**I10:** "Có lần nào anh/chị liên hệ mà **nhầm** không — hoá ra bạn ấy vẫn ổn?" | **A4** · **A2 nhìn từ phía cung** |
| 14.5–15 | **I11:** "Có cái gì trong hệ thống anh/chị **đã bỏ không dùng nữa** không? Vì sao?" | Bằng chứng mạnh nhất rằng thêm-một-màn-hình sẽ chết |

### 3.6. Probe bank & ba phản xạ khi data lệch

| Loại | Probe |
|---|---|
| Hành vi | "Rồi chuyện gì xảy ra tiếp?" · "Lúc đó bạn làm gì?" · "Kể lại theo thứ tự giúp mình." |
| Thời gian | "Khoảng bao lâu?" · "Mấy giờ?" · "Bao lâu sau thì có phản hồi?" |
| Lý do | "Vì sao lại chọn cách đó?" · "Điều gì khiến bạn thôi không làm cách kia?" |
| Workaround | "Đã thử cách nào khác chưa?" · "Có ghi lại ở đâu không?" · "Có nhờ ai không?" |
| Hậu quả | "Việc đó kéo theo chuyện gì?" · "Cuối cùng kết cục ra sao?" |
| Tần suất | "Lần gần nhất **trước đó** là khi nào?" |
| **Im lặng** | *đếm thầm 5 giây — câu quan trọng nhất thường nằm sau khoảng lặng* |

| Interviewee đưa ra | Phản xạ | Câu kéo về evidence |
|---|---|---|
| **Lời khen** — *"Nền tảng dùng tiện lắm."* | **Deflect** | "Cảm ơn bạn — quay lại buổi tối hôm đó chút, sau khi mở lại slide thì việc tiếp theo là gì?" |
| **Câu chung chung / lời hứa** — *"Thường thì mình sẽ hỏi giảng viên."* | **Anchor** | "**Lần gần nhất** bạn thực sự nhắn cho giảng viên là khi nào? Kể mình nghe lần đó." |
| **Ý tưởng / feature request** — *"Giá mà hệ thống tự nhắc."* | **Dig** | "Nếu có cái đó thì nó giúp bạn **làm được gì** mà giờ chưa làm được? **Hiện tại** bạn xử lý ra sao?" |
| **Điều-nên-làm** *(hay gặp ở giảng viên)* — *"Tất nhiên phải sát sao từng em chứ."* | **Anchor vào lịch** | "Tuần vừa rồi cụ thể anh/chị làm việc đó với **mấy em**? Vào **những ngày nào**?" |

### 3.7. Bản đồ câu hỏi → giả định được kiểm

| Giả định | Rủi ro | Câu kiểm | Kết quả làm nó **sụp** |
|---|---|---|---|
| **A1** — giảng viên có thời gian & mandate | 🔴 | I6, I7, I2 | Không được tính công, không ai kỳ vọng, danh sách cũ chưa từng được dùng |
| **A2** — tín hiệu phân biệt được "không hiểu" với việc khác | 🔴 | L5, L7, I10 | Lý do dừng là ngắt quãng/mệt; đọc lại vì kỹ chứ không vì khó |
| **A3** — học viên không thấy bị theo dõi | 🟡 | L9 | Từng bị nhắn và thấy khó chịu / phớt lờ |
| **A4** — can thiệp 1-1 thực sự gỡ được | 🟡 | I9 | Nhắn xong không ai trả lời, hoặc trả lời rồi vẫn không quay lại |
| **A5** — queue đủ ngắn để xử lý | 🟡 | I8 | Trần thật 3–5 người/tuần trên lớp 100+ |
| **A6** — "sau phiên học" còn kịp | 🔴 | L9, L5 | *"Hôm sau em quên rồi"* |

### 3.8. v1 → v2: đã sửa gì và vì sao

| # | Thay đổi | Lý do |
|---|---|---|
| 1 | **Cắt từ 20–25 phút xuống 15 phút**, chốt **8 câu bắt buộc** mỗi phần; phần còn lại chuyển thành probe tuỳ chọn | Chặng 3 chỉ cho **15 phút/lượt**. v1 dài 289 dòng, chạy hết chắc chắn tràn giờ và ép interviewer đọc bảng hỏi cho kịp — đúng dấu hiệu **chưa đạt Gate 3**. |
| 2 | **Gộp consent vào ngay đầu guide**, không tách thành thủ tục riêng | v1 để consent nằm ngoài guide → dễ quên bấm ghi trước khi xin phép. Consent là **điều kiện của Checkpoint 3**, phải là dòng đầu tiên. |
| 3 | **Đưa Phần II (giảng viên) lên ngang hàng Phần I**, không còn là "nếu có thời gian" | Pain 🅰️ mà **nhóm** chọn điều tra trước là pain **phía giảng viên**. v1 ưu tiên học viên là quyết định cá nhân của tôi, lệch khỏi kết luận nhóm. |
| 4 | **Bỏ Pain 🅲 (niềm tin vào AI) khỏi guide** | Không thể hỏi về độ chính xác của dự đoán mà không **làm lộ solution**. Chuyển sang vòng prototype. |
| 5 | **Thêm probe "Im lặng 5 giây"** vào bảng probe chính | Ở v1 nó nằm cuối file, dễ bỏ qua. Lỗi phổ biến nhất của interviewer mới là **nói lấp chỗ trống**. |
| 6 | **Mọi câu 🔥 được đánh dấu và đặt ở giữa buổi** (phút 8–12), không để cuối | Câu có thể giết chết case phải được hỏi khi vẫn **còn thời gian đào tiếp**, không phải lúc đã hết giờ. |

### 3.9. Sửa sau khi luyện — từ chính buổi phỏng vấn 4'35"

> Sáu thay đổi ở 3.8 đến từ **rà soát thiết kế**. Sáu thay đổi dưới đây đến từ **lỗi thật của tôi trong buổi luyện**, mỗi dòng dẫn về đúng phút trong `interview/transcript.md`.

| # | Chuyện đã xảy ra trong buổi | Sửa vào guide |
|---|---|---|
| **7** | **00:00 — lời mở đầu nói *"thu thập ý kiến cá nhân để cải tiến VLearn"*.** Ngay câu đầu tôi đã đặt user vào vai **người góp ý sản phẩm**. Hệ quả kéo dài cả buổi: user trả lời bằng *nhận xét về công cụ* thay vì *kể chuyện*. | Đưa lời mở đầu thành **câu phải đọc nguyên văn**, in đậm hai lệnh cấm ngay trên đầu guide: **không nói "cải tiến/góp ý/ý kiến"**, **không nhắc tên sản phẩm như một thứ đang được sửa**. Mở đầu bắt buộc bắt đầu bằng *"Hôm nay mình không demo hay giới thiệu gì cả…"* |
| **8** | **Consent ghi âm bị bỏ qua.** Tôi xin phép *phỏng vấn*, không xin phép *ghi âm* — hai việc khác nhau, và Checkpoint 3 yêu cầu cái thứ hai. | **Tách consent thành bước 0 riêng, có ô tick, đặt TRƯỚC mọi thứ khác** trong guide, kèm câu mẫu đọc nguyên văn và quy tắc **"chỉ bấm ghi sau khi nghe câu đồng ý, và ghi câu đồng ý đó vào đầu băng"**. |
| **9** | **00:13 — hỏi *"những lần gần nhất"* (số nhiều, không neo thời gian)** → user trả lời khái quát, cả buổi không có nổi một sự kiện có ngày giờ. | Story opener trong guide đổi thành bản **ép chọn một buổi**: *"…**một buổi cụ thể** thôi — **hôm đó là hôm nào, khoảng mấy giờ, bạn đang học phần nào?**"*. Thêm quy tắc: **chưa có ngày + giờ + module thì chưa được sang câu tiếp theo.** |
| **10** | **01:12 — tôi đính chính giữa buổi** (*"trên VLearn cũng có chức năng note đấy"*) và **bỏ ngang** đúng lúc user để lộ rằng họ không biết chức năng đó tồn tại. | Thêm vào Probe bank một mục mới — **"Khi user mô tả sai hoặc không biết về sản phẩm: KHÔNG đính chính."** Kèm probe thay thế: *"Lúc đó bạn đã tìm ở đâu? Tìm bao lâu rồi thôi? Cuối cùng bạn ghi vào đâu?"* |
| **11** | **02:50 — user nói *"khó quá thì mình bỏ qua"* và tôi chuyển câu.** Cả buổi **không lấy được một hậu quả nào** — thứ mà Evidence Map xếp là bắt buộc. | Đưa **hậu quả thành câu bắt buộc không được bỏ**, và gắn nó thành **phản xạ tự động**: hễ nghe *"bỏ qua / kệ / để sau / thôi luôn"* thì câu kế tiếp **luôn** là *"Lần gần nhất bạn bỏ qua là chỗ nào? Sau đó nó có quay lại làm khó bạn ở bài nào không?"* |
| **12** | **03:53 — nhận lời khen về lab coach làm câu trả lời** và chuyển câu, dù chính đề bài ghi rõ lời khen không phải evidence. | Nâng phản xạ **Deflect** từ một dòng trong bảng thành **câu mẫu bắt buộc**: *"Cảm ơn bạn — mà **lần gần nhất** anh/chị ấy nhắn cho bạn là khi nào? Lúc đó bạn đang vướng gì, và sau khi trao đổi xong bạn có quay lại phần đó không?"* |

> **Một thay đổi về cách chạy, không phải về câu hỏi:** buổi này dùng **4'35" / 15 phút** và tôi **nói nhiều hơn user (~53% / 47%)**. Guide v2 vì vậy thêm một dòng nhắc ở đầu mỗi phần: **"Nếu đến phút thứ 5 mà user chưa kể được một buổi có ngày giờ cụ thể, quay lại story opener — đừng đi tiếp."**

---

## 4. Practice Reflection

> Ba câu dưới đây được viết **sau** buổi luyện phỏng vấn 4'35" ngày 17/08/2026, dựa trên bản ghi đã bóc transcript. Dẫn chứng đầy đủ ở `interview/notes.md` §3–§4 và `interview/transcript.md`.

**1. Câu hỏi nào đã giúp user kể một tình huống cụ thể?**

Không phải một câu hỏi lớn, mà là **hai câu ngắn**:

- **"Ngoài điều đó ra thì bạn có chủ động research trên mạng hay những nguồn khác không?"** (01:50) → mở ra **chuỗi hành vi thật, kể đúng thứ tự**: *"trước hết mình sẽ search trên Google, nếu không có trên Google thì mình sẽ tra chatbot… nếu không hiểu nữa thì mình sẽ hỏi giảng viên. Nhưng tần suất mình hỏi giảng viên khá là ít, tại vì mình khá là rụt rè."* Đây là dữ liệu giá trị nhất cả buổi: vừa có **thứ tự**, vừa có **tần suất**, vừa có **lý do dừng lại**.
- **"Còn gì khác nữa không?"** (02:53) — một câu bỏ ngỏ, hỏi xong thì **im lặng chờ**. Chính khoảng lặng đó kéo ra quote đắt nhất: *"mình khá là ngại giao tiếp, nhưng nếu có cách gì đấy khiến mình giao tiếp với giảng viên **mà không cần phải nói chuyện** thì mình có thể sử dụng."*

**Điều tôi rút ra:** câu hỏi mở ra được chuyện thật đều là câu **ngắn, không gợi ý nội dung, và có chỗ trống để user tự lấp**. Còn những câu tôi soạn dài và đầy đủ nhất lại là những câu nhận về câu trả lời khái quát nhất.

**2. Chỗ nào mình cần làm tốt hơn ở lần phỏng vấn thật?**

**Lỗi nghiêm trọng nhất: phút 01:12.** User nói muốn ghi chú bằng note. Tôi đáp *"Và trên VLearn cũng có chức năng note đấy"*. User: **"Ủa thế nào? Mình không biết luôn."** Tôi nói *"À không sao"* rồi chuyển câu.

Tôi đã làm sai **hai việc cùng lúc**:
- **Đính chính / dạy sản phẩm cho user giữa buổi phỏng vấn** — đúng dấu hiệu "pitch solution" mà Gate 3 liệt kê.
- **Bỏ đúng tín hiệu đắt nhất của cả buổi.** Câu *"mình không biết luôn"* nói rằng thứ user gọi là "khó khăn" thực ra là **không tìm thấy chức năng đang tồn tại** — một discoverability problem, không phải mắc kẹt nội dung. Nếu đào tiếp (*tìm ở đâu, tìm bao lâu, cuối cùng ghi vào đâu*), tôi đã có một câu chuyện hoàn chỉnh. Thay vào đó tôi tự tay đóng nó lại.

**Hai lỗi hệ thống đi kèm:**
- **Không lấy được một hậu quả nào.** User nói *"khó quá thì mình bỏ qua"* (02:50) — tôi chuyển câu. Cả Evidence Map xoay quanh consequence, và tôi về tay không ở đúng ô đó.
- **Tôi nói nhiều hơn user: ~53% / 47%,** trong một buổi chỉ dài 4'35" trên khung 15 phút. Nói ít lại thì đã có thêm thời gian cho những chỗ đáng đào.

**Ba việc cụ thể tôi sẽ làm khác:** (1) khi user hiểu sai hoặc không biết về sản phẩm — **tuyệt đối không đính chính**, đào tiếp; (2) hễ nghe *"bỏ qua / thôi luôn / để sau"* — câu kế tiếp **luôn** là câu về hậu quả; (3) đọc consent ghi âm thành **bước 0 có ô tick**, không dựa vào trí nhớ.

**3. Sau khi luyện, nhóm đã sửa Conversation Guide ở đâu và vì sao?**

Sáu thay đổi, ghi đầy đủ ở **mục 3.9**, mỗi thay đổi truy về đúng một phút trong bản ghi:

| Sửa ở đâu | Vì sao |
|---|---|
| **Lời mở đầu** — cấm các từ *"cải tiến / góp ý / ý kiến"*, bắt buộc mở bằng *"hôm nay mình không demo hay giới thiệu gì cả"* | 00:00 tôi nói *"thu thập ý kiến cá nhân để cải tiến VLearn"* → user vào vai người góp ý sản phẩm và ở nguyên vai đó suốt buổi |
| **Consent tách thành bước 0 riêng, có ô tick** | Tôi xin phép *phỏng vấn* nhưng quên xin phép *ghi âm* — Checkpoint 3 đòi cái thứ hai |
| **Story opener ép chọn một buổi + quy tắc "chưa có ngày, giờ, module thì chưa đi tiếp"** | 00:13 tôi hỏi *"những lần gần nhất"* (số nhiều) → cả buổi không có nổi một sự kiện có mốc thời gian |
| **Probe bank thêm mục "user hiểu sai / không biết về sản phẩm → KHÔNG đính chính"** | Lỗi 01:12 ở câu 2 phía trên |
| **Câu hỏi hậu quả thành phản xạ tự động khi nghe "bỏ qua"** | 02:50 bị bỏ trôi → buổi phỏng vấn về tay không ở ô consequence |
| **Phản xạ Deflect với lời khen được viết thành câu mẫu bắt buộc** | 03:53 tôi nhận lời khen về lab coach làm câu trả lời, trong khi đề bài ghi rõ lời khen không phải evidence |

**Một thay đổi ở tầng cao hơn câu hỏi:** buổi này chỉ chạm được phía **học viên**, trong khi Pain 🅰️ mà **nhóm** chọn điều tra trước lại nằm ở phía **giảng viên** — và còn nhận một tín hiệu phản chứng chưa xác minh (*"thầy cô rất hay hỗ trợ mình"*, 03:53). Vì vậy vòng phỏng vấn tới **phải có instructor/coach thật**, nếu không **A1** và **A5** sẽ mãi là hai giả định 🔴 không ai kiểm.

---

## 5. AI Support Log

### 5.1. AI đã giúp gì

| Việc | AI đã làm |
|---|---|
| Gỡ solution → capability trung tính | Tách các câu trong directive thành **giao diện / công nghệ / nhịp / kênh / proxy tín hiệu**, giúp thấy 5 dòng đầu đều là **lựa chọn triển khai**, không phải vấn đề |
| Chuỗi Change | Viết tách bạch **output vs. outcome**, và chỉ ra chuỗi đòi hỏi **hai actor cùng thay đổi hành vi** — điểm gãy lớn nhất của case |
| Bản đồ giả định A1–A6 | Đặt tên và gán mức rủi ro cho từng mắt xích ngầm, rồi **ánh xạ từng câu hỏi phỏng vấn về đúng giả định nó kiểm** |
| Rà soát guide | Rà từ khoá lộ solution (*AI, tín hiệu, danh sách, ưu tiên, cảnh báo*) và rà thì của câu hỏi (quá khứ vs. tương lai) |
| Cấu trúc repo & biên bản | Dựng `interview/notes.md` gồm consent script, Interview Record và checklist tự kiểm |
| **Bóc transcript bản ghi** | Cài `faster-whisper` trong venv riêng và transcribe file `.m4a` **hoàn toàn offline trên máy cá nhân** (bản ghi không rời khỏi máy), rồi đối chiếu từng phút để điền Interview Record |
| **Soi lại buổi phỏng vấn** | Đếm tỉ lệ nói (**53% interviewer / 47% user**), chỉ ra 7 chỗ dẫn dắt hoặc bỏ lỡ tín hiệu, và truy từng thay đổi của guide về đúng mốc phút trong bản ghi |

### 5.2. Điểm AI làm sai hoặc hời hợt — và tôi đã sửa thế nào

| # | Vấn đề | Tôi đã sửa |
|---|---|---|
| **1** | **Tự đổi actor điều tra trước.** Bản lab do AI hỗ trợ chọn **học viên** làm actor điều tra trước, trong khi Chặng 1 của **nhóm** đã chốt là **giảng viên / quản lý học vụ**. AI trình bày lựa chọn đó như thể là kết luận duy nhất, **không hề ghi chú rằng nó khác với quyết định của nhóm**. | Tôi tách rõ **hai lớp** ở mục 2.9: bản của nhóm giữ nguyên actor giảng viên; phần mở rộng cá nhân được ghi đúng danh nghĩa là mở rộng. Guide v2 đưa **Phần II (giảng viên) lên ngang hàng** thay vì để là tuỳ chọn. |
| **2** | **Viết cho đầy đủ, không viết cho chạy được.** Guide v1 dài **289 dòng**, ngân sách 20–25 phút — trong khi Chặng 3 chỉ có **15 phút/lượt**. Nếu cầm nguyên bản đó vào phòng thì chắc chắn phải **đọc bảng hỏi cho kịp giờ**, đúng dấu hiệu chưa đạt của Gate 3. | Cắt xuống **8 câu bắt buộc/phần**, có mốc phút cụ thể; phần còn lại hạ xuống thành probe tuỳ chọn. |
| **3** | **Giữ một "pain" không phải pain.** AI để nguyên Pain 🅲 của nhóm (*người dùng mất niềm tin khi AI dự đoán sai*) trong danh sách giả thuyết cần kiểm, dù **không thể hỏi nó mà không làm lộ solution**. | Loại 🅲 khỏi Conversation Guide, ghi rõ lý do ở mục 2.5 và park sang vòng prototype. |
| **4** | **Xu hướng điền sẵn dữ liệu chưa có.** Khi được yêu cầu "hoàn thành bài lab" lúc chưa có bản ghi, AI hoàn toàn có thể viết luôn nội dung Interview Record — tức là **bịa lời của người được phỏng vấn**, thứ mà cả bài học này đang dạy là không được làm. | Tôi giữ biên bản **ở dạng trống** cho tới khi có bản ghi thật, rồi mới bóc transcript và điền. Mọi quote trong `notes.md` đều **có mốc phút** để đối chiếu ngược lại băng. |
| **5** | **AI đọc bản ghi "thuận chiều giả thuyết".** Ở lượt tổng hợp đầu, câu *"thầy cô rất hay hỗ trợ mình nên mình thấy rất hữu ích"* (03:53) suýt bị xếp vào evidence — trong khi đề bài ghi rõ **lời khen không phải bằng chứng về pain**, và đây thực ra là **tín hiệu phản chứng** cho tiền đề "hỗ trợ bị chậm hoặc bỏ sót". | Tách riêng trong `notes.md` §1.2 ②: ghi nhận là **lời khen chưa được đào thành sự kiện**, không tính là evidence, đồng thời đánh dấu là điểm phản chứng cần kiểm ở vòng sau. |
| **6** | **Câu 🔥 bị đặt sai chỗ.** Trong v1, các câu có thể giết chết case nằm rải rác, một số ở cuối guide. | Dồn các câu 🔥 vào **phút 8–12**, khi vẫn còn thời gian đào tiếp câu trả lời. |

### 5.3. Điều tôi tự rút ra về cách dùng AI trong problem discovery

AI rất mạnh ở việc **làm lộ các giả định ngầm** và **giữ cho câu hỏi không lộ solution** — đó là việc cần tính hệ thống và rà soát kỹ. Nhưng AI **không có evidence**: nó không ngồi trong buổi phỏng vấn, không nghe được câu người ta ngập ngừng trước khi trả lời. Mọi thứ AI viết trong repo này đều là **hypothesis**, và ranh giới đó phải do tôi giữ — vì bản thân AI sẵn sàng viết một câu chuyện nghe rất thuyết phục về một người không tồn tại.

---

## ✅ Trạng thái theo bốn gate đánh giá

| Gate | Trạng thái | Ở đâu |
|---|---|---|
| **1. Problem Framing** | ✅ Hoàn thành — đủ chuỗi `Solution → Change → Actor → Situation & Job → Pain → Evidence`, 3 giả thuyết cạnh tranh, nêu rõ điều gì làm giả thuyết sai, Parking Lot 7 hướng (4 hướng không AI) | README §2 |
| **2. Interview Design** | ✅ Hoàn thành — Big 3 nối với điều cần học, guide hỏi quá khứ, đã rà từ khoá lộ solution | README §3 |
| **3. Interview Practice** | 🟨 **Đã luyện, chưa đạt trọn** — có bản ghi 4'35" + Interview Record đã điền + 4 quote nguyên văn. **Còn thiếu: consent ghi âm** (mới xin phép phỏng vấn) và **screener không được chạy**. Tự chấm: dính "nói nhiều" (53/47) và một lần đính chính sản phẩm giữa buổi | `interview/notes.md` · `interview/transcript.md` |
| **4. Reflection & Revision** | ✅ Hoàn thành — 6 sửa đổi từ rà soát thiết kế (§3.8) **+ 6 sửa đổi từ lỗi thật trong buổi luyện, mỗi cái truy về đúng một mốc phút** (§3.9); Reflection chỉ ra lỗi cụ thể kèm dẫn chứng | README §3.8 · §3.9 · §4 |

### Việc phải làm trước khi nộp

| # | Việc | Vì sao |
|---|---|---|
| 1 | **Xin xác nhận đồng ý ghi âm từ `L01`** (tin nhắn là đủ), đính kèm vào `interview/` | Điều kiện bắt buộc của Checkpoint 3 — chi tiết ở `interview/notes.md` §0 |
| 2 | Nếu `L01` không đồng ý → **xoá `.m4a` và `transcript.md`**, chỉ giữ tổng hợp không định danh | Tôn trọng cam kết với người tham gia |
| 3 | **Không public repo** khi còn file `.m4a` và transcript trong đó | Consent trên băng không hề nói tới việc chia sẻ |
| 4 | Điền tên thật của `L01` vào ghi chú riêng (không đưa vào repo), giữ mã `L01` trong bài | Ẩn danh hoá đúng cách |
