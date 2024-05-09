# FSA_Payments
#### Each notebook covers a section of FSA payment analysis. 
#### 1.0_Data_DL: This notebook covers the steps to retrieve data from USDA website and describes potential structures for the dataset. 
#### 2.0_General_Fig: This notebook contains a couple of general figures to present data over time and over location. 
#### 3.0_CRP_Voter_Figs: 
You will have to change the filepath to be your own file path whenever new data files are called in, and for saving the outputted figures. 
1. This will first call in the county level shapefile of the US. Ensure that it has the FIPS code to name that we will use to match later on, it excludes the islands and territories of the US. Then plots this to ensure we have the correct area. 
2. You will use the file "countrypres_2000-2020.csv" to load in the county level voter data. There are some NA, a small proportion which actually doesn't have the total votes either so these observations are dropped. We match these to be able to merge with the county level shapefile, and then do the merge. 
3. With the merged voter data and shapefile, we segregate the data per election years of the candidatevotes as a share of the total votes, and plot the winner candidate in each county. We do this for 6 elections, with the same code, just modified per each election. 
4. Then we go back to the CRP payment data that is called "CRP_data.csv", chunk it and take the mean by each payment year. For example, the disbursed amount that is done in the year 2008. Then it does the same for 2009, 2010, etc. We change this into a pivot table of each county level final means to work with that dataframe. In an attempt to look at trends, we aggregate the years prior to elections and then merge this data to the shapefile for plotting the presidential election years of the payment data. 
5. Once the data are merged together, we then take the log of each the aggregated years and plot the logged amount across each county from 2008, 2009-2012, 2013-2016, and 2017-2020.
#### 4.0_CRP_Landuse:
"landuse_raw" is the folder storing the raw data, including:
	(1) 2008-2023, area of different land use type within each county. "2008_tab", "2009_tab",...
	(2) US county shape file "us_counties_2017"
	(3) Area of each county, "us_county_area"
	(4) CRP payment data from Khashi's output, "CRP_data"
"landuse_output" is the output folder
In the Jupiter notebook "4.0_CRP_Landuse", you can type "change directory" to find all the places where you need to change the directory
"data_raw" corresponds to the directory you store the "landuse_raw"
"output_path" corresponds to the directory you store the "landuse_output"
