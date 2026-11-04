# Ngày 4 · Quyền file

DevOps 80 ngày · 1. Sống trong terminal

## Bạn học gì

Quyền file: đọc rwx trong ls -l (chủ / nhóm / người khác), chmod +x, chmod 600, số 7-5-5

## Code trong video

### NGÀY 4 · QUYỀN FILE

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

### THÊM MỘT CHỮ — Thiếu đúng một chữ x

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

### QUYỀN BẰNG SỐ — 7-5-5 = rwx r-x r-x

Gõ trong terminal:

```bash
# r=4  w=2  x=1
chmod u=rwx,go=rx run.sh
stat -c '%a' run.sh
```

Kết quả:

```text
755
```

### CHMOD 600 — Khóa thanh toán: chỉ chủ đọc

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

## Đáp án câu đố Ngày 3

```bash
seq 3 7 > so.txt
tail -n 2 so.txt
```

In ra: `6` / `7`

## Câu đố hôm nay

Mười ký tự đầu là gì? Đoán trước, rồi chạy thử. Đáp án ở Ngày 5.

```bash
chmod 750 deploy.sh
ls -l deploy.sh
```

## Bài tập

Đặt 640 cho config.yaml, giải thích từng số; ls -l /etc/shadow — vì sao không đọc được?
