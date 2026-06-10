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

---

# PHẦN 2: ANDROID STUDIO

## Giới thiệu

Android Studio là môi trường phát triển tích hợp (IDE) chính thức để xây dựng ứng dụng Android bằng ngôn ngữ Java. Khác với MIT App Inventor dùng kéo thả block, Android Studio viết code thực sự — linh hoạt hơn, mạnh hơn, phù hợp với ứng dụng phức tạp.

---

## Bước 1 — Tạo project Android Studio

Mở Android Studio → **New Project** → chọn **Empty Views Activity** → điền thông tin:

| Trường | Giá trị |
|--------|---------|
| Name | `BaiTapLon_TEE0419` |
| Package name | `com.example.baitaplon_tee0419` |
| Language | `Java` |
| Minimum SDK | `API 24` |

Click **Finish** và chờ Gradle sync xong.

<img width="1456" height="818" alt="image" src="https://github.com/user-attachments/assets/f653ad53-85c4-4aef-9ea7-93bdfb6b7e9a" />


---

## Bước 2 — Cấu trúc project

Sau khi tạo xong, project có cấu trúc:

```
app/
├── manifests/
│   └── AndroidManifest.xml     ← Khai báo app, quyền, Activity
├── java/
│   └── com.example.baitaplon_tee0419/
│       ├── MainActivity.java   ← Activity 1 (About)
│       ├── Activity2.java      ← Activity 2 (Giải toán + API)
│       ├── Activity3.java      ← Activity 3 (WebView)
│       └── ActivityTuDien.java ← App1 (Từ điển Assets)
└── res/
    ├── layout/
    │   ├── activity_main.xml
    │   ├── activity_main2.xml
    │   ├── activity_3.xml
    │   └── activity_tu_dien.xml
    ├── values/
    │   └── strings.xml         ← Lưu chuỗi văn bản (tránh hardcode)
    └── assets/
        └── vocabulary.json     ← Dữ liệu từ vựng cho App1
```

<img width="612" height="1075" alt="image" src="https://github.com/user-attachments/assets/0b0f287d-a952-4e3d-a5ad-fe901cb95a85" />
<img width="625" height="1078" alt="image" src="https://github.com/user-attachments/assets/54ae9cbb-ae4e-4920-9274-c240b938a809" />

---

## Bước 3 — AndroidManifest.xml

### AndroidManifest.xml mô tả gì?

File `AndroidManifest.xml` là **khai báo tổng thể** của ứng dụng với hệ thống Android, bao gồm:
- Tên app, icon, theme
- Danh sách các **Activity** (màn hình) trong app
- Các **quyền** (permissions) app cần sử dụng

### Khai báo quyền INTERNET

App cần quyền truy cập Internet để gọi API và hiển thị WebView. Khai báo trong Manifest:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

Nếu không khai báo, Android sẽ **chặn** mọi kết nối mạng và app bị crash.

### Khai báo 3 Activity

```xml
<activity android:name=".MainActivity" android:exported="true">
    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>
<activity android:name=".Activity2" />
<activity android:name=".Activity3" />
<activity android:name=".ActivityTuDien" />
```

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/b5060c15-50d6-4eaa-990b-4e83ca460f34" />


---

## Bước 4 — Vòng đời Activity (Activity Lifecycle)

Mỗi Activity trải qua các trạng thái:

```
onCreate() → onStart() → onResume() → [App đang chạy]
                                           ↓
                                       onPause() → onStop() → onDestroy()
```

### Tại sao có sẵn hàm `onCreate()`?

Android Studio tự sinh sẵn hàm `onCreate()` vì đây là hàm **bắt buộc phải có** — được gọi đầu tiên khi Activity được tạo ra. Đây là nơi:
- Gọi `setContentView()` để nạp giao diện XML
- Khởi tạo các biến, widget
- Thiết lập sự kiện (onClick...)

Nếu không có `onCreate()`, Activity sẽ không hiển thị được gì.

---

## Bước 5 — strings.xml và tham chiếu tài nguyên

### Tại sao không hardcode?

Thay vì gõ thẳng chuỗi vào XML:
```xml
<!-- ❌ Hardcode - khó bảo trì -->
<TextView android:text="Họ tên: Tạ Phạm Đình Hòa" />
```

Lưu vào `res/values/strings.xml` và dùng tham chiếu:
```xml
<!-- ✅ Tham chiếu -->
<TextView android:text="@string/ten_sv" />
```

