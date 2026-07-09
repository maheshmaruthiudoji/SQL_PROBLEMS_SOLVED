175. Combine Two Tables

Problem Statement

Write a SQL query to report the following information for each person:

- first name
- last name
- city
- state

The data is stored in two tables:

Person Table

| Column Name | Type |
|-------------|------|
| personId | int |
| lastName | varchar |
| firstName | varchar |

`personId` is the primary key
Address Table

| Column Name | Type |
|-------------|------|
| addressId | int |
| personId | int |
| city | varchar |
| state | varchar |

If a person's address is not available in the Address table, return NULL for city and state.

---

SQL Solution

```
SELECT
    p.firstName,
    p.lastName,
    a.city,
    a.state
FROM Person AS p
LEFT JOIN Address AS a
ON p.personId = a.personId;
```

