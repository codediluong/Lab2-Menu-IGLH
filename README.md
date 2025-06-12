# Lab2-Menu-IGLH
# Title
Image inverse transformation (Biến đổi cường độ ảnh) là phép biến đổi cường độ ảnh từ tối sang sáng và ngược lại.
# Công Nghệ Sử Dụng
Ngôn ngữ: Python

## Thư viện:

Pillow (PIL): xử lý ảnh cơ bản như đọc, chuyển đổi và lưu ảnh.

NumPy: xử lý mảng ảnh dạng ma trận.

Matplotlib: hiển thị ảnh.

imageio: đọc ảnh theo chuẩn imageio (nếu cần).

scipy: khai báo nhưng chưa dùng trong đoạn mã này.

## Thuật toán sử dụng
Biến đổi ảnh xám bằng phép nghịch đảo (Inversion).

Chuyển ảnh xám màu sang ảnh mới bằng công thức:
<code> im_2 = 255 - im1 </code>

## Giải thích cách hoạt động
1. ** Import thư viện
   Mở ảnh xám
![image](https://github.com/user-attachments/assets/99ad07fc-e287-4c55-8ba4-8b6994512d33)

2. ** Chuyển đổi sang mảng NumPy
Ảnh được chuyển đổi thành mảng NumPy cho các hoạt động theo từng pixel.
![image](https://github.com/user-attachments/assets/a104fba9-c937-49b3-a6b4-8f5466a394da)


3. ## Đảo ngược ảnh
Mỗi giá trị pixel được trừ đi 255 để tạo thành giá trị âm.
![image](https://github.com/user-attachments/assets/1ae27eb6-4c7a-4cb4-bf90-386c500c4168)


4. ** Chuyển đổi trở lại thành ảnh và hiển thị
Mảng đảo ngược được chuyển đổi trở lại thành ảnh PIL và hiển thị bằng cả PIL và matplotlib
![image](https://github.com/user-attachments/assets/22668c20-09a1-4cdf-9205-3f9b3d8c11f3)

# Title
Thay đổi chất lượng ảnh với Power law (Gamma-Correction)
Dùng để tăng chất lượng của ảnh
![image](https://github.com/user-attachments/assets/71998113-7808-437e-bc4e-4f28825257b1)
# Công Nghệ Sử Dụng

1. ** Import thư viện
   Mở ảnh xám

![image](https://github.com/user-attachments/assets/3f288f84-80b5-4178-8ed8-dfa762bef756)

2. ** Chuyển đổi sang mảng NumPy
Ảnh được chuyển đổi thành mảng NumPy cho các hoạt động theo từng pixel.
![image](https://github.com/user-attachments/assets/8534ac0a-983d-4eda-ba37-4db052d19094)

3. ** Cho gamma bằng 5
![image](https://github.com/user-attachments/assets/b85773a7-1964-451d-a975-b342fe582575)
Giá trị gamma càng lớn thì ảnh càng tối

4. ** Chuyển dữ liệu sang float
![image](https://github.com/user-attachments/assets/6b28a997-47ff-4b85-8d22-2281c3ed78d0)

5. ** Tìm giá trị lớn nhất trong ảnh
![image](https://github.com/user-attachments/assets/a183c07b-3ecc-401e-83e2-08e7ca90e9f0)

6. ** Chuẩn hóa giá trị pixel
Mỗi pixel chia cho giá trị lớn nhất
![image](https://github.com/user-attachments/assets/4df5da58-f150-4cf2-bccb-3ada55624653)

7. ** Tính lũy thừa gamma (log domain)
![image](https://github.com/user-attachments/assets/7ab60aa8-9319-40e0-9483-b7127ce4aa70)
Thực hiện phép logarit rồi nhân với gamma

8. ** Áp dụng hàm mũ và scale lại về [0, 255]
![image](https://github.com/user-attachments/assets/8913c597-92ca-4548-a2fd-48d4c8519d44)

9. ## Chuyển dữ liệu về dạng unit8 để tạo ảnh
![image](https://github.com/user-attachments/assets/4f138fd2-d170-4eb6-981c-1c324b9e7b1e)

10. ** Chuyển đổi trở lại thành ảnh và hiển thị
Mảng đảo ngược được chuyển đổi trở lại thành ảnh PIL và hiển thị bằng cả PIL và matplotlib
Ảnh gốc và ảnh đã hiệu chỉnh gamma được hiển thị để so sánh.
![image](https://github.com/user-attachments/assets/22668c20-09a1-4cdf-9205-3f9b3d8c11f3)

## Title
Thay đổi cường độ điểm ảnh với Log Transformation

1. ** Import thư viện
   Mở ảnh xám

![image](https://github.com/user-attachments/assets/0db34dff-7757-4ba7-a805-704d4021a811)


2. ** Chuyển đổi sang mảng NumPy
Ảnh được chuyển đổi thành mảng NumPy cho các hoạt động theo từng pixel.
3. ** Chuyển sang dữ liệu dạng float
![image](https://github.com/user-attachments/assets/425c722b-2324-45b8-8542-4b1033374724)

4 ** Tìm giá trị lớn nhất mảng bl
![image](https://github.com/user-attachments/assets/fd87afc6-4642-49cd-b25f-576a65027af3)

5 ** Thực hiện biến đổi logarit cho từng pixel:
![image](https://github.com/user-attachments/assets/61bedde5-b53f-41e9-856d-d8c233c5bb12)

 np.log(1 + bl): lấy logarit tự nhiên của từng giá trị pixel cộng 1 (tránh log(0))
 Chia cho log(1 + b2) để chuẩn hóa về [0, 1]
 Nhân với 128 để đưa về dải cường độ mong muốn (có thể thay đổi hệ số này)

6. ** Chuyển kết quả về dạng unit8 để tạo ảnh
![image](https://github.com/user-attachments/assets/08b3109a-2e90-41ed-a896-ccf7d696c620)

7. ** Hiện thị lại ảnh gốc và sau biến đổi logarit
![image](https://github.com/user-attachments/assets/edbb36b9-3784-449c-aa7a-4c153a0da3c3)

## Title
Histogram equalization
Histogram (lược đồ xám) là biểu đồ tần xuất thống kê số lần xuất hiện các mức sáng trong ảnh.
Mục đích là cải tiến độ tương phản hai vùng sáng tối của ảnh. Trong ảnh grayscale, giá trị intensive của ảnh nằm [0, L-1]. Ảnh càng tối khi giá trị đi vào vùng low gray, ảnh càng sáng khi
giá trị đi vào vùng high gray. Hàm sử dụng xác suất, CDF(Cumulative Distribution) để tính.

![image](https://github.com/user-attachments/assets/39a1176e-4b5c-4c65-888f-dac494dc35c0)

1. ** Import thư viện
2. ** Mở ảnh xám
3. ** Chuyển đổi sang mảng NumPy
Ảnh được chuyển đổi thành mảng NumPy cho các hoạt động theo từng pixel

![image](https://github.com/user-attachments/assets/c20a1e09-6ff3-4ee1-a784-cef674fd9d73)

4. ** Chuyển mảng 2D thành 1D
![image](https://github.com/user-attachments/assets/f5c42b1f-6140-4cdd-8d82-19dcbf8cfd7c)

5. ** Chuyển về ảnh và hiển thị
![image](https://github.com/user-attachments/assets/cd0bb624-a438-4ee1-9e53-51cea953f942)


## Title
 Thay đổi ảnh với Contrast Stretching
Tương tự nhu Histogram Equalization nhưng thay đổi giá trị pixel thay vì dùng xác suất, CDF
để tính như Histogram. 

![image](https://github.com/user-attachments/assets/a0f66589-7590-4ab4-bd70-23baea3983ad)

## Cách hoạt động
1. ** Import thư viện
2. ** Mở ảnh xám
3. ** Chuyển đổi sang mảng NumPy
Ảnh được chuyển đổi thành mảng NumPy cho các hoạt động theo từng pixel

![image](https://github.com/user-attachments/assets/c20a1e09-6ff3-4ee1-a784-cef674fd9d73)

4. ** Tìm giá trị pixel nhỏ nhất (a) và lớn nhất (b) trong ảnh
![image](https://github.com/user-attachments/assets/a02b20c8-5a1a-41e2-9e8d-9403ef20b7f7)

5. ** Chuyển về dạng float
![image](https://github.com/user-attachments/assets/d512dd5e-142b-4941-85ad-0db761b83e8b)

6. ** Nhân 255 để đưa về dải 0-255
![image](https://github.com/user-attachments/assets/becdcf3b-3c66-41ea-bf14-b7932cd0b52c)

7. ** Chuyển kết quả về ảnh và hiển thị
![image](https://github.com/user-attachments/assets/27cff1d7-734b-450c-b5a8-aacb65f28046)
























