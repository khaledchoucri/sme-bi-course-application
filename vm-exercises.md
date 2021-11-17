# Virtual Machine (VM) Exercises

## :information_source: Read this before getting started
- The two exercises should not replicate the exact actions shown in your screencast. The goal of exercises is for learners to apply what was learned in the screencasts to new problems or situations. This is best pedagogical practice for retaining and building skills. For example, this can be done by using another dataset between screencasts and exercises or focusing on a different portion of the dataset.
- We can only run free versions of BI software in our virtual machine exercises. In the case of Power BI, make sure the exercises can run on [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) without any additional paid products. 
- Unsure what the scope of an exercise should be? Here's an [example](https://campus.datacamp.com/courses/introduction-to-power-bi/getting-started-with-power-bi?ex=14) from Introduction to Power BI. The first chapter of most DataCamp courses are free, so take a look at our [BI courses](https://learn.datacamp.com/courses?technologies=Tableau&technologies=Power%20BI) to get a feel for how we assess and guide learners.

## 1st VM Exercise

#### Dataset

- [X] Add datasets used to the `datasets/` folder

#### Files

- [x] **Initial**: Add file to the `exercises/`  folder with the name `ex-1-intial.twbx` or `ex-1-intial.pbix`, depending if you are auditioning for a Tableau or Power BI course.
- [x] **Solution**: Add file to the `exercises/`  folder with the name `ex-1-sol.twbx` or `ex-1-sol.pbix`

#### Learning Objective

Understanding the use of adding an Index to a table or grouped table.

#### Context

Using an index is one of the ways you can rank data when combined with the sorting function. This is especially useful when combined with the group by operation as it allows one to compare the overall ranking of a certain metric to the grouped ranking within its category. This will also serve as the introduction to reading and understanding M Language/M Code. 

#### Steps to be executed by the student (max 6)

- Sort the Table by *Units In Stock* (Descending) [Note the Formula that appears in the formula bar as it will come in handy later]
- Add an Index Column (starting from 1) then, within the Formula Bar, change the name of the newly created column from *Index* to *OverallStockRank*
- Use the GroupBy Operation, leaving the ProductName, ProductID, and UnitsInStock Columns ungrouped. Name the first aggregation *CategoryStock* with the Sum of *UnitsInStock*.
- Add an Aggregation called *Grouped* and select the operation **All Rows** 
- Sort the Grouped Table by *CategoryStock* (Descending)
- Add an Index Column (starting from 1) then, within the Formula Bar, change the name of the newly created column from *Index* to *CategoryStockRank*

#### Exercise question:
Which Category has the 4th Highest Stock Level?
- Condiments
- Beverages
- **_Dairy Products_**
- Confections

#### End goal:

![image](https://user-images.githubusercontent.com/56801313/142156083-6b5c99bf-4c45-4b5f-863f-3bb62b79bed0.png)

## 2nd VM Exercise

#### Dataset

- [X] Add datasets used to the `datasets/` folder

#### Files

- [X] **Initial**: Add file to the `exercises/`  folder with the name `ex-2-intial.twbx` or `ex-2-intial.pbix`, depending if you are auditioning for a Tableau or Power BI course.
- [X] **Solution**: Add file to the `exercises/`  folder with the name `ex-2-sol.twbx` or `ex-2-sol.pbix`

#### Learning Objective

How to use Custom Columns to perform operations on grouped tables/rows. 

#### Context

Group By is a powerful data manipulation technique that can help with the engineering of new features/columns as well as the summarization of large datasets. Together with the Custom Columns feature of PowerBI you can also perform manipulation on the grouped rows resulting in some advanced transformations.

#### Steps to be executed by the student (max 6)

- Create a Custom Column named *SortedCategoryProduct*. The formula should use the [Table.Sort()](https://docs.microsoft.com/en-us/powerquery-m/table-sort) function, with the first argument being the [Grouped] column created earlier through the group by action. While the Second Parameter should be a collection {} containing the "UnitsInStock" Column as well as the Order.Descending argument.
- Create a Custom Column named *RankedCategoryProduct*. The formula should use the [Table.AddIndexColumn()](https://docs.microsoft.com/en-us/powerquery-m/table-addindexcolumn) function, with the first argument being the [SortedCategoryProduct] column created in the earlier step. While the Second Parameter should be the name of the newly created column (*RankedCategoryProduct*), and the 3rd Argument should be 1 (the Starting Index). 
- Remove the *Grouped* and *SortedCategoryProduct* Columns. 
- Expand the *RankedCategoryProduct* column, selecting all fields except *CategoryName* and *CategoryID*

#### Exercise question:
Which Product has a *CategoryStockRank* of 3 AND a *CategoryProductStockRank* of 3?
- Raclette Courdavault
- **_Louisiana Fiery Hot Pepper Sauce_**
- Chef Anton's Cajun Seasoning
- Gudbrandsdalsost

#### End goal:

![image](https://user-images.githubusercontent.com/56801313/142163335-d7ac472a-2e33-46d1-a29d-4546e507de86.png)

