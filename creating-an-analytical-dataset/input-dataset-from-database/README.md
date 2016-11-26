Input Dataset from Database
===

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
