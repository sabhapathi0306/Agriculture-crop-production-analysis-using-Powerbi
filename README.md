# Agriculture Crop Production Analysis using Power Bi

For this project dataset was collected from Kaggle https://www.kaggle.com/datasets/abhinand05/crop-production-in-india

This dataset conatins around 240019 datasets with 6 columns[state name,distrct name ,crop ,crop_year,season ,area,production] and also some NAN values in production columns.These NaN are first filtered out using if else query in powerbi query .
NAN as 0 and datasets containing information about 33 states and 646 districts over 6 different seasons,124 different crops.Once after filtering the NAN values a groupby clause is created to group the districts and crops with production rate.
After all filteration interative analysis templet is developed using power bi ,where any can easly get understanding about kind of crop production in district level.Template includes 
two pages in first page ,overview about total states ,district ,total area ,total production , different season list ,year slide bar and bar graph.In second pages helps to 
understand the production rate of crops in different seasons and years with line graph and pie chart ,also gives the top five crops table.

![image](https://user-images.githubusercontent.com/70704151/189199070-3bb630d2-f147-4ab9-985c-fb0b97852474.png)

![image](https://user-images.githubusercontent.com/70704151/189199708-114e73f0-5f91-43fe-b2b4-8615fad427fb.png)

Example of working

![image](https://user-images.githubusercontent.com/70704151/189200520-0e36a004-8af9-42b9-a58b-38c619f7451a.png)

![image](https://user-images.githubusercontent.com/70704151/189200621-2f5b0338-fc70-45c8-8003-52ff14b8fa86.png)

Queries used:
= Table.AddColumn(#"Changed Type", "Filtered_production", each if [Production] = null then 0 else [Production])
=GROUPBY('new_data',new_data[State_Name],new_data[Districts],new_data[Crop],"Production_rate",SUMX(CURRENTGROUP(),new_data[Filtered_Production]))


Template is dynamic one can play and analyis the datasets as per their requirement 
