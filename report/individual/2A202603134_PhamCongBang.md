# Báo cáo thực hành Day 3 — điền trực tiếp trong fork của bạn

Cách dùng: Thay mọi dấu … bằng bài làm thật của bạn trước khi nộp link fork trên LMS. Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong hướng dẫn mẫu chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

Mã học viên theo lớp: 2A202603134
Ngày / CVAT local: 11/11/2026 / CVAT local
Công cụ đã dùng: CVAT local

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh LMS đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong submissions/ và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi chưa có, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, không phải điểm tự chấm.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic | easy_semantic.zip | 3 / 3 | 20 |
| medium_instance | medium_instance.zip | 3 / 3 | 32 |
| hard_panoptic | hard_panoptic.zip | 2 / 2 | 30 |
| cp1_holes | cp1_holes.zip | 1 / 1 | 3 |
| cp2_slice | cp2_slice.zip | 1 / 1 | 3 |
| cp5_occlusion | cp5_occlusion.zip | 1 / 1 | 3 |
| cp3_thin | cp3_thin.zip | 1 / 1 | 3 |
| cp4_curb | cp4_curb.zip | 1 / 1 | 3 |
| cp6_coverage | cp6_coverage.zip | 1 / 1 | 3 |
| Tổng tối đa | | | 100 |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở medium_instance, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

Ảnh, vị trí và object Medium đầu tiên tự vẽ: ảnh 000000181542.jpg, xe ô tô màu trắng bên trái đường.
Class và quy tắc tôi dùng để chọn biên: class car, chỉ vẽ phần nhìn thấy gồm vỏ xe kính và bánh xe, dừng lại ở mép tiếp giáp mặt đường chứ không lấy bóng râm dưới gầm.
Nếu dùng gợi ý sau đó: vùng gợi ý bị lan ra phần bóng dưới đường, tôi dùng công cụ chỉnh điểm kéo sát lại mép bánh xe.
Nếu không dùng gợi ý: không áp dụng.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi có thật trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

Task/ảnh/vùng: task cp2_slice, ảnh 000000017627.jpg, hai xe đỗ nối đuôi nhau.
Lỗi thuộc loại: gộp tách.
Bằng chứng tôi nhìn thấy: hai xe sát nhau bị dính thành một hình.
Quy tắc và hành động sửa: tách riêng từng xe thành hai đối tượng độc lập.
Sau sửa đã Save và export lại chưa? đã lưu và xuất lại file cp2_slice.zip.

Nếu bạn đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script, ghi ngắn một kết quả liên quan lỗi vừa sửa: script inspect_submissions báo ok cả 9 task / chưa có điểm. Scorecard ba tier tối đa 82, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một vùng cụ thể khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| cp1_holes ảnh 000000144300.jpg bánh xe máy | khoét nan hoa hay phủ kín cả vành | nhìn thấy rõ mặt đường phía sau qua các khe hở | khoét lỗ các khe nhìn xuyên ra đường |
| cp4_curb ảnh 7d83710e-4697c3b2.jpg mép bó vỉa | tính vào đường hay vỉa hè | gờ bê tông phân cách lối đi bộ với lòng đường | chọn mép bó vỉa thuộc về sidewalk |
| cp5_occlusion ảnh 000000336232.jpg người bị biển báo che | tách làm hai người hay giữ một người | người bị che một phần thân ở giữa nhưng cùng một người | giữ chung một đối tượng có hai mảng rời |
