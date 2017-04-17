BigDataProject

Term Project for Big Data Course at NYU Center for Data Science

Yanli Zhou, Liwei Song, Zhiqi Guo

Data Used:NYPD Complaint Data Historic

The dataset used for this project can be downloaded from the NYC Open Data at https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Historic/qgea-i56i.



#### Column data issue output instruction
#For outputof column 15-23.   
To get output of column 15-23 , please open output_script_liwei_15_23.

ADDR_PCT_CD-crime_addr.py   
LOC_OF_OCCUR_DESC-crime_loc.py   
PREM_TYP_DESC-crime_pt.py   
PARKS_NM-crime_park.py   
HADEVELOPT-crime_hd.py   
X_COORD_CD-crime_xc.py   
Y_COORD_CD-crime_yc.py   
Latitude-crime_latitude.py   
Longitude-crime_long.py    
Lat_Lon-crime_ll.py   


Enter spark-submit *.py NYPD_Complaint_Data_Historic in dumbo
Then use hadoop fs -getmerge *.out *out   

For example: to get output of Y_COORD_CD-crime_yc.py   
We could use:   
spark-submit crime_yc.py NYPD_Complaint_Data_Historic   
After pyspark successfully finsh the task, enter the following command:   
hadoop fs -getmerge crime_yc.out crime_yc.out    


Then, we could use check.py to check the number of valid/missing/invalid numbers of column output.   
For example for crime_yc.out:   
spark-submit check.py crime_yc.out   
Then    
hadoop fs -getmerge check.out check.out   


To check semantic type of column output,we could use check_semantic.py:   
For example:   
spark-submit check_semantic.py crime_yc.out   
Then    
hadoop fs -getmerge check.out check.out


####
Map Reduce Output for plots preparation
In order to make explorary plot of some columns, we also write some scripts to process different column.
Open mr_final
###For column 16-18:
PREM_TYP_DESC-crime_16.py output:crime_16.out
PARKS_NM-crime_17.py output:crime_17.out
HADEVELOPT-crime_18.py output:crime_18.out   

To run code:   
spark-submit crime_##.py    
hadoop fs -getmerge crime_##.out crime_##.out




