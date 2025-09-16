# Kolam_SIH

# Kolam Design Processor

This project allows analyzing Kolam images and recreating them programmatically.  

---

## Requirements

- Python 3.8+
- Install dependencies:

```bash
pip install numpy matplotlib opencv-python scikit-image scipy networkx scikit-learn shapely
Scripts Overview
```
1. Analyze a Kolam Image
```bash
python kolam_from_image.py <image_file>
```
Displays the original image with key points and paths highlighted.
Prints a summary of the design features.
Automatically saves a temporary extraction file (kolam_extraction.pkl).

2. Save Extraction
```bash
python kolam_save_extraction.py <image_file> -o <output_pickle_file>
```
Extracts design features from the image.
Saves all extracted data to a .pkl file for later use.
Prints a summary of the extracted design.

3. Recreate Kolam from Extraction
```bash
python kolam_recreate.py <pickle_file> -o <output_prefix> --dpi <dpi_value> --scale <scale_value>
```
Recreates the Kolam design using the previously saved extraction.
Saves the recreated design as .png and .svg.

Parameters:

--dpi : Resolution of the saved image (default 300)

--scale : Scale factor for the design (default 1.0)

--no-show : Do not display the plot window

Example Workflow
```bash
# Analyze and view Kolam
python kolam_from_image.py Kolam_png.jpg

# Save extraction for later use
python kolam_save_extraction.py Kolam_png.jpg -o kolam_extraction.pkl

# Recreate the Kolam
python kolam_recreate.py kolam_extraction.pkl -o kolam_final --dpi 300 --scale 1.0
```
Output
*.pkl → Saved extraction of design features.
*.png → Recreated Kolam image.
*.svg → Vector version of the design.

Notes
Input images should have clear strokes and dots for best results.
The scale and DPI can be adjusted when recreating the design.
Recommended workflow: analyze → save extraction → recreate.
