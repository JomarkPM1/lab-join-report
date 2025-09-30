# Reports API Overview

## JOIN Types Explained

- **INNER JOIN**: Returns rows with matching keys in both tables.
- **LEFT JOIN**: Returns all rows from the left table, plus matches from the right (NULL if no match).
- **RIGHT JOIN**: Returns all rows from the right table, plus matches from the left (NULL if no match).
- **FULL OUTER JOIN (emulated)**: Combines LEFT and RIGHT JOIN to include all rows from both tables.
- **CROSS JOIN**: Returns every possible combination of rows from both tables.
- **SELF JOIN**: Joins a table to itself to relate rows within that table.

## /api/reports Endpoints

- `/api/reports/users-with-roles`  
  Lists all users with their assigned roles (INNER JOIN).

- `/api/reports/users-with-profiles`  
  Lists all users with their profile info if present (LEFT JOIN).

- `/api/reports/roles-right-join`  
  Lists all roles and their assigned users; includes roles with no users (RIGHT JOIN emulated).

- `/api/reports/profiles-full-outer`  
  Lists all users and profiles, showing matches and unmatched records (FULL OUTER JOIN emulated).

- `/api/reports/user-role-combos`  
  Lists every combination of user and role (CROSS JOIN).

- `/api/reports/referrals`  
  Shows who referred whom with emails (SELF JOIN).

- `/api/reports/latest-login`  
  Shows each user’s latest login details (LEFT JOIN with subquery).

---

All endpoints require a Bearer token for authentication in the Authorization header.
