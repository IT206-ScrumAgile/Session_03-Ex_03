
## Phần 1 – Phân tích vai trò người dùng

| Vai trò | Nhu cầu chính |
|---|---|
| **Khách đi ghép** | Đặt chuyến chung với khách cùng hướng để đi với giá rẻ hơn, chia tiền rõ ràng và thanh toán nhanh bằng ví điện tử. |
| **Tài xế** | Chở nhiều khách cùng tuyến trong một chuyến (tối đa 3 khách) để tăng thu nhập mà xe không bị quá tải. |

---

## Phần 2 – Phân rã User Story

**US1 – Tìm khách ghép cùng tuyến**
- **As a** khách đi ghép,
- **I want** đặt chuyến ghép và được hệ thống tìm khách đi cùng hướng trong tối đa 5 phút,
- **So that** tôi đi chung xe với giá rẻ hơn đi riêng.
- *Small:* chỉ gồm luồng đặt chuyến và tìm khách (kèm xử lý khi hết 5 phút), không bao gồm chia tiền hay thanh toán nên làm xong trong vài ngày của một Sprint.

**US2 – Giới hạn tối đa 3 khách mỗi chuyến**
- **As a** tài xế,
- **I want** mỗi chuyến ghép chỉ nhận tối đa 3 khách đi cùng hướng và tự động khóa chuyến khi đã đủ 3 khách,
- **So that** xe không bị quá tải và lộ trình không bị kéo dài do nhận thêm khách.
- *Small:* chỉ là một quy tắc kiểm tra số khách và khóa chuyến, phạm vi hẹp, hoàn thành được trong vài ngày.

**US3 – Chia tiền và thanh toán bằng ví điện tử**
- **As a** khách đi ghép,
- **I want** tiền chuyến được tự động chia theo số khách thực tế và thanh toán phần của mình bằng ví điện tử,
- **So that** tôi chỉ trả đúng phần của mình mà không phải tính toán hay trả tiền mặt.
- *Small:* chỉ xử lý tính tiền chia và trừ ví cho một chuyến đã được ghép, tách khỏi việc tìm khách nên đủ nhỏ để làm trong một Sprint.

Bộ US thể hiện giới hạn số khách: US2 quy định tối đa 3 khách mỗi chuyến, và US3 chia tiền theo số khách thực tế (2 hoặc 3 khách).

---

## Phần 3 – Nghiệm thu (Acceptance Criteria cho US1)

**Kịch bản 1 – Tìm được khách ghép trong 5 phút**
- **Given** khách A đã đặt chuyến ghép và có một chuyến cùng hướng đang có dưới 3 khách,
- **When** hệ thống tìm khách ghép và tìm được trong vòng 5 phút,
- **Then** khách A được ghép vào chuyến đó, hai bên nhận thông báo ghép thành công, và chuyến không vượt quá 3 khách.

**Kịch bản 2 – Quá 5 phút không tìm được khách ghép**
- **Given** khách A đã đặt chuyến ghép và chưa có khách nào cùng hướng phù hợp,
- **When** đã quá 5 phút mà hệ thống vẫn không tìm được khách ghép,
- **Then** hệ thống dừng tìm kiếm và cho khách A chọn: đi riêng với giá thường, hoặc hủy chuyến miễn phí.
