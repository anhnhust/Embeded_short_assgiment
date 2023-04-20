# Embeded_short_assgiment
# EmbIf - Exercise 1: Simple Control Loop
Sử dụng công Eclipse CDT và trình phỏng tạo QEMU để phát triển một dự án nhúng đơn giản, chạy trên hệ nhúng ARM, thực thi các công việc sau:
1. Định kỳ lấy dữ liệu từ một cảm biến (ví dụ đo nhiệt độ, độ ẩm);
2. Xử lý dữ liệu có được, xuất kết quả ra màn hình nhúng/LED và/hoặc đưa ra lệnh điều khiển đến một cổng giao tiếp (ví dụ điều khiển máy bơm, quạt gió).
Báo cáo gồm mã nguồn trên github và ảnh chụp screenshot cho thấy chương trình đã chạy.
# Giải quyết bài toán:
1. Giả sử rằng nhiệt độ thu thập từ cảm biến sẽ được lưu vào một mảng.
2. Khi chạy chương trình sẽ sử dụng "IF ELSE" để so sánh với ngưỡng ( ở bài này lấy ngưỡng là 30 độ C)
3. Đưa đến tín hiệu điều khiển bật tắt Quạt gió. Lớn hơn 30 độ sẽ bật quạt gió đồng thời bật LED xanh. Bé hơn hoặc bằng 30 độ sẽ tắt quạt gió và tắt LED.
```c
      // Print the current temperature
      trace_printf("Temperature: %d\n", temperature[seconds % 5]);

      // Check if the current temperature is above 30
      if (temperature[seconds % 5] > 30) {
        blink_led_on(); // Turn on the LED
        trace_puts("BAT QUAT GIO, LED XANH BAT!");
      } else {
        blink_led_off(); // Turn off the LED
        trace_puts("TAT QUAT GIO, LED XANH TAT!");
      }
 #Kết Quả
 ![Result](https://github.com/anhnhust/Embeded_short_assgiment/blob/main/src/result_embeded.JPG)
