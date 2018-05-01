# Hospital Finder Using Semantic Web Technologies

Final project for the course - CS 6315: Semantic Web, Spring 2018 
<br>
<blockquote>Correlation between leading causes of death and neighboring hospitals using Semantic Web technologies</blockquote>


**Team members**
- Ankita Patil
- Krupali Patel
- Shivdev Kumar

**Demo**: Dempnstration of the project can be found <a href="https://youtu.be/MIHdjxrGKTQ">here</a>.


<hr>

## Project Description

The project aims to find the top five leading causes of death and once we find it, we address one of leading causes of death and suggest hospitals near to a user for that particular disease so that they can be cured if possible and we can reduce the death rate for that particular disease. For this purpose, data about "Potentially Excess Deaths from the Five Leading Causes of Death(NCHS)" from National Vital Statistics System is used and combined with the "Timely and Effective Care- Hospital" and "500 Cities: Local Data for Better Health" for the year 2014.
<br>
## Datasets

1. **Timely and Effective Care – Hospital**<br>
**Link:** https://catalog.data.gov/dataset/timely-and-effective-care-hospital-e4aad<br>
**Domain:** Federal<br>
**Description:** This data set includes provider-level data for measures of heart attack care, heart failure care, pneumonia care, surgical care, emergency department care, preventive care, children asthma care, blood clot prevention and treatment, pregnancy and delivery care, and cancer care. <br>
**Format available:** CSV, RDF, JSON, XSL

2. **Potentially Excess Deaths from the Five Leading Causes of Death**<br>
*Link:* https://catalog.data.gov/dataset/nchs-potentially-excess-deaths-from-the-five-leading-causes-of-death<br>
*Domain:* Federal<br>
*Description:* This dataset contains Potentially Excess Deaths from the Five Leading Causes of Death in Nonmetropolitan and Metropolitan Areas, United States, 2005-2015. Mortality data for U.S. residents come from the National Vital Statistics System. <br>
*Format available:* CSV, RDF, JSON, XSL

3. **500 Cities: Local Data for Better Health<br>**
**Link:** https://catalog.data.gov/dataset/500-cities-local-data-for-better-health-b32fd<br>
**Domain:** Federal<br>
**Description:** This is the complete dataset for the 500 Cities project. This dataset includes 2013, 2014 model-based small area estimates for 27 measures of chronic disease related to unhealthy behaviors, health outcomes and use of preventive services. It includes estimates for the 500 largest US cities and approximately 28,000 census tracts within these cities. These estimates can be used to identify emerging health problems and to inform development and implementation of effective, targeted public health prevention activities.<br>
**Format available:** CSV, RDF, JSON, XSL
<br>

## Data Pre-processing

- The datasets downloaded from the <a href="www.data.gov">www.data.gov</a> are in CSV format
- Apache Fuskei requires data in RDF format. Hence, in order to convert the data into RDF format <a href="https://github.com/timrdf/csv2rdf4lod-automation/wiki">csv2rdf4lod-automation tool</a> is used.
- Converted pre-processed data can be found <a href="https://utdallas.app.box.com/folder/48845277745">here</a>.
<br>

## Technology Stack

- Apache Fuseki 3.6 (SPARQL server) to load the data and create SPARQL endpoints
- Bootstrap 4 and JavaScript for front-end
- Google Visulaization API
- Google Maps API
- csv2rdf4lod-automation tool for converting the data from CSV to RDF format
<br>

## Instructions to run the code

1. Download <a href="https://jena.apache.org/documentation/fuseki2/">Apache Jena Fuseki</a> 
2. Go to the location where Apache Jena Fuskei is downloaded
3. Create a folder named *dataDir* in Apache Fueski's directory
4. To Start Fuseki Server, open command prompt and type the command

    ```
      java -Xmx8096M -jar fuseki-server.jar --update --loc=dataDir /myDataset

    ```
 5. Now, in the browser go to http://localhost:3030/
 6. Click on "manage datasets" tab and beside /myDataset click on "upload data" and load all the 3 datasets from the dataset folder with a graph name for all the 3 datasets. For example load city.rdf with graph name as "city", load hospital.rdf with graph name "hospital" and load nchs.rdf with graph name "nchs".
 7. After the datasets are uploaded successfully, from <a href="https://github.com/patilankita79/HospitalFinderUsingSemanticWeb/tree/master/Webapp">Webapp</a> folder, open <a href="https://github.com/patilankita79/HospitalFinderUsingSemanticWeb/blob/master/Webapp/index.html">index.html</a> to view the results

