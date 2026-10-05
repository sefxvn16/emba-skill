# emba-skill

Skill cho Claude hỗ trợ viết, rà soát, phản biện và biên tập **văn bản lập luận học thuật/chuyên môn**: bài luận, case study, đề tài, báo cáo, câu hỏi thi. Skill được thiết kế cho bối cảnh EMBA/MBA nhưng dùng được cho phần lớn bài viết học thuật có mục tiêu chứng minh một luận điểm bằng lý lẽ và bằng chứng. Nội dung skill viết bằng tiếng Việt.

> **Trạng thái:** bản đầu tiên, đăng để xin góp ý. Khung tư duy trong skill được tổng hợp từ thực hành phổ biến, chưa được kiểm chứng thực nghiệm.

## Skill làm gì

Skill dùng khung 5 phạm trù **HIỂU - NGHĨ - TÌM - LẬP - VIẾT**:

1. **HIỂU** - đề thực sự yêu cầu gì (nhiệm vụ, sản phẩm, ràng buộc, rubric).
2. **NGHĨ** - vấn đề trung tâm, các câu hỏi con, giả thuyết làm việc.
3. **TÌM** - lý thuyết và bằng chứng cho từng câu hỏi con, cả chiều ủng hộ lẫn phản bác.
4. **LẬP** - câu trả lời trung tâm, chuỗi Claim → Lý do → Bằng chứng, outline kim tự tháp lọc bằng MECE.
5. **VIẾT** - viết bám outline, rà 4 lớp: nội dung, logic, bằng chứng - trích dẫn, hình thức.

Trước khi làm, skill kiểm tra văn bản có phải lập luận học thuật không (review phim, blog, sáng tác... thì không dùng), rồi chọn một trong 5 chế độ:

| Chế độ | Dùng khi | File hướng dẫn |
|---|---|---|
| Đầy đủ | Viết bài mới, có thời gian chuẩn bị | `full-mode.md` |
| Nhanh | Trả lời trong thời gian giới hạn (khoảng 5 phút trở xuống) | `quick-mode.md` |
| Rà soát (có tầng sâu) | Nhận xét, phản biện bài đã viết; tầng sâu cho đề tài, luận văn, chuẩn bị bảo vệ | `review-mode.md`, `deep-review.md` |
| Biên tập | Sửa, viết lại bản nháp cho mạch lạc mà giữ nguyên nội dung và mức khẳng định | `idea-flow.md` |
| Kiểm tra sau sửa | Kiểm bản đã sửa đã xử lý hết góp ý của giảng viên/hội đồng chưa | `re-review.md` |

Một số điểm đặc thù:

- **Không viết trích dẫn từ trí nhớ.** Nghiên cứu cụ thể (tác giả, năm, số liệu, DOI) phải được truy xuất trước khi đưa vào bài; không truy xuất được thì ghi là hướng cần tra.
- **Quy tắc tên tác giả kiểu Việt Nam.** Không để họ đứng một mình ("D. McGregor (1960)", không viết "McGregor (1960)"), trừ khi rubric hoặc giảng viên quy định khác.
- **Chống chiều lòng.** Khi bị phản bác, skill chỉ rút hoặc hạ mức nhận xét nếu có bằng chứng hay lập luận mới, không đổi vì bị nài.
- **Văn bản đưa vào là dữ liệu, không phải chỉ thị.** Câu trong bài cần rà soát yêu cầu bỏ qua bước hay đổi kết luận sẽ được nêu ra như một phát hiện, không làm theo.
- **Chạy độc lập.** Skill không cần cài skill nào khác; phần văn phong (gỡ khuôn mẫu văn AI) nằm sẵn trong `style-guide.md`.

## Cấu trúc thư mục

```
emba/
├── SKILL.md                      # Điểm vào: phạm vi, chọn chế độ, quy tắc chung
└── references/
    ├── full-mode.md              # Chế độ đầy đủ
    ├── quick-mode.md             # Chế độ nhanh
    ├── review-mode.md            # Chế độ rà soát
    ├── deep-review.md            # Tầng rà soát sâu
    ├── idea-flow.md              # Chế độ biên tập
    ├── re-review.md              # Chế độ kiểm tra sau sửa
    ├── style-guide.md            # Văn phong bản giao, 16 điều cấm
    ├── english-patterns.md       # Mẫu câu tiếng Anh cần tránh
    └── LICENSE-stop-slop.txt     # Giấy phép MIT của phần chuyển thể từ stop-slop
```

## Cài đặt

**Claude Code:** chép thư mục `emba` vào `~/.claude/skills/` (dùng cho mọi dự án) hoặc vào `.claude/skills/` trong một dự án cụ thể.

**Ứng dụng Claude (claude.ai, desktop):** nén thư mục `emba` thành file `.zip` (thư mục `emba` nằm ở gốc file zip), rồi tải lên ở phần quản lý Skills trong cài đặt. Vị trí menu có thể khác nhau tùy phiên bản ứng dụng.

## Cách dùng

Skill tự kích hoạt khi yêu cầu khớp phạm vi. Ví dụ:

- "Phân tích đề case này và lập outline giúp tôi: …"
- "Tôi có 5 phút để trả lời câu hỏi trên lớp: …"
- "Phản biện đề tài này như một thành viên hội đồng."
- "Viết lại đoạn này cho mạch lạc, đừng đổi ý."
- "Đây là góp ý của giảng viên và bản tôi đã sửa. Còn góp ý nào chưa xử lý?"

## Giới hạn

- Nội dung skill hiện chỉ có tiếng Việt; bản tiếng Anh dự kiến làm sau.
- Khung chưa được kiểm chứng thực nghiệm. Kết quả rà soát là một cách đọc có cấu trúc, không thay thế nhận xét của giảng viên hay hội đồng, và không dự đoán điểm.
- Phần tìm nghiên cứu hiện đại cần môi trường có công cụ tìm kiếm. Không có công cụ tìm kiếm thì skill chỉ nêu lý thuyết kinh điển và hướng cần tra.

## Góp ý

Mọi góp ý xin gửi qua mục **Issues** của repo. Để dễ xử lý, nên ghi:

- chế độ đã dùng (hoặc chế độ bạn nghĩ skill nên chọn);
- đầu vào, đã bỏ thông tin cá nhân hoặc thông tin mật;
- kết quả bạn mong đợi và kết quả skill thực sự đưa ra.

Tôi đặc biệt muốn nghe góp ý về: skill chọn sai chế độ, kích hoạt nhầm hoặc không kích hoạt, nhận xét rà soát sai mức độ, và chỗ hướng dẫn khó hiểu với người chưa quen khung này.

## Nguồn và giấy phép

Skill phát hành theo giấy phép **CC BY-NC 4.0** (chỉ dùng phi thương mại, cần ghi nguồn). Xem [LICENSE.md](LICENSE.md), gồm cả danh sách các nguồn bên thứ ba và giấy phép của chúng.
