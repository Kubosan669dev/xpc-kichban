# xpc-script-writer

Skill cho Claude để viết **kịch bản video ngắn** (Reels / Shorts / TikTok) về PC, linh kiện và build máy theo đúng giọng kênh **XPC Computer – Toàn Máy Tính**.

Skill được xây dựng từ toàn bộ kho video của kênh: 118 tiêu đề và lời thoại thật của 91 video.

Mỗi kịch bản gồm:
- Lời thoại để quay.
- Tiêu đề thumbnail 2–3 dòng, kèm màu từng dòng.
- Tiêu đề Facebook, caption, mô tả và hashtag.
- Gợi ý dựng.
- Nguồn tham khảo và các điểm cần kiểm tra lại.

## Bốn định dạng
| | Định dạng | Ví dụ |
|---|---|---|
| A | Tin tức / Giải thích | "DLSS 5 có đáng bật không?" |
| B | Hỏi – đáp tư vấn (X hay Y, có nên nâng…) | "14600K hay Ultra 245K?" |
| C | Cấu hình theo ngân sách / nhu cầu | "50 triệu build PC gaming cấu hình nào?" |
| D | Mẹo nhanh / Review tại shop | "Máy bật không lên, đừng vội mang đi sửa" |

## Cấu trúc thư mục
```
xpc-script-writer/
├── SKILL.md                       # Hướng dẫn chính cho Claude
├── references/
│   └── kho-video.md               # 118 video đã làm, chia theo nhóm, để tránh trùng chủ đề
└── examples/
    ├── vi-du-A-tin-tuc.md
    ├── vi-du-B-hoi-dap.md
    ├── vi-du-B2-thieu-boi-canh.md
    ├── vi-du-C-cau-hinh.md
    └── vi-du-D-meo-nhanh.md
```

## Cài đặt
- **Claude.ai / ứng dụng Claude:** vào Settings → Capabilities → Skills → *Upload skill*, rồi chọn file `xpc-script-writer.zip`.
- **Claude Code:** chép thư mục `xpc-script-writer/` vào `~/.claude/skills/` để dùng cho mọi dự án, hoặc vào `.claude/skills/` trong repo.

## Cách dùng
Một vài yêu cầu mẫu:
- "Viết kịch bản: Có nên mua RTX 5070 lúc này?"
- "Khách hỏi: em đang dùng 3060 nên nâng lên card nào ạ? Viết kịch bản trả lời."
- "Viết 5 kịch bản từ các bài báo này: <link>, <link>…"

Claude sẽ tự làm các bước sau:
1. Kiểm tra trùng chủ đề trong kho video.
2. Chọn định dạng phù hợp.
3. Tra cứu giá và số liệu mới nhất.
4. Trả về một file `.md` chứa toàn bộ kịch bản.

## Cập nhật
Sau mỗi lô video mới, thêm tiêu đề vào `references/kho-video.md`.

## Quy trình liên quan
Sau khi quay, clip thô được dựng bằng skill `xpc-shorts-pipeline` (cắt, phụ đề, nhạc, thumbnail, đăng sheet). Tiêu đề thumbnail và caption trong kịch bản được dùng lại trực tiếp ở bước này.
