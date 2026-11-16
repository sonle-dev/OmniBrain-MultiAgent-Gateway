# ĐỀ CƯƠNG CHI TIẾT ĐỒ ÁN TỐT NGHIỆP — HƯỚNG H12: PHÁT TRIỂN TÁC TỬ AI

> **ĐƠN VỊ**: TRƯỜNG ĐẠI HỌC CÔNG NGHỆ THÔNG TIN VÀ TRUYỀN THÔNG (ICTU) — KHOA CNTT  
> **HƯỚNG ĐỀ TÀI**: `H12. Phát triển tác tử AI`

---

### 1. THÔNG TIN SINH VIÊN NHẬN ĐỀ TÀI
- Họ và tên: *(Điền họ và tên sinh viên)*
- Mã sinh viên: *(Điền mã sinh viên)*
- Lớp: *(Điền tên lớp hành chính)*
- Điện thoại: *(Điền số điện thoại)*
- Email: *(Điền email sinh viên)*

---

### 2. THÔNG TIN VỀ GIẢNG VIÊN HƯỚNG DẪN
- Học hàm, học vị: *(Điền học hàm, học vị của GVHD)*
- Họ và tên: *(Điền họ tên GVHD)*
- Khoa: Công nghệ thông tin
- Bộ môn: *(Điền bộ môn của GVHD)*
- Điện thoại: *(Điền SĐT của GVHD)*
- Email: *(Điền email của GVHD)*

---

### 3. ĐỀ TÀI
> **Nghiên cứu và phát triển nền tảng Multi-Agent AI Gateway tích hợp công nghệ GraphRAG và Dynamic Tool Calling**

---

### 4. THỜI GIAN THỰC HIỆN
- **Thời gian**: 10 tuần *(Từ ngày 17/11/2026 đến ngày 26/01/2027 hoặc theo kế hoạch của Khoa)*

---

### 5. MỤC TIÊU
1. **Mục tiêu nghiên cứu**:
   - Nghiên cứu cơ chế vận hành của Tác tử AI (AI Agent), mô hình suy luận ReAct (Reasoning and Acting) và kỹ thuật gọi công cụ (Dynamic Tool Calling / Function Calling).
   - Nghiên cứu kỹ thuật GraphRAG (Knowledge Graph RAG kết hợp NetworkX) nhằm giải quyết triệt để vấn đề ảo giác thông tin (anti-hallucination) và hỗ trợ suy luận đa bước (multi-hop reasoning).
   - Nghiên cứu cơ chế điều phối mô hình lai (Hybrid Local / Cloud Routing) tối ưu chi phí và đảm bảo độ sẵn sàng cao (Zero-Key Tolerance).
2. **Mục tiêu ứng dụng**:
   - Xây dựng thành công nền tảng AI Gateway độc lập (OmniBrain Core) bằng FastAPI, cho phép mọi ứng dụng phần mềm (Web, LMS, ERP) dễ dàng tích hợp năng lực AI thông qua RESTful API và Universal Client SDK.
   - Hiện thực hóa thành công các tác tử chuyên biệt: Tác tử tra cứu dữ liệu thời gian thực (Database Tool Calling), Tác tử suy luận tài liệu (GraphRAG), Tác tử giao tiếp tự nhiên và Tác tử sinh đề thi tự sửa lỗi (Self-Correction Quiz Engine).
   - Triển khai thực nghiệm tích hợp bộ não AI vào hệ thống minh chứng, đánh giá hiệu năng về độ trễ (TTFT), tỷ lệ trúng bộ nhớ đệm (Semantic Cache) và độ chính xác của phản hồi.

---

### 6. YÊU CẦU VỀ CHUẨN NĂNG LỰC (BỘ CLO + PI CỦA HƯỚNG H12)
*(Giữ nguyên 100% cố định theo quy định của Khoa)*

---

### 7. YÊU CẦU VỀ SẢN PHẨM

