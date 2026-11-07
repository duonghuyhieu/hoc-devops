# DevOps 80 ngày — code theo video

[![Kiểm code theo video](https://github.com/duonghuyhieu/hoc-devops/actions/workflows/kiem.yml/badge.svg)](https://github.com/duonghuyhieu/hoc-devops/actions/workflows/kiem.yml) [![Mở bằng Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/duonghuyhieu/hoc-devops)

Code của từng video trong series «DevOps 80 ngày» trên kênh **Hiếu học mỗi ngày**. Mỗi ngày một thư mục: README ghi bạn học gì, từng đoạn code trên video kèm lệnh chạy và kết quả máy đã chạy thật, câu đố, đáp án câu đố hôm trước và bài tập. Mỗi tuần máy tự chạy lại toàn bộ code để chắc vẫn ra đúng như video.

## Cách học

```bash
git clone https://github.com/duonghuyhieu/hoc-devops.git
cd hoc-devops
```

1. Xem video ngày N, mở thư mục `ngay-01`… đọc README, chạy từng file.
2. Làm bài trong thư mục `bai-lam/` (git bỏ qua thư mục này): chép thư mục ngày sang đó rồi sửa, vd `bai-lam/ngay-05/`. Đừng sửa thẳng file trong thư mục ngày.
3. Có video mới: `git pull` — vì bài của bạn nằm trong `bai-lam/` nên không bao giờ bị xung đột.

Không dùng git: nút **Code → Download ZIP**. Không muốn cài gì: nút **Mở bằng Codespaces** ở trên (chạy trên trình duyệt, tài khoản GitHub miễn phí có khoảng 60 giờ mỗi tháng).

## Cài đặt

Một terminal: macOS / Linux có sẵn; Windows cài WSL (`wsl --install` trong PowerShell) rồi mở Ubuntu. Lệnh trong README gõ trong terminal; đoạn đánh dấu «cố ý sai» chỉ để đọc, đừng chạy y nguyên.

## Lộ trình

5/80 ngày đã có video.

| Ngày | Bài | Code |
|---:|---|---|
| 0 | Giới thiệu khóa DevOps 80 ngày | [✅ ngay-00](ngay-00/) |
| | **1. Sống trong terminal** | |
| 1 | Terminal và đường dẫn | [✅ ngay-01](ngay-01/) |
| 2 | Tạo, chép, dời, xoá | [✅ ngay-02](ngay-02/) |
| 3 | Xem file | [✅ ngay-03](ngay-03/) |
| 4 | Quyền file | [✅ ngay-04](ngay-04/) |
| 5 | Tiến trình | [✅ ngay-05](ngay-05/) |
| 6 | Biến môi trường | ⏳ sắp có |
| 7 | Cài phần mềm và sửa file | ⏳ sắp có |
| 8 | Dịch vụ chạy nền với systemd | ⏳ sắp có |
| | **2. Ống nối & script** | |
| 9 | Chuyển hướng và pipe | ⏳ sắp có |
| 10 | grep | ⏳ sắp có |
| 11 | sed và awk vừa đủ | ⏳ sắp có |
| 12 | Script bash (1/2) | ⏳ sắp có |
| 13 | Script bash (2/2) | ⏳ sắp có |
| 14 | Máy còn khoẻ không | ⏳ sắp có |
| | **3. Mạng cho dev** | |
| 15 | IP và cổng | ⏳ sắp có |
| 16 | DNS | ⏳ sắp có |
| 17 | HTTP | ⏳ sắp có |
| 18 | curl | ⏳ sắp có |
| 19 | HTTPS và chứng chỉ TLS | ⏳ sắp có |
| 20 | SSH | ⏳ sắp có |
| | **4. Git như người đi làm** | |
| 21 | Git bên trong | ⏳ sắp có |
| 22 | Gộp nhánh | ⏳ sắp có |
| 23 | Quy trình nhóm | ⏳ sắp có |
| 24 | Sửa sai trong Git | ⏳ sắp có |
| 25 | ÔN CẤP 1 (terminal, script, mạng, Git) | ⏳ sắp có |
| 26 | DỰ ÁN CẤP 1 | ⏳ sắp có |
| | **5. Docker** | |
| 27 | Container là gì | ⏳ sắp có |
| 28 | docker run | ⏳ sắp có |
| 29 | Gỡ lỗi container | ⏳ sắp có |
| 30 | Dockerfile (1/3) | ⏳ sắp có |
| 31 | Dockerfile (2/3) | ⏳ sắp có |
| 32 | Dockerfile (3/3) | ⏳ sắp có |
| 33 | Đặt tên image và registry | ⏳ sắp có |
| 34 | Dữ liệu bền | ⏳ sắp có |
| 35 | Mạng Docker | ⏳ sắp có |
| 36 | Dockerfile an toàn hơn | ⏳ sắp có |
| 37 | Secret đúng chỗ | ⏳ sắp có |
| | **6. Docker Compose** | |
| 38 | Docker Compose (1/3) | ⏳ sắp có |
| 39 | Docker Compose (2/3) | ⏳ sắp có |
| 40 | Docker Compose (3/3) | ⏳ sắp có |
| | **7. CI/CD với GitHub Actions** | |
| 41 | CI/CD và workflow đầu tiên chạy test | ⏳ sắp có |
| 42 | Matrix | ⏳ sắp có |
| 43 | Secret và biến của Actions | ⏳ sắp có |
| 44 | Build và đẩy image lên GHCR trong CI | ⏳ sắp có |
| 45 | Phát hành an toàn | ⏳ sắp có |
| 46 | Bảo vệ pipeline | ⏳ sắp có |
| | **8. Kubernetes nhập môn** | |
| 47 | Kubernetes là gì và Pod đầu tiên | ⏳ sắp có |
| 48 | Deployment (1/2) | ⏳ sắp có |
| 49 | Deployment (2/2) | ⏳ sắp có |
| 50 | Service | ⏳ sắp có |
| 51 | ConfigMap (cấu hình) và Secret (mật khẩu) tách khỏi image | ⏳ sắp có |
| 52 | Gỡ lỗi pod | ⏳ sắp có |
| 53 | ÔN CẤP 2 (Docker, Compose, CI/CD, Kubernetes nhập môn) | ⏳ sắp có |
| 54 | DỰ ÁN CẤP 2 | ⏳ sắp có |
| | **9. Kubernetes đi làm** | |
| 55 | Probe | ⏳ sắp có |
| 56 | Tài nguyên | ⏳ sắp có |
| 57 | Chia cluster | ⏳ sắp có |
| 58 | Ra Internet bằng Gateway API | ⏳ sắp có |
| 59 | Lưu trữ bền | ⏳ sắp có |
| 60 | Helm | ⏳ sắp có |
| | **10. Hạ tầng bằng code & cloud** | |
| 61 | Hạ tầng bằng code (IaC) | ⏳ sắp có |
| 62 | Biến, count, output và module | ⏳ sắp có |
| 63 | Cloud căn bản (1/2) | ⏳ sắp có |
| 64 | Cloud căn bản (2/2) | ⏳ sắp có |
| 65 | State của Terraform | ⏳ sắp có |
| 66 | Cụm Kubernetes trên cloud bằng Terraform | ⏳ sắp có |
| | **11. Quan sát hệ thống** | |
| 67 | Log | ⏳ sắp có |
| 68 | Metric | ⏳ sắp có |
| 69 | PromQL | ⏳ sắp có |
| 70 | Cảnh báo | ⏳ sắp có |
| 71 | Tracing | ⏳ sắp có |
| | **12. An toàn & tin cậy** | |
| 72 | Quét lỗ hổng (CVE) trong image bằng Trivy | ⏳ sắp có |
| 73 | Chuỗi cung ứng | ⏳ sắp có |
| 74 | Đo độ tin cậy | ⏳ sắp có |
| 75 | Database production | ⏳ sắp có |
| 76 | Triển khai an toàn | ⏳ sắp có |
| 77 | Tự co giãn | ⏳ sắp có |
| 78 | Xử lý sự cố | ⏳ sắp có |
| | **13. Tốt nghiệp** | |
| 79 | DỰ ÁN CUỐI (1/2) | ⏳ sắp có |
| 80 | DỰ ÁN CUỐI (2/2) | ⏳ sắp có |

## Báo lỗi, hỏi bài

- Code chạy khác video, README sai: [Issues → Báo lỗi bài học](https://github.com/duonghuyhieu/hoc-devops/issues/new/choose).
- Hỏi bài, nhờ giải thích: [Discussions](https://github.com/duonghuyhieu/hoc-devops/discussions).

## Giấy phép

Code: MIT (`LICENSE`) — dùng thoải mái. Chữ trong README: CC BY 4.0 (`LICENSE-NOI-DUNG.md`) — dùng lại thì ghi công kênh Hiếu học mỗi ngày.
