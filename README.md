# Fabric Defect Detection

A simple web app to detect defects in fabric using AI.

## What it does
- Upload fabric images to find defects
- Use your camera for live defect detection
- Shows defect types like stains, cuts, holes

## Quick Start

### 1. Install Python
You need Python 3.8 or newer.

### 2. Setup
```bash
# Download the code
git clone <your-repo-url>
cd fabric-defect-detection

# Create virtual environment
python -m venv venv

# Activate it
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# Install requirements
pip install -r requirements.txt
```

### 3. Run the app
```bash
python app.py
```

Open your browser and go to: `http://localhost:5000`

## How to use

### Upload images
1. Go to the main page
2. Drag and drop a fabric image or click to browse
3. Click "Detect Defects"
4. See the results with defect locations

### Use camera
1. Click "Camera" in the menu
2. Click "Start Camera"
3. Point camera at fabric
4. See live defect detection

## Common problems

**"Model not found"** - Make sure your model file is in the right folder

**"Camera not working"** - Allow camera access in your browser

**"App is slow"** - Close other programs to free up memory

## Files
- `app.py` - Main application
- `fabric_defect_detector.py` - AI detection code
- `templates/` - Web pages
- `requirements.txt` - Required packages

That's it! Simple fabric defect detection.