### Cú pháp tham chiếu:
```
@<loại_tài_nguyên>/<tên>
```
Ví dụ: `@string/ten_sv`, `@color/primary`, `@drawable/icon`

### Ưu điểm:
- Thay đổi một chỗ, áp dụng toàn app
- Android tự động chọn giá trị đúng theo **ngôn ngữ** (LANGUAGE), **vùng** (LOCATION), **theme** (THEME) của thiết bị
- App có thể hỗ trợ đa ngôn ngữ (tiếng Việt/tiếng Anh) tự động

```xml
<resources>
    <string name="app_name">BaiTapLon_TEE0419</string>
    <string name="ten_sv">Họ tên: Tạ Phạm Đình Hòa</string>
    <string name="mssv">MSSV: K225480106088</string>
    <string name="lop">Lớp: 58KTPM</string>
    <string name="btn_giai_toan">Giải Phương Trình</string>
    <string name="btn_xem_web">Xem Trang Web</string>
</resources>
```
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/599f2b36-b0f3-483c-b3de-26a991704c45" />


---

## Bước 6 — Activity 1: About (MainActivity)

### Giao diện activity_main.xml

Dùng `LinearLayout` để xếp các component theo chiều dọc (`orientation="vertical"`), căn giữa (`gravity="center"`):

```xml
<LinearLayout
    android:orientation="vertical"
    android:gravity="center"
    android:padding="24dp">

    <TextView android:text="@string/ten_sv" android:textSize="20sp"/>
    <TextView android:text="@string/mssv" android:textSize="16sp"/>
    <TextView android:text="@string/lop" android:textSize="16sp"/>
    <Button android:id="@+id/btnGotoAct2" android:text="@string/btn_giai_toan"/>
    <Button android:id="@+id/btnGotoAct3" android:text="@string/btn_xem_web"/>
    <Button android:id="@+id/btnTuDien" android:text="Từ Điển Anh - Việt"/>
</LinearLayout>
```

**Đối tượng chứa LinearLayout:** Gộp các thành phần con lại theo cùng một quy luật sắp xếp. `orientation="vertical"` → xếp theo chiều dọc. `gravity="center"` → căn giữa màn hình.

### Code MainActivity.java

```java
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btnAct2 = findViewById(R.id.btnGotoAct2);
        Button btnAct3 = findViewById(R.id.btnGotoAct3);
        Button btnTuDien = findViewById(R.id.btnTuDien);

        // Cách 1: setOnClickListener dùng lambda
        btnAct2.setOnClickListener(v -> {
            Intent intent = new Intent(MainActivity.this, Activity2.class);
            startActivity(intent);
        });

        btnAct3.setOnClickListener(v -> {
            startActivity(new Intent(MainActivity.this, Activity3.class));
        });

        btnTuDien.setOnClickListener(v -> {
            startActivity(new Intent(MainActivity.this, ActivityTuDien.class));
        });
    }
}
```

**Tương tác với layout:**
- `findViewById(R.id.btnGotoAct2)` → lấy đối tượng Button từ layout XML
- `setOnClickListener` → đăng ký sự kiện click
- Để text hiển thị đúng LANGUAGE/THEME: dùng `@string/` thay vì hardcode

**2 cách xử lý sự kiện:**
1. `setOnClickListener(v -> { ... })` — viết thẳng trong Java (lambda)
2. `android:onClick="tenHam"` trong XML → khai báo hàm trong Activity
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/3bcf63a5-09e0-46e5-9dd2-ee9b433e9d1a" />


---

## Bước 7 — Activity 2: Giải PT bậc 1 + Gọi API

### Mô tả bài toán

Giải phương trình bậc 1: **ax + b = 0**
- Nếu a = 0, b = 0 → Vô số nghiệm
- Nếu a = 0, b ≠ 0 → Vô nghiệm  
- Nếu a ≠ 0 → x = -b/a

Sau khi giải xong → gửi kết quả lên API:
- URL: `https://k58kmt.tdh.io.vn/api`
- Method: POST, Content-Type: application/json
- Body: `{"app_by":"K225480106088", "input":{a,b}, "output":{ketluan, nghiem}}`
- Response: `{"ok":1, "stt":1234}`

### Giao diện activity_main2.xml

