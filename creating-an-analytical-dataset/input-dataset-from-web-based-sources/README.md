Input dataset from Web Based Sources
===
#### Input procedure
1. Use Text Input to input the URL [Full link](http://www.5280.com/topdocslist?title=&specialty=All&hospital=All&distance%5Bpostal_code%5D=&distance%5Bsearch_distance%5D=5&distance%5Bsearch_units%5D=mile&field_year_value=&field_doctor_current_year_value_checkbox=0&page=full);
2. Use the Download Tool (under connectors) to Download the contents of the specified URL;
3. Use the Browse tool to **so we can view the data that comes out**;

#### Alteryx Web-Based sources workflow
![alteryx-workflow-web-based](https://cloud.githubusercontent.com/assets/16644017/20640385/d9cc2776-b41f-11e6-9357-ce47a04f303f.JPG)

#### Result
![web-scraping](https://cloud.githubusercontent.com/assets/16644017/20640376/9b4b95a4-b41f-11e6-9c7e-41c18c3d644d.JPG)


Exercise
===
- Scrape a page on the Alteryx site containing the list of Alteryx ACEs.
- The ACE program highlights the most influential and supportive experts of Alteryx Analytics.
- Scrape the page [http://www.alteryx.com/ace-program](http://www.alteryx.com/ace-program) and output the results to a CSV file with no delimiter (Delimiter is \0) and where the first row does not contain the field names.

#### Workflow on Alteryx (Scrape the page content on Alteryx)
![csv-output-workflow](https://cloud.githubusercontent.com/assets/16644017/20640495/8523f4f8-b422-11e6-9376-9421c3328d23.JPG)

#### CSV Output
![csv-output](https://cloud.githubusercontent.com/assets/16644017/20640461/d0f2c57c-b421-11e6-8642-506229278c12.JPG)
