# fruit sorting

In this project, we wrote a fruit classification program that separates bad fruits from good ones

## Modules

```python
import pandas as pd
```

## Usage

Reading the data file

```python
fruits = pd.read_table('fruit.txt')
fruits.head()
```

Separating the names of fruits from the data file

```python
fruits.groupby('fruit_name').size()
fruits.shape
```

Because our input is not a variable

```python
X = fruits[['mass', 'width', 'height', 'color_score']]

y = fruits['fruit_label']
```

This code uses the train_test_split function in sklearn to split the input data (X and y) into two training and test sets. The data is divided into 80% for training and 20% for testing. Also, by using the random_state parameter, the data is divided randomly, and by assigning a fixed number to this parameter, it is possible to perform multiple tests with the same data divisions.

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=0, test_size=0.2)
```

This code uses MinMaxScaler to scale the features of the training and test data to the same scale, such that each feature is in the interval [0, 1]. First, by calling fit_transform, it applies this scaling to the training data, and then by calling transform, it applies it to the test data.

```python
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

from sklearn.linear_model import LogisticRegression
logreg = LogisticRegression()
logreg.fit(X_train, y_train)
logreg.predict(X_train)
logreg.score(X_train, y_train) 
logreg.score(X_test, y_test)
```

## Result

This project was written by Majid Tajanjari and the Aiolearn team, and we need your support!❤️ 

# دسته بندی میوه ها

در این پروژه ما یک برنامه طبقه بندی میوه نوشتیم که میوه های بد را از میوه های خوب جدا می کند

## ماژول

```python
import pandas as pd
```

## نحوه استفاده

خواندن فایل دیتا

```python
fruits = pd.read_table('fruit.txt')
fruits.head()
```

تفکیک نام میوه ها از فایل دیتا

```python
fruits.groupby('fruit_name').size()
fruits.shape
```

چون ورودی ما متغیر نیست

```python
X = fruits[['mass', 'width', 'height', 'color_score']]

y = fruits['fruit_label']
```

این کد از تابع train_test_split در sklearn برای تقسیم داده های ورودی (X و y) به دو مجموعه آموزشی و آزمایشی استفاده می کند. داده ها به 80 درصد برای آموزش و 20 درصد برای آزمایش تقسیم می شوند. همچنین با استفاده از پارامتر random_state داده ها به صورت تصادفی تقسیم می شوند و با اختصاص یک عدد ثابت به این پارامتر می توان تست های متعدد با تقسیم های داده مشابه انجام داد.

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=0, test_size=0.2)
```

این کد از MinMaxScaler برای مقیاس‌بندی ویژگی‌های داده‌های آموزشی و آزمایشی در مقیاس یکسان استفاده می‌کند، به طوری که هر ویژگی در بازه [0، 1] باشد. ابتدا با فراخوانی fit_transform این مقیاس بندی را روی داده های آموزشی اعمال می کند و سپس با فراخوانی transform آن را روی داده های تست اعمال می کند.

```python
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

from sklearn.linear_model import LogisticRegression
logreg = LogisticRegression()
logreg.fit(X_train, y_train)
logreg.predict(X_train)
logreg.score(X_train, y_train) 
logreg.score(X_test, y_test)
```

## نتیجه

این پروژه توسط مجید تجن جاری و تیم Aiolearn نوشته شده است و ما به حمایت شما نیازمندیم!❤️