# Lab 2 - Mạng Neural Tích Chập (CNN)

Tìm hiểu, xây dựng, huấn luyện và đánh giá các kiến trúc mạng CNN trên bộ dữ liệu hình ảnh món ăn Việt Nam VinaFood21.

## 👤 Thông tin sinh viên

| Thông tin | Chi tiết |
|---|---|
| **Họ và tên** | Đặng Nguyễn Tú Trinh |
| **MSSV** | 24521858 |
| **Lớp** | DS201.R11.1 |
| **Môn học** | DS201 - Deep Learning trong Khoa học Dữ liệu |

## 📂 Cấu trúc Repository

```text
lab2_dl/
│
├── BTTL.ipynb
│
├── BTVN.ipynb
│
├── outputs_lenet/
│
├── outputs_googlenet/
│
├── outputs_resnet18/
│
├── outputs_resnet50_hf/
│
└── README.md
```

### Mô tả các tệp và thư mục

| Tệp / Thư mục | Nội dung |
|---|---|
| `BTTL.ipynb` | Notebook bài tập thực hành trên lớp |
| `BTVN.ipynb` | Notebook bài tập về nhà, bao gồm các mô hình CNN |
| `outputs_lenet/` | Kết quả thực nghiệm mô hình LeNet-5 |
| `outputs_googlenet/` | Kết quả thực nghiệm mô hình GoogLeNet |
| `outputs_resnet18/` | Kết quả thực nghiệm mô hình ResNet-18 |
| `outputs_resnet50_hf/` | Kết quả thực nghiệm mô hình ResNet-50 sử dụng pretrained weights từ Hugging Face |

## 📚 Nội dung thực hiện

### 1. Bài tập thực hành trên lớp (BTTL)

### 2. Bài tập về nhà (BTVN)

**Bài 1 - Xây dựng mô hình LeNet-5**

- Xây dựng và huấn luyện mô hình LeNet trên bộ dữ liệu VinaFood21.
- Sử dụng ảnh đầu vào kích thước 64×64×3, gồm 21 lớp.
- Thực nghiệm với hai phương pháp Pooling: Average Pooling và Max Pooling.
- Sử dụng Adam Optimizer.
- Đánh giá mô hình bằng Accuracy, Precision, Recall và Macro-F1.
- Phân tích số lượng tham số, F1-score từng lớp và Confusion Matrix.

**Bài 2 - Xây dựng mô hình GoogLeNet**

- Xây dựng phiên bản GoogLeNet rút gọn với 3–4 Inception Blocks.
- Sử dụng ảnh đầu vào kích thước 64×64.
- Triển khai các nhánh Inception và kết hợp bằng `torch.cat()`.
- Sử dụng Global Average Pooling trước lớp phân loại.
- Huấn luyện bằng Adam Optimizer.
- Đánh giá bằng Accuracy, Precision, Recall và Macro-F1.
- So sánh với LeNet-5 về số lượng tham số, thời gian huấn luyện mỗi epoch và Macro-F1.

**Bài 3 - Xây dựng mô hình ResNet-18**

- Tự xây dựng kiến trúc ResNet-18 với cấu hình `[2, 2, 2, 2]`.
- Sử dụng BasicBlock với Identity Shortcut và Projection Shortcut.
- Huấn luyện mô hình từ đầu, không sử dụng pretrained weights.
- Thực nghiệm với hai trường hợp: có và không có Data Augmentation.
- Sử dụng ảnh đầu vào kích thước 96×96 hoặc 112×112.
- So sánh Training Loss, Validation Loss và Macro-F1 giữa hai lần thực nghiệm.

**Bài 4 - Fine-tuning mô hình ResNet-50 Pretrained**

- Sử dụng mô hình `microsoft/resnet-50` từ Hugging Face.
- Thay đổi lớp phân loại cuối cùng để phù hợp với 21 lớp của VinaFood21.
- Thực nghiệm hai phương pháp:
  - **Feature Extraction:** Đóng băng Backbone, chỉ huấn luyện lớp phân loại.
  - **Fine-tuning:** Cập nhật trọng số của toàn bộ mô hình.
- Sử dụng ảnh đầu vào kích thước 224×224.
- So sánh kết quả của hai phương pháp thông qua các độ đo đánh giá.

## 📊 Đánh giá và so sánh mô hình

Các mô hình được đánh giá trên tập kiểm thử bằng những độ đo: Accuracy, Precision, Recall, Macro-F1

Các kết quả thực nghiệm được tổng hợp và so sánh dựa trên:

- Số lượng tham số của mô hình.
- Thời gian huấn luyện trung bình mỗi epoch.
- Accuracy trên tập kiểm thử.
- Macro-F1 trên tập kiểm thử.

## 🛠️ Công nghệ và thư viện sử dụng

- **Python**
- **PyTorch:** Xây dựng và huấn luyện mô hình Deep Learning.
- **Torchvision:** Xử lý hình ảnh và hỗ trợ các kiến trúc CNN.
- **Hugging Face Transformers:** Sử dụng mô hình ResNet-50 pretrained.
- **Scikit-learn:** Tính toán các độ đo đánh giá mô hình.
- **NumPy:** Xử lý dữ liệu dạng mảng.
- **Matplotlib & Seaborn:** Trực quan hóa kết quả và Confusion Matrix.
- **Jupyter Notebook:** Môi trường triển khai và thực nghiệm.

## 🚀 Hướng dẫn sử dụng

### 1. Clone repository

```bash
git clone https://github.com/dangtrinh0987654321-debug/lab2_dl.git

cd lab2_dl
```

### 2. Cài đặt thư viện

```bash
pip install torch torchvision transformers scikit-learn matplotlib seaborn
```

### 3. Chuẩn bị dữ liệu

Sử dụng bộ dữ liệu **VinaFood21** gồm 21 lớp món ăn Việt Nam.

[Link tải bộ dữ liệu VinaFood21](https://drive.google.com/file/d/1UpZOf0XlwvB4rKpyZ35iwTA8oWHqDBbR/view)

Sau khi tải và giải nén, tổ chức dữ liệu theo cấu trúc:

```text
VinaFood21/
│
├── train/
│   ├── class_1/
│   ├── class_2/
│   └── ...
│
├── val/
│   ├── class_1/
│   ├── class_2/
│   └── ...
│
└── test/
    ├── class_1/
    ├── class_2/
    └── ...
```

Dữ liệu ban đầu chỉ có `train/` và `test/`, cần tách tập validation từ tập train theo hướng dẫn trong notebook.

### 4. Chạy Notebook

Khởi chạy Jupyter Notebook:

```bash
jupyter notebook
```

Mở các notebook tương ứng:

- `BTTL.ipynb`: Thực hiện các bài tập thực hành trên lớp.
- `BTVN.ipynb`: Thực hiện các bài tập bắt buộc và nâng cao.

---

**GitHub Repository:** [lab2_dl](https://github.com/dangtrinh0987654321-debug/lab2_dl)
