# DevOps 80 ngày — code dự án theo video

[![Kiểm code theo video](https://github.com/duonghuyhieu/hoc-devops/actions/workflows/kiem.yml/badge.svg)](https://github.com/duonghuyhieu/hoc-devops/actions/workflows/kiem.yml) [![Mở bằng Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/duonghuyhieu/hoc-devops)

Code các bài dự án và bài mini trong series «DevOps 80 ngày» trên kênh **Hiếu học mỗi ngày** — những bài code dài, khó gõ lại theo video. Bài thường ngắn, gõ theo video là đủ nên không có ở đây. Mỗi bài một thư mục: README ghi bạn học gì, từng đoạn code trên video kèm lệnh chạy và kết quả máy đã chạy thật, câu đố và bài tập. Mỗi tuần máy tự chạy lại toàn bộ code để chắc vẫn ra đúng như video.

## Cách học

```bash
git clone https://github.com/duonghuyhieu/hoc-devops.git
cd hoc-devops
```

1. Xem video bài dự án, mở thư mục của ngày đó (vd `ngay-26`), đọc README, chạy từng file.
2. Làm bài trong thư mục `bai-lam/` (git bỏ qua thư mục này): chép thư mục ngày sang đó rồi sửa, vd `bai-lam/ngay-26/`. Đừng sửa thẳng file trong thư mục ngày.
3. Có bài dự án mới: `git pull` — vì bài của bạn nằm trong `bai-lam/` nên không bao giờ bị xung đột.

Không dùng git: nút **Code → Download ZIP**. Không muốn cài gì: nút **Mở bằng Codespaces** ở trên (chạy trên trình duyệt, tài khoản GitHub miễn phí có khoảng 60 giờ mỗi tháng).

## Cài đặt

Một terminal: macOS / Linux có sẵn; Windows cài WSL (`wsl --install` trong PowerShell) rồi mở Ubuntu. Lệnh trong README gõ trong terminal; đoạn đánh dấu «cố ý sai» chỉ để đọc, đừng chạy y nguyên.

## Các bài dự án

0/4 bài đã có code (khóa 80 ngày).

| Ngày | Bài | Code |
|---:|---|---|
| 26 | DỰ ÁN CẤP 1: script canh website | ⏳ sắp có |
| 54 | DỰ ÁN CẤP 2: image chuẩn (multi-stage, non-root, healthcheck; CI đẩy lên GHCR khi gắn tag) rồi đưa lên cluster kind từ file YAML trong Git | ⏳ sắp có |
| 79 | DỰ ÁN CUỐI (1/2): pipeline phát hành tái sử dụng (workflow_call) | ⏳ sắp có |
| 80 | DỰ ÁN CUỐI (2/2): lên production an toàn | ⏳ sắp có |

## Báo lỗi, hỏi bài

- Code chạy khác video, README sai: [Issues → Báo lỗi bài học](https://github.com/duonghuyhieu/hoc-devops/issues/new/choose).
- Hỏi bài, nhờ giải thích: [Discussions](https://github.com/duonghuyhieu/hoc-devops/discussions).

## Giấy phép

Code: MIT (`LICENSE`) — dùng thoải mái. Chữ trong README: CC BY 4.0 (`LICENSE-NOI-DUNG.md`) — dùng lại thì ghi công kênh Hiếu học mỗi ngày.
