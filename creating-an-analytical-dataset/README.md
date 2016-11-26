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
Reference in [input-dataset-from-file](./input-dataset-from-file)

### 3b. Input a dataset into Alteryx (from Database);
--------
Reference in [input-dataset-from-database](./input-dataset-from-database)


