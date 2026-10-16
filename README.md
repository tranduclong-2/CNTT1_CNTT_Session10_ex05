# PHẦN 1. PHÂN TÍCH BÀI TOÁN

## 1. Xác định Input và Output

| Thành phần | Nội dung |
|---|---|
| Input (Đầu vào) | Nhiệt độ, độ ẩm không khí và độ ẩm đất từ cảm biến |
| Process (Xử lý) | Raspberry Pi xử lý dữ liệu, so sánh với ngưỡng cài đặt |
| Output (Đầu ra) | Điều khiển relay bật/tắt máy bơm và ghi nhật ký |

## 2. Sơ đồ phối hợp phần cứng

![Sơ đồ Smart-Farm: cảm biến DHT22 và cảm biến độ ẩm đất gửi dữ liệu đến Raspberry Pi, sau đó Raspberry Pi điều khiển GPIO, relay và máy bơm](https://mermaid.ink/img/pako:eJyrVkrOT0lVslJKy8kvT85ILCpRCHGJyVNQcIyOUXJ-uGtxrkJS5sNd-_MUXDxCjIxilGIVdHXtFJyBskGJxQVJqUVFlQoBmQr6CsH5zkBZkFYndK1HJj7cPVPh4a6VuSDmrqUlcGNAyp3BTBeQpoxjG44tzEtXKCk6vCYvQyGgsiQjP89KwTPAX0FbwcXTOxxqgwtYiytQi3uApz9U0BUs6AZyWWpOYiVU1A0s6g4U9T28sFIh6djCXKCMko5SbmpRbmJmipJVtVJJRmouKAxSUtMSS3NKlGprAXKEYJ8)

- SoC: Hệ thống trên một chip, tích hợp CPU và các thành phần điều khiển.
- IPO: Quy trình nhận dữ liệu, xử lý dữ liệu và tạo đầu ra.
- DIKW: Mô hình chuyển dữ liệu thành thông tin, tri thức và quyết định.

# PHẦN 2. README.MD HOÀN CHỈNH

# 🚀 Smart-Farm – Hệ thống trang trại thông minh

## 1. Mô tả dự án

**Smart-Farm** là hệ thống IoT hỗ trợ người nông dân tại trang trại Lan giám sát môi trường và tự động điều khiển tưới cây.

Hệ thống sử dụng Raspberry Pi, cảm biến và chương trình Python để thu thập dữ liệu, xử lý thông tin và hỗ trợ chăm sóc cây trồng.

## 2. Sơ đồ hệ thống

![Sơ đồ kết nối hệ thống Smart-Farm gồm DHT22, cảm biến độ ẩm đất, Raspberry Pi, GPIO, relay và máy bơm](https://mermaid.ink/img/pako:eJyrVkrOT0lVslJKy8kvT85ILCpRCHGJyVNQcIyOUXJ-uGtxrkJS5sNd-_MUXDxCjIxilGIVdHXtFJyBskGJxQVJqUVFlQoBmQr6CsH5zkBZkFYndK1HJj7cPVPh4a6VuSDmrqUlcGNAyp3BTBeQpoxjG44tzEtXKCk6vCYvQyGgsiQjP89KwTPAX0FbwcXTOxxqgwtYiytQi3uApz9U0BUs6AZyWWpOYiVU1A0s6g4U9T28sFIh6djCXKCMko5SbmpRbmJmipJVtVJJRmouKAxSUtMSS3NKlGprAXKEYJ8)

Quy trình hoạt động:

1. Cảm biến thu thập dữ liệu môi trường.
2. Raspberry Pi tiếp nhận và xử lý dữ liệu.
3. Chương trình kiểm tra các điều kiện tưới.
4. GPIO gửi tín hiệu đến relay.
5. Relay điều khiển máy bơm tưới cây.
6. Hệ thống ghi nhật ký hoạt động.

## 3. Hướng dẫn cài đặt

### Bước 1: Chuẩn bị thiết bị

- Raspberry Pi đã cài hệ điều hành.
- Cảm biến DHT22 đo nhiệt độ và độ ẩm không khí.
- Cảm biến độ ẩm đất.
- Module relay và máy bơm phù hợp.
- Dây nối, nguồn điện và thẻ nhớ.

### Bước 2: Cài đặt môi trường

Mở Terminal trên Raspberry Pi và chạy:

```bash
sudo apt update
sudo apt install -y python3 python3-venv python3-pip git
```

Tạo thư mục dự án và môi trường Python:

```bash
mkdir smart-farm
cd smart-farm
python3 -m venv .venv
source .venv/bin/activate
```

Nếu dự án đã có file `requirements.txt`, cài đặt thư viện:

```bash
python -m pip install -r requirements.txt
```

### Bước 3: Chạy chương trình

Sau khi đã tạo file `main.py` và cấu hình thiết bị, chạy:

```bash
python main.py
```

Lưu ý: Các thư viện, chân GPIO và cấu hình phần cứng cần phù hợp với mẫu Raspberry Pi đang sử dụng.

## 4. Tính năng hệ thống

- [x] Thu thập nhiệt độ và độ ẩm không khí bằng DHT22.
- [x] Sử dụng Raspberry Pi làm bộ xử lý trung tâm.
- [x] Xử lý dữ liệu theo mô hình IPO.
- [ ] Kết nối cảm biến độ ẩm đất.
- [ ] Tự động bật/tắt máy bơm theo ngưỡng cài đặt.
- [ ] Ghi nhật ký hoạt động.
- [ ] Kiểm tra hệ thống khi cảm biến bị lỗi.

## 5. Bảng thông số hệ thống

| Thành phần | Chức năng | Thông số/Ghi chú |
|---|---|---|
| Raspberry Pi | Xử lý dữ liệu | Máy tính nhúng sử dụng SoC |
| DHT22 | Đo nhiệt độ và độ ẩm không khí | Nhiệt độ khoảng -40 đến 80°C |
| Cảm biến độ ẩm đất | Đo độ ẩm đất | Chọn loại tương thích |
| GPIO | Gửi và nhận tín hiệu | Cấu hình theo sơ đồ chân |
| Relay | Điều khiển mạch máy bơm | Phù hợp điện áp và dòng tải |
| Máy bơm | Tưới cây | Dùng nguồn điện phù hợp |
| Python | Xử lý dữ liệu | Chương trình điều khiển |

## 6. Nguyên lý hoạt động theo mô hình IPO

IPO gồm ba thành phần:

- **Input:** Nhận nhiệt độ, độ ẩm không khí và độ ẩm đất từ cảm biến.
- **Process:** Raspberry Pi xử lý dữ liệu và so sánh với ngưỡng đã cài đặt.
- **Output:** Điều khiển relay để bật hoặc tắt máy bơm.

Ví dụ:

Cảm biến phát hiện đất có độ ẩm 25%. Nếu ngưỡng tưới được cài đặt là 40%, hệ thống có thể bật máy bơm. Khi độ ẩm đạt mức phù hợp, hệ thống sẽ tắt máy bơm.

Nhiệt độ cao không nên là điều kiện duy nhất để quyết định tưới cây.

## 7. Chu kỳ Fetch – Decode – Execute

Khi CPU thực hiện lệnh trong chương trình, quá trình cơ bản gồm ba giai đoạn:

> **Fetch (Lấy lệnh):** CPU lấy lệnh cần thực hiện từ bộ nhớ.
>
> **Decode (Giải mã):** CPU phân tích lệnh để xác định thao tác cần thực hiện.
>
> **Execute (Thực thi):** CPU thực hiện thao tác tương ứng, chẳng hạn tính toán hoặc kiểm tra điều kiện.

Chu kỳ này lặp lại trong quá trình CPU thực thi chương trình. Tín hiệu bật máy bơm là kết quả của chương trình điều khiển và phần cứng, không phải CPU trực tiếp cấp điện cho máy bơm.

## 8. Mô hình kim tự tháp DIKW

DIKW mô tả quá trình chuyển dữ liệu thô thành quyết định có ích.

```text
              /\
             /  \
            / TRÍ TUỆ \
           / Quyết định \
          /--------------\
         /    TRI THỨC    \
        /  Hiểu điều kiện  \
       /------------------\
      /    THÔNG TIN       \
     / Dữ liệu có ý nghĩa   \
    /----------------------\
   /       DỮ LIỆU          \
  / Nhiệt độ, độ ẩm đo được  \
 /__________________________\
```

Ví dụ tại trang trại Lan:

| Cấp độ | Ví dụ |
|---|---|
| Data (Dữ liệu) | Nhiệt độ 34°C, độ ẩm đất 25% |
| Information (Thông tin) | Nhiệt độ cao, đất đang khô |
| Knowledge (Tri thức) | Độ ẩm đất thấp hơn ngưỡng tưới đã cài đặt |
| Wisdom (Trí tuệ) | Quyết định bật máy bơm và kiểm tra lại độ ẩm |

DIKW giúp hệ thống chuyển dữ liệu cảm biến thành thông tin và hỗ trợ đưa ra hành động phù hợp.

## 9. Lưu ý và xử lý sự cố

### Trường hợp RAM gần đầy do nhật ký

Nhật ký thường được lưu trên ổ đĩa. Tuy nhiên, nếu chương trình giữ quá nhiều nội dung nhật ký trong RAM hoặc bộ nhớ đệm, hệ thống có thể thiếu bộ nhớ.

### Bước 1: Kiểm tra RAM

```bash
free -h
```

### Bước 2: Kiểm tra tiến trình sử dụng RAM

```bash
top
```

### Bước 3: Kiểm tra dung lượng nhật ký

```bash
du -sh /var/log
```

### Bước 4: Giới hạn nhật ký

- Cấu hình `logrotate` để giới hạn kích thước và thời gian lưu nhật ký.
- Ghi nhật ký theo từng phần thay vì giữ toàn bộ nội dung trong RAM.
- Kiểm tra chương trình nào sử dụng nhiều bộ nhớ trước khi xử lý.
- Không xóa tùy tiện tệp hệ thống.

### Bước 5: Dọn nhật ký hệ thống khi cần

Kiểm tra dung lượng journal:

```bash
sudo journalctl --disk-usage
```

Xóa các bản ghi journal đã lưu trữ cũ hơn 7 ngày:

```bash
sudo journalctl --vacuum-time=7d
```

Lưu ý: Lệnh trên dọn nhật ký đã lưu trữ trên ổ đĩa, không trực tiếp giải phóng RAM. Cần xác định nguyên nhân trước khi xử lý.

**Không xóa hàng loạt tệp trong `/var/log` và không khởi động lại hệ thống khi máy bơm chưa ở trạng thái an toàn.**

## 10. An toàn vận hành

- Kiểm tra dây nối trước khi cấp nguồn.
- Không nối máy bơm trực tiếp vào chân GPIO.
- Sử dụng relay hoặc mạch điều khiển phù hợp với điện áp và dòng tải.
- Cài đặt ngưỡng tưới phù hợp với loại cây.
- Khi cảm biến lỗi, ưu tiên đưa máy bơm về trạng thái an toàn.
- Kiểm tra thiết bị thực tế trước khi vận hành tự động liên tục.

## 11. Kết luận

Smart-Farm kết hợp IoT, SoC, IPO và DIKW để hỗ trợ giám sát môi trường và tự động hóa tưới cây. README giúp người sử dụng hiểu cấu trúc hệ thống, cách cài đặt, nguyên lý hoạt động và cách xử lý sự cố cơ bản.

# PHẦN 3. KIỂM THỬ TÌNH HUỐNG RAM ĐẦY

| Tình huống | Cách xử lý |
|---|---|
| RAM gần đầy | Dùng `free -h` và `top` để kiểm tra |
| Nhật ký chiếm nhiều dung lượng ổ đĩa | Kiểm tra bằng `du -sh /var/log` |
| Chương trình giữ quá nhiều nhật ký trong RAM | Giới hạn bộ đệm, ghi theo từng phần |
| Journal chiếm nhiều ổ đĩa | Kiểm tra trước khi dọn các bản ghi cũ |
| Máy bơm đang hoạt động khi xảy ra lỗi | Đưa hệ thống về trạng thái an toàn trước khi khởi động lại |

**Kết quả mong đợi:** Hệ thống tiếp tục hoạt động ổn định, hạn chế thiếu RAM, giữ lại nhật ký cần thiết và tránh gây mất an toàn cho máy bơm.
