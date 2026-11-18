# ĐỀ CƯƠNG ĐỒ ÁN / KHÓA LUẬN TỐT NGHIỆP — HƯỚNG H12: PHÁT TRIỂN TÁC TỬ AI

> **ĐƠN VỊ**: TRƯỜNG ĐẠI HỌC CÔNG NGHỆ THÔNG TIN VÀ TRUYỀN THÔNG (ICTU) — KHOA CNTT  
> **HƯỚNG ĐỀ TÀI**: `H12. Phát triển tác tử AI`

---

### 1. THÔNG TIN SINH VIÊN NHẬN ĐỀ TÀI
- **Họ và tên**: Lê Hồng Sơn
- **Mã sinh viên**: DTC235200647
- **Lớp**: CNTT K22B
- **Điện thoại**: 0348063722
- **Email**: dtc235200647@ictu.edu.vn

---

### 2. THÔNG TIN VỀ GIẢNG VIÊN HƯỚNG DẪN
- **Họ và tên**: Lê Thu Trang
- **Học hàm, học vị**: Thạc sĩ
- **Khoa**: Công nghệ thông tin
- **Bộ môn**: Hệ thống thông tin
- **Điện thoại**: 0983754948
- **Email**: lttrang@ictu.edu.vn

---

### 3. ĐỀ TÀI
> **Xây dựng nền tảng tác tử AI hỗ trợ hỏi đáp học liệu và sinh đề thi tích hợp GraphRAG cho hệ thống quản lý học tập (LMS)**

---

### 4. THỜI GIAN THỰC HIỆN
- **Thời gian**: 10 tuần, từ ngày **12/11/2026** đến ngày **21/01/2027**

---

### 5. MỤC TIÊU
1. **Mục tiêu nghiên cứu**:
   - Nghiên cứu cơ chế vận hành của Tác tử AI (AI Agent), mô hình suy luận ReAct (Reasoning and Acting) và kỹ thuật gọi công cụ (Dynamic Tool Calling / Function Calling).
   - Nghiên cứu kỹ thuật GraphRAG (Knowledge Graph RAG kết hợp NetworkX) nhằm giải quyết triệt để vấn đề ảo giác thông tin (anti-hallucination) và hỗ trợ suy luận đa bước (multi-hop reasoning).
   - Nghiên cứu cơ chế điều phối mô hình lai (Hybrid Local / Cloud Routing) tối ưu chi phí và đảm bảo độ sẵn sàng cao (Zero-Key Tolerance).
2. **Mục tiêu ứng dụng**:
   - Xây dựng thành công nền tảng AI Gateway độc lập (OmniBrain Core) bằng FastAPI, cho phép hệ thống quản lý học tập (LMS) dễ dàng tích hợp năng lực AI thông qua RESTful API và Universal Client SDK.
   - Hiện thực hóa thành công các tác tử chuyên biệt: Tác tử tra cứu dữ liệu thời gian thực (Database Tool Calling), Tác tử suy luận tài liệu (GraphRAG), Tác tử giao tiếp tự nhiên và Tác tử sinh đề thi tự sửa lỗi (Self-Correction Quiz Engine).
   - Triển khai thực nghiệm tích hợp bộ não AI vào hệ thống, đánh giá hiệu năng về độ trễ (TTFT), tỷ lệ trúng bộ nhớ đệm (Semantic Cache) và độ chính xác của phản hồi.

---

### 6. YÊU CẦU VỀ CHUẨN NĂNG LỰC
*(Giữ nguyên 100% cố định theo quy định của Khoa)*

| Mã CLO | Nội dung CLO | % CLO | Mã PI | Nội dung PI | % PI |
| :---: | :--- | :---: | :---: | :--- | :---: |
| **1** | Phân tích được bài toán và xác định yêu cầu cho hệ thống AI Agent | 20 | **1.1** | Xác định được bài toán phù hợp với AI Agent | 5 |
| | | | **1.2** | Phân tích workflow nghiệp vụ | 5 |
| | | | **1.3** | Xác định vai trò agent và nhiệm vụ | 10 |
| **2** | Thiết kế được kiến trúc và các thành phần của AI Agent | 30 | **2.1** | Thiết kế kiến trúc AI Agent | 15 |
| | | | **2.2** | Thiết kế tool và API | 10 |
| | | | **2.3** | Thiết kế memory / knowledge | 5 |
| **3** | Triển khai được hệ thống AI Agent tích hợp LLM và các công cụ | 40 | **3.1** | Xây dựng agent bằng framework | 5 |
| | | | **3.2** | Tích hợp LLM | 5 |
| | | | **3.3** | Tích hợp tools | 20 |
| | | | **3.4** | Xây dựng reasoning workflow | 10 |
| **4** | Đánh giá, kiểm thử và triển khai được hệ thống AI Agent | 10 | **4.1** | Đánh giá hiệu quả agent | 5 |
| | | | **4.2** | Triển khai hệ thống | 5 |

