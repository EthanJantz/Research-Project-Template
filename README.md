# Research Project Management Template

This template provides a general structure for research projects. The following sections will explain how and why this structure is defined and provide best practices for keeping projects organized. By following this structure researchers will be better able to get acquainted with ongoing projects and finished projects will be archived in a way that ensures future access to data and methods. This template was developed as a tool to help maintain continuity within an organizational research context, but has been used in many personal projects as well.

## Project Structure

This template is built around 4 folders: Info, Data, Scripts, and Output. This README file is located in what we'll call the root folder.

### Root Folder

The root folder is where all project files and folders are located. Main project files go here, these include:

* A `README.md` file containing important information about the project. This includes instructions for replicating any findings, detailed information on where data was sourced, and some narrative information explaining the origins and purpose of the project. If this project is hosted on a GitHub repository, this README file will be the first thing a person sees if they look at the repository page.

* The main project files. These files take the data and scripts to generate output. For example, a main project `.Mxd` file would wrangle and analyse shapefiles and CSV files from the data folder to generate a map using ArcGIS; or a `.R` file would utilize helper scripts from the scripts folder to wrangle, visualize, and analyze data to generate a report. Generally there will only be one main project file, but depending on what software tools are used in the project there may be more.

* For Git projects, `.gitignore`, `.gitattribute`, and `.git` files.

### Info Folder

The Info folder is located within the root folder, and in the template is labeled `01_Info`. It contains notes and narrative that aren't directly related to the technical processes performed in research. This could include:

* Documents containing annotated bibliographies or literature reviews.

* Narrative documents detailing important background information on the project like how research decisions were made or notes on who has been involved in the project and what their role was.

* Logs of actions performed within the project and to-do lists so newcomers can see what has been done and what still needs to be done.

Generally, this folder will be the first one to be filled in as researchers gather background information and notes on how they will carry out their research. In the case of client-based work, information about what the client's needs are and what methods to use will be placed in here.

### Data Folder

The Data folder is located within the root folder, and in the template is labelled `02_Data`. All data related to a project will be held inside the Data folder's sub-folders. There are multiple sub-folders within the Data folder:

* The `Raw` folder contains all raw, unprocessed research data. This could be tables pulled directly from the US Census, spatial data pulled from the City of Chicago's Open Data Portal, or spreadsheets provided by a client. Raw data is generally left as-is after being saved in this folder. Any changes or outputs using raw data are saved in the `Processed` folder.

* The `Processed` folder contains data files that have been altered (or wrangled) as part of the research process. For example, a table of new variables created using raw Census data would be saved to this folder. Keeping raw and processed data separate makes it easier for researchers to keep organized and avoid costly mistakes resulting from ambiguous file names.

* The `Metadata` folder contains any data that was created as part of the research process or that describes relationships between data in the other two Data sub-folders. A crosswalk connecting Census data to shapefiles for mapping or a dictionary of variables and their descriptions would be contained in this folder.

It is best practice to keep the number of sub-folders from the root below 4. This structure was designed to allow researchers leeway in how they organize data within the Data subfolders while still providing some predictable structure for future reference. For organizational purposes, it is good practice to keep spatial data files like `.shp` and related files separate from tabular data files like `.csv` or `.xlsx` files using sub-folders. It is also recommended to maintain data separated by source, so having folders within the `Raw` folder, for example, with labels like "Census" or "Client" would be appropriate.

### Scripts Folder

The Scripts folder is located within the root folder, and in the template is labelled `03_Scripts`. This folder contains helper scripts such as `.R`, `.Py`, or `.SQL` files that would be used to wrangle, transform, and analyze the data but aren't the main project file. In an R project this folder could contain a `funcitons.R` script to hold custom functions used in research. In a QGIS or ArcGIS project this may contain `.Py` scripts used as part of the GIS process.

### Output Folder

The Output folder is located within the root folder, and in the template is labeled `04_Output`. All research outputs are saved to one of the two sub-folders within:

* Files saved in the `01_Internal` folder are interim outputs that are intended to be shared with other Voorhees members but not the public. This could include internal presentations or maps for discussion, map outputs that will be included as part of a final report, or draft documents. If the project is hosted on a GitHub repository all files within this folder will be hidden by the `.gitignore` file.

* Files saved in the `02_External` folder are final outputs from the project. Generally, a project can be considered finished once an external output has been saved like a final report, conference presentations, infographics or maps in `.pdf` or image formats. Files saved here are explicitly meant to be shared with the public or client, depending on the nature of the project.

## Best Practices

The following are recommendations on best practices when managing and organizing a research project.

* Keep folders as shallow as possible, if someone accessing your data needs to go through 10 subfolders to find a file you may want to consider reorganizing your Data folder. Using this template it is recommended to keep data organized by source, so within a given data folder there will likely only be two subfolders. For example, raw census data may be kept in `02_Data/Raw/Census/ACS_5yr_2019_DP02.csv`. Spatial data should be labelled as such, so census tract shapefiles would be located within `02_Data/Raw/Census/Spatial/tracts.shp`. Keeping folders concise and descriptive makes it easier to understand data sources in the main project file.

* Use concise, descriptive file names. Avoid creating a series of updates such that your final file is named `output_final_FINALFINAL_FINALFORREAL.jpeg`. If a situation comes up where version control is necessary it is recommended to use Box or, more preferrably, GitHub to handle this for you.

## Using this Template

When first starting a project, copy this folder (`Template Project Folder/`) to a new location and rename the template to something appropriate to the project. Before doing anything else, make sure you have read the above section explaining the project structure and fill out the following sections. As you work on the project make sure to update the `README` file, it is much easier to do so along the way than it is to do the whole thing once you finish the project. Remember, everything in the following sections is meant to be public-facing and provide a crash course on how to use and understand this project.

### [PROJECT NAME]

Describe the project, its goals, and what research questions are being answered. This can be short, since more extensive background information will be found in the `01_Info` folder.

#### Data

Describe data sources with links or citations for retrieving the data. You want to ensure that someone who doesn't know anything about this project would be able to find and download the raw data on their own if the data folder was accidentally corrupted or deleted.

#### How To

Describe how to use the main project files, scripts, and data to generate the final output. Depending on the complexity of the project this could be as simple as "Run the main project file, `Main.R` using R studio." In the case of more complicated research, it may be important to explain how to set up project-specific software or which order to run project files in.
