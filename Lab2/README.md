# Lab 2: Visualization using Amazon QuickSight

## Signing up for Amazon Quicksight Standard Edition

1. Open the [AWS ManagementConsole for QuickSight](https://us-east-1.quicksight.aws.amazon.com/sn/start).
2. If this is the first time you are accessing QuickSight, you will see a sign-uplanding page for QuickSight. 
3. Click on **Sign up for QuickSight**.

> **Note:** Chrome browser might timeout at this step. If that's the case, try this step in Firefox/Microsoft Edge/Safari.

![]()

4. On the next page, for the subscription type select the **"standard Edition"** and click **Continue**. 

![]()

5. On the next page,

   i. Enter a unique **QuickSight account name.**

   ii. Enter avalid email for **Notification email address**.

   iii. Just for this step, leave the **QuickSight capacity region **as **N.Virginia**. 

   iv. Ensure that **Enable autodiscovery of your data and users in your Amazon Redshift, Amazon RDS and AWS IAM Services** and **Amazon Athena** boxes are checked. 

   v. **Click finish**. 

   vi. You will be presented with a with message **Congratulations**! **You are signed up for Amazon QuickSight! **on successful sign up. Click on **Go to Amazon QuickSight**. 

![]()

6. On the Amazon QuickSight dashboard, navigate to User Settings page on the Top-Right section and click **Manage QuickSight**.

![]()

7. In this section, click on **Account Settings**.

![]()

8. Under Account Settings, in **Account Permissions ** Click **Edit AWS Permissions**.
9. Check the box for **Amazon S3** and you will see a pop-up to select Amazon S3 buckets.
10. Ensure **Select All **is checked.
11. Click on **Select buckets**.

![]()

12. Check the box for **Amazon S3 Storage Analytics **[Optional].
13. Click **Apply**.

![]()

## Configuring Amazon QuickSight to use Amazon Athena as data source

> For this lab, you will need to choose the **US West (Oregon)** region. 

1. Click on the region icon on the top-right corner of the page, and select **US West (Oregon)**. 

![]()

2. Click on **Manage data** on the top-right corner of the webpage to review existing data sets.
3. Click on **New data set** on the top-left corner of the webpage and review the options. 

![]()

4. Select **Athena** as a Data source.

![]()

5. Enter the **Data source** **name** (e.g. *AthenaDataSource*).
6. Click **Create data source**.

![]()

7. Select the mydatabase database.

![]()

8. Choose the **nytaxirides **table.
9. Choose **Edit/Preview** data.

> This is a crucial step. Please ensure you choose **Edit/Preview** data.

![]()

10. Under **Fields** on the left column, choose **New field**

    i. Select the **extract **operation from Function list.

    ii. Select **pickup_datetime** from the **Field list**.

    iii. For **Calculated field name**, type **hourofday**.

    iv. Type ‘HH’ so the Formula is **extract('HH',{pickup_datetime})**

    v. Choose **Create** to add a field which is calculated from an existing field. In this case, the **hourofday** field is calculated from the **pickup_datetime filed** based on the specified formula.

![]()

11. Choose **Save and Visualize** on top of the page.

## Visualizing the data using Amazon QuickSight

Now that you have configured the data source and created a new filed to represent the hour of the day, in this section you will filter the data by year followed by month to visualize the taxi data for the entire month of January 2016 based on the **pickup_datetime** field.

### Add year based filter to visualize the dataset for the year 2016

1. Ensure that current AWS region is **US West (Oregon)** region.

2. Under the **Fields List**, select the **year** field to show the distribution of fares per year.

3. To reformat the **year** without comma

   i. Select the dropdown arrow for the **year **field.

   ii. Select **Format 1,234.5678 **from the dropdown menu.

   iii. Select **12345**.

![]()

4. To add a filter on the **year** filed, 

   i. Select the dropdown for **year** field from the **Fields list**.

   ii. Select **Add filter to the field** from the dropdown menu.

![]()

5. To filter the data only for the year 2016,

   i. Choose the new filter that you just created by clicking on **#** next to filter name **year **under the **Edit filter** menu.

   ii. Select **Filter list** and **Include** for the two dropdowns under the filter name.

   iii. Deselect **ALL**.

   iv. Select only **2016**.

   v. Select **Close**.

![]()

### Add the month based filter for the month of January

1. Ensure that current AWS region is **US West(Oregon)** region.
2. Select **Visualize** from the navigation menu in the left-hand corner.
3. Under the **Fields list**, deselect **year**by clicking on **year** field name.
4. Select **month** by clicking on the **month** field name from the **Fields list**.

![]()

5. To filter the data set for the month of January (Month 1)

   i. Select the dropdown arrow for **month **field under the **Fields List**.

   ii. Select **Add filter to the field**.

![]()

6. To filter the data for month of January 2016 (Month 1),

   i. Choose the new filter that you just created by clicking on **# **next to filter name **month **under the **Edit Filter** menu.

   ii. Select **Filter list** and **Include** for the two dropdowns under the filter name.

   iii. Deselect **ALL**.

   iv. Select only **1**.

   v. Select **Close**.

![]()

### Visualize the data by hour of day for the month of January 2016

1. Select **Visualize** from the navigation menu in the left-hand corner.
2. Under the **Fields list**, deselect **month** by clicking on **month** field name.
3. Select **hourofday** by clicking on the **hourofday** field name from the **Fields list**.

![]()

4. Change the visual type to a line chart by selecting the line chart icon highlighted in the screenshot below under **Visual types**.
5. Using the slider on x-axis, select the entire range [0,23] for **hourofday** field.

![]()

### Visualize the data for the month of January 2016 for all taxi types(yellow, green, fhv)

1. Click on the double drop-down arrow underneath your username at the top-right corner of the page to reveal **X-axis**, **Value** and **Color** under **Field wells**.
2. Under the **Fields list**, deselect **hourofday** by clicking on **hourofday** field name.
3. Select **pickup_datetime** for x-axis by clicking on the **pickup_datetime **field name from **Fields list**.
4. Select **type** for Color by clicking on the **type** field name from **Fields list.**

![]()

5. Click on the field name **pickup_datetime** in x-axis to reveal a sub-menu.
6. Select **Aggregate:Year **from the revealed sub-menu.
7. Select **Day **to aggregate by day.

![]()

8. Using the slider on x-axis, select the entire month of January 2016 for **pickup_datetime** field.
9. Le Voila !

![]()

> Using Amazon QuickSight, you were able to see patterns across a time-series data by building visualizations, performing ad-hoc analysis, and quickly generating insights.
---
## License

This library is licensed under the Apache 2.0 License. 


















































