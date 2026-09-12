# Lab 02 — Worksheet: AI Product Scoping (Vin Smart Future)

---

## 🏛️ 1. Bối cảnh thực tế: Vin Smart Future (Vingroup)

**Vingroup** — Tập đoàn tư nhân lớn nhất Việt Nam — vừa sáp nhập toàn bộ các phòng ban công nghệ thuộc các công ty thành viên thành một đơn vị công nghệ thống nhất mang tên **Vin Smart Future**. 

Nhiệm vụ của **Vin Smart Future** là xây dựng các giải pháp AI, số hóa, và tự động hóa cốt lõi để nâng cao hiệu suất vận hành và trải nghiệm khách hàng xuyên suốt các công ty thành viên:
* 🚗 **VinFast:** Hệ thống xe điện thông minh (EV), trợ lý AI ảo trong xe, dự đoán bảo trì pin, và quản lý chuỗi cung ứng sản xuất.
* 🚕 **Xanh SM (GSM):** Vận hành đội xe taxi/xe máy điện thông minh, điều vận thông minh (Smart Dispatching), tối ưu hóa lộ trình di chuyển.
* 🏢 **Vinhomes:** Quản lý đô thị thông minh (Smart Cities), trợ lý cư dân thông minh, tối ưu hóa mức tiêu thụ năng lượng.
* 🏥 **Vinmec:** Y tế thông minh, chẩn đoán hình ảnh bằng AI, tối ưu hóa quản lý hồ sơ bệnh án.
* 🎢 **Vinpearl / VinWonders:** Trải nghiệm du lịch số hóa, quản lý phòng và luồng khách thông minh tại các khu vui chơi.

Trong buổi Lab hôm nay, nhóm của bạn sẽ đóng vai trò là **AI Product Engineer** tại **Vin Smart Future**, tiến hành tìm kiếm, scoping, phân tích độ khả thi, thiết lập ranh giới vận hành, và xây dựng một **bản mẫu kỹ thuật (prompt prototype)** cho một bài toán cụ thể thuộc một trong những mảng kinh doanh trên.

---

## 📊 2. Cơ cấu tính điểm bài lab

### 👥 Điểm nhóm (60 điểm)

| Gate | Điểm | Deliverable | Tiêu chí chấm |
|---|---:|---|---|
| **G1. Workflow Mapping** | 20 | Problem Deep-Dive | Vẽ chi tiết quy trình hiện tại: các bước, handoff, thời gian, bottleneck |
| **G2. Problem Statement** | 20 | Problem Deep-Dive | Problem Statement 6-field bám sát thực tế, metric có số và ranh giới rõ ràng |
| **G3. AI Fit & Future Flow** | 10 | Problem Deep-Dive | So sánh Rule vs LLM vs Agent, future flow có bước AI, ranh giới và Fallback |
| **G4. Decision Quality** | 10 | Problem Deep-Dive | Quyết định Go/Not Yet/No-Go trung thực và có chứng cứ rõ ràng |

### 👤 Điểm cá nhân (40 điểm)

| Gate | Điểm | Deliverable | Tiêu chí chấm |
|---|---:|---|---|
| **I1. Scan & Cards** | 15 | Quick Cards | Liệt kê 5 problems sử dụng 3 lenses, hoàn thiện 3 quick cards chất lượng |
| **I2. Prototyping** | 10 | 02-lab/ | Chạy thử nghiệm programmatic prompt prototype thành công |
| **I3. AI Log & Reflection** | 15 | 03-ai-log.md | Phản ánh trung thực về việc dùng AI làm thought-partner (giúp gì, sai gì, sửa gì) |

---

# 🚀 Phase 0 — worked Example: Xanh SM Intelligent Dispatcher (15 min)

*Giảng viên walk-through ví dụ thực tế từ Vin Smart Future để bạn hiểu rõ cách scoping một bài toán AI.*
Đọc chi tiết worked example tại file [02-deliverable-example.md](02-deliverable-example.md).

---

# 🔍 Phase 1 — SCAN (Cá nhân, 20 min)

Hãy sử dụng **4 Lenses** dưới đây để quét qua hoạt động vận hành của các công ty thành viên Vingroup. Ghi lại **ít nhất 5 bài toán/bottleneck** thực tế.

