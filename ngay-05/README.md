# Ngày 5 · Tiến trình

DevOps 80 ngày · 1. Sống trong terminal

## Bạn học gì

Tiến trình: ps, kill; SIGTERM (xin dừng) và SIGKILL (giết ngay), vì sao không nên quen tay kill -9

## Code trong video

### NGÀY 5 · TIẾN TRÌNH

Gõ trong terminal:

```bash
ps -o pid,stat,cmd -C node
kill 4321  # SIGTERM, app có bắt
sleep 1
ps -o pid,stat,cmd -C node
```

Kết quả:

```text
    PID STAT CMD
   4321 Sl   node playlist.js
    PID STAT CMD
```

### ĐOẠN B — Thêm hai ký tự

Gõ trong terminal:

```bash
ps -o pid,stat,cmd -C node
kill -9 4321  # gửi SIGKILL
sleep 1
ps -o pid,stat,cmd -C node
```

Kết quả:

```text
    PID STAT CMD
   4321 Sl   node playlist.js
    PID STAT CMD
```

### BẮT SIGTERM — Dạy app nghe gõ cửa

Minh họa (playlist.js):

```text
process.on('SIGTERM', () => {
  fs.writeFileSync('playlist.json',
    JSON.stringify(playlist));
  console.log('luu xong, thoat');
  process.exit(0);
});
```

Kết quả:

```text
luu xong, thoat
```

### LỖI HAY GẶP — Trừ chín giữa lúc ghi

Gõ trong terminal — đoạn cố ý sai, đừng chạy y nguyên:

```bash
kill -9 4321  # lúc đang ghi file
node playlist.js
```

Kết quả:

```text
<anonymous_script>:1
[{"id":1},{"id":2},{"id":3}
SyntaxError: Expected ',' or ']' after
array element in JSON at position 27
(line 1 column 28)
```

## Đáp án câu đố Ngày 4

```bash
chmod 750 deploy.sh
ls -l deploy.sh
```

In ra: `-rwxr-x---`

## Câu đố hôm nay

Dòng «luu xong» có hiện? Đoán trước, rồi chạy thử. Đáp án ở Ngày 6.

```bash
# playlist.js đã bắt SIGTERM
kill -9 4321
```

## Bài tập

Chạy sleep 300 &, tìm PID bằng pgrep sleep, dừng bằng kill, kiểm lại bằng jobs.
