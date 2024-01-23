---
title: Filter data based on user in a report | On-premise
description: This documentation explains how to filter data based on user login in a report using Bold Reports Designer.
keywords: report-platform, reporting
---

# How to filter data based on user in a report

In on-premise server, we can filter and display the data based on user who runs the report. In this section, we have explained the report design which displays the sales history of a salesperson who runs the report. Follow the step by step procedure to design such report in Bold Reports Designer.
First we need to connect to the data, and present it in table format using table report item.

## Connecting to Data

Here to showcase the sales history, sample data is prepared by creating a temporary table using SQL query in the query designer. You can also [connect to your data](./../../../designer-guide/report-designer/manage-data/) from any of your server or local database.
1. Click the `Data` icon in the configuration panel to launch a `Data` configuration pane.
![Report Designer page](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/data-pane.png)
2. Click on the `New Data` button in Data panel.
3. In the connection type panel, click the data source type that you want to connect. Here, `SQL` connection type is used to demonstrate.
![Connection types](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/connection-types.png)
4. In the new data source configuration panel, fill the server name and related details. As I said earlier, we are going to create a data set by temporary table concept. So, you can provide credentials and connect with any of your server or local databases.
![Connection panel](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/new-datasource.png)
5. Click on the `Connect` button, now the following view will be displayed.
![Query builder](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/query-designer.png)
6. In the query builder, you can build query with existing tables in your database or use the below query.

   ```sql
   DROP TABLE UserInfo
   CREATE TABLE UserInfo
   (
   user_id INT IDENTITY PRIMARY KEY,
   SalesPersonID VARCHAR(200) NOT NULL,
   SalesPerson VARCHAR(100) NOT NULL,
   CustomerName VARCHAR(100) NOT NULL,
   ProductName VARCHAR(100) NOT NULL,
   PurchaseDate DATETIME NOT NULL,
   ExpiryDate DATETIME NOT NULL,
   Amount Float,
   LicenseType VARCHAR(100) NOT NULL
   )
   INSERT INTO UserInfo
   VALUES ('smith@syncfusion.com','Smith', 'James', 'WEB (Essential JS 2)', '3/1/2016', '3/1/2017','23456', 'Standard'),
   ('smith@syncfusion.com','Smith', 'Jeff', 'WEB (Essential JS 1)', '9/8/2019', '9/8/2020','12323', 'Community'),
   ('smith@syncfusion.com','Smith', 'Armstrong', 'Embedded Reporting Tools', '1/12/2018', '1/12/2020','79897', 'Standard'),
   ('smith@syncfusion.com','Smith', 'Cromley', 'EnterpriseBI', '1/12/2018', '1/12/2020','45364', 'Platinum'),
   ('smith@syncfusion.com','Smith', 'Richardson', 'EnterpriseBI', '2/11/2017', '2/11/2020','21467', 'Platinum'),
   ('smith@syncfusion.com','Smith', 'Horton', 'Cloud BI', '9/11/2018', '2/11/2020','87897', 'Standard'),
   ('smith@syncfusion.com','Smith', 'Washington', 'Embedded BI', '3/8/2019', '3/8/2020','13446', 'Platinum'),
   ('smith@syncfusion.com','Smith', 'Victoria', 'WEB (Essential JS 2)', '3/8/2019', '3/8/2020','43566', 'Standard'),
   ('smith@syncfusion.com','Smith', 'Eric', 'FILE FORMAT', '3/8/2004', '8/12/2005','67899', 'Community'),
   ('smith@syncfusion.com','Smith', 'John', 'MOBILE', '8/8/2019', '8/8/2020','89800', 'Standard'),
   ('anderson@syncfusion.com','Anderson', 'Eric', 'WEB (Essential JS 2)', '1/1/2016', '1/1/2017','23456', 'Standard'),
   ('anderson@syncfusion.com','Anderson', 'James', 'WEB (Essential JS 1)', '10/8/2019', '10/8/2020','12323', 'Community'),
   ('anderson@syncfusion.com','Anderson', 'Victoria', 'Embedded Reporting Tools', '11/12/2018', '11/12/2020','79897', 'Standard'),
   ('anderson@syncfusion.com','Anderson', 'Charles', 'EnterpriseBI', '12/12/2018', '12/12/2020','45364', 'Platinum'),
   ('anderson@syncfusion.com','Anderson', 'Horton', 'EnterpriseBI', '5/11/2017', '5/11/2020','21467', 'Platinum'),
   ('anderson@syncfusion.com','Anderson', 'Richard', 'Cloud BI', '6/11/2018', '6/11/2020','87897', 'Standard'),
   ('anderson@syncfusion.com','Anderson', 'John', 'Embedded BI', '4/8/2019', '4/8/2020','13446', 'Platinum'),
   ('anderson@syncfusion.com','Anderson', 'Steffy', 'WEB (Essential JS 2)', '12/8/2019', '12/8/2020','43566', 'Standard'),
   ('anderson@syncfusion.com','Anderson', 'Pat', 'FILE FORMAT', '7/8/2004', '7/12/2005','67899', 'Community'),
   ('anderson@syncfusion.com','Anderson', 'Moffy', 'MOBILE', '5/8/2019', '5/8/2020','89800', 'Standard')
   SELECT * FROM UserInfo
   ```

   > Note: The above query is static sample data created for demonstration purpose.