### 4 Lenses tìm bài toán AI cho Vingroup:
1. **Lặp lại (Repetitive):** Tác vụ lặp đi lặp lại nhiều lần hằng ngày. (Ví dụ: So khớp hóa đơn sạc điện tại VinFast, route lại chuyến taxi tại Xanh SM).
2. **Tốn thời gian (Time-consuming):** Tác vụ ngốn thời gian xử lý thủ công của nhân viên. (Ví dụ: Soạn thảo phản hồi đánh giá 1-star của cư dân Vinhomes).
3. **AI có thể tốt hơn (AI-upgrade):** Dịch vụ khách hàng hiện tại còn chậm hoặc phản hồi rập khuôn. (Ví dụ: Chatbot CSKH Vinpearl hỗ trợ đặt vé vui chơi).
4. **Pain từ người khác (Stakeholder Pain):** Bottleneck khiến khách hàng hoặc nhân viên thực địa phàn nàn. (Ví dụ: Tài xế Xanh SM phàn nàn về việc hệ thống gợi ý điểm đón khách không chính xác).

> [!TIP]
> **🤖 AI Prompts — Partner brainstorm:**
> Hãy sử dụng prompt sau để brainstorm các bài toán thực tế nếu bạn chưa có ý tưởng:
> *"Tôi là AI Engineer tại Vin Smart Future (Vingroup). Tôi đang tìm kiếm các pain point vận hành cụ thể có thể tối ưu bằng AI cho mảng [Chọn một: VinFast / Xanh SM / Vinhomes / Vinmec]. Hãy gợi ý cho tôi 5 quy trình nghiệp vụ thủ công, tốn nhiều thời gian và gây rò rỉ hiệu suất kèm con số thống kê ước tính về tổn thất."*

### 📝 List bài toán của tôi:
| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 |VinFast |Voice AI & NLP |Phân loại cuộc gọi tổng đài (1900 2323 89) tự động bằng AI nhận diện giọng nói và ý định (intent), giải quyết nút thắt cổ chai khi chuyển máy. |
| 2 |VinFast |Predictive Maintenance |Phân tích dữ liệu IoT từ linh kiện xe để dự báo lỗi hỏng trước kỳ hạn, tối ưu hóa quy trình kiểm tra chất lượng và bảo hành. |
| 3 |Xanh SM |Reinforcement Learning |Tự động hóa việc điều phối và ghép nối (matching) đơn hàng/tài xế thay cho thao tác gán thủ công của đội trưởng vận hành. |
| 4 |Xanh SM |Anomaly Detection |Nhận diện hành vi gian lận chính xác bằng học máy để hệ thống đánh giá tài xế công bằng hơn, giảm thiểu thời gian giải trình. |
| 5 |Vinmec |Ambient Clinical AI |Trợ lý AI lắng nghe và tự động chuyển đổi hội thoại y khoa thành hồ sơ bệnh án, giảm tải gánh nặng giấy tờ thủ công cho bác sĩ/điều dưỡng. |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                       │
│                                                             │
│ Bài toán (1 câu):Predictive Maintenance (Bảo trì dự đoán)   │
│ Công ty thành viên: [x] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)?Khách hàng (chủ xe) & KTV xưởng dịch vụ │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Xe hỏng đột xuất ──> 2. Gọi cứu hộ kéo về xưởng ──>    │
│   3. KTV cắm máy test thủ công ──> 4. Chờ linh kiện & Sửa.  │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? 3&4 (⏱ 48-120h/lượt)      │ 
│ AI có thể nhảy vào hỗ trợ ở bước nào? Nhảy vào trước Bước 1 │
│ (Dự báo rủi ro qua luồng dữ liệu từ vi điều khiển gửi về hệ │
│ thống backend FastAPI để chủ động nhắc lịch bảo dưỡng).     │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? ______________________│
│   Giảm tỷ lệ xe nằm bãi đột xuất 30%; Rút ngắn downtime chờ │
│ sửa chữa từ 72h ──> under 4h (do linh kiện đã sẵn sàng).    │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```
```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2                                        │
│                                                             │
│ Bài toán (1 câu): Fraud & Anomaly Detection (Phát hiện gian │
│ lận) bằng Machine Learning để giảm tỷ lệ phạt oan tài xế.   │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Tài xế & Nhân viên vận hành (đối soát) │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Hệ thống rule bắt lỗi ──> 2. Phạt/Khóa app tài xế ──>  │
│   3. Tài xế khiếu nại ──> 4. NV tra cứu log GPS thủ công.   │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 4 (48h/lượt khiếu nại)│
│ AI có thể nhảy vào hỗ trợ ở bước nào? Thay thế Bước 1       │
│ (Dùng thuật toán phân cụm hành vi để phân biệt cuốc xe bất  │
│ thường do ngoại cảnh với cố ý gian lận ngay từ đầu).        │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│ Giảm tỷ lệ nhận diện sai (false positive) xuống dưới 5%;    │
│ Tiết kiệm 100% thời gian đối soát thủ công của vận hành.    │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```
```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                       │
│                                                             │
│ Bài toán (1 câu): Smart Dispatch & Matching (Điều phối thông│
│ minh) bằng RL để tự động ghép tài xế với đơn hàng tối ưu.   │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Đội trưởng vận hành & Tài xế giao hàng │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Đơn nổ lên hệ thống ──> 2. NV check bản đồ vị trí ──>  │
│   3. Check lượng pin/trạng thái xe ──> 4. Gán đơn thủ công. │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2 & 3 (⏱ 3-5 phút/đơn)│
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bao trọn Bước 2, 3, 4 │
│ (Agent AI tự động đánh giá môi trường, khoảng cách, SoC pin │
│ và ra quyết định gán đơn ngay lập tức theo thời gian thực). │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│ Rút ngắn thời gian gán đơn từ 3 phút ──> under 1 second;    │
│ Giảm 20% thời gian chờ lấy hàng, tăng năng suất tài xế.     │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---

