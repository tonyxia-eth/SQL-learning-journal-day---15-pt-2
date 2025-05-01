# SQL-learning-journal-day---15-pt-2

# 💻 SQL Learning Journey — Day 15

## 🗓️ Date: [Insert Date]
## 🚀 Focus: Tasks 5, 6, and 7 (Player Career Tracking, Team Aggregates, Salary Analysis)

### ✅ What I Practiced

- Revisited **Task 5** and successfully wrote queries to find all teams a player has played for using `JOIN`, `DISTINCT`, and filtering logic.
- Moved into **Task 6** with `GROUP BY` and aggregate functions like `SUM(H)` to find total team hits in a given year.
- Tackled **Task 7** with complex queries to find:
  - The highest-paid player in MLB history
  - Players earning over $10M in a given year
  - Players with multi-year high salaries using `HAVING COUNT(DISTINCT year) >= 2`

### 🧠 Key Learnings

- **JOINs are about relationships**, not the data you want to display.
- **GROUP BY** defines *who or what* you're measuring, while aggregate functions like `SUM`, `AVG`, or `COUNT` tell you *how much* they did.
- **WHERE filters rows**, while **HAVING filters groups** — a crucial distinction that helped me debug group-based queries.
- Recognized the impact of column accuracy: mixing up `team_id` vs `team.name` caused mismatches, and I now know how to debug that fast.
- I hit a wall during my final quiz, but now understand that frustration is part of deeper learning — rewiring my brain for intermediate SQL!

### 🛠️ Commands I Used

```bash
-- Run queries and redirect to output
cat 6.sql | sqlite3 moneyball.db > "6.sql - results.txt"

-- Run multiple JOINs
SELECT teams.name, SUM(H) AS "total hits"
FROM performances
JOIN teams ON performances.team_id = teams.id
WHERE year = 1999
GROUP BY teams.name
ORDER BY "total hits" DESC
LIMIT 5;

📌 Summary
Today I worked hard to balance review and new challenges. I understand that confusion isn't failure — it's part of the process. Proud of the effort. Day 15 logged ✅
