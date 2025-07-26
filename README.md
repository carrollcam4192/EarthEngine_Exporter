# Google EarthEngine Exporter

This repository contains a python notebook that takes a KML file and exports the region within the file to an image in the user's google drive. This code can be used in conjunction with Google earth Pro to precisely outline key regions of interest, and perform a batch export of satellite images, saving time when there are multiple regions that need to be clipped.

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

Next, copy and paste your kml file into the project folder.
After that, the user will copy the file PATH into the geopandas 'read_file' function (should be in the 'Data Cleaning and File Conversion' cell):
```
gdf = gpd.read_file('Path/to/kml_file') ### <=== EDIT THIS LINE
```




create virtual envirnment (python 3.11)
install requirements

```test inline
 #test inline
print('hello world')
