# Data Cleaning using power query editor 2

Data cleansing is a crucial step in the data preparation and analysis process. It entails detecting and fixing flaws, inconsistencies, and inaccuracies in datasets in order to ensure that the data is accurate, reliable, and fit for analysis.

The purpose of this exercise is to enhance my proficiency in data cleaning by utilizing the Power Query Editor in Excel
The dataset is downloaded from this [site](https://foresightbi.com.ng/microsoft-power-bi/dirty-data-samples-to-practice-on/)

## The Dataset
Order ID and the Order Date are well structured in column1 and column2 respectively. However, the Segment and Ship Mode are on Rows instead of columns. They are placed on the first two rows, starting from column2 above the Order ID and Order Date. 

## Data cleaning process

Import the data and delete all steps from promoted header in the applied steps in the query setting
Now getting the segment and ship Mode on the Rows to column is one of the important aspect of this data cleaning process.
The transpose feature in the transform tab helps in achieving this. However before we use the transpose feature, we need to merge the column1 and column2 into one column. 

**-Hold the CTRL key on the keyboard**

**-Click and the select column1 and column2**

**-Right click on header of the selected columns and select Merge columns**

**-Choose a seperator, in this case - space and click ok**

Now transpose the entire dataset using the transpose feature in the transform tab. By transposing the data, the structure of the dataset changes. The rows become columns and columns become rows. In this case, we have our merged column as a row after transposing the dataset. 

Click on the **use first row as headers** feature in the transform tab to use the first rows as column names

Click on the fill feature in the transform tab and select **fill down** in the drop-down menu to fill down the column of ship mode.


Now to get the merged column back (now as row), unpivot the columns containing the merged column(now as row) attributes. 
To do this; 

**-select the Ship mode and Segment columns**

**-In the transform tab, click on unpivot Columns and select unpivot other columns from the drop-dowmn menu**

To get the OrderId and OrderDate columns, split the attribute column. To do this select the Attribute column and in the tranform tab, click on split column and select **By delimeter** from the dropdown menu. Choose space and click ok. 
