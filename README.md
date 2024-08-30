# python-sqlite3

## Database
```bash
$ sqlite3 DatabaseName.db
```
```sqlite
sqlite3> ATTACH DATABASE 'DatabaseName' As 'Alias-Name';
sqlite3> DETACH DATABASE 'Alias-Name';
```

### Table
```sqlite
sqlite3> .databases
sqlite3> .tables
sqlite3> .schema
sqlite3> .quit
```



## Python
```python
import sqlite3

conn = sqlite3.connect(':memory:')
conn.execute("""
    CREATE TABLE COMPANY
        (ID INT PRIMARY KEY NOT NULL
        , NAME TEXT NOT NULL
        , AGE INT NOT NULL
        , ADDRESS CHAR(50)
        , SALARY REAL);
""")
conn.close()
```

### Pandas
```python
import pandas as pd
import sqlite3

conn = sqlite3.connect(':memory:')
conn.execute("""
    CREATE TABLE COMPANY
        (ID INT PRIMARY KEY NOT NULL
        , NAME TEXT NOT NULL
        , AGE INT NOT NULL
        , ADDRESS CHAR(50)
        , SALARY REAL);
""")
df = pd.read_sql("SELECT * FROM COMPANY", conn, index_col=None)
conn.close()
```
