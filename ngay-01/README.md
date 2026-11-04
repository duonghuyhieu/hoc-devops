# Ngày 1 · Terminal và đường dẫn

DevOps 80 ngày · 1. Sống trong terminal

## Bạn học gì

Terminal và đường dẫn: pwd, ls, cd; đường dẫn tuyệt đối và tương đối, ~ và .. (trên Windows học qua WSL)

## Code trong video

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

### BẠN ĐANG Ở ĐÂU? — Hỏi máy trước đã

Gõ trong terminal:

```bash
pwd
```

Kết quả:

```text
/var/log
```

### VỀ NHÀ RỒI ĐI — Đổi chỗ đứng

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

### LÙI VÀ NHẢY — Lùi một cấp hay nhảy thẳng

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

## Câu đố hôm nay

pwd in ra gì? Đoán trước, rồi chạy thử. Đáp án ở Ngày 2.

```bash
cd ~/du-an/shop
cd ../..
pwd
```

## Bài tập

Từ home: cd /var/log, cd ~, rồi cd - ; mỗi bước gõ pwd.
