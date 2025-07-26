# Google EarthEngine Exporter

This repository contains a python notebook that takes a KML file and exports the region within the file to an image in the user's Google Drive. This code can be used in conjunction with Google Earth Pro to precisely outline key regions of interest, and perform a batch export of satellite images, saving time when there are multiple regions that need to be clipped.

---
# Requirements:
- Python 3.11
- Google Earth Pro
---
# Instructions:
To start, navigate to the project folder in the terminal, and create a python virtual environment within the project folder:
```
python3.11 -m venv venv
```
Next, activate the virutal environment within the project folder:
```
source venv/bin/activate
```

Next, use the 'requirements.txt' file to replicate the virtual environment with the proper packages:
```
pip install -r requirements.txt
```
At this point, the user will be ready to run the program. Run the import cells and authenticate google earth engine use for the project. A browser window will pop open, and after authorizing use, an authorization token be generated. At the top of the code editor window there should be a prompt to enter this token.

Next, copy and paste the kml file into the project folder.
After that, the user will copy the file PATH into the geopandas 'read_file' function (should be in the 'Data Cleaning and File Conversion' cell):
```python
gdf = gpd.read_file('Path/to/kml_file') ### <=== EDIT THIS LINE
```


Lastly, the user will need to specify an image description, a folder for your the image to reside in (if not it will be in the user's drive itself), and a name for the file.

```python
task = ee.batch.Export.image.toDrive(
    image=vis_image,
    description='Description of the Clipped image', ### <=== EDIT THIS LINE
    folder='My_googledrive_folder', ### <=== EDIT THIS LINE
    fileNamePrefix='file_name', ### <=== EDIT THIS LINE
    scale=10,  # Native resolution
    region=my_region,
    maxPixels=1e9,
    formatOptions={'cloudOptimized': True}
)
```
# Once all the cells have completed running, a .tif file should be present within the user's Google Drive, in the specified folder, which shows the clipped image!

