# OmniBrain AI Platform Core — Multi-Agent AI Gateway

> **ĐỒ ÁN TỐT NGHIỆP ĐẠI HỌC — HƯỚNG H12: PHÁT TRIỂN TÁC TỬ AI (ICTU)**  
> **Đề tài**: *Nghiên cứu và phát triển nền tảng Multi-Agent AI Gateway tích hợp công nghệ GraphRAG và Dynamic Tool Calling*

---

## 🎯 1. Giới thiệu tổng quan
**OmniBrain AI Platform Core** là một nền tảng AI Gateway đa tác tử độc lập (Decoupled Microservice) đóng vai trò bộ não điều phối trung tâm. Hệ thống cho phép các ứng dụng phần mềm (Web, LMS, ERP, CRM) tích hợp năng lực AI chuyên sâu mà không bị phụ thuộc cứng vào bất kỳ nhà cung cấp mô hình thương mại nào.

### Các năng lực cốt lõi:
1. **GraphRAG (Knowledge Graph Engine)**: Chống ảo giác bằng mạng lưới thực thể - quan hệ NetworkX, hỗ trợ suy luận đa bước kèm trích dẫn nguồn (Citations).
2. **Dynamic Tool Calling**: Cung cấp công cụ SQL an toàn (Safe Read-Only) để Agent tự động truy vấn dữ liệu thời gian thực.
3. **Hybrid Routing & Zero-Key Tolerance**: Mặc định chạy 100% bằng Local Ollama (`qwen2.5:7b`, `deepseek-r1:8b`, `nomic-embed-text`) trên máy chủ riêng; tự động chuyển vùng (Fallback) lên Cloud API khi quá tải hoặc cần suy luận nặng.
4. **Tối ưu hóa độ trễ**: Fast-Path Intent Classifier (<300ms), Semantic Cache DB (<50ms), VRAM Pinning (`keep_alive: -1`), SSE Streaming Typewriter.

---

## 📁 2. Cấu trúc thư mục đồ án

```text
D:\H12_OmniBrain_MultiAgent_Gateway\
├── PROJECT_MEMORY.md             # Bộ nhớ ngữ cảnh Master của toàn bộ đồ án
├── README.md                     # Tài liệu tổng quan & hướng dẫn vận hành
├── docs/                         # Tài liệu đề cương chi tiết & bản thiết kế
│   └── DE_CUONG_CHI_TIET_H12.md  # Đề cương chi tiết nộp Khoa CNTT
├── app/                          # Mã nguồn Bộ não AI Gateway (FastAPI)
│   ├── main.py                   # API Entrypoint, CORS & Routers
│   ├── core/                     # Cấu hình, bảo mật, semantic cache
│   ├── api/v1/                   # Các endpoints điều phối
│   └── services/                 # LLM Factory, GraphRAG, Tool Engine
├── static/                       # Universal Client SDK (omnibrain-client.js)
├── benchmark/                    # Dữ liệu & Kịch bản đo lường hiệu năng
└── tests/                        # Bộ kiểm thử tự động
```

---

## 🚀 3. Hướng dẫn cài đặt và khởi chạy

### Bước 1: Cài đặt môi trường Python (Khuyến nghị Python 3.10+)
```bash
pip install fastapi uvicorn litellm networkx sqlalchemy httpx pydantic
```

### Bước 2: Khởi chạy Bộ não trung tâm
```bash
uvicorn app.main:app --host 127.0.0.1 --port 8000 --reload
```

### Bước 3: Kiểm tra tài liệu tương tác Swagger API
Truy cập: `http://127.0.0.1:8000/docs`
