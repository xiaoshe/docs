# 日期类函数

```python
df = spark.createDataFrame([('2020-01-01',)], ['dt'])
df.show()
'''
+----------+
|        dt|
+----------+
|2020-01-01|
+----------+
'''
df.select(F.add_months(df.dt, 1).alias('next_month'),  # 下月
          F.add_months(df.dt, -1).alias('prev_month'), # 上月
          F.date_add(df.dt, 1).alias('next_date'), # 明天
          F.date_sub(df.dt, 1).alias('prev_date'), # 昨天
          F.date_format(df.dt, 'yyyy.MM.dd').alias('date'), # 格式
          F.dayofmonth('dt').alias('day'), # 某月第x天，从1开始
          F.dayofweek('dt').alias('wday'), # 某周第x天，周日开始算第1天
          F.dayofyear('dt').alias('yday'), # 某年第x天，从1开始
          F.month('dt').alias('month'), # 月
          F.quarter('dt').alias('quarter'), # 季
          F.weekofyear('dt').alias('week'), # 某年第x周，从1开始
          F.year('dt').alias('year') # 年
          ).show()
'''
+----------+----------+----------+----------+----------+---+----+----+-----+-------+----+----+
|next_month|prev_month| next_date| prev_date|      date|day|wday|yday|month|quarter|week|year|
+----------+----------+----------+----------+----------+---+----+----+-----+-------+----+----+
|2020-02-01|2019-12-01|2020-01-02|2019-12-31|2020.01.01|  1|   4|   1|    1|      1|   1|2020|
+----------+----------+----------+----------+----------+---+----+----+-----+-------+----+----+

'''
```


date_trunc: 精确到某个时间维度，其后的时间维度设置为0.
```python
df = spark.createDataFrame([('2020-06-28 12:00:32',)], ['dt'])
df.show()
'''
+-------------------+
|                 dt|
+-------------------+
|2020-06-28 12:00:32|
+-------------------+
'''

df.select(F.date_trunc('year', df.dt).alias('year'), # 精确到年
          F.date_trunc('mon', df.dt).alias('month'), # 精确到月
          F.date_trunc('day', df.dt).alias('day'), # 精确到天
          F.date_trunc('hour', df.dt).alias('hour'),
          F.date_trunc('minute', df.dt).alias('minute'),
          F.date_trunc('second', df.dt).alias('second'),
          F.date_trunc('week', df.dt).alias('week'), # 精确到周
          F.date_trunc('quarter', df.dt).alias('quarter') # 精确到季
         ).show()
'''
+-------------------+-------------------+-------------------+-------------------+-------------------+-------------------+-------------------+-------------------+
|               year|              month|                day|               hour|             minute|             second|               week|            quarter|
+-------------------+-------------------+-------------------+-------------------+-------------------+-------------------+-------------------+-------------------+
|2020-01-01 00:00:00|2020-06-01 00:00:00|2020-06-28 00:00:00|2020-06-28 12:00:00|2020-06-28 12:00:00|2020-06-28 12:00:32|2020-06-22 00:00:00|2020-04-01 00:00:00|
+-------------------+-------------------+-------------------+-------------------+-------------------+-------------------+-------------------+-------------------+
'''
```
