#  BÀI TẬP LỚN - PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG
### Môn học: TEE0419

---

## Thông tin sinh viên

| Thông tin | Chi tiết |
|-----------|---------|
| **Họ và tên** | Tạ Phạm Đình Hòa |
| **Mã số sinh viên** | K225480106088 |
| **Lớp** | 58KTPM |
| **Môn học** | Phát triển ứng dụng trên thiết bị di động - TEE0419 |

---

# PHẦN 1: MIT APP INVENTOR

## Bước 1 — Tạo project mới

Truy cập [https://ai2.appinventor.mit.edu](https://ai2.appinventor.mit.edu), đăng nhập bằng tài khoản Google.  
Click **"New project"** → đặt tên `BaiTapLon_K225480106088` → click **OK**.

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/c84c92c7-8517-4fb4-a325-0993a0234605" />


---

## Bước 2 — Làm quen giao diện Designer

Sau khi tạo project, màn hình **Designer** hiện ra gồm 4 vùng chính:

- **Palette** (trái): Kho các component như Button, Label, TextBox, WebViewer... chia theo nhóm
- **Viewer** (giữa): Màn hình điện thoại ảo — kéo component vào đây để xây dựng giao diện
- **Components** (phải trên): Danh sách component đã thêm vào screen
- **Properties** (phải dưới): Thuộc tính của component đang chọn (text, màu, kích thước...)

**Cách kéo thả:** Nhấn giữ component trong Palette → kéo thả vào Viewer.  
**Cách thay đổi thuộc tính:** Click vào component → chỉnh trong bảng Properties bên phải.

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/8824de66-b8f5-4c68-99a1-70d848bd569c" />

---

## Bước 3 — Tạo đủ 3 Screen

Click dấu **"+"** trên thanh **Screens** để thêm screen mới.  
Tạo lần lượt: `Screen2`, `Screen3`.
<img width="826" height="618" alt="image" src="https://github.com/user-attachments/assets/eddc1ecb-1d4a-44dd-aecb-0b671b999af6" />


---

## Bước 4 — Thiết kế Screen1 (About)

Chọn **Screen1** → vào **Designer**, kéo thả các component sau vào Viewer:

| Component | Tên đặt | Thuộc tính |
|-----------|---------|-----------|
| Label | Label1 | Text: "Tạ Phạm Đình Hòa", FontSize: 20 |
| Label | Label2 | Text: "MSSV: K225480106088", FontSize: 16 |
| Label | Label3 | Text: "Lớp: K58.KTP", FontSize: 16 |
| Button | btnScreen2 | Text: "Gải Phương Trình" |
| Button | btnScreen3 | Text: "Trang Web" |

> Sau khi kéo thả xong, click từng Button → click **Rename** để đổi tên thành `btnScreen2`, `btnScreen3`.

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/8824de66-b8f5-4c68-99a1-70d848bd569c" />

---

## Bước 5 — Lập trình Blocks cho Screen1

Click nút **Blocks** (góc trên phải) để chuyển sang màn hình lập trình.

**Cách ghép block:**
- Click tên component bên trái (vd: `btnScreen2`) → kéo block `when btnScreen2.Click do` ra giữa
- Click **Control** → kéo block `open another screen screenName` thả vào trong
- Điền tên screen cần mở vào ô text

**Bản chất của việc kéo thả block:** Mỗi block đại diện cho một câu lệnh lập trình. Ghép block với nhau chính là đang viết code nhưng bằng hình ảnh trực quan — chỉ những block phù hợp kiểu dữ liệu mới khớp được với nhau, giúp tránh lỗi sai kiểu.

**Ưu điểm so với viết code:** Trực quan, không cần nhớ cú pháp, không bị lỗi typo (gõ sai chữ), dễ học cho người mới.  
**Nhược điểm:** Khó xây dựng logic phức tạp, khó tái sử dụng, không linh hoạt bằng code thực sự.

**Copy Paste Block — Backpack:**  Chuột phải vào block → "Add to Backpack" để lưu. Mở Backpack → kéo ra để dùng lại ở Screen khác hoặc project khác. Tương tự Ctrl+C / Ctrl+V nhưng dùng được xuyên màn hình.

```
when btnScreen2.Click → open another screen "Screen2"
when btnScreen3.Click → open another screen "Screen3"
```

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/20887e10-84a3-4ebb-8445-132c8491ebd4" />


---

## Bước 6 — Thiết kế Screen2 (Giải PT bậc 1)

Chuyển sang **Screen2** → **Designer**, kéo thả:

| Component | Tên đặt | Thuộc tính |
|-----------|---------|-----------|
| Label | Label1 | Text: "Nhập a (ax + b = 0)" |
| TextBox | txtA | Hint: "Nhập số a", NumbersOnly: bật |
| TextBox | txtB | Hint: "Nhập số b", NumbersOnly: bật |
| Button | btnGiai | Text: "Giải" |
| Label | lblKetQua | Text: "Kết quả hiển thị ở đây" |
| Button | btnBack | Text: "Quay lại" |

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/955364a5-b8bf-4c7c-ac4e-ece10bca43dd" />


---

## Bước 7 — Lập trình Blocks cho Screen2

**Thuật toán giải PT bậc 1 (ax + b = 0):**
- Nếu a = 0 → phương trình vô nghiệm (hoặc vô số nghiệm)
- Nếu a ≠ 0 → nghiệm x = −b / a

**Cách ghép block `then/else`:** Ô `then` và `else` chỉ nhận block **hành động** (statement), không nhận block giá trị trực tiếp. Vì vậy phải dùng `set lblKetQua.Text to` bên trong, sau đó mới gắn giá trị vào ô `to`.

```
when btnGiai.Click
  if txtA.Text = "0"
    then: set lblKetQua.Text → "Phuong trinh vo nghiem"
    else: set lblKetQua.Text → join "x = " + (0 - txtB.Text) / txtA.Text

when btnBack.Click → close screen
```

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/27be2388-8a31-4f21-af10-3f22ccb6f074" />


---

## Bước 8 — Thiết kế Screen3 (WebView)

Chuyển sang **Screen3** → **Designer**, kéo thả:

| Component | Tên đặt | Thuộc tính |
|-----------|---------|-----------|
| Button | btnBack | Text: "Quay lại" |
| WebViewer | WebViewer1 | HomeUrl: `https://k58kmt.tdh.io.vn?masv=K225480106088`, Width: Fill parent, Height: Fill parent |

Trang web `https://k58kmt.tdh.io.vn?masv=K225480106088` là trang web có sẵn của môn học, được thiết kế **responsive** — tự động co giãn phù hợp với màn hình điện thoại.

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/015617c7-00c4-42ce-b85b-c59f379fb583" />


---



## Bước 10 — Kết quả chạy thử MIT App Inventor

Kết nối điện thoại qua **MIT AI2 Companion** hoặc build APK qua **Build → Android App (.apk)**.

| Screen | Kết quả |
|--------|---------|
| Screen1 | Hiển thị thông tin, 2 nút chuyển màn hình |
| Screen2 | Nhập a=2, b=4 → x = -2.0 |
| Screen3 | Trang web môn học hiển thị đúng trên điện thoại |

<img width="870" height="1883" alt="image" src="https://github.com/user-attachments/assets/fca73a25-2f0a-4aa4-8826-ca63f0850c4c" />

<img width="870" height="1883" alt="image" src="https://github.com/user-attachments/assets/f68fd9af-619a-4555-b899-d9cc3bfa94b5" />

<img width="870" height="1883" alt="image" src="https://github.com/user-attachments/assets/e8155031-ce6b-4576-89ac-27513512b1ec" />


---

# PHẦN 2: ANDROID STUDIO

> *Phần này sẽ được cập nhật sau khi hoàn thành Android Studio*

---
