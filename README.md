# Data Cleaning using power query editor 2

Data cleansing is a crucial step in the data preparation and analysis process. It entails detecting and fixing flaws, inconsistencies, and inaccuracies in datasets in order to ensure that the data is accurate, reliable, and fit for analysis.

The purpose of this exercise is to enhance my proficiency in data cleaning by utilizing the Power Query Editor in Excel
The dataset is downloaded from this [site](https://foresightbi.com.ng/microsoft-power-bi/dirty-data-samples-to-practice-on/)

## The Dataset
Order ID and the Order Date are well structured in column1 and column2 respectively. However, the Segment and Ship Mode are on Rows instead of columns. They are placed on the first two rows, starting from column2, above the Order ID and Order Date. 

Preview of the dataset
![The data](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/89c62d71-543e-4413-a2c5-5a2fd62eba98)

## Data cleaning process

Import the data and delete all steps from promoted header in the applied steps in the query setting

![applied step](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/2c1244bd-66e2-4d33-b9c3-68c98d4c1fda)

Now getting the segment and ship Mode on the Rows to columns is one of the important aspects of this data cleaning process.
The transpose feature in the transform tab helps in achieving this. However, before we use the transpose feature, we need to merge columns 1 and 2 into one column.

**-Hold the CTRL key on the keyboard**

**-Click and the select column1 and column2**

**-Right click on header of the selected columns and select Merge columns**

**-Choose a seperator, in this case - space and click ok**

![merge](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/7bb57b06-3a53-4858-9b30-66e2b62b5d73)

Now transpose the entire dataset using the transpose feature in the transform tab. By transposing the data, the structure of the dataset changes. The rows become columns and columns become rows. In this case, we have our merged column as a row after transposing the dataset. 

![transpose outcome](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/a4e9c4ae-e12a-4183-af5b-ec9eec7fe80f)


Click on the **use first row as headers** feature in the transform tab to use the first rows as column names

![use first row as header](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/c9bd5836-75d6-416d-87b6-6216e9473e77)


Click on the fill feature in the transform tab and select **fill down** in the drop-down menu to fill down the column of ship mode.

![fill down](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/7c789328-e90a-4201-b111-58c0c4d60898)


Now to get the merged column back (now as row), unpivot the columns containing the merged column(now as row) attributes. 
To do this; 

**-select the Ship mode and Segment columns**

**-In the transform tab, click on unpivot Columns and select unpivot other columns from the drop-dowmn menu**

![unpivot](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/b24f5ee6-1f76-4edb-9c44-1e0f)

To get the OrderId and OrderDate columns, split the attribute column. To do this select the Attribute column and in the tranform tab, click on split column and select **By delimeter** from the dropdown menu. Choose space and click ok. 

![Slip column and okay](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/9799069b-acb0-4a6d-9773-7c9ba3c53ead)

Rename Attribute1 and Attribute2 columns as OrderID and OrderDate respectively and remove Attribute3 column

![Rename and remove attribute3 column](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/45ba5901-e5a2-4df4-8561-22ea874c1262)

Well done. We have a clean data 

![Final outcome](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/assets/132214828/ce0a3e8c-e91e-428b-992a-b3b22cc4f952)

Take a look at the clean data [here](https://github.com/dannieRope/Data_Cleaning_Using_Excels-_Power_Query_Editor2/blob/main/clean.xlsx)



