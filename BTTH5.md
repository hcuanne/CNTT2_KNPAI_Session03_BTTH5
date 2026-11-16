
# 1. Bối cảnh
Cửa hàng công nghệ cần phân loại phản hồi khách hàng để xác định mức độ ưu tiên xử lý.

# 2. Yêu cầu đầu ra
- Tạo Prompt Zero-shot và Few-shot.
- Few-shot có ít nhất 3 ví dụ mẫu.
- Phân loại 5 phản hồi thành 3 nhãn.
- Xuất kết quả dạng bảng.
- So sánh độ chính xác và tính nhất quán.

# 3. Bài làm

## Prompt 1: Zero-shot

Phân loại 5 phản hồi khách hàng thành 3 nhãn:
- Tích cực: Khen ngợi, hài lòng.
- Tiêu cực: Phàn nàn, không hài lòng.
- Yêu cầu hỗ trợ: Cần giải quyết vấn đề cụ thể.

Chọn một nhãn phù hợp nhất cho mỗi phản hồi.
Xuất bảng gồm STT, Phản hồi, Nhãn phân loại, Lý do.

## Prompt 2: Few-shot

Phân loại phản hồi dựa trên các ví dụ:

- "Sản phẩm rất tốt." → Tích cực
- "Giao hàng quá chậm." → Tiêu cực
- "Tôi cần đổi sản phẩm bị lỗi." → Yêu cầu hỗ trợ

Áp dụng quy tắc trên để phân loại 5 phản hồi.
Nếu khách hàng yêu cầu giải quyết vấn đề cụ thể,
ưu tiên nhãn "Yêu cầu hỗ trợ".

Xuất bảng gồm STT, Phản hồi, Nhãn phân loại, Lý do.

## Kết quả phân loại

| STT | Phản hồi | Nhãn phân loại | Lý do |
|---|---|---|---|
| 1 | Sản phẩm đẹp, giao hàng nhanh, rất hài lòng. | Tích cực | Khen ngợi sản phẩm và giao hàng. |
| 2 | Tôi đã đặt hàng 5 ngày nhưng chưa nhận được. | Tiêu cực | Phàn nàn giao hàng chậm. |
| 3 | Tai nghe không kết nối được Bluetooth. | Yêu cầu hỗ trợ | Cần hỗ trợ kỹ thuật. |
| 4 | Nhân viên tư vấn rất nhiệt tình. | Tích cực | Khen ngợi nhân viên. |
| 5 | Tôi muốn hoàn tiền vì sản phẩm bị lỗi. | Yêu cầu hỗ trợ | Yêu cầu hoàn tiền. |

### So sánh Zero-shot và Few-shot

| Tiêu chí | Zero-shot | Few-shot |
|---|---|---|
| Độ chính xác | Có thể phân loại đúng nhưng dễ nhầm nhãn. | Có xu hướng chính xác hơn nhờ ví dụ. |
| Tính nhất quán | Có thể thay đổi giữa các lần chạy. | Ổn định hơn nhờ quy tắc mẫu. |
| Ưu điểm | Prompt ngắn, dễ sử dụng. | Phân loại rõ ràng, dễ kiểm soát. |