#### a. Mô tả tóm tắt yêu cầu về sản phẩm
Hệ thống **OmniBrain AI Platform Core** là một nền tảng AI Gateway đa tác tử (Multi-Agent Gateway) độc lập theo kiến trúc Microservice Decoupled. Sản phẩm bao gồm:
1. **Dịch vụ Gateway trung tâm (Backend FastAPI)**: Cung cấp bộ API chuẩn hóa quản lý xác thực (`X-API-Key`), kiểm soát lưu lượng (Rate Limiter), bộ nhớ đệm ngữ nghĩa (Semantic Cache), bộ định tuyến tác vụ thông minh (Intelligent Specialist Dispatcher) và cơ chế chuyển vùng mô hình tự động (Local Ollama ➔ Cloud Fallback).
2. **Hệ thống Tri thức & Tác tử (Knowledge & Agent Engine)**: Mô-đun GraphRAG trích xuất thực thể - mối quan hệ bằng NetworkX kèm trích dẫn nguồn (Citations); Bộ công cụ Dynamic Tool Calling truy vấn cơ sở dữ liệu thời gian thực có kiểm soát bảo mật.
3. **Thư viện tích hợp & Giao diện minh chứng**: Universal JavaScript Client SDK (`omnibrain-client.js`) hỗ trợ hiển thị dòng chữ thời gian thực (SSE Streaming Typewriter) và giao diện minh chứng đóng vai trò môi trường thử nghiệm năng lực của bộ não.

#### b. Yêu cầu chi tiết theo từng mã PI
- **PI 1.1 (Xác định bài toán phù hợp AI Agent)**: Phân tích hạn chế của Chatbot/RAG phẳng truyền thống; xác định bài toán xây dựng nền tảng Gateway điều phối đa tác tử giải quyết triệt để vấn đề ảo giác và truy xuất dữ liệu động.
- **PI 1.2 (Phân tích workflow nghiệp vụ)**: Xây dựng sơ đồ phân luồng: User Input ➔ Gateway ➔ Fast-Path Router (<300ms) ➔ Task Dispatcher ➔ Tool/GraphRAG Execution ➔ LLM Response ➔ SSE Streaming.
- **PI 1.3 (Xác định vai trò agent và nhiệm vụ)**: Xây dựng 4 tác tử cốt lõi: Chat Agent, Reasoning & Quiz Agent (tự sửa lỗi), GraphRAG Agent (trích dẫn nguồn), Database Action Agent (đọc CSDL an toàn).
- **PI 2.1 (Thiết kế kiến trúc AI Agent)**: Thiết kế kiến trúc 5 tầng Decoupled: SDK Layer ➔ Gateway Layer ➔ Routing Layer ➔ Execution Layer ➔ Hybrid Model Infrastructure.
- **PI 2.2 (Thiết kế kết nối API)**: Thiết kế tối thiểu 3 công cụ (Tools): Tra cứu thông tin CSDL, tra cứu tiến độ/hồ sơ, và công cụ tìm kiếm dữ liệu ngoài.
- **PI 2.3 (Thiết kế memory / knowledge)**: Tích hợp Semantic Cache (bộ nhớ đệm ngữ nghĩa giảm độ trễ và tiết kiệm token); xây dựng Knowledge Base đồ thị tri thức (GraphRAG) bằng NetworkX hỗ trợ phân vùng Multi-Tenant.
- **PI 3.1 (Xây dựng agent bằng framework)**: Phát triển khung điều phối tác tử tùy biến bằng FastAPI kết hợp LiteLLM tối ưu tài nguyên.
- **PI 3.2 (Tích hợp LLM)**: Thiết lập kiến trúc Hybrid Models ưu tiên Local Ollama (`qwen2.5:7b`, `deepseek-r1:8b`, `nomic-embed-text`) làm lõi Zero-Key bảo mật; Cloud API làm dự phòng; tự động tiêm mốc thời gian thực vào System Prompt.
- **PI 3.3 (Tích hợp tools)**: Lập trình Dynamic Tool Calling với bộ lọc an toàn Read-Only SQL, ngăn chặn triệt để SQL Injection hoặc phá hoại dữ liệu.
- **PI 3.4 (Xây dựng reasoning workflow)**: Triển khai quy trình ReAct: Tiếp nhận ➔ Phân tích ý định ➔ Chọn Tool ➔ Thực thi ➔ Tổng hợp câu trả lời; kèm vòng lặp tự sửa lỗi khi sinh cấu trúc JSON.
- **PI 4.1 (Đánh giá hiệu quả agent)**: Xây dựng bộ test tối thiểu 20-30 kịch bản; đo đạc chỉ số định lượng: TTFT, Cache Hit Rate, độ chính xác của trích dẫn (Citations), và so sánh hiệu quả chi phí.
- **PI 4.2 (Triển khai hệ thống)**: Đóng gói Docker / Docker Compose, tài liệu tương tác tự động Swagger UI (`/docs`), Client SDK JavaScript, và bộ tài liệu hướng dẫn cài đặt/vận hành chi tiết.

