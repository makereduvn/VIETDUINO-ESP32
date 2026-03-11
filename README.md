# Mạch phát triển Vietduino ESP32
Vietduino ESP32 là mạch phát triển do MakerEDU nghiên cứu và sản xuất, dựa trên module ESP-WROOM-32E chính hãng Espressif. Bo mạch được thiết kế theo form factor Arduino, với hình dạng và cách bố trí chân tín hiệu tương đồng cao với chuẩn Arduino, giúp người dùng dễ dàng tiếp cận, học tập và phát triển ứng dụng.

Nhờ tích hợp vi điều khiển ESP32 hiệu năng cao, Vietduino ESP32 mang lại khả năng xử lý mạnh mẽ cùng kết nối Wi-Fi và Bluetooth BLE linh hoạt, phù hợp cho nhiều ứng dụng như IoT, AIoT, hệ thống điều khiển không dây, nghiên cứu nhúng và giáo dục STEM.

Vietduino ESP32 sử dụng mạch nguồn xung giảm áp hiệu suất cao, giúp hoạt động ổn định với dải điện áp đầu vào rộng và cung cấp dòng lớn cho các module ngoại vi. Bên cạnh đó, mạch còn được trang bị IC chuyển đổi USB–UART CH340 chính hãng và cơ chế tự động cách ly nguồn USB, giúp tăng độ ổn định và bảo vệ cổng USB của máy tính khi sử dụng nguồn ngoài.

Vietduino ESP32 là lựa chọn lý tưởng cho giáo dục STEM, phòng thí nghiệm, maker space, nghiên cứu và phát triển sản phẩm IoT.

## Ưu điểm nổi bật
- Tương thích hệ sinh thái Arduino
  - Thiết kế theo chuẩn form Arduino
  - Bố trí chân tín hiệu tương đồng với Arduino
  - Hỗ trợ môi trường phát triển Arduino IDE, ESP-IDF, MicroPython
- Hiệu năng xử lý mạnh mẽ
  - Sử dụng ESP32-D0WD-V3
  - CPU Xtensa LX6 dual-core 32-bit
  - Tốc độ lên tới 240 MHz
  - Bộ nhớ RAM lớn, phù hợp cho các ứng dụng IoT và xử lý dữ liệu
- Kết nối không dây tích hợp
  - Wi-Fi 802.11 b/g/n
  - Bluetooth 4.2 BR/EDR và BLE
  - Hỗ trợ nhiều giao thức IoT như MQTT, HTTP, WebSocket
- Mạch nguồn hiệu suất cao
  - Sử dụng nguồn xung buck converter
  - Hiệu suất chuyển đổi cao
  - Tỏa nhiệt thấp
  - Hỗ trợ điện áp đầu vào rộng 6 ~ 24VDC
  - Dòng đầu ra lớn cho các thiết bị ngoại vi
- Giao tiếp USB ổn định
  - IC USB–UART CH340 chính hãng
  - Nạp chương trình và giao tiếp Serial ổn định
- Bảo vệ cổng USB máy tính
  - Tích hợp chức năng tự động cách ly nguồn USB
  - Khi cấp nguồn ngoài qua VIN hoặc jack DC, nguồn USB sẽ được ngắt tự động

## Thông số kỹ thuật
- Vi điều khiển
  - Module: ESP-WROOM-32E (Espressif)
  - CPU: ESP32-D0WD-V3
  - Kiến trúc: Xtensa dual-core 32-bit LX6
  - Tốc độ xung nhịp: Lên đến 240 MHz
- Bộ nhớ
  - ROM: 448 KB
  - SRAM: 520 KB
  - RTC SRAM: 16 KB
  - SPI Flash: 4MB hoặc 16MB
- Nguồn vào
  - DC Jack / VIN: 6 ~ 24VDC
  - USB-C: 5VDC
- Nguồn ra
  - 5V: tối đa 1500 mA
  - 3.3V: tối đa 700 mA
- Wi-Fi
  - Chuẩn: 802.11 b/g/n
  - Tốc độ: tối đa 150 Mbps
  - Tần số: 2.4 GHz
- Bluetooth
  - Bluetooth 4.2 BR/EDR
  - Bluetooth Low Energy (BLE)
