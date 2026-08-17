# Lab 17 Submission

## Kết quả và phân tích benchmark

Memory-enabled đạt **11/11 (100%)**, còn no-memory đạt **2/11 (18,18%)**; xem `reports/comparison.md`. Không có layer yếu nhất riêng lẻ: short-term, long-term, episodic, semantic và mixed đều đạt 100%. Case lấy nhiều context nhất là **E03 long-term: 1.649 token**, do Context Block và facts về open loop/deadline cùng được truy hồi.

E07 cần kết hợp **long-term** (preference cá nhân `Python`) với **semantic** (quy tắc `Idempotency-Key`). Memory-enabled giảm trung bình **20,85%** so với full source. No-memory giảm **81,82%** nhưng hit rate thấp vì phần lớn trả context rỗng; token reduction chỉ có ý nghĩa khi đi cùng evidence hit rate.

E08 minh họa recency theo scope: ràng buộc mới của `BLUEBIRD-42` là `TypeScript`/`NestJS`, trong khi preference `Python` cũ vẫn hợp lệ cho `ORCHID-27`. E10 cho thấy compaction giữ constraint `REVIEW-DEADLINE-1600`, `Friday`, `16:00` trong durable notes dù raw turn cũ đã bị đẩy khỏi cửa sổ. Buffer không đủ bền vững vì token tăng tuyến tính và cuối cùng vượt context budget.

Privacy drill được chạy sau khi lưu benchmark: delete và verify-only đều trả `Zep user absent: True`, `Redis user keys remaining: 0`; shared semantic KB vẫn nguyên.

UI Streamlit tải 11 case, hiển thị evidence/budget từng layer và chat tiếp cùng user/thread; E07 live kết hợp short-term, long-term và semantic.

## Câu hỏi bắt buộc

**Layer quan trọng nhất trong bộ test:** long-term, vì chi phối bốn case E02, E03, E08, E09 và đóng góp cho E07; nó kiểm tra cross-session recall, open loop, conflict/recency và user isolation.

**Context Block/Zep so với Redis + Qdrant:** Zep cung cấp user graph, temporal facts, Context Block và managed ingestion/search nên giảm công sức orchestration, conflict và provenance. Redis nhanh, minh bạch cho KV/TTL/open loop; Qdrant linh hoạt cho vector retrieval và tự chủ dữ liệu, nhưng đội phát triển phải tự xây extraction, namespace, ranking, temporal validity, deletion và vận hành. Lựa chọn phụ thuộc yêu cầu kiểm soát, chi phí và độ phức tạp vận hành.

**Guardrail chống memory poisoning:** chỉ ghi khi user đã opt-in và loại memory được cho phép; redact PII; tách namespace user/shared; lưu source, timestamp, confidence, scope và validity; ưu tiên fact mới đúng scope nhưng không xóa provenance cũ. Instruction hoặc preference tác động cao phải qua policy/human review; heartbeat chỉ deduplicate/expire/recap, không tự cấp quyền hay tạo instruction bền vững.
