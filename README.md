 # modules.py

>1. 用于配置
```python
    from pymysql import connect
    from pymysql import cursors
    conf = model({})
    conf.host = '127.0.0.1'
    conf.user = 'root'
    conf.password = 'dandanMIJIAN'
    conf.charset = 'utf8mb4'
    conf.db = 'wen10_cn'
    conf.cursorclass = cursors.DictCursor
    # 可以这样配置
    #connection = connect(host=conf.host, user=conf.user, password=conf.password,
    #                      charset=conf.charset, db=conf.db,
    #                      cursorclass=conf.cursorclass)
    # 也可以这样使用
    connection = connect(**conf)
    with connection.cursor() as cursor:
        sql = "SELECT * FROM `you_table` limit 0, 100
        cursor.execute(sql)
        result = cursor.fetchall()
        print(result)
```

>2. 用户对象访问
```python
    conf.array = [{'dd': {'cc': {'ee': {'xx' : 'test'}}}}, {'a': 'b'}]
    conf.word = {'aa': 'bb'}
    conf.zz = [{'zz': 'xxx'}, {'uu': 'ww'}]
    print(conf.array[0].dd.cc.ee)

```
