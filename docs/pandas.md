# pandas

## pandas安装
使用pip安装pandas：

    pip install pandas
安装后可以查看pandas版本
```python
    >>>import pandas as pd
    >>>pd.__version__
```
## pandas数据结构——Series
Series为一维数组：pandas.Series( data, index, dtype, name, copy)
参数说明：

    data：一组数据(ndarray 类型)。
    index：数据索引标签，如果不指定，默认从 0 开始。
    dtype：数据类型，默认会自己判断。
    name：设置名称。
    copy：拷贝数据，默认为 False。
有关series的更多操作：
```python
    # 获取值
    value = series[2]  # 获取索引为2的值
    # 获取多个值
    subset = series[1:4]  # 获取索引为1到3的值
    # 使用自定义索引
    value = series_with_index['b']  # 获取索引为'b'的值
    # 索引和值的对应关系
    for index, value in series_with_index.items():
        print(f"Index: {index}, Value: {value}")
    # 算术运算
    result = series * 2  # 所有元素乘以2
    # 过滤
    filtered_series = series[series > 2]  # 选择大于2的元素
    # 数学函数
    import numpy as np
    result = np.sqrt(series)  # 对每个元素取平方根
    # 获取索引
    index = series_with_index.index
    # 获取值数组
    values = series_with_index.values
    # 获取描述统计信息
    stats = series_with_index.describe()
    # 获取最大值和最小值的索引
    max_index = series_with_index.idxmax()
    min_index = series_with_index.idxmin()
```
## pandas数据结构——DataFrame
DataFrame是一个表格型的数据结构，类似Series组成的字典：pandas.DataFrame( data, index, columns, dtype, copy)
参数说明：
    
    data：一组数据(ndarray、series, map, lists, dict 等类型)。
    index：索引值，或者可以称为行标签。
    columns：列标签，默认为 RangeIndex (0, 1, 2, …, n) 。
    dtype：数据类型。
    copy：拷贝数据，默认为 False。