```xml
<LinearLayout android:orientation="vertical" android:padding="24dp">
    <TextView android:text="Giải phương trình bậc 1: ax + b = 0"/>
    <EditText android:id="@+id/etA" android:hint="Nhập hệ số a"
        android:inputType="numberDecimal|numberSigned"/>
    <EditText android:id="@+id/etB" android:hint="Nhập hệ số b"
        android:inputType="numberDecimal|numberSigned"/>
    <Button android:id="@+id/btnGiai" android:text="Giải"/>
    <TextView android:id="@+id/tvKetQua" android:text="Kết quả hiển thị ở đây"/>
</LinearLayout>
```

**`inputType="numberDecimal|numberSigned"`** → bàn phím số, cho phép nhập số âm (dấu `-`)

### Code Activity2.java — Giải toán

```java
private void giaiPhuongTrinh() {
    double a = Double.parseDouble(etA.getText().toString().trim());
    double b = Double.parseDouble(etB.getText().toString().trim());
    String ketLuan;
    double nghiem = 0;

    if (a == 0) {
        ketLuan = (b == 0) ? "Vô số nghiệm" : "Vô nghiệm";
    } else {
        nghiem = -b / a;
        ketLuan = "x = " + nghiem;
    }
    tvKetQua.setText(ketLuan);
    guiAPI(a, b, ketLuan, nghiem);
}
```

### Code Activity2.java — Gọi API

```java
// Gọi API trong Thread riêng — KHÔNG được gọi network trên Main Thread
private void guiAPI(double a, double b, String ketLuan, double nghiem) {
    new Thread(() -> {
        try {
            URL url = new URL("https://k58kmt.tdh.io.vn/api");
            HttpURLConnection conn = (HttpURLConnection) url.openConnection();
            conn.setRequestMethod("POST");
            conn.setRequestProperty("Content-Type", "application/json");
            conn.setDoOutput(true);

            // Tạo JSON body
            JSONObject input = new JSONObject();
            input.put("a", a); input.put("b", b);
            input.put("name", "hello tac ke");

            JSONObject output = new JSONObject();
            output.put("ketluan", ketLuan);
            output.put("nghiem", nghiem);

            JSONObject body = new JSONObject();
            body.put("app_by", "K225480106088");
            body.put("input", input);
            body.put("output", output);

            // Gửi request
            OutputStream os = conn.getOutputStream();
            os.write(body.toString().getBytes());
            os.close();

            // Đọc response
            BufferedReader br = new BufferedReader(
                new InputStreamReader(conn.getInputStream()));
            StringBuilder response = new StringBuilder();
            String line;
            while ((line = br.readLine()) != null) response.append(line);

            // Cập nhật UI phải dùng runOnUiThread
            String finalResp = response.toString();
            runOnUiThread(() ->
                Toast.makeText(this, "API: " + finalResp, Toast.LENGTH_SHORT).show()
            );
        } catch (Exception e) {
            e.printStackTrace();
        }
    }).start();
}
```

**Tại sao dùng Thread riêng?** Android không cho phép gọi mạng (network) trên Main Thread vì sẽ làm đơ giao diện. Phải dùng `new Thread()` để chạy nền, sau đó dùng `runOnUiThread()` để cập nhật UI.

![Activity2 giao diện](images/android_07_activity2_layout.png)
![Activity2 chạy thử](images/android_08_activity2_run.png)
![Activity2 gọi API thành công](images/android_09_activity2_api.png)

---

## Bước 8 — Activity 3: WebView

### Mô tả

Hiển thị trang web `https://k58kmt.tdh.io.vn?masv=K225480106088` bên trong app, không mở trình duyệt ngoài.

### Giao diện activity_3.xml

```xml
<LinearLayout android:orientation="vertical">
    <WebView
        android:id="@+id/webView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
</LinearLayout>
```

### Code Activity3.java

```java
public class Activity3 extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_3);

        WebView webView = findViewById(R.id.webView);

        // Bật JavaScript để trang web chạy đầy đủ
        webView.getSettings().setJavaScriptEnabled(true);

        // Mở link trong app, không mở browser ngoài
        webView.setWebViewClient(new WebViewClient());

        // Load trang web môn học
        webView.loadUrl("https://k58kmt.tdh.io.vn?masv=K225480106088");
    }
}
```

**`setWebViewClient(new WebViewClient())`** → khi click link trong trang web, vẫn mở trong app thay vì bật Chrome ra ngoài.

![Activity3 WebView](images/android_10_activity3_run.png)