---

### 7. YÊU CẦU VỀ SẢN PHẨM

#### a. Mô tả tóm tắt yêu cầu về sản phẩm
Hệ thống **OmniBrain AI Platform Core** là một nền tảng AI Gateway đa tác tử (Multi-Agent Gateway) độc lập theo kiến trúc Microservice Decoupled. Sản phẩm bao gồm:
1. **Dịch vụ Gateway trung tâm (Backend FastAPI)**: Cung cấp bộ API chuẩn hóa quản lý xác thực (`X-API-Key`), kiểm soát lưu lượng (Rate Limiter), bộ nhớ đệm ngữ nghĩa (Semantic Cache), bộ định tuyến tác vụ thông minh (Intelligent Specialist Dispatcher) và cơ chế chuyển vùng mô hình tự động (Local Ollama ➔ Cloud Fallback).
2. **Hệ thống Tri thức & Tác tử (Knowledge & Agent Engine)**: Mô-đun GraphRAG trích xuất thực thể - mối quan hệ bằng NetworkX kèm trích dẫn nguồn (Citations); Bộ công cụ Dynamic Tool Calling truy vấn cơ sở dữ liệu thời gian thực có kiểm soát bảo mật.
3. **Thư viện tích hợp & Giao diện minh chứng**: Universal JavaScript Client SDK (`omnibrain-client.js`) hỗ trợ hiển thị dòng chữ thời gian thực (SSE Streaming Typewriter) và giao diện Cổng thông tin đào tạo (LMS Portal) đóng vai trò môi trường thử nghiệm minh chứng năng lực của bộ não.

#### b. Yêu cầu chi tiết

