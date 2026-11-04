# Ngày 2 · Tạo, chép, dời, xoá

DevOps 80 ngày · 1. Sống trong terminal

## Bạn học gì

Tạo, chép, dời, xoá: mkdir -p, touch, cp, mv, rm, rm -r (Linux không có thùng rác)

## Code trong video

### NGÀY 2 · TẠO, CHÉP, DỜI, XÓA

Gõ trong terminal — đoạn cố ý sai, đừng chạy y nguyên:

```bash
# máy chủ mới, chưa có thư mục game
mkdir game/logs
```

Kết quả:

```text
mkdir: cannot create directory
'game/logs': No such file or directory
```

### THÊM HAI KÝ TỰ — Cờ -p tạo luôn thư mục cha

Gõ trong terminal:

```bash
# máy chủ mới, chưa có thư mục game
mkdir -p game/logs
ls game
```

Kết quả:

```text
logs
```

### CHÉP RỒI DỜI — Chép dự phòng rồi dời đi

Gõ trong terminal:

```bash
touch game/server.conf
cp game/server.conf{,.bak}
mv game/server.conf.bak game/logs/
ls game game/logs
```

Kết quả:

```text
game:
logs  server.conf
game/logs:
server.conf.bak
```

### LỖI HAY GẶP — Thừa một dấu cách

Gõ trong terminal — đoạn cố ý sai, đừng chạy y nguyên:

```bash
# định gõ: rm -rf ~/logs
rm -rf ~ /logs
```

Kết quả:

```text
rm: cannot remove '/home/an':
Permission denied
```

## Đáp án câu đố Ngày 1

```bash
cd ~/du-an/shop
cd ../..
pwd
```

In ra: `/home/an`

## Câu đố hôm nay

ls kho in ra gì? Đoán trước, rồi chạy thử. Đáp án ở Ngày 3.

```bash
mkdir -p kho/logs kho/backup
mv kho/logs kho/backup
ls kho
```

## Bài tập

Tạo game/{src,logs,backup} bằng một lệnh mkdir -p, chép một file vào backup, đổi tên nó thành ngay-03.bak bằng mv.
