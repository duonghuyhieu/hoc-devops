# Ngày 4 · Quyền file

> DevOps 80 ngày · 1. Sống trong terminal · video 1 phút 10 giây

## Bạn học gì

Quyền file: đọc rwx trong ls -l (chủ / nhóm / người khác), chmod +x, chmod 600, số 7-5-5

## Đáp án câu đố Ngày 3

```bash
seq 3 7 > so.txt
tail -n 2 so.txt
```

In ra: `6` / `7`

## Bài học

_Đi theo đúng thứ tự video. Lời giảng là lời đọc trong video; code và kết quả là bản máy đã chạy thật._

### NGÀY 4 · QUYỀN FILE

Đáp án hôm qua: sáu và bảy.

Gõ trong terminal — đoạn cố ý sai, đừng chạy y nguyên:

```bash
ls -l run.sh
./run.sh
```

Kết quả:

```text
-rw-r--r-- 1 an an 90 Oct 12 09:15 run.sh
bash: ./run.sh: Permission denied
```

Script khởi động ví lên máy chủ, chủ file mà không chạy nổi. Thủ phạm nằm trong mười ký tự đầu — thấy chưa?

### THÊM MỘT CHỮ — Thiếu đúng một chữ x

Vậy thủ phạm là chữ x thiếu, tức quyền chạy. Pipeline ngày tám mươi cũng là chuỗi script như thế.

Gõ trong terminal:

```bash
chmod +x run.sh
ls -l run.sh
./run.sh
```

Kết quả:

```text
-rwxr-xr-x 1 an an 90 Oct 12 09:15 run.sh
Ví đã chạy ở cổng 3000
```

chmod cộng x thêm quyền, ví lên ngay.

### Ý chính — ĐỌC MƯỜI KÝ TỰ — -rwxr-xr-x loại · u · g · o

Nhưng đọc sao: gạch đầu là file, d là thư mục. Chín ký tự sau: đọc, sửa, chạy của chủ, nhóm, khách. Như thẻ từ chung cư: chủ được sửa, hàng xóm và khách thường chỉ được xem. Gãy ở chỗ: với file x là chạy, với thư mục mới là bước vào.

- **- / d** — file / thư mục
- **r w x** — đọc · sửa · chạy
- **u g o** — chủ · nhóm · người khác
- **x** — file: chạy · thư mục: cd vào

Ghi nhớ nhanh: u chủ căn hộ · g cùng tầng · o khách

### QUYỀN BẰNG SỐ — 7-5-5 = rwx r-x r-x

Giờ viết gọn bằng số: đọc bốn, sửa hai, chạy một. Mẹo: stat in thẳng con số — bạn đoán mấy?

Gõ trong terminal:

```bash
# r=4  w=2  x=1
chmod u=rwx,go=rx run.sh
stat -c '%a' run.sh
```

**Đoán trước khi chạy — Bạn đoán stat in số mấy?**

- A. `777`
- B. `755`
- C. `644`

Kết quả:

```text
755
```

Đáp án đúng: **B**.

Bảy năm năm: chủ đủ bảy, còn lại bốn cộng một.

### CHMOD 600 — Khóa thanh toán: chỉ chủ đọc

Khoan đã, file khóa thanh toán thì phải kín. Mặc định sáu bốn bốn, ai vào máy cũng đọc.

Gõ trong terminal:

```bash
# r=4  w=2  x=1
chmod 600 .env
stat -c '%a %A' .env
```

Kết quả:

```text
600 -rw-------
```

Sáu không không chỉ chủ đọc sửa; bảy bảy bảy là mở toang.

## Tóm lại

Tóm lại: script cần x, file khóa cần sáu không không.

## Câu đố hôm nay

Mười ký tự đầu là gì? Đoán trước, rồi chạy thử. Đáp án ở Ngày 5.

```bash
chmod 750 deploy.sh
ls -l deploy.sh
```

## Bài tập

Đặt 640 cho config.yaml, giải thích từng số; ls -l /etc/shadow — vì sao không đọc được?
