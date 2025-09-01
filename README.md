# Fabric Defect Detection Web Application

A modern web application for real-time fabric defect detection using YOLOv8 and Flask. This application provides both image upload and real-time camera detection capabilities for identifying defects in fabric materials.

## 🚀 Features

- **Image Upload Detection**: Upload fabric images and get instant defect detection results
- **Real-time Camera Detection**: Use your webcam for live fabric defect monitoring
- **Advanced AI Model**: Powered by YOLOv8 custom-trained model for fabric defects
- **Real-time Statistics**: Live FPS, defect counts, and confidence thresholds
- **Responsive Web Interface**: Modern Bootstrap-based UI with drag-and-drop functionality
- **Confidence Control**: Adjustable confidence threshold for detection sensitivity
- **Defect Classification**: Detailed breakdown of different defect types (stain, cut, hole, etc.)

## 🛠️ Technology Stack

- **Backend**: Flask (Python)
- **AI Model**: YOLOv8 (PyTorch)
- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 5
- **Computer Vision**: OpenCV
- **Image Processing**: NumPy, Pillow

## 📋 Prerequisites

- Python 3.8 or higher
- CUDA-capable GPU (optional, for faster inference)
- Webcam (for camera detection mode)

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/fabric-defect-detection-web.git
   cd fabric-defect-detection-web
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Download the YOLOv8 model**
   - Place your trained YOLOv8 model file at `./yolov8-fabric-defect-detection/best.pt`
   - Or update the model path in `app.py` to point to your model file

## 🎯 Usage

### Starting the Application

```bash
python app.py
```

The application will start on `http://localhost:5000`

### Web Interface

1. **Image Upload Mode** (`/`)
   - Drag and drop fabric images or click to browse
   - Adjust confidence threshold using the slider
   - Click "Detect Defects" to analyze the image
   - View results with bounding boxes and defect counts

2. **Camera Mode** (`/camera`)
   - Click "Start Camera" to enable webcam
   - Enable/disable real-time detection
   - Adjust confidence threshold on the fly
   - Monitor live statistics and defect counts

### API Endpoints

- `GET /` - Main page (image upload)
- `GET /camera` - Camera detection page
- `POST /detect` - Image defect detection
- `POST /update_confidence` - Update confidence threshold
- `GET /health` - Health check endpoint

## 📁 Project Structure

```
fabric-defect-detection-web/
├── app.py                      # Flask application
├── fabric_defect_detector.py   # Core detection logic
├── requirements.txt            # Python dependencies
├── README.md                  # This file
├── templates/                 # HTML templates
│   ├── index.html            # Main page template
│   └── camera.html           # Camera page template
├── uploads/                   # Upload directory (auto-created)
└── yolov8-fabric-defect-detection/
    └── best.pt               # YOLOv8 model file
```

## 🔧 Configuration

### Model Path
Update the model path in `app.py`:
```python
model_path = "./yolov8-fabric-defect-detection/best.pt"
```

### Confidence Threshold
Default confidence threshold is 0.4. Adjust in the web interface or modify the code.

### Upload Limits
Maximum file size is 16MB. Modify in `app.py`:
```python
app.config['MAX_CONTENT_LENGTH'] = 16 * 1024 * 1024
```

## 🎨 Customization

### Adding New Defect Types
The application automatically detects defect types from your YOLOv8 model. No code changes needed.

### UI Customization
Modify the HTML templates in the `templates/` directory to customize the appearance.

### Detection Parameters
Adjust detection parameters in `fabric_defect_detector.py`:
- Confidence threshold
- IoU threshold
- Model input size

## 🚀 Deployment

### Local Development
```bash
python app.py
```

### Production Deployment
For production deployment, consider using:
- Gunicorn or uWSGI as WSGI server
- Nginx as reverse proxy
- Environment variables for configuration
- HTTPS for security

Example with Gunicorn:
```bash
pip install gunicorn
gunicorn -w 4 -b 0.0.0.0:5000 app:app
```

## 📊 Performance

- **Image Processing**: ~100-500ms per image (depending on hardware)
- **Camera Detection**: 1 FPS (configurable)
- **Memory Usage**: ~2-4GB RAM (depending on model size)
- **GPU Acceleration**: Significantly faster with CUDA support

## 🐛 Troubleshooting

### Common Issues

1. **Model not found**
   - Ensure the model file exists at the specified path
   - Check file permissions

2. **Camera access denied**
   - Allow camera permissions in your browser
   - Check if another application is using the camera

3. **CUDA errors**
   - Install PyTorch with CUDA support
   - Check GPU compatibility

4. **Memory issues**
   - Reduce model input size
   - Close other applications

### Debug Mode
Enable debug mode in `app.py`:
```python
app.run(debug=True, host='0.0.0.0', port=5000)
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Ultralytics](https://github.com/ultralytics/ultralytics) for YOLOv8
- [Flask](https://flask.palletsprojects.com/) for the web framework
- [Bootstrap](https://getbootstrap.com/) for the UI components
- [OpenCV](https://opencv.org/) for computer vision capabilities

## 📞 Support

For support and questions:
- Create an issue in the GitHub repository
- Check the troubleshooting section
- Review the code comments for implementation details

## 🔄 Updates

Stay updated with the latest features and improvements by:
- Watching the repository
- Checking the releases page
- Following the commit history

---

**Made with ❤️ for the textile industry**