| PI | Yêu cầu tối thiểu |
| :---: | :--- |
| **1.1** | - Mô tả bài toán xây dựng nền tảng AI Gateway đa tác tử tập trung, độc lập (Decoupled Microservice) phục vụ tích hợp trí tuệ nhân tạo vào các hệ thống phần mềm nghiệp vụ.<br>- Phân tích các loại yêu cầu thường gặp: hỏi đáp tri thức tài liệu nội bộ, tra cứu dữ liệu thời gian thực từ cơ sở dữ liệu, suy luận logic và sinh đề thi.<br>- Phân tích hạn chế của Chatbot rule-based và RAG vector phẳng truyền thống: dễ bị ảo giác (hallucination), thiếu khả năng liên kết thực thể đa tầng, phụ thuộc cứng vào API thương mại và tiềm ẩn nguy cơ rò rỉ dữ liệu.<br>- Giải thích tính cấp thiết của việc xây dựng nền tảng Multi-Agent Gateway tích hợp GraphRAG và cơ chế định tuyến lai (Hybrid Local / Cloud Routing). |
| **1.2** | - Xây dựng sơ đồ workflow tổng thể: Client App / User Input ➔ API Gateway (Xác thực & Semantic Cache) ➔ Fast-Path Router (Lọc ý định đơn giản <300ms) ➔ Intelligent Task Dispatcher ➔ Kích hoạt Dynamic Tool tra cứu hoặc GraphRAG Engine ➔ LLM tổng hợp ngữ cảnh ➔ Trả kết quả về Client dạng SSE Streaming (Server-Sent Events). |
| **1.3** | - Agent có thể:<br>+ **Chat Agent**: Giao tiếp tiếng Việt tự nhiên, giải đáp thắc mắc tổng quan.<br>+ **Reasoning & Quiz Agent**: Suy luận logic, sinh đề thi dạng JSON chuẩn có vòng lặp tự sửa lỗi.<br>+ **GraphRAG Agent**: Tra cứu tri thức đồ thị thực thể từ tài liệu và đính kèm trích dẫn nguồn (Citations).<br>+ **Database Action Agent**: Tự động chuyển đổi câu hỏi tự nhiên thành truy vấn dữ liệu thời gian thực an toàn từ cơ sở dữ liệu. |
| **2.1** | - Thiết kế kiến trúc hệ thống phân tầng Decoupled: `Client App / SDK Layer` ➔ `FastAPI Gateway Layer (Security, Rate Limit, Semantic Cache)` ➔ `Routing & Orchestration Layer` ➔ `Execution Layer (Dynamic Tools & GraphRAG Engine)` ➔ `Hybrid LLM Infrastructure (Local Ollama / Cloud Fallback)`.<br>- Vẽ sơ đồ khối kiến trúc hệ thống và sơ đồ tuần tự (Sequence Diagram) xử lý yêu cầu.<br>- Mô tả chi tiết vai trò của từng thành phần trong hệ thống. |
| **2.2** | - Thiết kế tối thiểu 3 tools thực thi:<br>1. **Safe Read-Only SQL Tool**: Tra cứu dữ liệu thời gian thực từ cơ sở dữ liệu LMS (lịch thi, tiến độ học tập, thông tin môn học).<br>2. **GraphRAG Retrieval Tool**: Truy xuất thực thể và mối quan hệ tri thức từ tài liệu học liệu/giáo trình bằng NetworkX kèm trích dẫn.<br>3. **External Search Tool**: Kết nối công cụ tìm kiếm bên ngoài khi dữ liệu nội bộ chưa đáp ứng. |
| **2.3** | - Thiết kế Memory & Knowledge Base:<br>+ Xây dựng cơ chế **Semantic Cache** (bộ nhớ đệm ngữ nghĩa) lưu trữ vector câu hỏi trên SQLite/Redis nhằm giảm độ trễ phản hồi (<50ms) và triệt tiêu chi phí token đối với các câu hỏi lặp lại.<br>+ Xây dựng Knowledge Base đồ thị tri thức (**GraphRAG**): Nạp tài liệu (PDF, PPTX, TXT), sử dụng NetworkX bóc tách mạng lưới Entity-Relationship theo cơ chế phân vùng đa đối tượng (Multi-tenant Namespaces). |
| **3.1** | - Sử dụng framework **FastAPI** xây dựng hệ thống Gateway độc lập hiệu năng cao, kết hợp thư viện điều phối mô hình **LiteLLM**, quản lý kết nối bất đồng bộ (Persistent Async Connection Pooling) và cơ chế ghim mô hình trên bộ nhớ GPU (Ollama VRAM Pinning với `keep_alive: -1`). |
| **3.2** | - Thiết kế Prompt Engineering:<br>+ **System Prompt động**: Tự động tiêm thông tin mốc thời gian thực tế (`Asia/Ho_Chi_Minh`, GMT+7) vào ngữ cảnh nhằm khắc phục triệt để lỗi ảo giác mốc thời gian.<br>+ **Prompt Template chuyên biệt**: Tối ưu hóa cấu trúc chỉ dẫn riêng cho từng tác vụ (Chat, Suy luận ReAct, GraphRAG, Function Calling). |
| **3.3** | - Tích hợp và lập trình Tools:<br>+ Lập trình mô-đun **Dynamic Tool Calling** cho phép tác tử tự nhận diện ý định và kích hoạt hàm tương ứng.<br>+ Triển khai cơ chế kiểm soát an toàn: Chỉ cho phép các lệnh SQL dạng đọc (Read-Only SELECT), kiểm duyệt tham số đầu vào nhằm ngăn chặn triệt để lỗ hổng SQL Injection và bảo vệ an toàn dữ liệu hệ thống. |
| **3.4** | - Xây dựng quy trình suy luận ReAct (Reasoning and Acting): User input ➔ Semantic analysis & Intent classification ➔ Tool selection ➔ Tool execution ➔ Context synthesis ➔ Response generation kèm trích dẫn (Citations).<br>- Tích hợp vòng lặp tự sửa lỗi (Self-Correction Loop) khi sinh dữ liệu có cấu trúc (JSON Schema Validation). |
| **4.1** | - Xây dựng bộ test đánh giá với tối thiểu 30 kịch bản kiểm thử bao phủ toàn bộ các nhóm tác vụ (chào hỏi nhanh, tra cứu tri thức đồ thị, truy vấn dữ liệu động, suy luận logic).<br>- Đo lường và báo cáo các chỉ số định lượng: Thời gian phản hồi token đầu tiên (TTFT), tỷ lệ trúng Semantic Cache, độ trễ giữa Local Ollama và Cloud API, độ chính xác của trích dẫn nguồn (Faithfulness & Citation Accuracy). |
| **4.2** | - Đóng gói dịch vụ Backend bằng **Docker / Docker Compose**.<br>- Triển khai dịch vụ API Gateway chuẩn RESTful kèm giao diện tài liệu tương tác Swagger UI (`/docs`).<br>- Phát triển thư viện tích hợp Universal JavaScript Client SDK (`omnibrain-client.js`) hỗ trợ hiệu ứng hiển thị thời gian thực (SSE Streaming Typewriter).<br>- Triển khai giao diện minh chứng (PoC) và cung cấp bộ tài liệu hướng dẫn cài đặt, cấu hình mô hình và tài liệu hướng dẫn sử dụng API. |

