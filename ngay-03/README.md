# Ngày 3 · Xem file

DevOps 80 ngày · 1. Sống trong terminal

## Bạn học gì

Xem file: cat, less, head, tail, tail -f để theo dõi log đang chạy

## Code trong video

### NGÀY 3 · XEM FILE VÀ LOG

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

### ĐẦU FILE — head lấy dòng đầu

Gõ trong terminal:

```bash
head -n 1 dat-xe.log
```

Kết quả:

```text
08:00 khoi-dong
```

### LỖI HAY GẶP — File 3 GB mà gõ cat

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

## Đáp án câu đố Ngày 2

```bash
mkdir -p kho/logs kho/backup
mv kho/logs kho/backup
ls kho
```

In ra: `backup`

## Câu đố hôm nay

Màn hình hiện những số nào? Đoán trước, rồi chạy thử. Đáp án ở Ngày 4.

```bash
seq 3 7 > so.txt
tail -n 2 so.txt
```

## Bài tập

Xem 20 dòng cuối /var/log/syslog, rồi mở bằng less tìm error.
