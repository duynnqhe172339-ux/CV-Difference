# CV-Difference
1.Tải hai bức ảnh vào biến before và after

2.Chuyển đổi hai bức ảnh sang màu xám và lưu vào biến before_gray và after_gray

3.Tính chỉ số SSIM (Structural Similarity Index Measure) giữa hai bức ảnh xám để đánh giá mức độ tương đồng của chúng. Chỉ số này nằm trong khoảng [0,1] với 1 là hoàn toàn giống nhau. Kết quả được lưu vào biến score và diff. Biến diff chứa các giá trị khác biệt thực tế giữa hai bức ảnh và có kiểu dữ liệu là số thực trong khoảng [0,1]

4.Chuyển đổi biến diff sang kiểu dữ liệu là số nguyên 8 bit trong khoảng [0,255] để có thể sử dụng với OpenCV. Sau đó ghép ba kênh màu của diff lại để tạo thành biến diff_box

5.Phân ngưỡng biến diff để tạo ra biến thresh chứa các điểm ảnh có giá trị khác 0 (nghĩa là có sự khác biệt). Sau đó tìm các đường viền của các vùng khác biệt và lưu vào biến contours

6.Tạo ra một biến mask có kích thước bằng với bức ảnh before và có giá trị ban đầu là 0. Tạo ra một bản sao của bức ảnh after và lưu vào biến filled_after

7.Duyệt qua các đường viền trong biến contours và tính diện tích của chúng. Nếu diện tích lớn hơn 40, ta sẽ vẽ một hình chữ nhật bao quanh vùng khác biệt đó trên các bức ảnh before, after và diff_box với màu xanh lá. Ta cũng sẽ vẽ các đường viền đó trên biến mask với màu trắng và trên biến filled_after với màu xanh lá

8.Hiển thị các bức ảnh before, after, diff, diff_box, mask và filled_after lên màn hình. Chờ người dùng nhấn phím để kết thúc chương trình