# 🏗️ Phase 3 — DEEP-DIVE (Nhóm, 85 min)

## 3.1. Current-State Workflow Mapping (25 min)
**Vẽ quy trình hiện tại lên bảng/giấy A3.** Sử dụng các ký hiệu:
* 🔴 **Bottleneck:** Bước gây tắc nghẽn, tốn thời gian, hoặc sai sót nhiều nhất.
* 🔄 **Handoff:** Điểm chuyển giao thông tin giữa người và hệ thống, hoặc giữa các bộ phận.
* Ghi rõ thời gian vận hành trung bình: **Tổng cộng = ____ phút/lượt**.
┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│ Bước 1       │    │ Bước 2       │    │ Bước 3       │    │ Bước 4       │
│ Khách báo    │    │ Đọc hiểu &   │    │ Tra cứu chéo │    │ Gọi điện xác │
│ mất đồ       │ ──→│ bóc tách data│ ──→│ Trip_ID & SĐT│ ──→│ minh tài xế  │
│ qua Chat/Call│    │ từ nội dung  │    │ trên hệ thống│    │ đang chạy    │
│ Ai: CSKH     │    │ Ai: CSKH     │    │ Ai: CSKH     │    │ Ai: CSKH     │
│ ⏱ 2 phút     │    │ ⏱ 5 phút 🔴  │    │ ⏱ 5 phút 🔴  │    │ ⏱ 2 phút     │
│ In: Text/Call│    │ In: Nội dung │    │ In: Giờ, xe  │    │ In: SĐT      │
│ Out: Ticket  │    │ Out: Entity  │    │ Out: Info    │    │ Out: Kết quả │
└──────────────┘    └──────────────┘    └──────────────┘    └──────────────┘
                                                                   │
                                                                   ▼
                                                           ┌──────────────┐
                                                           │ Bước 5       │
                                                           │ Phản hồi kết │
                                                           │ quả cho khách│
                                                           │ Ai: CSKH     │
                                                           │ ⏱ 1 phút     │
                                                           └──────────────┘

🔴 = Bottlenecks
⏱ Tổng thời gian xử lý thủ công: 15 phút/lượt.

## 3.2. Problem Statement (6-field) & Metrics (15 min)
Điền đầy đủ 6 trường thông tin của bài toán:

| Field | Nội dung chi tiết |
|---|---|
| **1. Actor / Operator** | Nhân viên Tổng đài CSKH Tier 1 của Xanh SM. |
| **2. Current Workflow** | Khách hàng báo mất đồ qua Chat/App. CSKH đọc hiểu nội dung thô, bóc tách thông tin thủ công, mở hệ thống quản lý cuốc xe để tra cứu ID chuyến đi và SĐT tài xế, gọi xác minh và phản hồi khách (tốn ~15-20 phút/lượt). |
| **3. Bottleneck** |Bước đọc hiểu tin nhắn rườm rà/thiếu logic của khách để trích xuất thông tin (Tên đồ vật, biển số, giờ đi) và việc thao tác copy-paste tra cứu chéo thủ công giữa các phần mềm. |
| **4. Business Impact** | Thời gian xử lý (AHT) cao gây quá tải tổng đài. Bỏ lỡ "thời gian vàng" khiến tài xế đã đi xa hoặc nhận khách mới, làm giảm mạnh tỷ lệ thu hồi tài sản và giảm sự hài lòng của khách hàng.|
| **5. Success Metric** | AI phân loại đúng ý định và trích xuất chính xác 95% các trường thông tin (Entities) ra định dạng JSON dưới 3 giây cho mỗi ticket. |
| **6. Operational Boundary** | AI ĐƯỢC PHÉP: Trích xuất dữ liệu, tự động hỏi lại nếu thiếu thông tin, gọi API tra cứu chuyến đi.TUYỆT ĐỐI KHÔNG: Không cung cấp SĐT/thông tin cá nhân của tài xế cho khách. Không cam kết chắc chắn sẽ tìm thấy đồ. Các ticket báo mất đồ giá trị cao (trang sức, laptop) hoặc đòi bồi thường bắt buộc phải qua con người duyệt (HITL). |

## 3.3. Future-State Flow & AI Fit (25 min)
* **Xác định mức AI Fit (AI-Fit Matrix):** Giải pháp thuộc nhóm nào? [ ] Rule / State-Machine [ ] LLM Feature [ ] Agentic Loop.
* **Vẽ Future-State Flow:** Đánh dấu rõ:
  * 🔵 **AI Step:** Tác vụ LLM xử lý.
  * 🟢 **Human Step (HITL):** Bước con người phê duyệt/review (Human-in-the-loop).
  * ↩️ **Fallback:** Kế hoạch dự phòng khi LLM trả về kết quả lỗi hoặc không tự tin.

---┌─────────────────────────────────────────────────────────────┐
│ KHÁCH BÁO MẤT ĐỒ (Chat/App/Hotline)                         │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│ 🔵 AI STEP 1 — LLM Parse & Classify                        │
│ • Đọc tin nhắn khách                                        │
│ • Trích xuất JSON: item, time, license_plate, sentiment    │
│ • RAG tra cứu chính sách Lost & Found                       │
│ • Output: structured JSON (dưới 3s)                         │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
              ┌────────────┴────────────┐
              │                         │
    [Đủ thông tin?]            [Thiếu / Ambiguous?]
              │                         │
              ▼                         ▼
┌──────────────────────────┐  ┌──────────────────────────┐
│ 🔵 AI STEP 2 — API Query │  │ 🔵 AI STEP 2b — Ask back │
│ • Gọi CRM API tra TripID │  │ • Draft câu hỏi làm rõ   │
│ • Lấy SĐT tài xế (nội bộ)│  │ • Gửi khách (HITL nếu   │
│                          │  │   sentiment < ngưỡng)    │
└──────────┬───────────────┘  └──────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────┐
│ 🔵 AI STEP 3 — Auto Notify Driver                           │
│ • Bắn notification đến app tài xế                           │
│ • Nội dung: "[DRAFT_ONLY] Có khách báo quên <item>..."      │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
              ┌────────────┴────────────┐
              │                         │
     [Giá trị cao / VIP?]    [Đồ thông thường]
              │                         │
              ▼                         ▼
┌──────────────────────────┐  ┌──────────────────────────┐
│ 🟢 HUMAN STEP (HITL)     │  │ 🔵 AI STEP 4 — Auto reply│
│ • CSKH Tier 1 review     │  │ • Gửi khách phản hồi mẫu │
│ • Xác nhận trước khi gửi │  │ • Đóng ticket tự động    │
│ • Xử lý ngoại lệ         │  │                          │
└──────────────────────────┘  └──────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│ ↩️ FALLBACK — Khi LLM không tự tin (< 0.7 confidence)      │
│ hoặc input là teencode nặng / ngôn ngữ đe dọa               │
│ → Bypass AI, route thẳng CSKH Tier 1                        │
└─────────────────────────────────────────────────────────────┘

