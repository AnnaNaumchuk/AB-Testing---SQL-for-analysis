# AB Testing - SQL for Analysis
### SQL-запит для аналізу А/В тесту

## Overview / Огляд
This project provides an SQL query for analyzing A/B test results.  
It aggregates sessions, orders, events, and new account creation to evaluate user behavior across test groups.  

Цей проєкт містить SQL‑запит для аналізу результатів А/В тесту.  
Він агрегує дані про сесії, замовлення, події та створення нових акаунтів для оцінки поведінки користувачів у різних групах тесту.

## Query Logic / Логіка запиту
The query builds several Common Table Expressions (CTEs):  
Запит формує кілька проміжних таблиць (CTE):

- **[session_info](ca://s?q=session_info_CTE)** — base session data with test and group identifiers.  
- **[session_with_orders](ca://s?q=session_with_orders_CTE)** — counts sessions that resulted in orders.  
- **[events](ca://s?q=events_CTE)** — aggregates event counts per session.  
- **[session](ca://s?q=session_CTE)** — counts total sessions per test group.  
- **[account](ca://s?q=account_CTE)** — counts new accounts created during sessions.  

Finally, results are combined with `UNION ALL` into a unified dataset for analysis.  
У фіналі результати об’єднуються через `UNION ALL` у єдиний датасет для аналізу.

## Output Fields / Поля результату
- Date / Дата  
- Country / Країна  
- Device / Девайс  
- Continent / Континент  
- Channel / Канал  
- Test / Тест  
- Test group / Група тесту  
- Event name / Назва події  
- Value (count) / Значення (кількість)  

## Goals / Цілі
- Compare conversion metrics between test groups / Порівняння конверсій між групами тесту  
- Evaluate session and order dynamics / Аналіз динаміки сесій та замовлень  
- Track event frequency / Відстеження частоти подій  
- Measure new account creation / Оцінка створення нових акаунтів  

## How to Use / Використання
1. Run the SQL query in BigQuery or another compatible environment.  
2. Export results into a dataset for further visualization (Tableau, Python, etc.).  
3. Use the dataset to calculate conversion rates, p‑values, and statistical significance.  

---

This repository demonstrates SQL skills for A/B testing analysis and portfolio projects.  
Цей репозиторій демонструє навички SQL для аналізу А/В тестів та портфоліо‑проєктів.
