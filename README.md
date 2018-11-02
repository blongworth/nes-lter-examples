# Examples of using online data produced by the NES-LTER information management system (IMS)

This repository contains example data from NES-LTER along with executable code for downloading and visualizing the data in Python (Jupyter), R, and MATLAB.

The NES-LTER IMS is under development and its current capabilities include parsing raw data and producing cleaned-up CSV data that can be read by any programming language. Raw data includes both instrument data such as CTD bottle summary files, as well as PI-provided spreadsheets. The "data cleaning" is the first part of the proposed data pipeline that would support queries and discovery, access to data, and export to external repositories, all through RESTful web APIs that can pull the data directly into your favorite tools. The idea is to reduce the data handling burden on PIs and create a streamlined, automated process for accessing and using NES-LTER data.

Although the examples here are all in CSV format, the data pipeline will generate other formats as appropriate, e.g., NetCDF.

In the examples, data is read from GitHub and visualized in various useful ways. In our eventual data pipeline we will provide web APIs and will not be serving data from GitHub, but the code examples here would only have to be slightly modified (changing the access URL) to work with the data pipeline.

### What is "data cleaning"?

For data to be easily machine readable, it has to
* Be in a widely-supported format (e.g., CSV, NetCDF)
* Contain consistent types of values for a given variable (e.g., not putting words in a date column)
* Link to other data through common variables (e.g., cruise/cast/niskin)
* Contain sufficient metadata to be interpreted properly (e.g., NetCDF attributes)
* Use variable names that are legal in programming langauges (e.g., "chl" instead of "Chl (μg/l)")
* Not contain unnecessary variation (e.g., "> 10" and ">10" meaning the same thing)
* Use consistent ways of indicating missing values

"Cleaning" data is the process of taking data that doesn't meet some of these criteria and reformatting or otherwise modifying it to meet the criteria. In addition to cleaning data after the fact, the things that have to be done to clean a particular dataset can serve as recommendations for formatting or structuring the dataset going forward.

Our code for cleaning data is mostly contained in the `nes-lter-ims`(https://github.com/nes-lter-ims) repository. It will grow as we work on new data types and as new data is provided to us by PIs.
