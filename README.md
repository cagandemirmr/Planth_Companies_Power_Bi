# Planth_Companies_Power_Bi

First, i check data types and remove dublicates.
![image](https://github.com/user-attachments/assets/75514df2-16f4-4529-9d82-58cd98dfbd2e)

![image](https://github.com/user-attachments/assets/a27698aa-eb27-4401-9d30-ff2275c796d5)


Change Column name to work more efficiently
![image](https://github.com/user-attachments/assets/bae6792a-98db-4140-9326-bf38ff76481f)

Change data type of date in a correct format.
![image](https://github.com/user-attachments/assets/2f620356-9f5b-409c-9b2e-f97df28bb2b3)

Create table from new table in modelling tab. And write dax as  calender(date(2022,01,01),date(2024,12,31))
![image](https://github.com/user-attachments/assets/e7632de9-864e-4aa0-9623-21c798ccc09a) 
![image](https://github.com/user-attachments/assets/9231752e-4f9c-4cd0-ad48-48ff6ae1f308)


Create column ıf date table is in the last sale date.
Dax function of the code.
Inpast = 
var lastsalesdate = MAX(fact_Sales[Date_Time])
var lastsalesdatePY =EDATE(lastsalesdate,-12)
return
Dim_date[Date]<= lastsalesdatePY


After that, i create table to create slider.
![image](https://github.com/user-attachments/assets/050ebe8c-8777-4917-ad8c-4ae8edd1bc25)

Calculate sales based on previous date values by using dim_dates in measures.
DAX function:
PYTD_Sales = 
CALCULATE([Sales],
                    SAMEPERIODLASTYEAR(Dim_date[Date]),Dim_date[Inpast]=TRUE) 

Calculate YTD by using measures:
YTD_Sales = TOTALYTD([Sales],fact_Sales[Date_Time])


Create Slider from SLC_values
![image](https://github.com/user-attachments/assets/b138c283-7fa4-4db5-a946-cd7f08a2107e)

In this slicers, i created measure table using dax formula below:
S_PYTD = 
var selected_value = SELECTEDVALUE(SLC_values[Values])
var result = SWITCH(selected_value,
    "Sales",[PYTD_Sales],
    "Quantity",[PYTD_Quantity],
    "Gross_Profit",[PYTD_Gross_Profit],
    BLANK())
RETURN result

I used same formula to YTD and PYTD vs YTD slicers.

![image](https://github.com/user-attachments/assets/ae371889-b4d6-44fd-8949-eee9909838ae)

Add Background to the Board.
![image](https://github.com/user-attachments/assets/8b430e9c-aff9-48bb-a4bd-294bcc62eb0c)

I display worst 10 countries in terms of differences from PYTD to YTD.

![image](https://github.com/user-attachments/assets/8983eabf-3a45-47ed-a581-315434e2a3e0)

![image](https://github.com/user-attachments/assets/8851287e-061c-4c75-b4c9-f479a48fa7db)

Also,Added waterfall graph between PYTD vs YTD and Date,month,country,Product type,Product Name categories. I prefer many categories because i want to drill down.

![image](https://github.com/user-attachments/assets/2ac042e4-4a9b-4301-ab15-c68192a8321c)

![image](https://github.com/user-attachments/assets/5f75d1d9-2ab2-4411-96f8-fb86a3a6c3cb)

![image](https://github.com/user-attachments/assets/366cefde-0872-4597-ab86-70c11d10e4b6)

Also, i wanted to create Line and Stacked column. I wanted to compare YTD and PYTD values in terms of quarter and monh date.

![image](https://github.com/user-attachments/assets/160f919c-793c-4762-a70e-a03d2e74e316)

![image](https://github.com/user-attachments/assets/b2b45f96-9d42-48f0-b963-3cf0523ca441)

![image](https://github.com/user-attachments/assets/89d7f378-83a1-4164-815e-792188a5ab97)


I create scatter plot and add zoom slider to compare Gross Percentage and YTD.


![image](https://github.com/user-attachments/assets/0df72a78-90d9-46a4-aadd-7ec9023316b2)


![image](https://github.com/user-attachments/assets/c8ab6e40-9a0c-466b-8025-c15f10ac7717)

And define median line.

![image](https://github.com/user-attachments/assets/9a913442-ddf8-4be6-a1cf-92efb74baaf1)

Create measure for highlight.
![image](https://github.com/user-attachments/assets/b6f04681-938e-4414-96a9-b34ce37d144a)

In the last step, i edit card with conditional formatting.In this format, i change the color of text and fill.

![image](https://github.com/user-attachments/assets/f3840b21-de46-43ec-aa6b-33ae15b84eb3)


![image](https://github.com/user-attachments/assets/8a221a49-c46e-4015-9eb1-032240df35b0).


I adopt to the graph. 

![image](https://github.com/user-attachments/assets/4fbd827c-04a9-46f7-a88f-5ed2a8a3ad63)


In the end, i change layout.
![image](https://github.com/user-attachments/assets/aa4ff72e-5e2d-4295-b248-b018cdb2fad6)