---

### 8. YÊU CẦU VỀ QUYỂN BÁO CÁO
*(Cố định 4 chương theo quy định của Khoa)*
- Chương 1: Cơ sở lý thuyết và công nghệ AI Agent
- Chương 2: Phân tích bài toán và thiết kế hệ thống AI Agent
- Chương 3: Xây dựng hệ thống AI Agent
- Chương 4: Đánh giá và triển khai hệ thống

---

### 9. TIẾN ĐỘ THỰC HIỆN (KẾ HOẠCH 10 TUẦN)

| STT | Thời gian | Công việc | Kết quả dự kiến |
| :---: | :---: | :--- | :--- |
| 1 | **Tuần 1** | Khảo sát tổng quan, nghiên cứu lý thuyết về AI Agent, Multi-Agent Gateway, ReAct Pattern, GraphRAG và Semantic Cache. | Báo cáo cơ sở lý thuyết (Chương 1); Tài liệu phân tích bài toán và yêu cầu hệ thống. |
| 2 | **Tuần 2** | Thiết kế kiến trúc tổng thể của OmniBrain AI Platform Core: Phân tầng Gateway, các thành phần định tuyến, cấu trúc dữ liệu và API Contract. | Sơ đồ kiến trúc tổng thể, Sơ đồ tuần tự các luồng xử lý (Chương 2). |
| 3 | **Tuần 3** | Xây dựng hạ tầng Gateway bằng FastAPI: Xử lý middleware CORS, xác thực API Key, Semantic Cache Engine và Fast-Path Intent Router. | Mã nguồn lõi Gateway chạy ổn định, kiểm thử phản hồi Fast-Path đạt < 300ms. |
| 4 | **Tuần 4** | Xây dựng mô-đun LLM Factory và cơ chế Hybrid Routing: Tích hợp Local Ollama, VRAM Pinning và cơ chế Graceful Cloud Fallback (Zero-Key Tolerance). | Hoàn thiện bộ điều phối LLM, hệ thống chạy trơn tru cả khi không có internet hoặc API key bên ngoài. |
| 5 | **Tuần 5** | Xây dựng Knowledge Engine với GraphRAG: Xử lý tài liệu, trích xuất Entity-Relationship Graph bằng NetworkX, hỗ trợ phân vùng Multi-Tenant. | Module GraphRAG hoàn thiện, trích xuất và truy xuất đồ thị tri thức kèm trích dẫn nguồn (Citations). |
| 6 | **Tuần 6** | Hiện thực hóa cơ chế Dynamic Tool Calling: Xây dựng Safe Read-Only Database Tool cho phép Agent tự động truy vấn dữ liệu thực tế từ cơ sở dữ liệu. | Module Tool Calling hoạt động chính xác, Agent tự chuyển đổi ngôn ngữ tự nhiên thành câu truy vấn SQL an toàn. |
| 7 | **Tuần 7** | Xây dựng Reasoning Workflow và Tác tử sinh đề thi (Quiz Agent) có vòng lặp tự sửa lỗi (Self-Correction Loop). Hoàn thiện Universal JS Client SDK. | API Quiz sinh JSON chuẩn 100%; File `omnibrain-client.js` hỗ trợ SSE Streaming Typewriter hoàn chỉnh. |
| 8 | **Tuần 8** | Tích hợp thử nghiệm nền tảng OmniBrain vào ứng dụng minh chứng; Kiểm thử tích hợp toàn diện các luồng nghiệp vụ. | Hoàn thiện hệ thống demo hoạt động trực quan giữa ứng dụng Client và Bộ não trung tâm OmniBrain. |
| 9 | **Tuần 9** | Thực hiện đo lường đánh giá hiệu năng (Benchmark): Đo thời gian đáp ứng (TTFT), tỷ lệ trúng Cache, so sánh độ chính xác của GraphRAG và hiệu quả chi phí. | Bảng số liệu thực nghiệm, biểu đồ đánh giá hoàn chỉnh cho Chương 3 & Chương 4 của báo cáo. |
| 10 | **Tuần 10** | Đóng gói sản phẩm (Docker), rà soát toàn bộ tài liệu hướng dẫn cài đặt/sử dụng, hoàn thiện bản in quyển đồ án tốt nghiệp và slide báo cáo. | Quyển báo cáo đồ án tốt nghiệp hoàn chỉnh theo quy chuẩn; Bộ mã nguồn và sản phẩm demo sẵn sàng bảo vệ trước Hội đồng. |
