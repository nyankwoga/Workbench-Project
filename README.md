-- Query 1: Gender Distribution
SELECT Gender, COUNT(*) FROM users GROUP BY Gender;

-- Query 2: Interest Frequency
SELECT Interest, COUNT(*) FROM user_interests GROUP BY Interest;

-- Additional Queries:

-- Query 3: Age Distribution (optional)
SELECT 
    CASE
        WHEN DOB BETWEEN '1950-01-01' AND '1959-12-31' THEN '1950s'
        WHEN DOB BETWEEN '1960-01-01' AND '1969-12-31' THEN '1960s'
        WHEN DOB BETWEEN '1970-01-01' AND '1979-12-31' THEN '1970s'
        WHEN DOB BETWEEN '1980-01-01' AND '1989-12-31' THEN '1980s'
        WHEN DOB BETWEEN '1990-01-01' AND '1999-12-31' THEN '1990s'
        WHEN DOB BETWEEN '2000-01-01' AND '2009-12-31' THEN '2000s'
    END AS AgeGroup, COUNT(*)
FROM users
GROUP BY AgeGroup;

-- Query 4: Users by Country
SELECT Country, COUNT(*) FROM users GROUP BY Country;

-- Query 5: Interests of Female Users
SELECT Interest, COUNT(*) 
FROM users
JOIN user_interests ON users.UserID = user_interests.UserID
WHERE Gender = 'Female'
GROUP BY Interest;

# Workbench-Project-