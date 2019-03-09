# Create a table in Azure Data Studio

*The following tutorial is based on this [Microsoft article](https://docs.microsoft.com/de-de/sql/azure-data-studio/quickstart-sql-database?view=sql-server-2017).*

Create a customers table with the following variables in [schema](https://docs.microsoft.com/de-de/dotnet/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server) `dbo`: 

- CustomerId 
- Name
- Location
- Sales

and set the variable `CustomerId`as the primary key column.

### Create a table

1) Right-click on your Azure Data Studio in the SERVERS sidebar and select New Query.
2) Paste this SQL into the query editor.

```{sql}
CREATE TABLE dbo.Customers
(
   CustomerId         INT    NOT NULL   PRIMARY KEY,
   Name     [NVARCHAR](50)  NOT NULL,
   City     [NVARCHAR](50)  NOT NULL,
   Country  [NVARCHAR](50)  NOT NULL,
   Sales              INT   NOT NULL
);
GO
```

3) From the toolbar, select Run. Notifications appear in the MESSAGES pane showing query progress.


### Insert rows into the table 'Customers'

Replace the previous query with this one and select Run.

```{sql}
INSERT INTO dbo.Customers
   ([CustomerId],[Name],[Location],[Sales])
VALUES
   ( 1, N'Alexander', N'Stuttgart', N'Germany', 1000),
   ( 2, N'Sarah', N'London', N'UK', 500),
   ( 3, N'Maria', N'Berlin', N'Germany',250),
   ( 4, N'Paul', N'London', N'UK', 1200)
GO
```

### View the result

Select rows from table 'Customers'. Replace the previous query with this one and select Run. Select rows from table

```{sql}
'Customers'
SELECT * FROM dbo.Customers;
```

