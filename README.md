# DCGAN FashionMNIST

Dự án sử dụng Deep Convolutional GAN (DCGAN) để sinh ảnh thời trang mới dựa trên tập dữ liệu FashionMNIST gồm 28x28 ảnh xám 10 loại quần áo cơ bản. Dự án giúp bạn hiểu cách GAN tạo ra dữ liệu mới từ nhiễu và thực hành xây dựng, huấn luyện GAN với PyTorch.

---

## Kiến trúc mô hình

- **Generator (G):** Biến vector nhiễu z_dim=100 thành ảnh 28x28. Dùng nhiều lớp Linear và hàm kích hoạt LeakyReLU để tăng tính phi tuyến, đầu ra chuẩn hóa [-1, 1] với Tanh.
- **Discriminator (D):** Phân biệt ảnh thật và giả, nhận đầu vào là ảnh flatten 784 chiều, đầu ra xác suất [0,1] với Sigmoid.
- **Loss:** Binary Cross Entropy (BCELoss) cho cả hai mạng, tối ưu hóa bằng Adam với lr=0.0002 và betas=(0.5,0.999).
- **Huấn luyện:** D alternately học phân biệt real/fake, G học đánh lừa D. In loss mỗi epoch, sinh ảnh mẫu mỗi 5 epoch để theo dõi tiến bộ.

---

## Hình ảnh kết quả

Dưới đây là các grid 25 ảnh mẫu được sinh ra ở các giai đoạn huấn luyện:

<div align="center">

<table>
  <tr>
    <td align="center">
      <img src="https://github.com/HitDrama/DCgan-Fashionmnist-Generator/blob/main/static/epoch5-10.png" alt="Epoch 1-10" width="230"/>
      <br/>
      <b>Epoch 1–10</b>
    </td>
    <td align="center">
      <img src="https://github.com/HitDrama/DCgan-Fashionmnist-Generator/blob/main/static/epoch15-20.png" alt="Epoch 11-20" width="230"/>
      <br/>
      <b>Epoch 11–20</b>
    </td>
  </tr>
  <tr>
    <td colspan="2" align="center">
      <img src="https://github.com/HitDrama/DCgan-Fashionmnist-Generator/blob/main/static/epoch25-30.png" alt="Epoch 21-30" width="480"/>
      <br/>
      <b>Epoch 21–30</b>
    </td>
  </tr>
</table>

</div>




---

## Build & Dev

**Người thực hiện:**  
> Đặng Tố Nhân

---

*Clone code, chạy thử, chỉnh tham số, hoặc mở rộng mô hình tuỳ ý bạn!*