pandas可以使用loc属性返回指定行的数据：
```python
    import pandas as pd

    data = {
      "calories": [420, 380, 390],
      "duration": [50, 40, 45]
    }

    # 数据载入到 DataFrame 对象
    df = pd.DataFrame(data)

    # 返回第一行
    print(df.loc[0])
    # 返回第二行
    print(df.loc[1])
```
有关DataFrame的更多操作：
```python
    # 获取列
    name_column = df['Name']
    # 获取行
    first_row = df.loc[0]
    # 选择多列
    subset = df[['Name', 'Age']]
    # 过滤行
    filtered_rows = df[df['Age'] > 30]
    # 获取列名
    columns = df.columns
    # 获取形状（行数和列数）
    shape = df.shape
    # 获取索引
    index = df.index
    # 获取描述统计信息
    stats = df.describe()
    # 添加新列
    df['Salary'] = [50000, 60000, 70000]
    # 删除列
    df.drop('City', axis=1, inplace=True)
    # 排序
    df.sort_values(by='Age', ascending=False, inplace=True)
    # 重命名列
    df.rename(columns={'Name': 'Full Name'}, inplace=True)
    # 从CSV文件创建 DataFrame
    df_csv = pd.read_csv('example.csv')
    # 从Excel文件创建 DataFrame
    df_excel = pd.read_excel('example.xlsx')
    # 从字典列表创建 DataFrame
    data_list = [{'Name': 'Alice', 'Age': 25}, {'Name': 'Bob', 'Age': 30}]
    df_from_list = pd.DataFrame(data_list)
```
## pandas数据获取
数据集的文件格式常见的有csv、json、excel等，具体见[pandas常用函数](#pandas常用函数)。
## pandas数据清洗
1.**pandas清洗空值**：DataFrame.dropna(axis=0, how='any', thresh=None, subset=None, inplace=False)
参数说明：

    axis：默认为 0，表示逢空值剔除整行，如果设置参数 axis＝1 表示逢空值去掉整列。
    how：默认为 'any' 如果一行（或一列）里任何一个数据有出现 NA 就去掉整行，如果设置 how='all' 一行（或列）都是 NA 才去掉这整行。
    thresh：设置需要多少非空值的数据才可以保留下来的。
    subset：设置想要检查的列。如果是多个列，可以使用列名的 list 作为参数。
    inplace：如果设置 True，将计算得到的值直接覆盖之前的值并返回 None，修改的是源数据。
可以通过isnull()判断各个单元格是否为空。
2.**pandas清洗格式错误的数据**：将所有单元格转换成相同格式的数据
3.**pandas清洗错误数据**：替换或者移除
例如：删除年龄大于120的行
```python
    import pandas as pd

    person = {
      "name": ['Google', 'Runoob' , 'Taobao'],
      "age": [50, 40, 12345]    # 12345 年龄数据是错误的
    }

    df = pd.DataFrame(person)

    for x in df.index:
      if df.loc[x, "age"] > 120:
        df.drop(x, inplace = True)

    print(df.to_string())
```
4.**pandas清洗重复数据**：使用duplicated()和drop_duplicates()方法。如果对应的数据是重复的，duplicated()会返回True，否则返回False。
## pandas常用函数
**读取数据**
|函数|说明|
|-|-|
|pd.read_csv(filename)|读取 CSV 文件；|
|pd.read_excel(filename)|读取 Excel 文件；|
|pd.read_sql(query, connection_object)|从 SQL 数据库读取数据；|
|pd.read_json(json_string)|从 JSON 字符串中读取数据；|
|pd.read_html(url)|从 HTML 页面中读取数据。|

**查看数据**
|函数|说明|
|-|-|
|df.head(n)|显示前 n 行数据；|
|df.tail(n)|显示后 n 行数据；|
|df.info()|显示数据的信息，包括列名、数据类型、缺失值等；|
|df.describe()|显示数据的基本统计信息，包括均值、方差、最大值、最小值等；|
|df.shape|显示数据的行数和列数。|

**数据清洗**
|函数|说明|
|-|-|
|df.dropna()|删除包含缺失值的行或列；|
|df.fillna(value)|将缺失值替换为指定的值；|
|df.replace(old_value, new_value)|将指定值替换为新值；|
|df.duplicated()|检查是否有重复的数据；|
|df.drop_duplicates()|删除重复的数据。|

**数据选择和切片**
|函数|说明|
|-|-|
|df[column_name]|选择指定的列；|
|df.loc[row_index, column_name]|通过标签选择数据；|
|df.iloc[row_index, column_index]|通过位置选择数据；|
|df.ix[row_index, column_name]|通过标签或位置选择数据；|
|df.filter(items=[column_name1, column_name2])|选择指定的列；|
|df.filter(regex='regex')|选择列名匹配正则表达式的列；|
|df.sample(n)|随机选择 n 行数据。|

**数据排序**
|函数|说明|
|-|-|
|df.sort_values(column_name)	|按照指定列的值排序；|
|df.sort_values([column_name1, column_name2], ascending=[True, False])	|按照多个列的值排序；|
|df.sort_index()	|按照索引排序。|

**数据分组和聚合**
|函数|说明|
|-|-|
|df.groupby(column_name)|按照指定列进行分组；|
|df.aggregate(function_name)|对分组后的数据进行聚合操作；|
|df.pivot_table(values, index, columns, aggfunc)|生成透视表。|

**数据合并**
|函数|说明|
|-|-|
|pd.concat([df1, df2])|将多个数据框按照行或列进行合并；|
|pd.merge(df1, df2, on=column_name)|按照指定列将两个数据框进行合并。|

**数据选择和过滤**
|函数|说明|
|-|-|
|df.loc[row_indexer, column_indexer]|按标签选择行和列。|
|df.iloc[row_indexer, column_indexer]|按位置选择行和列。|
|df[df['column_name'] > value]|选择列中满足条件的行。|
|df.query('column_name > value')|使用字符串表达式选择列中满足条件的行。|

**数据统计和描述**
|函数|说明|
|-|-|
|df.describe()|计算基本统计信息，如均值、标准差、最小值、最大值等。|
|df.mean()|计算每列的平均值。|
|df.median()|计算每列的中位数。|
|df.mode()|计算每列的众数。|
|df.count()|计算每列非缺失值的数量。|
