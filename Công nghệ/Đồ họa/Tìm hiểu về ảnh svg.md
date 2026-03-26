Câu hỏi: bây giơ tớ lại tò mò về ảnh .svg, bình thường các định dạng ảnh khác như png hay jpg sẽ có các điểm màu dẫn tới chúng có giới hạn về kích thước và không thể phóng to mà vẫn giữ được độ sắc nét như svg nhỉ?

Đúng rồi đấy! Cậu đã nắm bắt được điểm mấu chốt nhất phân biệt giữa ảnh **Bitmap (Raster)** và ảnh **Vector** rồi.

Sự khác biệt này đến từ "ngôn ngữ" mà máy tính dùng để hiểu và hiển thị bức ảnh.

---

## 1. Tại sao JPG/PNG lại bị vỡ hình?
Các định dạng như **JPG, PNG, hay GIF** được gọi là ảnh **Raster (hoặc Bitmap)**.
* **Cấu tạo:** Chúng được tạo thành từ một lưới hàng triệu điểm màu nhỏ xíu gọi là **pixels**.
* **Hạn chế:** Khi cậu phóng to, máy tính đơn giản là kéo giãn các điểm pixel này ra. Vì không có thêm dữ liệu mới để lấp đầy khoảng trống, các cạnh sẽ trở nên răng cưa và hình ảnh bị mờ đi (hiện tượng "pixelated").



## 2. Tại sao SVG lại "vô hạn" về kích thước?
**SVG (Scalable Vector Graphics)** không lưu trữ các điểm màu. Thay vào đó, nó lưu trữ **các công thức toán học**.

* **Cấu tạo:** Một file SVG thực chất là một đoạn mã XML. Thay vì nói "điểm này màu đỏ", nó sẽ nói: "Hãy vẽ một hình tròn có bán kính $r$, tâm tại $(x, y)$ và đổ màu đỏ".
* **Khả năng co giãn:** Khi cậu phóng to một file SVG lên gấp 100 lần, máy tính chỉ cần tính toán lại công thức: $r \times 100$. Vì toán học là chính xác tuyệt đối, các đường nét luôn giữ được độ mượt mà và sắc nét ở bất kỳ kích thước nào, từ biểu tượng nhỏ trên điện thoại đến biển quảng cáo khổng lồ.

### Bảng so sánh nhanh

| Đặc điểm | Raster (JPG, PNG) | Vector (SVG) |
| :--- | :--- | :--- |
| **Đơn vị cơ bản** | Pixel (Điểm ảnh) | Path (Đường dẫn toán học) |
| **Phóng to** | Bị vỡ hình, mờ | Luôn sắc nét |
| **Dung lượng file** | Tăng theo độ phân giải | Phụ thuộc vào độ phức tạp của chi tiết |
| **Ứng dụng tốt nhất** | Ảnh chụp, phong cảnh | Logo, icon, biểu đồ, hình minh họa |

---

## 3. Một sự thật thú vị: Cậu có thể đọc được ảnh SVG
Vì SVG là mã nguồn, cậu hoàn toàn có thể mở một file SVG bằng Notepad và sửa màu sắc của nó chỉ bằng cách đổi mã màu (ví dụ từ `fill="red"` sang `fill="blue"`). Các trình duyệt web cực kỳ "yêu" SVG vì chúng nhẹ và có thể tương tác được bằng code.

Tuy nhiên, SVG có một "điểm yếu": Nó không thể dùng để lưu trữ những bức ảnh có chi tiết cực kỳ phức tạp như ảnh chụp chân dung, vì việc chuyển từng sợi tóc hay sắc thái da thành công thức toán học sẽ làm file nặng khủng khiếp và máy tính xử lý không nổi.

Cậu có muốn tớ giải thích thêm về cách người ta dùng code để tạo ra một hình tròn hay hình vuông trong file SVG không? Hay cậu muốn biết cách chuyển đổi giữa hai loại ảnh này?