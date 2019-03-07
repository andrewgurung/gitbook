# SQL Techniques

### Get your environment set up

1. Install [SQLite](https://www.sqlite.org/quickstart.html) which is a lightweight popular database
2. Install [DB Browser for SQLite](https://sqlitebrowser.org/dl/)

### Create A New Database

* SQLite: At a shell or DOS prompt, enter: "**sqlite3 test.db**". This will create a new database named "test.db". \(You can use a different name if you like.\)
* DB Browser: Provides an easier user interface to execute SQL queries

### SQL basics

#### Create a table

```sql
create table exercise_logs ( id integer primary key autoincrement,
type text, minutes integer,
calories integer,
heart_rate integer);
```

#### Insert data into a table

```sql
INSERT INTO exercise_logs (type, minutes, calories, heart_rate) VALUES ('biking', 60, 100, 110);
INSERT INTO exercise_logs (type, minutes, calories, heart_rate) VALUES ('biking', 45, 120, 100);
INSERT INTO exercise_logs (type, minutes, calories, heart_rate) VALUES ('football', 62, 200, 120);
INSERT INTO exercise_logs (type, minutes, calories, heart_rate) VALUES ('football', 90, 210, 140);
INSERT INTO exercise_logs (type, minutes, calories, heart_rate) VALUES ('swimming', 30, 110, 120);
INSERT INTO exercise_logs (type, minutes, calories, heart_rate) VALUES ('swimming', 40, 150, 130);
```

#### Select statements

```sql
SELECT type, sum(calories) as total_calories
FROM exercise_logs 
GROUP BY type;
```

_type total\_calories  
biking 220  
football 410   
swimming 260_

### Credits

* [Data Lit SQL Techniques](https://www.theschool.ai/courses/data-lit/lessons/sql-techniques-for-hospital-database-management/)