---

## Bước 9 — App1: Từ Điển từ Assets (ActivityTuDien)

### Vấn đề đặt ra

Cần một app tra từ vựng tiếng Anh hoạt động **hoàn toàn offline**, không cần kết nối mạng.

### Giải pháp: Dữ liệu chuẩn bị trước trong Assets

Thư mục `assets/` trong Android Studio chứa các file đi kèm app khi cài đặt. Mọi file trong `assets/` đều được đóng gói vào file APK — app có thể đọc offline hoàn toàn.

**Lợi ích:**
- Hoạt động không cần mạng
- Tốc độ đọc nhanh (file local)
- Phù hợp: từ điển, hướng dẫn, tài liệu tham khảo

### Đặc thù dữ liệu

File `assets/vocabulary.json` — mảng JSON, mỗi phần tử gồm 2 trường:

```json
[
  {"word": "Hello", "meaning": "Xin chào"},
  {"word": "Goodbye", "meaning": "Tạm biệt"},
  ...
]
```

**Đặc thù:** Dữ liệu tĩnh, cấu trúc đơn giản (key-value), không thay đổi sau khi cài app.

### Cú pháp truy cập file trong Assets

```java
InputStream is = getAssets().open("vocabulary.json");
```

### Thuật toán xử lý dữ liệu

1. Đọc file JSON từ Assets bằng `AssetManager`
2. Parse chuỗi JSON thành `JSONArray`
3. Duyệt từng phần tử (vòng lặp for), lấy `word` và `meaning`
4. Ghép thành chuỗi hiển thị, đưa vào `ArrayList<String>`
5. Tìm kiếm realtime: dùng `adapter.getFilter().filter(keyword)` khi người dùng gõ

**Đây là thuật toán Linear Search** — duyệt tuần tự qua toàn bộ danh sách để lọc từ khớp với từ khóa tìm kiếm.

### Đối tượng hiển thị dữ liệu

- **`ListView`** — hiển thị danh sách cuộn được
- **`ArrayAdapter`** — cầu nối giữa dữ liệu (`ArrayList`) và `ListView`
- **`EditText`** + **`TextWatcher`** — ô tìm kiếm realtime

### Code ActivityTuDien.java

```java
// Đọc file từ Assets
private void docDuLieuTuAssets() {
    try {
        InputStream is = getAssets().open("vocabulary.json");
        byte[] buffer = new byte[is.available()];
        is.read(buffer);
        is.close();
        String json = new String(buffer, "UTF-8");

        // Parse JSON
        JSONArray arr = new JSONArray(json);
        for (int i = 0; i < arr.length(); i++) {
            JSONObject obj = arr.getJSONObject(i);
            String word = obj.getString("word");
            String meaning = obj.getString("meaning");
            danhSachGoc.add(word + "  →  " + meaning);
        }
    } catch (Exception e) {
        e.printStackTrace();
    }
}

// Tìm kiếm realtime
etSearch.addTextChangedListener(new TextWatcher() {
    @Override
    public void onTextChanged(CharSequence s, int start, int before, int count) {
        adapter.getFilter().filter(s); // Lọc danh sách theo từ khóa
    }
    // ... các hàm khác để trống
});
```

![App1 Assets JSON](images/android_11_assets_json.png)
![App1 ListView](images/android_12_tudien_run.png)
![App1 Tìm kiếm](images/android_13_tudien_search.png)

---

## Bước 10 — Kết quả chạy thử Android Studio

Nhấn **▶ Run** trên Android Studio, app chạy trên Emulator Pixel 6 API 37:

| Activity | Chức năng | Kết quả |
|----------|-----------|---------|
| MainActivity | About + 3 nút điều hướng | ✅ Hiển thị tên, MSSV, lớp |
| Activity2 | Giải PT bậc 1 + gọi API | ✅ Nhập a=1, b=3 → x=-3.0, API trả về `{ok:1}` |
| Activity3 | WebView trang web môn học | ✅ Trang web hiển thị đúng |
| ActivityTuDien | Từ điển + tìm kiếm offline | ✅ 20 từ vựng, tìm kiếm realtime |

![Kết quả MainActivity](images/android_14_main_run.png)
![Kết quả Activity2](images/android_15_giai_pt_run.png)
![Kết quả Activity3](images/android_16_webview_run.png)
![Kết quả App1 Từ điển](images/android_17_tudien_final.png)

---