---

### 8. YÊU CẦU VỀ QUYỂN BÁO CÁO
*(Cố định 4 chương theo quy định của Khoa)*
- **Chương 1**: Cơ sở lý thuyết và công nghệ AI Agent
- **Chương 2**: Phân tích bài toán và thiết kế hệ thống AI Agent
- **Chương 3**: Xây dựng hệ thống AI Agent
- **Chương 4**: Đánh giá và triển khai hệ thống

---

### 9. TIẾN ĐỘ THỰC HIỆN (KẾ HOẠCH 10 TUẦN)

| STT | Thời gian | Công việc | Kết quả dự kiến |
| :---: | :---: | :--- | :--- |
| 1 | **Tuần 1** | Khảo sát tổng quan, nghiên cứu lý thuyết về AI Agent, Multi-Agent Gateway, ReAct Pattern, GraphRAG và Semantic Cache. | Báo cáo cơ sở lý thuyết; Tài liệu phân tích bài toán và yêu cầu hệ thống. |
| 2 | **Tuần 2** | Thiết kế kiến trúc tổng thể của OmniBrain AI Platform Core: Phân tầng Gateway, các thành phần định tuyến, cấu trúc dữ liệu và API Contract. | Sơ đồ kiến trúc tổng thể, Sơ đồ tuần tự các luồng xử lý. |
| 3 | **Tuần 3** | Xây dựng hạ tầng Gateway bằng FastAPI: Xử lý middleware CORS, xác thực API Key, Semantic Cache Engine và Fast-Path Intent Router. | Mã nguồn lõi Gateway chạy ổn định, kiểm thử phản hồi Fast-Path đạt < 300ms. |
| 4 | **Tuần 4** | Xây dựng mô-đun LLM Factory và cơ chế Hybrid Routing: Tích hợp Local Ollama, VRAM Pinning và cơ chế Graceful Cloud Fallback (Zero-Key Tolerance). | Hoàn thiện bộ điều phối LLM, hệ thống chạy trơn tru cả khi không có internet hoặc API key bên ngoài. |
| 5 | **Tuần 5** | Xây dựng Knowledge Engine với GraphRAG: Xử lý tài liệu, trích xuất Entity-Relationship Graph bằng NetworkX, hỗ trợ phân vùng Multi-Tenant. | Module GraphRAG hoàn thiện, trích xuất và truy xuất đồ thị tri thức kèm trích dẫn nguồn (Citations). |
| 6 | **Tuần 6** | Hiện thực hóa cơ chế Dynamic Tool Calling: Xây dựng Safe Read-Only Database Tool cho phép Agent tự động truy vấn dữ liệu thực tế từ cơ sở dữ liệu. | Module Tool Calling hoạt động chính xác, Agent tự chuyển đổi ngôn ngữ tự nhiên thành câu truy vấn SQL an toàn. |
| 7 | **Tuần 7** | Xây dựng Reasoning Workflow và Tác tử sinh đề thi (Quiz Agent) có vòng lặp tự sửa lỗi (Self-Correction Loop). Hoàn thiện Universal JS Client SDK. | API Quiz sinh JSON chuẩn 100%; File omnibrain-client.js hỗ trợ SSE Streaming Typewriter hoàn chỉnh. |
| 8 | **Tuần 8** | Tích hợp thử nghiệm nền tảng OmniBrain vào ứng dụng minh chứng (Cổng thông tin LMS); Kiểm thử tích hợp toàn diện các luồng nghiệp vụ. | Hoàn thiện hệ thống demo hoạt động trực quan giữa ứng dụng Client và Bộ não trung tâm OmniBrain. |
| 9 | **Tuần 9** | Thực hiện đo lường đánh giá hiệu năng (Benchmark): Đo thời gian đáp ứng (TTFT), tỷ lệ trúng Cache, so sánh độ chính xác của GraphRAG và hiệu quả chi phí. | Bảng số liệu thực nghiệm, biểu đồ đánh giá hoàn chỉnh cho báo cáo. |
| 10 | **Tuần 10** | Đóng gói sản phẩm (Docker), rà soát toàn bộ tài liệu hướng dẫn cài đặt/sử dụng, hoàn thiện bản in quyển đồ án tốt nghiệp và slide báo cáo. | Quyển báo cáo đồ án tốt nghiệp hoàn chỉnh theo quy chuẩn; Bộ mã nguồn và sản phẩm demo. |
