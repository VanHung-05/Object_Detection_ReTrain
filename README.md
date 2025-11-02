# Object Detection Using YOLO & Retrain Models

Ứng dụng phát hiện đối tượng sử dụng YOLOv8 models với Flask web interface. Hỗ trợ phát hiện đối tượng trên ảnh tĩnh, real-time qua webcam, và hybrid detection kết hợp COCO classes với custom model.

## Tính năng

- **Image Detection**: Phát hiện đối tượng trong ảnh tĩnh (JPG, PNG)
- **Real-time Detection**: Phát hiện đối tượng real-time với webcam
- **Hybrid Detection**: Kết hợp model COCO (80 classes) với custom trained model (desk class)
- **Statistics & Visualization**: Thống kê và biểu đồ số lượng đối tượng được phát hiện
- **Web Interface**: Giao diện web thân thiện với người dùng

## Yêu cầu hệ thống

- Python 3.8+
- Webcam (cho chức năng real-time detection)

## Cài đặt


### 1. Cài đặt dependencies

```bash
pip install -r requirements.txt
```

## 2. Sử dụng

### Web Application

Khởi động Flask web server:

```bash
python app.py
```

Truy cập ứng dụng tại: **http://localhost:5001**

#### Tính năng Web Interface:

1. **Image Detection**
   - Chọn file ảnh (JPG, PNG)
   - Điều chỉnh confidence threshold (0.1 - 0.9)
   - Chọn mode: Standard YOLO hoặc Hybrid (COCO + Custom)
   - Click "Áp dụng" để xử lý
   - Xem và tải xuống ảnh đã được xử lý

2. **Real-time Detection**
   - Click "Launch Camera Application" để mở ứng dụng real-time
   - Chọn confidence threshold và hybrid mode (nếu cần)
   - Ứng dụng sẽ mở trong cửa sổ riêng



#### Phím tắt trong Real-time Detection:

- `q`: Thoát ứng dụng
- `s`: Lưu frame hiện tại
- `c`: Thay đổi confidence threshold (0.3, 0.5, 0.6, 0.7, 0.8)
- `r`: Hiển thị báo cáo thống kê đối tượng
- `h`: Chuyển đổi giữa Standard và Hybrid mode


## Cấu trúc Project

```
Object-Detection-Using-Yolo-Pretrained/
├── app.py                      # Flask web application
├── imageDetection.py           # Image processing functions
├── models.py                   # YOLOv8 model wrapper (PyTorch)
├── hybrid_models.py           # Hybrid detector (COCO + Custom)
├── run_realtime.py            # Real-time detection script
├── statistic_object.py         # Statistics and plotting
├── requirements.txt            # Python dependencies
├── model_weights/              # Model weights directory
│   ├── best.pt                # Custom trained model (best)
│   ├── last.pt                # Custom trained model (last)
│   └── yolov8n.pt             # YOLOv8 nano pretrained
├── templates/                  # HTML templates
│   └── index.html             # Web interface
├── static/                     # Static files
│   ├── style.css              # CSS styles
│   └── scripts.js             # JavaScript functions
├── data/                       # Data storage
│   └── object_count.json      # Object count statistics
├── plots/                      # Generated plots
│   └── object_count_*.png     # Statistics plots
└── test_data/                  # Test images
    ├── di-bo-pham-luat_*.jpg
    └── di-bo-sang-duong.jpg
```

## Tác giả

Project được phát triển cho môn học Artificial Intelligence.

