# Coffee-Shop-Sales

Creating an interactive dashboard to show revenue and transaction trends from a dataset with 150,000 rows. If you want the dataset, it can be downloaded by clicking <a href = "https://maven-datasets.s3.amazonaws.com/Coffee+Shop+Sales/Coffee+Shop+Sales.zip">here</a>.

## Objective:
#### To find sales trends over time, which days of the week were busiest, and top sellers. Then creating a interactive dashboard for the stores in the area.

### Prepare the data:

To begin, I created six new rows to add to the dataset. `Revenue`, `Month`, `Month Name`, `Weekday`, `Weekday Name`, and `Hour`
  `Revenue` just mulitipled `unit_price` and `transaction_qty` together.
  `Month` used the formula `=MONTH(B2)`
  `Month Name` used the formula `=TEXT(B2,"MMM")`
  `Weekday` used the formula `=WEEKDAY(B2,2*)` *used 2 to have the weekday start on a Monday
  `Weekday Name` used the formula `=TEXT(B2,"DDD")`
  `Hour` used the formula `=HOUR(C2)`

After this the data was ready to be used and created a few Pivot Tables.

### Pivot Tables & Charts:

#### Total Revenue by Month:

 This pivot table used the 'sum of `Revenue`' as the value and used `Month Name` as the label for the rows:
 
 ![image](https://github.com/user-attachments/assets/9ca37069-8f0b-4730-9872-fe7d082211e3)

 Using this table, I created a line chart.  Hid the grid lines, changed the colors, and added totals aboved the plotted points:
 
 ![image](https://github.com/user-attachments/assets/49f71856-7c28-4921-8845-c5512e183e7c)


#### Transactions by the Day of the Week:

This pivot table used the 'count of `transaction_id`' as the value and used `Week Name` as the label for the rows:

![image](https://github.com/user-attachments/assets/69565e1f-ef85-42c5-832a-556a087144b4)

Using this table, I created a column chart.  Hid the grid lines and changed the colors:

![image](https://github.com/user-attachments/assets/a058b9d1-310d-454e-8c83-bdd0c12b1f87)

#### Transactions by the Hour of the Day:

This one was very similar to the one before, just swapped out `Week Name` label for `Hour` in the rows section:

![image](https://github.com/user-attachments/assets/36b3a35a-539e-41ec-8514-1394bbee0f26)

The Chart was also done the same way as well:

![image](https://github.com/user-attachments/assets/34865bac-7119-442a-b5ff-30eef3b57e18)

#### Transactions by Product Category:

This pivot table used the 'count of `transaction_id`' again as the value and used `product_category` as the label for the rows.
Then also sorted it in DESC order by 'count of `transaction_id`':

![image](https://github.com/user-attachments/assets/7eab7c4e-c2ed-4595-ac66-8b48b229473f)

The chart for this one was a bar chart.  Cleaned it up again, got rid of labels and added totals to the right of the bar:

![image](https://github.com/user-attachments/assets/5754510b-21cc-4411-9ff0-78dec8d1e7d1)

#### Top 15 Products:

For this one, just a pivot table was create, no chart.  This one used both values that were used above, 'count of `transaction_id`' and 'sum of `Revenue`'.
Sorted it in DESC order by 'count of `transaction_id`' and added a filter for only the Top 15:

![image](https://github.com/user-attachments/assets/42d7beb3-2f97-40ec-8f1c-926de2382835)


## Dashboard:

For this I hid the Pivot tables, all except the Top 15 Products one.
Then formatted the remaining charts into a good order, hid Headings, Gridlines, and Formula Bar and added a slicer for the `store_location`. Now anyone would be able to see the information on any of the stores or any combination of them:

![image](https://github.com/user-attachments/assets/58c9bef9-0831-48db-bbcc-fd39cf38ed70)