- Giao tiếp ngoại vi: SPI, UART, I2C,...
- IC USB-UART: CH340
- Ăng-ten: PCB antenna
- Thành phần trên bo mạch
  - Nút nhấn: Reset
  - LED: TX / RX / IO18
  - Cổng USB: USB-C
- Chuẩn header: Arduino Compatible

## Kích thước
![Vietduino ESP32](/extras/vietduino_esp32_1.png)

## Hướng dẫn sử dụng cơ bản với Arduino IDE
### Bước 1: Cài đặt Arduino IDE và cấu hình mạch
- Tải và cài đặt [Phần mềm Arduino IDE từ trang chủ Arduino](https://www.arduino.cc/en/software) phù hợp với hệ điều hành đang sử dụng.
- Sau khi cài đặt, chọn Tools → Board → Boards Manager, tìm từ khoá "esp32" để cài đặt cấu hình các mạch "esp32 by Espressif Systems".
![Vietduino ESP32](/extras/vietduino_esp32_3.png)
### Bước 2: Kết nối mạch với máy tính
- Kết nối Vietduino ESP32 với máy tính bằng cáp USB vào cổng USB-UART.
- Khi kết nối thành công, LED nguồn (ON) trên mạch sẽ sáng.
### Bước 3: Cài đặt driver CH340
- Vietduino ESP32 sử dụng IC CH340 để giao tiếp USB–UART.
- Thông thường Driver sẽ tự nhận trên hầu hết các hệ điều hành, nếu máy tính chưa nhận driver, [tải và cài đặt Driver CH343P tại đây.](https://www.wch-ic.com/downloads/CH341SER_ZIP.html)
### Bước 4: Cấu hình mạch trong Arduino IDE
Thực hiện các thiết lập sau trong Arduino IDE:
- Chọn loại board: Tools → Board → esp32 → ESP32 Dev Module
- Cấu hình các thông số cần thiết như Flash Size, Partititon Scheme (theo phiên bản bộ nhớ Flash bạn đang sử dụng), các thông số khác có thể để ở mặc định. _(Lưu ý mục Upload Speed với Windows có thể chọn tốc độ 921600, tuy nhiên với MacOS hoặc các hệ điều hành khác nếu báo lỗi thì nên chọn 115200)_
- Chọn cổng kết nối (Port): Tools → Port → chọn cổng tương ứng với Vietduino ESP32 (nếu chưa xác định được, hãy rút cáp USB và cắm lại để nhận diện cổng mới xuất hiện).
_Dưới đây là ví dụ cấu hình mạch Vietduino ESP32 phiên bản 16MB:_
![Vietduino ESP32](/extras/vietduino_esp32_4.png)
### Bước 5: Nạp chương trình thử nghiệm (Wifi Scan)
Sau khi cấu hình xong, bạn có thể nạp chương trình mẫu tại File → Examples → Wifi → WiFiScan để kiểm tra mạch, mạch có thiết kế chức năng nạp tự động nên không cần nhấn các nút Boot hoặc Reset.
![Vietduino ESP32](/extras/vietduino_esp32_5.png)

Chương trình này sẽ quét các mạng Wifi có sẵn trong khu vực và hiển thị lên Serial Monitor của Arduino.
![Vietduino ESP32](/extras/vietduino_esp32_6.png)
## Lưu ý sử dụng an toàn
- Không đặt mạch trên bề mặt kim loại dẫn điện
- Tránh môi trường:
  - Ẩm ướt
  - Nhiệt độ cao
  - Nhiều bụi dẫn điện
- Nên sử dụng với nguồn điện chất lượng tốt
- Luôn đảm bảo mạch:
  - Không bị chập mạch
  - Không đấu sai cực nguồn
  - Khi mạch được cấp nguồn ngoài, không rút/cắm USB liên tục trong lúc tải lớn đang hoạt động
- Nên ngắt nguồn ngoài trước khi:
  - Thay đổi đấu nối phần cứng
  - Kết nối lại với máy tính để nạp chương trình
 ## Hình ảnh sản phẩm
![Vietduino ESP32](/extras/vietduino_esp32_7.png)
![Vietduino ESP32](/extras/vietduino_esp32_8.png)








