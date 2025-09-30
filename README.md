# Day6-Task

# 📘 Library Database – Subqueries Examples

This project demonstrates **different types of subqueries** in MySQL using a Library Management System database.  
We explore `IN`, `EXISTS`, `Scalar Subqueries`, and `Correlated Subqueries`.

---

## 🔹 1. Subquery with `IN`
SELECT Name FROM Member WHERE Member_Id IN (SELECT Member_Id FROM Loan);
👉 Finds members who have borrowed at least one book.  

---

## 🔹 2. Subquery with `EXISTS`

SELECT Staff_Name FROM Staff s
WHERE EXISTS (SELECT 1 FROM Loan l WHERE l.Staff_Id = s.Staff_Id);

👉 Finds staff who have issued at least one book.  

---

## 🔹 3. Scalar Subquery

SELECT Title, Price FROM Books
WHERE Price = (SELECT MAX(Price) FROM Books);

👉 Finds the book(s) with the **highest price**.  
- Scalar subquery returns a **single value** (`MAX(Price)`).  

---

## 🔹 4. Correlated Subquery

SELECT Title, Cat_Id, Price
FROM Books b1
WHERE Price = (SELECT MAX(Price) FROM Books b2 WHERE b1.Cat_Id = b2.Cat_Id);

👉 Finds the **highest-priced book in each category**.  
- Subquery depends on outer query (`b1.Cat_Id`).  

---

## 📝 Key Points
- **IN** → Compares value against a list.  
- **EXISTS** → Checks if rows exist (True/False).  
- **Scalar Subquery** → Returns a single value.  
- **Correlated Subquery** → Executes row-by-row, depends on outer query.  

---

⚡ This README explains the usage of different subquery types in a real database scenario.  
