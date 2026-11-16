# H12 OMNIBRAIN MULTI-AGENT GATEWAY — MASTER PROJECT MEMORY

> **BỘ NHỚ DỰ ÁN ĐỒ ÁN TỐT NGHIỆP — KHOA CNTT (ICTU)**
> *File này lưu trữ toàn bộ thông tin đề tài, kiến trúc hệ thống, chuẩn năng lực CLO-PI và kế hoạch thực hiện để phục vụ phát triển xuyên suốt từ đầu đến khi bảo vệ.*

---

## 📌 1. THÔNG TIN PHÁP LÝ & ĐỀ CƯƠNG ĐỒ ÁN

- **Mã định hướng Khoa**: `H12. Phát triển tác tử AI`
- **Tên đề tài chính thức**:
  > **Nghiên cứu và phát triển nền tảng Multi-Agent AI Gateway tích hợp công nghệ GraphRAG và Dynamic Tool Calling**
  *(Tên tiếng Anh: Research and Development of a Multi-Agent AI Gateway Platform Integrating GraphRAG and Dynamic Tool Calling)*
- **Quy tắc đặt tên file nộp**: `H12.[Mã_SV].[Họ_Tên].[Lớp].pdf`
- **Thời gian thực hiện**: 10 tuần

---

## 🧠 2. BẢN CHẤT CỐT LÕI (MENTAL MODEL)

OmniBrain không phải là một ứng dụng web đơn lẻ, mà là một **Nền tảng Bộ não trung tâm (AI Gateway / Multi-Agent Orchestrator)** độc lập theo kiến trúc Decoupled Microservice.
- **Vai trò**: Cung cấp "trí tuệ và tay chân" cho các hệ thống phần mềm doanh nghiệp/giáo dục qua REST API và Client SDK.
- **4 Trụ cột kỹ thuật**:
  1. **GraphRAG (NetworkX)**: Chống ảo giác (Anti-hallucination), trích xuất thực thể - mối quan hệ từ tài liệu, truy xuất đa bước (Multi-hop) kèm trích dẫn nguồn (Citations).
  2. **Dynamic Tool Calling**: Tra cứu cơ sở dữ liệu thời gian thực (Safe Read-Only SQL Engine) giúp Agent hành động thực tế.
  3. **Hybrid Routing (Local-First & Zero-Key)**: Ưu tiên xử lý trên Local Ollama (`qwen2.5:7b`, `deepseek-r1:8b`, `nomic-embed-text`) trên máy chủ nội bộ (bảo mật tuyệt đối, zero chi phí token), tự động chuyển vùng (Fallback) lên Cloud API khi cần thiết.
  4. **Tối ưu hóa độ trễ**: Fast-Path Intent Regex (<300ms), Semantic Cache DB (<50ms), VRAM Pinning (`keep_alive: -1`), SSE Streaming Typewriter.

---

## 🏗️ 3. CẤU TRÚC THƯ MỤC DỰ ÁN MỚI (`D:\H12_OmniBrain_MultiAgent_Gateway`)

```text
D:\H12_OmniBrain_MultiAgent_Gateway\
├── PROJECT_MEMORY.md            # [FILE NÀY] Bộ nhớ Master ghi nhớ toàn bộ dự án
├── README.md                    # Giới thiệu tổng quan & hướng dẫn cài đặt/chạy
├── requirements.txt             # Thư viện phụ thuộc (FastAPI, LiteLLM, NetworkX...)
├── .env.example                 # Mẫu biến môi trường cấu hình cổng, API keys
├── docs/                        # Thư mục tài liệu báo cáo & đề cương
│   ├── DE_CUONG_CHI_TIET_H12.md # Bản điền chi tiết đề cương nộp Khoa
│   └── architecture_diagram.png # Sơ đồ kiến trúc hệ thống
├── app/                         # Mã nguồn Bộ não AI Gateway (FastAPI Core)
│   ├── main.py                  # Entrypoint, CORS, Middleware & Routers
│   ├── core/                    # Config, Security (API Key), Semantic Cache
│   ├── api/v1/                  # Endpoints: /chat, /graph-rag, /agent, /quiz...
│   └── services/                # LLM Factory, GraphRAG Service, Dynamic Tooling
├── static/                      # Thư viện Universal Client SDK (omnibrain-client.js)
├── benchmark/                   # Dữ liệu & Kịch bản kiểm thử đo lường (Chương 3 & 4)
└── tests/                       # Bộ kiểm thử tự động (Unit & Integration tests)
```

---

## 📋 4. BẢNG TIẾN ĐỘ 10 TUẦN HOÀN THIỆN ĐỒ ÁN

- **Tuần 1**: Khảo sát tổng quan, hoàn thiện đề cương, viết Chương 1 (Cơ sở lý thuyết AI Agent, Gateway, GraphRAG).
- **Tuần 2**: Thiết kế kiến trúc tổng thể, mô hình dữ liệu, viết Chương 2 (Phân tích và thiết kế hệ thống).
- **Tuần 3**: Xây dựng hạ tầng Gateway (FastAPI, Semantic Cache, Fast-Path Router).
- **Tuần 4**: Xây dựng LLM Factory, tích hợp Ollama Local & Hybrid Routing (Zero-Key Tolerance).
- **Tuần 5**: Hiện thực hóa Knowledge Engine với GraphRAG (NetworkX Entity-Relationship).
- **Tuần 6**: Hiện thực hóa Dynamic Tool Calling (Safe SQL Tool tra cứu CSDL thời gian thực).
- **Tuần 7**: Xây dựng Reasoning Workflow, Quiz Agent tự sửa lỗi, hoàn thiện Universal JS SDK.
- **Tuần 8**: Tích hợp thử nghiệm với hệ thống minh chứng (Consumer App), kiểm thử toàn diện luồng nghiệp vụ.
- **Tuần 9**: Thực hiện Benchmark đo đạc (TTFT, Cache Hit, Accuracy, Token saving), viết Chương 3 & 4.
- **Tuần 10**: Đóng gói Docker, hoàn thiện quyển báo cáo tốt nghiệp, làm slide và sẵn sàng bảo vệ.
