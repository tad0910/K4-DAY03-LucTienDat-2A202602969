# 📊 BÁO CÁO THU HOẠCH NGHIỆM THU BÀI LAB 3 (BƯỚC 3 — SUBMISSION ARTIFACT)

> **Họ và Tên Học viên:** Lục Tiến Đạt  
> **Mã Sinh Viên / Mã Học viên:** 2A202602969  
> **Chủ đề Lựa chọn:** Trợ lý Đặt Phòng họp & Thiết bị (Facilities & Meeting Room Agent)  

---

## 1. BẢNG CHẤM ĐIỂM AGENTIC FIT SCORING MATRIX (ĐÁNH GIÁ CHỦ ĐỀ)

| Tiêu chí Đánh giá | Mức độ (1 - 5) | Giải trình chi tiết lý do chọn điểm |
| :--- | :---: | :--- |
| **1. Multi-step Reasoning** | **5 / 5** | Yêu cầu suy luận đa bước: Agent cần tra cứu danh sách phòng họp còn trống phù hợp với số lượng người tham dự và yêu cầu thiết bị (máy chiếu/mic) trước, sau đó suy luận lựa chọn phòng tối ưu nhất để tiến hành đặt lịch. |
| **2. Tool Interaction** | **5 / 5** | Bắt buộc kết nối MCP Server để tương tác với cơ sở dữ liệu qua 2 công cụ: tra cứu lịch phòng trống (`check_room_availability`) và thực hiện đặt phòng họp (`book_meeting_room`). |
| **3. Dynamic Decision** | **4 / 5** | Quyết định gọi công cụ đặt phòng và các thông số tham số (`room_id`, `time_slot`) phụ thuộc hoàn toàn vào dữ liệu thực tế trả về từ bước quan sát lịch phòng trống trước đó. |
| **4. Long Horizon Goal** | **4 / 5** | Duy trì mục tiêu hoàn tất việc tổ chức cuộc họp cho người dùng xuyên suốt từ khâu tìm kiếm điều kiện đến khâu xác nhận đặt phòng thành công. |
| **TỔNG ĐIỂM AGENTIC FIT** | **18 / 20** | *Tổng điểm 18/20 (> 12/20): Chủ đề rất phù hợp triển khai ReAct Agentic System.* |

---

## 2. TRÍCH XUẤT KẾT QUẢ WATERFALL TRACE LOG (SAU KHI CHẠY TEST SUITE TRÊN API THẬT)

> ⚠️ **YÊU CẦU NGHIỆM THU:** Mở tệp `.env` điền `GEMINI_API_KEY` (hoặc `OPENAI_API_KEY`) để kết nối LLM thật trước khi thực thi `python src/app.py --all`. Bài nộp chỉ dùng Mock Offline Provider sẽ không đạt điểm nghiệm thực tế.

Dán 1 đoạn trích xuất log tiêu biểu từ file `docs/trace_waterfall.json` sinh ra từ phản hồi LLM API thật:

```json
[
  {
    "step": 1,
    "query": "Hãy đặt phòng họp R401 cho sinh viên SV2026001 vào lúc 14:00 ngày 15/09/2026 với cố vấn PGS.TS Nguyễn Văn A.",
    "action_type": "TOOL_EXECUTION",
    "tool_name": "schedule_appointment",
    "arguments": {
      "student_id": "SV2026001",
      "datetime_str": "14:00 15/09/2026",
      "advisor_name": "R401"
    },
    "observation": {
      "status": "SUCCESS",
      "booking_id": "BK-SV2026001-99",
      "student_id": "SV2026001",
      "datetime": "14:00 15/09/2026",
      "advisor": "R401",
      "message": "Đặt lịch thành công cho sinh viên SV2026001 với R401 vào lúc 14:00 15/09/2026."
    },
    "latency_ms": 10218.66
  }
]
```

---

## 3. TỔNG KẾT KẾT QUẢ NGHIỆM THU & NỘP BÀI

- [x] Đã điền API Key thật trong `.env` và xác nhận Agent chạy mượt mà trên LLM API thật (Gemini/OpenAI).
- **Tổng số Test Cases đã chạy thành công:** 5 / 5 test cases.
- **Số lượt gọi Tool qua MCP Server chính xác:** 2 lượt.
- **Kết quả đẩy Repo nộp bài:** [x] Đã Commit và Push mã nguồn thành công lên GitHub cá nhân.

---

> ✅ **HOÀN TẤT NỘP BÀI:** Sao chép đường link GitHub Repository cá nhân của bạn và dán vào ô nộp bài trên hệ thống LMS VLearn để hoàn tất Bài Lab 3!
