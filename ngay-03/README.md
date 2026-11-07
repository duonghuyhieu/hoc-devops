# Ngày 3 · Xem file

> DevOps 80 ngày · 1. Sống trong terminal · video 1 phút 3 giây

## Bạn học gì

Xem file: cat, less, head, tail, tail -f để theo dõi log đang chạy

## Đáp án câu đố Ngày 2

```bash
mkdir -p kho/logs kho/backup
mv kho/logs kho/backup
ls kho
```

In ra: `backup`

## Bài học

_Đi theo đúng thứ tự video. Lời giảng là lời đọc trong video; code và kết quả là bản máy đã chạy thật._

### NGÀY 3 · XEM FILE VÀ LOG

Đáp án hôm qua: backup.

Gõ trong terminal:

```bash
tail -n 3 dat-xe.log
```

Kết quả:

```text
09:59 #102 nhan
10:00 #103 LOI-tt
10:00 #104 nhan
$
```

Khách kêu không gọi được xe: tail in ba dòng log. Thêm một chữ, lệnh không dừng nữa — chữ gì?

### THÊM MỘT CHỮ — Một chữ f bám log sống

Gõ trong terminal:

```bash
tail -f -n 3 dat-xe.log
```

Kết quả:

```text
09:59 #102 nhan
10:00 #103 LOI-tt
10:00 #104 nhan
10:01 #105 nhan
10:01 #106 LOI-tt
```

Chính là chữ f: bám file, lỗi mới hiện ngay. Như đứng cạnh máy in order: phiếu ra là thấy. Máy in tự ngừng, lệnh này phải bấm Ctrl C. Ngày tám mươi máy canh SLO hộ, hôm nay bạn tự đọc.

### Ý chính — BỐN CÁCH ĐỌC FILE — Bốn cách đọc file

Vậy tail là một trong bốn cách. Lệnh cat in cả file một lèo, hợp file ngắn. Lệnh head thì ngược lại, lấy dòng đầu. Còn less mở file, lật từng trang.

- **tail -n** — vài dòng cuối
- **cat** — in cả file
- **head -n** — vài dòng đầu
- **less** — lật từng trang

Ghi nhớ nhanh: tail -f log sống · less / tìm · q thoát · Ctrl+C dừng lệnh

### ĐẦU FILE — head lấy dòng đầu

Giờ thử head xin một dòng. Bạn đoán nó in dòng nào?

Gõ trong terminal:

```bash
head -n 1 dat-xe.log
```

**Đoán trước khi chạy — Bạn đoán in dòng nào?**

- A. `10:01 #106 LOI-tt`
- B. `08:00 khoi-dong`
- C. `Lỗi khi chạy`

Kết quả:

```text
08:00 khoi-dong
```

Đáp án đúng: **B**.

Dòng khởi động tám giờ: head đếm từ đầu.

### LỖI HAY GẶP — File 3 GB mà gõ cat

Nhưng file nặng ba gigabyte mà gõ cat.

Gõ trong terminal — đoạn cố ý sai, đừng chạy y nguyên:

```bash
du -h dat-xe.log
cat dat-xe.log
```

Kết quả:

```text
3.2G    dat-xe.log
08:00 khoi-dong
08:00 #001 nhan
08:00 #002 nhan
^C
```

Màn hình trôi cả triệu dòng, phải bấm Ctrl C cắt ngang. Sửa: dùng less, mẹo là bấm Shift F để bám log.

## Tóm lại

Tóm lại: khách kêu lỗi thì bám log bằng chữ f.

## Câu đố hôm nay

Màn hình hiện những số nào? Đoán trước, rồi chạy thử. Đáp án ở Ngày 4.

```bash
seq 3 7 > so.txt
tail -n 2 so.txt
```

## Bài tập

Xem 20 dòng cuối /var/log/syslog, rồi mở bằng less tìm error.
