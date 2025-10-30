Internship - Task 7: Creating View
The primary objective of this task was to learn and practice creating and utilizing **Views** in SQL. [cite_start]Views are essential tools for implementing data **abstraction**, enhancing **security**, and creating **reusable SQL logic**[cite: 4, 9, 11, 23].

## Tools Used
* [cite_start]**Database**: SQLite / MySQL (as per task instructions) [cite: 5]
* [cite_start]**Client**: DB Browser for SQLite / MySQL Workbench [cite: 5]

##  Key Concepts Covered
* **View Definition**: A view is a stored query that acts like a virtual table.
* [cite_start]**Abstraction**: Hiding complex details like joins, aggregations, and business logic.
* [cite_start]**Security**: Restricting user access to sensitive columns (like sales data) or rows.
* [cite_start]**`WITH CHECK OPTION`**: Enforces that all data modifications (INSERT/UPDATE) made through the view adhere to the view's filtering conditions[cite: 22].
* [cite_start]**Dropping a View**: The SQL command `DROP VIEW ViewName;` is used to remove a view.

## Deliverables: View Definitions and Usage Examples

The following views demonstrate the objectives of the task:

### 1. `UK_Bestsellers_View` (Abstraction of Join and Filter)
**Goal**: Simplifies a complex query to show highly successful books from UK authors.

```sql
CREATE VIEW UK_Bestsellers_View AS
SELECT
    B.Title,
    B.PublicationYear,
    B.CopiesSold,
    A.FirstName,
    A.LastName
FROM
    Books B
JOIN
    Authors A ON B.AuthorID = A.AuthorID
WHERE
    A.Country = 'UK' AND B.CopiesSold >= 15000000;
