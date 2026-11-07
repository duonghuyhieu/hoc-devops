# Ngày 1 · Terminal và đường dẫn

> DevOps 80 ngày · 1. Sống trong terminal · video 1 phút 19 giây

## Bạn học gì

Terminal và đường dẫn: pwd, ls, cd; đường dẫn tuyệt đối và tương đối, ~ và .. (trên Windows học qua WSL)

## Bài học

_Đi theo đúng thứ tự video. Lời giảng là lời đọc trong video; code và kết quả là bản máy đã chạy thật._

### NGÀY 1 · TERMINAL VÀ ĐƯỜNG DẪN

Gõ trong terminal — đoạn cố ý sai, đừng chạy y nguyên:

```bash
# đọc log xong, giờ vào code shop
cd du-an/shop
```

Kết quả:

```text
bash: cd: du-an/shop: No such file or
directory
```

Hai giờ sáng shop sập, đọc log xong vào thư mục app — máy bảo không có. Thư mục vẫn nguyên, vậy sai ở đâu?

### Ý chính — CUỐI KHÓA LÀM ĐƯỢC — 80 ngày làm được gì

Đó mới là ngày một trong tám mươi, mỗi ngày một video. Đi từ dòng lệnh, qua Docker, tới kiểm thử và triển khai. Ngày cuối bạn tự đưa app lên chạy thật; gạch đầu: biết mình đứng đâu.

- **Terminal, bash** — tự động hóa việc lặp lại
- **Docker, Compose** — đóng gói, chạy nhiều dịch vụ
- **GitHub Actions** — test, build, deploy tự động
- **Kubernetes, Terraform** — chạy app, dựng hạ tầng, cảnh báo

Ghi nhớ nhanh: 80 ngày  · Video ngắn gõ theo được · Dự án cuối lên production

### BẠN ĐANG Ở ĐÂU? — Hỏi máy trước đã

Quay lại máy chủ: pwd in ra chỗ bạn đang đứng. Bạn đoán nó in gì?

Gõ trong terminal:

```bash
pwd
```

**Đoán trước khi chạy — Bạn đoán pwd in ra gì?**

- A. `/home/an`
- B. `/var/log`
- C. `/home/an/du-an/shop`

Kết quả:

```text
/var/log
```

Đáp án đúng: **B**.

Thư mục log: bạn chưa rời chỗ cũ nên máy tìm app trong đó.

### VỀ NHÀ RỒI ĐI — Đổi chỗ đứng

Vậy về nhà trước: dấu ngã là lối tắt tới home. Lệnh ls liệt kê quanh đó: có thư mục dự án.

Gõ trong terminal:

```bash
pwd
cd ~
ls
cd du-an/shop
pwd
```

Kết quả:

```text
/var/log
du-an  tai-lieu
/home/an/du-an/shop
```

Giờ pwd báo bạn đã ở trong shop.

### Ý chính — TUYỆT ĐỐI · TƯƠNG ĐỐI — Hai cách chỉ đường

Hóa ra có hai loại: tuyệt đối đi từ gốc, như địa chỉ đủ trên đơn. Tương đối như chỉ đường qua điện thoại: đúng khi biết shipper đứng đâu. Nhưng shipper còn hỏi lại, máy thì không — nên pwd trước.

- **/var/log** — tuyệt đối, đi từ gốc /
- **du-an/shop** — tương đối, tính từ chỗ đứng
- **~ và ..** — về home / lùi một cấp
- **pwd** — hỏi chỗ đứng trước khi đi

Ghi nhớ nhanh: Tuyệt đối địa chỉ đủ · Tương đối chỉ đường · pwd hỏi chỗ đứng

### LÙI VÀ NHẢY — Lùi một cấp hay nhảy thẳng

Thế còn lùi: hai dấu chấm lên thư mục cha.

Gõ trong terminal:

```bash
# Windows: gõ trong WSL (Ubuntu)
cd ..
pwd
cd /var/log
pwd
```

Kết quả:

```text
/home/an/du-an
/var/log
```

Đường tuyệt đối thì nhảy thẳng tới log, đứng đâu cũng được. Mẹo dân code: gõ vài chữ đầu rồi nhấn Tab, máy điền nốt. Windows thì gõ y hệt trong WSL.

## Tóm lại

Tóm lại: đi đâu cũng hỏi pwd trước. Giờ bạn biết vì sao đêm đó máy bảo không có.

## Câu đố hôm nay

pwd in ra gì? Đoán trước, rồi chạy thử. Đáp án ở Ngày 2.

```bash
cd ~/du-an/shop
cd ../..
pwd
```

## Bài tập

Từ home: cd /var/log, cd ~, rồi cd - ; mỗi bước gõ pwd.
