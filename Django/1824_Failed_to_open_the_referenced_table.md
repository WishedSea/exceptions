# Environment
> ## PC
>> CPU: Apple M1
>> OS: macOS Ventura 13.2
>
> ## Versions
>> Python: 3.10.9
>> Django: 4.1.5
>> PyMySQL: 1.0.2

# When?
> 1. Default AUTH_USER_MODEL changed

# Error Message
```
$ python manage.py migrate                                             
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, sessions
Running migrations:
  Applying contenttypes.0001_initial... OK
  Applying admin.0001_initial...Traceback (most recent call last):
File "/~/lib/python3.10/site-packages/django/db/backends/utils.py", line 89, in _execute
    return self.cursor.execute(sql, params)
.
.
.
File "/~/lib/python3.10/site-packages/pymysql/err.py", line 143, in raise_mysql_exception
    raise errorclass(errno, errval)
pymysql.err.OperationalError: (1824, "Failed to open the referenced table 'blablabla'")
```

# solve
First, Do migration APP after migrate

$ python manage.py makemigrations [APP_NAME]
$ python manage.py migrate