## 🛠️ Các bước thực hiện

1. Cài đặt các công cụ cần thiết

```
sudo apt update && sudo apt install git python3 python3-pip -y
```

2. Clone repository SocialFish từ Githup:

```
git clone https://github.com/UndeadSec/SocialFish.git
```

3. Điều hướng vào thư mục SocialFish

```
cd ~/SocialFish
```
 4. Chạy file

```
python3 SocialFish.py eliot Ns369369
```
- Cần phải kích hoạt môi trường ảo trước khi chạy file:
  
```
source venv/bin/activate
```
---

<img width="949" height="480" alt="image" src="https://github.com/user-attachments/assets/876fe858-00b6-4a23-afcd-ef7e17a429ef" />

---

5. Truy cập link sau để vào giao diện công cụ

```
http://127.0.0.1:5000/neptune
```

<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/9bc0a309-ddf8-4144-93d3-a17f861b92ae" />

---


| Mục | Chức năng |
| --- | --------- |
| `Clone` | Nhập URL trang web bạn muốn giả mạo (VD: `https://facebook.com`) |
| `Redirection` | URL sẽ chuyển hướng người dùng sau khi nhập xong tài khoản (VD: `https://google.com`) |
| ⚡ Biểu tượng tia sét | Bắt đầu quá trình clone và khởi chạy server phishing |

| Tùy chọn | Mô tả |
| ------- | ----- |
| `Custom HTML` | Cho phép bạn viết lại giao diện HTML theo ý muốn |
| `Inject beef-xss` | Tích hợp framework tấn công XSS (pentest nâng cao) |

6. Gửi link đến nạn nhân

- Nội bộ: `http://127.0.0.1:5000`
- Qua Internet: Dùng [Ngrok](https://ngrok.com)

6. Theo dõi thông tin
- Log hiển thị ở terminal hoặc ngay trên giao diện web
