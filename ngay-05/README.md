# Ngày 5 · Tiến trình

> DevOps 80 ngày · 1. Sống trong terminal · video 1 phút 11 giây

## Bạn học gì

Tiến trình: ps, kill; SIGTERM (xin dừng) và SIGKILL (giết ngay), vì sao không nên quen tay kill -9

## Đáp án câu đố Ngày 4

```bash
chmod 750 deploy.sh
ls -l deploy.sh
```

In ra: `-rwxr-x---`

## Bài học

_Đi theo đúng thứ tự video. Lời giảng là lời đọc trong video; code và kết quả là bản máy đã chạy thật._

### NGÀY 5 · TIẾN TRÌNH

Hôm qua: chủ đủ quyền, nhóm đọc chạy, ngoài trống.

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

Gõ kill, app nhạc tắt, bảng trống. Thêm hai ký tự, app vẫn tắt mà playlist hỏng — ký tự nào?

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

Hóa ra là trừ chín, bảng vẫn trống y hệt. Ngày tám mươi tung bản mới, app cũ phải tắt êm bằng SIGTERM, không phải trừ chín.

### Ý chính — HAI TÍN HIỆU — kill = gửi tín hiệu

Đó là vì kill gửi SIGTERM, tín hiệu xin dừng. Như karaoke hết giờ: nhân viên gõ cửa, khách dọn đồ trả phòng. Trừ chín là SIGKILL: cúp điện, bài bỏ dở. Chỗ gãy: khách tự biết dọn, app thì không.

- **ps** — PID, trạng thái, lệnh đang chạy
- **kill PID** — gửi SIGTERM: xin dừng
- **kill -9 PID** — SIGKILL: giết ngay, không bắt được
- **bắt SIGTERM** — app tự dọn rồi mới thoát

Ghi nhớ nhanh: ps xem PID · SIGTERM xin dừng · SIGKILL giết ngay

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

Vậy app tự bắt SIGTERM, ghi nốt playlist rồi thoát. Thiếu đoạn này, Node tắt ngay. Docker cũng gõ cửa, mười giây sau mới cúp điện.

### LỖI HAY GẶP — Trừ chín giữa lúc ghi

Quay lại playlist hỏng: trừ chín trúng lúc đang ghi. Bật lại, bạn đoán ra sao?

Gõ trong terminal — đoạn cố ý sai, đừng chạy y nguyên:

```bash
kill -9 4321  # lúc đang ghi file
node playlist.js
```

**Đoán trước khi chạy — Bật lại app sẽ ra sao?**

- A. `Chạy bình thường`
- B. `Lỗi khi chạy`
- C. `Playlist trống`

Kết quả:

```text
<anonymous_script>:1
[{"id":1},{"id":2},{"id":3}
SyntaxError: Expected ',' or ']' after
array element in JSON at position 27
(line 1 column 28)
```

Đáp án đúng: **B**.

Lỗi khi chạy: file đứt giữa chừng. Nên kill thường trước, trừ chín khi treo cứng. Mẹo: pgrep cờ a hiện mã kèm lệnh, khỏi giết nhầm.

## Tóm lại

Tóm lại: kill thường để app dọn, trừ chín là đường cùng.

## Câu đố hôm nay

Dòng «luu xong» có hiện? Đoán trước, rồi chạy thử. Đáp án ở Ngày 6.

```bash
# playlist.js đã bắt SIGTERM
kill -9 4321
```

## Bài tập

Chạy sleep 300 &, tìm PID bằng pgrep sleep, dừng bằng kill, kiểm lại bằng jobs.
