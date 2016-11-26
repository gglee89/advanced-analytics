# Creating an Analytical Dataset
Personal notes based on Udacity's course "Creating an analysical dataset".

### General Info
------
## This steps and guidelines are based on Udacity's course
- Name of the course: Building High Conversion Web Forms;
- Link to the course: [https://classroom.udacity.com/courses/ud977/](https://classroom.udacity.com/courses/ud977/);

## What I've learned:
------
1. The most common sources of data;
2. The different ways data are structured and why it matters;
3. Input a dataset into Alteryx;
4. Recognize structural issues;
5. Optimize the field types to fit the data;

## Environment:
-------
- OS:
  - macOS Sierra 10.12.1;
  - Windows 10 Pro;
- Analytical Tool:
  - Alteryx Designer x64 (Trial Version - 14days)
  - Alteryx Cloud Share [https://use.cloudshare.com/Ent/Enterprise/index.aspx](https://use.cloudshare.com/Ent/Enterprise/index.aspx);
![screen shot 2016-11-26 at 4 35 02 pm](https://cloud.githubusercontent.com/assets/16644017/20638860/537ff0d6-b3f6-11e6-9c71-c23cf4e1739e.png)

### 1. Most common sources of data:
--------
![screen shot 2016-11-26 at 4 14 50 pm](https://cloud.githubusercontent.com/assets/16644017/20638762/919d57e4-b3f3-11e6-8855-b97d3974908f.png)
- Transactional data:
  - E.g. Recorded at the supermarket for every purchase;
- Device data:
  - E.g. TV, mobile, cable boxes, and etc.
- Collected data:
  - E.g. Weather, census, flight data, and etc.
  
### 2. Different ways data are structured and why it matters:
--------
- Structured:
  - Typically organized into **columns** and **rows** like in a spreadsheet;
  - Interchangeable terminology: **Column (Fields) X Rows (Records)**;
  - Each column represent a variable;
  - Each row represent a record of data;
  - Easily accessible, and commonly stored in databases or files;
  - Easy to use;
- Unstructured;
  - Can have no struture to it at all;
  - You have to pull what you want out of it;
  - E.g. Resume/CV, tweet, or a contract;
- Semi-Structure;
  - Has some structure to it;
  - Still requires some work to put it into a structure format of columns and rows;
  - E.g. 1: 
    - Computer system log file (requires parsing and manipulating that puts the data into a format that is easy to analyze)
  - E.g. 2: 
    - Catalog of music CDs in XML format. There's clearly a structure with each CD having a TITLE, ARTIST, COUNTRY, COMPANY, PRICE and YEAR. But it's not in a typical **columns and rows** format
    - Still needs a bit of work to put the data into a format that can easily be used.
```xml
<Catalog>
  <CD>
    <TITLE>Still got the Blues</TITLE>
    <ARTIST>Gary Moore</ARTIST>
    <COUNTRY>UK</COUNTRY>
    <COMPANY>Virgin Records</COMPANY>
    <PRICE>10.20</PRICE>
    <YEAR>1990</YEAR>
  </CD>
</Catalog>
```

### 3a. Input a dataset into Alteryx (from File);
--------
![screen shot 2016-11-26 at 4 39 07 pm](https://cloud.githubusercontent.com/assets/16644017/20638878/e28e5e70-b3f6-11e6-8155-ddb4914d0b69.png)
- **(Scenario example 1:)** Our Marketing department wants to know the customers that are in *Denver*:
  - In total there are 2,669 customers in the CSV file;
  - Filtering the search the result is **1,166 customers in Denver**
  
- **(Scenario example 2:)** Which customer segment makes out the most of the Denver customers:
  - We *summarize* the data and **Group By** "Customer Segment" and **Count** the Customer Ids [Unique] and *Sort* descending our summarized-count values;
  - This brings us the following result:
  
![screen shot 2016-11-26 at 4 50 58 pm](https://cloud.githubusercontent.com/assets/16644017/20638915/b632eb28-b3f8-11e6-8bd2-b65e3d0218fc.png)

- **(Scenario example 3:)** How many store have more than 300 customers?
  - And the correct answer would be **5(five)**.
![screen shot 2016-11-26 at 4 57 08 pm](https://cloud.githubusercontent.com/assets/16644017/20638956/81ba7b9e-b3f9-11e6-8548-51f647758d2c.png)

### 3b. Input a dataset into Alteryx (from Database);
--------
- For this example I will use the following websites to assist my DB connection:
  - Import preset JSON file (companies.zip - 14.8MB compressed) from [http://jsonstudio.com/resources/](http://jsonstudio.com/resources/);
  - mLab [https://mlab.com/home](https://mlab.com/home)
    - Import downloaded input file (companies.json) to new MongoDB collection;
    - mongoimport -h ds111188.mlab.com:11188 -d gl-data-analysis -c startups -u <user> -p <password> --file <input file>;
    - Download speed took **44 seconds**; In Seoul, South Korea where my internet connection speed is (75 Mbps = 9.375 MB/s) on average;
```zsh
$ mongoimport -h ds111188.mlab.com:11188 -d gl-data-analysis -c startups -u <dbuser> -p <dbuser_pwd> --file companies.json
2016-11-26T18:00:51.867+0900	connected to: ds111188.mlab.com:11188
2016-11-26T18:00:52.699+0900	[###.....................] gl-data-analysis.startups	9.39MB/74.6MB (12.6%)
2016-11-26T18:00:55.701+0900	[###.....................] gl-data-analysis.startups	9.39MB/74.6MB (12.6%)
2016-11-26T18:00:58.701+0900	[###.....................] gl-data-analysis.startups	9.39MB/74.6MB (12.6%)
2016-11-26T18:01:01.699+0900	[###.....................] gl-data-analysis.startups	9.39MB/74.6MB (12.6%)
2016-11-26T18:01:04.697+0900	[####....................] gl-data-analysis.startups	14.8MB/74.6MB (19.8%)
2016-11-26T18:01:07.696+0900	[######..................] gl-data-analysis.startups	19.3MB/74.6MB (25.8%)
2016-11-26T18:01:10.700+0900	[########................] gl-data-analysis.startups	26.6MB/74.6MB (35.6%)
2016-11-26T18:01:13.696+0900	[###########.............] gl-data-analysis.startups	37.0MB/74.6MB (49.6%)
2016-11-26T18:01:16.701+0900	[##############..........] gl-data-analysis.startups	43.9MB/74.6MB (58.9%)
2016-11-26T18:01:19.699+0900	[################........] gl-data-analysis.startups	50.9MB/74.6MB (68.2%)
2016-11-26T18:01:22.696+0900	[##################......] gl-data-analysis.startups	57.8MB/74.6MB (77.5%)
2016-11-26T18:01:25.697+0900	[####################....] gl-data-analysis.startups	65.3MB/74.6MB (87.5%)
2016-11-26T18:01:28.700+0900	[####################....] gl-data-analysis.startups	65.3MB/74.6MB (87.5%)
2016-11-26T18:01:31.701+0900	[######################..] gl-data-analysis.startups	68.8MB/74.6MB (92.1%)
2016-11-26T18:01:34.700+0900	[########################] gl-data-analysis.startups	74.6MB/74.6MB (100.0%)
2016-11-26T18:01:35.952+0900	[########################] gl-data-analysis.startups	74.6MB/74.6MB (100.0%)
2016-11-26T18:01:35.952+0900	imported 18801 documents
```
  - Outcome on mLab.
![screen shot 2016-11-26 at 6 05 25 pm](https://cloud.githubusercontent.com/assets/16644017/20639309/f4f0d5c8-b402-11e6-9e40-72477439dc88.png)
  - Importing collection(startups) on MongoDB(mlab.com) to Alteryx. I've used the **MongoDB Input** connector built in to Alteryx's tools. 
![capture](https://cloud.githubusercontent.com/assets/16644017/20640150/ff3190c4-b419-11e6-98cc-a6c5a3e7a5be.JPG)
  - Some general execution information:
    - Records found: 18801;
    - Fetch time: 12:43 minutes:
    
![time-lapsed](https://cloud.githubusercontent.com/assets/16644017/20640242/bf59b312-b41b-11e6-893c-477e195b5722.JPG)


