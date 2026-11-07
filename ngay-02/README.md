# Ngày 2 · Tạo, chép, dời, xoá

> DevOps 80 ngày · 1. Sống trong terminal · video 1 phút 8 giây

## Bạn học gì

Tạo, chép, dời, xoá: mkdir -p, touch, cp, mv, rm, rm -r (Linux không có thùng rác)

## Đáp án câu đố Ngày 1

```bash
cd ~/du-an/shop
cd ../..
pwd
```

In ra: `/home/an`

## Bài học

_Đi theo đúng thứ tự video. Lời giảng là lời đọc trong video; code và kết quả là bản máy đã chạy thật._

### NGÀY 2 · TẠO, CHÉP, DỜI, XÓA

Đáp án hôm qua: home của An. Máy chủ game mới, script dựng thư mục log, bạn đoán ra gì?

Gõ trong terminal — đoạn cố ý sai, đừng chạy y nguyên:

```bash
# máy chủ mới, chưa có thư mục game
mkdir game/logs
```

**Đoán trước khi chạy — Bạn đoán lệnh này ra gì?**

- A. `Tạo cả game lẫn logs`
- B. `Chỉ tạo thư mục game`
- C. `Lỗi khi chạy`

Kết quả:

```text
mkdir: cannot create directory
'game/logs': No such file or directory
```

Đáp án đúng: **C**.

Lỗi, vì chưa có thư mục game; hai ký tự nào cứu?

### THÊM HAI KÝ TỰ — Cờ -p tạo luôn thư mục cha

Đó là cờ p: thiếu thư mục cha thì tạo, có rồi vẫn im.

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

Chạy lại trăm lần vẫn êm, gạch đầu cho app lên production ngày tám mươi.

### CHÉP RỒI DỜI — Chép dự phòng rồi dời đi

Giờ touch tạo file cấu hình rỗng. Mẹo chép dự phòng: cặp ngoặc nhọn nhân đôi tên file, bản thứ hai thêm đuôi bak.

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

Còn mv bê bản đó vào thư mục log.

### Ý chính — KHO CỦA BẠN — Kho sách trên máy chủ

Vậy như kho sách: đóng kệ, photo, bê kệ khác. Đích chưa có thì mv thành đổi tên. Chỉ gãy ở rm: nghiền luôn, Linux không có thùng rác. Thư mục thì thêm cờ r.

- **mkdir -p** — đóng kệ, kèm kệ cha
- **touch, cp** — file rỗng, photo một bản
- **mv** — bê sang kệ, hoặc đổi tên
- **rm, rm -r** — xóa file, xóa cả thư mục

Ghi nhớ nhanh: rm không thùng rác · -f ép xóa, không hỏi · ls trước rồi mới rm

### LỖI HAY GẶP — Thừa một dấu cách

Khoan, cờ f là ép xóa: thừa một dấu cách là sạch home.

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

Máy chỉ than không xóa được home, vì bên trong đã sạch. An toàn: ls đúng đường dẫn đó trước, rồi mới xóa.

## Tóm lại

Tóm lại: cờ p giữ script sống, xóa thì nhìn trước.

## Câu đố hôm nay

ls kho in ra gì? Đoán trước, rồi chạy thử. Đáp án ở Ngày 3.

```bash
mkdir -p kho/logs kho/backup
mv kho/logs kho/backup
ls kho
```

## Bài tập

Tạo game/{src,logs,backup} bằng một lệnh mkdir -p, chép một file vào backup, đổi tên nó thành ngay-03.bak bằng mv.