7. Switch to the query mode and enter the query.
![Code mode](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/enter-query.png)

## Create query parameter

To filter the user specific data, create a parameter at query level. Add the below `WHERE` clause statement in the query mode.

```sql
WHERE SalesPersonID = @userid
```

## Filter data using user collection

The User collection provides detail about the user who ran the report. To filter the sales history, passing the sales person id as value for **user_id** parameter. Follow the below steps to assign the value for parameter.

1. Click on the Parameter icon in the query designer toolbar.
![Report parameter option in toolbar](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/parameter-icon.png)
2. By default, the Parameters dialog will be open with `@user_id` parameter.
![Parameters dialog](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/parameter-dialog.png)
3. Click on the small square icon next to the `Value` field.
![Option to add expression](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/expression-icon.png)
4. It will launch the expression dialog like below.
![Expression builder](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/expression-dialog.png)
5. Enter the `=User!UserID` expression in the text area and click OK.
![Enter expression to filter data](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/enter-expression.png)
6. Click `Finish`.

When the report runs the data set values will be filtered based on the current user who runs the report.

## Display data in table

The table report item is listed in the item panel under the Data Regions category.
![Table report item in item panel](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/itempanel.png)

Drag and drop the table report item into the design area from the item panel.
![Add table to the design](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/add-table.png)

Assign the required data fields in the table cell and format the report design as required using the properties listed in property panel. Refer [Simple Table Design](./../../../designer-guide/report-designer/report-items/tablix/design-ssrs-rdl-report-using-table/) section to learn the designing steps in detail.
The below report design will display the customer name, purchase details and sales amount achieved by a salesperson when the report runs.
![Simple table design to view sales history](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/design-view.png)

## Adding header to the report

To complete the design, add a header to the report. In the report header, we can show the salesperson name and title for the report. Follow the below steps to add header to the report.

1. Right-click on the design surface and select `Add Header` from context menu.
![Add header option in context menu](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/add-report-header.png)
2. To add the text to the header, drag the textbox report item to the header area.
![Adding textbox in header](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/add-textbox-in-header.png)
3. Right click inside the textbox and select `Expression` option from context menu.
![Add expression in text box](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/expression-menu.png)
4. In the expression builder, assign the `=First(Fields!SalesPerson.Value,"DataSet1")` expression.
![Enter expression to display sales person](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/add-expression-value-in-text-box.png)
5. Click OK.
6. Enter `- Sales History` text in the text box.
![Enter report title](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/append-title.png)

You can format the header textbox using the properties listed in the properties panel.

![Final report design view](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/header-output.png)

## Report Preview

Preview the report. Now based on the current user, the data will be displayed in the table as shown below.

![Sales history data of current user](/static/assets/on-premise/images/how-to/filter-data-based-on-user-in-a-report/report-preview.png)

You can download the report design from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/saleshistory-107027917).