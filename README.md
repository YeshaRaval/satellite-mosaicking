# Image Mosaicking

## Overview
This project implements an image mosaicking pipeline using feature matching, RANSAC, homography estimation, and optimization. It provides both a Streamlit web interface and script-based usage for generating panoramas by stitching multiple images together.

## Features
- SIFT-based feature detection and matching
- RANSAC for robust homography estimation
- Levenberg-Marquardt optimization for homography refinement
- Automatic image alignment and stitching
- Streamlit web app for interactive mosaic generation
- Support for both direct image upload and folder-based batch processing

## Folder Structure
- `app.py`: Main Streamlit web app for interactive mosaic generation
- `old.py`: Legacy Streamlit app for folder-based image mosaicking
- `image_mosaic.py`: Core logic for image mosaicking (script-based)
- `match_features.py`: SIFT feature extraction and matching
- `ransac.py`: RANSAC algorithm for robust homography estimation
- `optimize_fcn.py`: Optimization routines for homography refinement
- `estimate_homography.py`: Homography estimation and related utilities

## Installation
1. Clone this repository:
   ```bash
   git clone <repo-url>
   cd mosaicking
   ```
2. Install dependencies (recommended: use a virtual environment):
   ```bash
   pip install -r requirements.txt
   ```

## Requirements
- Python 3.7+
- streamlit
- numpy
- opencv-python
- scipy
- matplotlib
- pillow

You can create a `requirements.txt` with:
```
streamlit
numpy
opencv-python
scipy
matplotlib
pillow
```

## Usage

### 1. Streamlit Web App
Run the web app:
```bash
streamlit run app.py
```
- Upload 2 or more images (JPG/PNG) in the order to be stitched.
- Click "Generate Mosaic" to create and download the panorama.

### 2. Script-based Usage
You can use `image_mosaic.py` for batch processing:
```bash
python image_mosaic.py
```
- By default, it looks for a folder named `trial2` and stitches all images inside.
- Modify the `parent_folder` and `img_name_list` in the `__main__` block as needed.

### 3. Folder-based Streamlit App
Run the legacy app:
```bash
streamlit run old.py
```
- Enter the path to a folder containing images.
- Select the number of images and generate the mosaic interactively.

## Tips for Best Results
- Upload images in the order they should be stitched (left to right or right to left).
- Use images taken from the same position with only rotation for best alignment.
- Higher resolution images yield better mosaics but require more processing time.

## License
MIT License

## Acknowledgements
- OpenCV for computer vision routines
- Streamlit for the web interface 
