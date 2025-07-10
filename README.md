This is a project I made during the Columbia Lede Program.

It is about bike infrastructure, and safety for cyclists in Brooklyn.
The primary data sources were the NYC Open Data, and the NYC Department of Transportation.
The data processing is documented in the CyclistsWIR.ipynb file.
The maps were made in QGIS, Adobe After Effects and Photoshop.
I used a scrollama template to make the webpage.
I also used the help of Claude and Gemini to help me with the data processing and website.
Thanks to Streetsblog for diligent documentation of NYC bike news.

Steps for project-
	1. Get data
	2. Clean data and create geodata in Pandas and GeoPandas
	3. Create intersections based on 20m clusters
	4. Map all locations on map in QGIS
	5. Export base map layers and points of each map from QGIS
	6. Overlay each layer on base map in After Effects (Can be skipped. I used AE because I initially wanted to create a timelapse png sequence of the crashes heatmap.)
	7. Export frames from After Effects and import them into Photoshop
	8. Annotate and Illustrate maps in Photoshop
	9. Gather images from DoT and Streetsblog sources
	10. Assemble and annotate images in Photoshop
	11. Record video of dangerous intersections
	12. Edit video in Adobe Premiere, export, then reduce filesize using an online .webm video converter.
	13. Create webpage
	14. Upload to github

Data needed for this- 
	1. Location of speed humps
		a. https://data.cityofnewyork.us/Transportation/VZV_Speed-Humps/jknp-skuy/about_data
	2. Location of bike lanes
		a. https://data.cityofnewyork.us/dataset/New-York-City-Bike-Routes-Map-/9e2b-mctv
	3. Location  of bike crashes
		a. https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95/about_data
	4. NYC DoT Cyclist safety report 2017
		a. https://www.nyc.gov/html/dot/downloads/pdf/bike-safety-study-fullreport2017.pdf
	5. NYC DoT Daylighting study 2025
		a. https://lede-admin.nyc.streetsblog.org/wp-content/uploads/sites/48/2025/01/DOT-Daylighting-Study.pdf
	
	6. In the NYC Open Data portal, queried data for-
		a. Borough IS Brooklyn
			i. No. of pedestrians injured != 0
		b. OR
		c. Borough IS Brooklyn
			i. No. of pedestrians killed != 0
		d. OR
		e. Borough is Brooklyn
			i. No. of cyclists killed != 0
		f. OR
		g. Borough is Brooklyn
			i. No. of cyclists killed !=0
	7. Created a severity score in Pandas for QGIS heat map
		a. ("NUMBER OF CYCLIST INJURED" * 3) + ("NUMBER OF CYCLIST KILLED" * 10)
		b. Deaths get a 10x score, injuries get a 3x score
			i. Eg. 
			§ 1 injured, 0 killed = (1 × 3) + (0 × 10) = 3
			§ 0 injured, 1 killed = (0 × 3) + (1 × 10) = 10
			§ 2 injured, 1 killed = (2 × 3) + (1 × 10) = 16




## License

MIT License

Copyright (c) 2025 Anurag Prasad Papolu

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
