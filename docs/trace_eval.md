# 📊 BÁO CÁO THU HOẠCH NGHIỆM THU BÀI LAB 3 (BƯỚC 3 — SUBMISSION ARTIFACT)

> **Họ và Tên Học viên:** [Điền Họ và Tên]  
> **Mã Sinh Viên / Mã Học viên:** [Điền MSSV]  
> **Chủ đề Lựa chọn:** *Trợ lý Đặt Phòng họp & Thiết bị (Facilities Agent): Kiểm tra lịch phòng trống, thiết bị và tạo booking phòng họp.*

---

## 1. BẢNG CHẤM ĐIỂM AGENTIC FIT SCORING MATRIX (ĐÁNH GIÁ CHỦ ĐỀ)

| Tiêu chí Đánh giá | Mức độ (1 - 5) | Giải trình chi tiết lý do chọn điểm |
| :--- | :---: | :--- |
| **1. Multi-step Reasoning** | 4 / 5 | Agent cần phân tích yêu cầu (sức chứa, thiết bị, thời gian) -> tra cứu phòng trống -> chọn phòng thích hợp -> thực hiện tạo booking. |
| **2. Tool Interaction** | 5 / 5 | Cần tương tác liên tục với MCP Server / CSDL để tra cứu trạng thái phòng, kiểm tra thiết bị đi kèm và thực thi API đặt phòng. |
| **3. Dynamic Decision** | 5 / 5 | Quyết định bước tiếp theo phụ thuộc vào kết quả quan sát (nếu phòng yêu cầu bị trùng lịch hoặc thiếu thiết bị, Agent sẽ linh hoạt gợi ý phòng/khung giờ khác). |
| **4. Long Horizon Goal** | 4 / 5 | Agent duy trì mục tiêu hoàn tất đặt phòng họp thành công xuyên suốt chuỗi thao tác (tìm kiếm -> lựa chọn -> xác nhận -> hoàn tất đặt phòng). |
| **TỔNG ĐIỂM AGENTIC FIT** | **18 / 20** | *Nếu tổng điểm > 12/20: Bài toán rất phù hợp triển khai Agentic System.* |

---

## 2. TRÍCH XUẤT KẾT QUẢ WATERFALL TRACE LOG (SAU KHI CHẠY TEST SUITE TRÊN API THẬT)

> ⚠️ **YÊU CẦU NGHIỆM THU:** Mở tệp `.env` điền `GEMINI_API_KEY` (hoặc `OPENAI_API_KEY`) để kết nối LLM thật trước khi thực thi `python src/app.py --all`. Bài nộp chỉ dùng Mock Offline Provider sẽ không đạt điểm nghiệm thực tế.

Dán 1 đoạn trích xuất log tiêu biểu từ file `docs/trace_waterfall.json` sinh ra từ phản hồi LLM API thật:

```json
[
  {
    "step": 1,
    "query": "Đặt phòng họp P.301 và thiết bị máy chiếu cho sinh viên SV2026001 vào lúc 14:00 ngày 15/09/2026.",
    "action_type": "TOOL_EXECUTION",
    "tool_name": "schedule_appointment",
    "arguments": {
      "datetime_str": "14:00 15/09/2026",
      "student_id": "SV2026001",
      "advisor_name": "Phòng họp P.301 - Máy chiếu"
    },
    "observation": {
      "status": "SUCCESS",
      "booking_id": "BK-SV2026001-99",
      "student_id": "SV2026001",
      "datetime": "14:00 15/09/2026",
      "advisor": "Phòng họp P.301 - Máy chiếu",
      "message": "Đặt lịch thành công cho sinh viên SV2026001 với Phòng họp P.301 - Máy chiếu vào lúc 14:00 15/09/2026."
    },
    "latency_ms": 2472.95
  }
]
```

---

## 3. TỔNG KẾT KẾT QUẢ NGHIỆM THU & NỘP BÀI

- [x] Đã điền API Key thật trong `.env` và xác nhận Agent chạy mượt mà trên LLM API thật (Gemini).
- **Tổng số Test Cases đã chạy thành công:** 5 / 5 test cases.
- **Số lượt gọi Tool qua MCP Server chính xác:** 4 lượt.
- **Kết quả đẩy Repo nộp bài:** [x] Đã Commit và Push mã nguồn thành công lên GitHub cá nhân.

---

> ✅ **HOÀN TẤT NỘP BÀI:** Sao chép đường link GitHub Repository cá nhân của bạn và dán vào ô nộp bài trên hệ thống LMS VLearn để hoàn tất Bài Lab 3!
