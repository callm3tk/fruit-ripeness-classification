# 🍎 Fruit Ripeness Classification

## � Giới thiệu
Dự án **Fruit Ripeness Classification** sử dụng Deep Learning (Convolutional Neural Network - CNN) để phân loại độ chín của trái cây từ hình ảnh. Mô hình được xây dựng bằng TensorFlow/Keras và được huấn luyện trên tập dữ liệu hình ảnh được chia thành các lớp phân loại khác nhau (ví dụ: chưa chín, đang chín, quá chín).

Dự án này minh họa toàn bộ quy trình Machine Learning từ xử lý dữ liệu, xây dựng mô hình, cho đến đánh giá hiệu suất.

---

## 🎯 Mục tiêu

- ✅ Xây dựng mô hình CNN để phân loại độ chín của trái cây  
- ✅ Áp dụng các kỹ thuật xử lý hình ảnh (Image Preprocessing)  
- ✅ Huấn luyện mô hình Deep Learning với callbacks tối ưu  
- ✅ Đánh giá hiệu suất mô hình bằng các chỉ số phù hợp  
- ✅ Sinh kết quả phân loại trên tập Test  

---

## 🛠️ Công nghệ sử dụng

| Công nghệ | Phiên bản | Mục đích |
|-----------|----------|---------|
| Python | 3.8+ | Ngôn ngữ lập trình chính |
| TensorFlow | Latest | Framework Deep Learning |
| Keras | Built-in TF | API xây dựng mô hình Neural Network |
| NumPy | 1.26.4 | Xử lý mảng số học |
| Pandas | 2.2.2 | Xử lý dữ liệu dạng bảng |
| Scikit-learn | 1.4.2 | Công cụ Machine Learning (metrics, preprocessing) |
| Matplotlib | 3.8.4 | Vẽ biểu đồ và trực quan hóa |
| Seaborn | 0.13.2 | Trực quan hóa thống kê |
| Pillow (PIL) | Implicit | Xử lý hình ảnh |
| Jupyter | 1.0.0 | Môi trường phát triển interactiv |

---

## 🔄 Quy trình thực hiện

### 1️⃣ Data Loading
- Tải hình ảnh từ các thư mục con (mỗi thư mục đại diện một lớp)
- Chuẩn hóa kích thước hình ảnh về (128, 128, 3)
- Chuẩn hóa giá trị pixel về [0, 1]

### 2️⃣ Data Splitting
- Chia dữ liệu train/val/test
- Train: 80% từ dataset gốc
- Validation: 20% từ dataset gốc
- Test: Tập test riêng

### 3️⃣ Model Architecture
- Xây dựng CNN với các lớp:
  - Convolutional layers với ReLU activation
  - MaxPooling layers để giảm chiều
  - Dropout layers để tránh overfitting
  - Dense layers và Softmax output

### 4️⃣ Training
- Sử dụng Adam optimizer
- Loss function: Categorical Crossentropy
- Callbacks: EarlyStopping, ModelCheckpoint, ReduceLROnPlateau

### 5️⃣ Evaluation
- Đánh giá trên tập Test
- Hiển thị Classification Report
- Confusion Matrix
- Visualization các dự đoán sai

---

## 📁 Cấu trúc dự án

```
Fruit_Ripeness_Classification/
│
├── Fruit_Ripeness_Classification.ipynb  # Notebook chính
├── README.md                             # File này
├── requirements.txt                      # Dependencies
├── data/                                 # Thư mục chứa dữ liệu
│   ├── Train/
│   │   ├── Class_1/
│   │   ├── Class_2/
│   │   └── ...
│   └── Test/
│       ├── Class_1/
│       ├── Class_2/
│       └── ...
└── images/                               # Thư mục lưu biểu đồ, kết quả
```

---

## 🚀 Hướng dẫn chạy

### Yêu cầu hệ thống
- Python 3.8 hoặc cao hơn
- pip hoặc conda
- Ít nhất 4GB RAM (khuyến khích 8GB+)
- GPU (NVIDIA CUDA) khuyến nghị để tăng tốc độ huấn luyện

### Bước 1: Clone hoặc tải repository
```bash
# Nếu dùng git
git clone https://github.com/callm3tk/fruit-ripeness-classification.git
cd fruit-ripeness-classification

# Hoặc tải file zip và giải nén
```

### Bước 2: Tạo môi trường ảo (Optional nhưng khuyến nghị)
```bash
# Dùng venv
python -m venv venv
venv\Scripts\activate  # Trên Windows
source venv/bin/activate  # Trên macOS/Linux

# Hoặc dùng conda
conda create -n fruit_ripeness python=3.9
conda activate fruit_ripeness
```

### Bước 3: Cài đặt dependencies
```bash
pip install -r requirements.txt
```

### Bước 4: Chuẩn bị dữ liệu
- Tạo thư mục `data/Train/` và `data/Test/`
- Sắp xếp ảnh theo cấu trúc thư mục theo lớp (Class-based folders)
- Ví dụ:
  ```
  data/Train/
    ├── unripe/
    ├── ripe/
    └── overripe/
  ```

### Bước 5: Chạy Jupyter Notebook
```bash
jupyter notebook Fruit_Ripeness_Classification.ipynb
```

---

## 📊 Kết quả mong đợi

- **Accuracy trên Test set**: 85-95% (tuỳ vào chất lượng dataset)
- **Confusion Matrix**: Hiển thị ma trận nhầm lẫn giữa các lớp
- **Classification Report**: Chi tiết Precision, Recall, F1-score
- **Visualization**: Hình ảnh dự đoán đúng và sai

---

## 🔧 Tuning và Cải thiện

Để cải thiện hiệu suất mô hình:

1. **Data Augmentation**: Áp dụng rotation, flip, zoom để tăng dataset
2. **Model Architecture**: Thử các mô hình pre-trained như ResNet50, MobileNet
3. **Hyperparameter Tuning**: Điều chỉnh learning rate, batch size, epochs
4. **Class Imbalance**: Nếu dataset không cân bằng, dùng class weights
5. **Cross-validation**: Sử dụng K-Fold Cross-Validation

---

## 📚 Tài liệu tham khảo

- [TensorFlow/Keras Documentation](https://www.tensorflow.org/api_docs)
- [Scikit-learn Metrics](https://scikit-learn.org/stable/modules/model_evaluation.html)
- [Image Classification Best Practices](https://www.tensorflow.org/tutorials/images/classification)

---

## 👨‍💻 Tác giả

Phát triển bởi [Tên của bạn]

---

## 📝 License

Dự án này được phát hành dưới license MIT. Xem file LICENSE để chi tiết.

---

## ❓ Hỗ trợ

Nếu gặp lỗi hoặc có câu hỏi:
- Mở GitHub Issue
- Kiểm tra các lỗi phổ biến trong troubleshooting
- Liên hệ qua email: [your-email@example.com]