# 💻 Phase 4 — TECHNICAL PROMPT PROTOTYPE (Nhóm, 30 min)

Để đảm bảo kỹ sư của Vin Smart Future luôn giữ vững năng lực lập trình, nhóm của bạn sẽ tiến hành **lập trình bản mẫu prompt** trực tiếp trên **Gemini 2.5 Flash** bằng Python để stress-test hệ thống.

### Hướng dẫn thực hiện:
1. Mở file [starter-code/prompt_prototype.py](starter-code/prompt_prototype.py) bằng VS Code/Cursor.
2. Hoàn thiện các nội dung sau:
   * **System Prompt:** Viết chỉ thị cực kỳ nghiêm ngặt quy định vai trò, nhiệm vụ, định dạng output và **Operational Boundary (Ranh giới cấm)** của mô hình.
   * **Structured Output:** Định nghĩa định dạng JSON output rõ ràng.
   * **Adversarial Test Cases:** Viết ít nhất 3 prompts "tấn công" (Adversarial inputs) cố tình dụ AI vượt ranh giới hoặc đưa ra câu trả lời không được phép để kiểm tra xem ranh giới của bạn có thực sự vững chắc.
3. Chạy file python:
   ```bash
   python3 prompt_prototype.py
   ```
4. Kiểm tra xem các ranh giới an toàn có bị LLM phá vỡ hay không và ghi lại kết quả vào worksheet.

---

# 🏁 Phase 5 — EVALUATE (Nhóm, 20 min)

### AI Readiness Checklist:
[x] 1. Chúng tôi có sẵn dữ liệu mẫu/logs sạch để test?
       → Có. Hàng nghìn ticket Lost & Found lịch sử trên CRM Xanh SM,
         đã được gán nhãn (item type, trip ID, resolution status).
       → Cần thêm: gán nhãn "requires_human" cho 200 ticket mẫu để test.

[x] 2. Rủi ro khi AI sai có nằm trong tầm kiểm soát (HITL/Fallback)?
       → Có. AI CHỈ xử lý backend (text → JSON → API call).
       → AI KHÔNG trực tiếp giao tiếp với khách — mọi draft_reply đều
         có tag [DRAFT_ONLY] và phải qua CSKH review trước khi gửi.
       → Fallback: confidence < 0.7 hoặc input bất thường → route CSKH.

[x] 3. Stakeholders sẵn sàng thay đổi quy trình làm việc cũ?
       → Có. Giám đốc CSKH Xanh SM đang chịu KPI giảm AHT 30% trong Q1.
       → Tổng đài viên Tier 1 được giải phóng khỏi khâu copy-paste,
         chuyển sang xử lý case phức tạp hơn.

### Quyết định cuối cùng của Ban Giám Đốc Vin Smart Future:
[x] **GO (Bắt đầu xây dựng Prototype):** Bắt đầu phát triển với scope hẹp.
[ ] **NOT YET (Cần tích lũy thêm dữ liệu/xác lập baseline):** Trì hoãn để chuẩn bị thêm.
[ ] **NO-GO (Không khả thi / Rule-based tốt hơn):** Hủy bỏ dự án AI này.

**Justification (Lý giải quyết định dựa trên bằng chứng kỹ thuật và chi phí):**
> Bài toán trích xuất thực thể (NER) và phân loại ý định (Intent Classification) là thế mạnh cốt lõi của LLM hiện nay, với độ chính xác > 95% trên các benchmark tiếng Việt (PhoBERT, ViT5). Chúng tôi chọn scope hẹp — chỉ dùng LLM ở tầng backend (Text → JSON → API trigger), không để AI giao tiếp trực tiếp với khách. Điều này loại bỏ 100% rủi ro hallucination ảnh hưởng đến khách hàng, vì mọi output đều có tag [DRAFT_ONLY] và phải qua HITL

---

# 📝 Phase 6 — REFLECTION (Cá nhân)
*Ghi nhận phản ánh của cá nhân bạn về việc phối hợp với AI trong buổi học hôm nay vào file `03-ai-log.md`.*
