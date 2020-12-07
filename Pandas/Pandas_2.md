```python
import pandas as pd
```

# Basic Operation, adding, deleting, updating , removing Colum and Rows in DF


```python
inter_org = pd.read_csv('datasets/international_org.csv')
print(inter_org)
# Add a column in the dataframe with default values
inter_org['Founded on'] = 1950
inter_org
```

      Organization Name  Headquater
    0               FAO        Rome
    1               ICJ   The Hague
    2               IMF  Washington
    3            UNESCO       Paris
    4               UNO    New York
    5        World Bank  Washington
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Organization Name</th>
      <th>Headquater</th>
      <th>Founded on</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>FAO</td>
      <td>Rome</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>1</th>
      <td>ICJ</td>
      <td>The Hague</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>2</th>
      <td>IMF</td>
      <td>Washington</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>3</th>
      <td>UNESCO</td>
      <td>Paris</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>4</th>
      <td>UNO</td>
      <td>New York</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>5</th>
      <td>World Bank</td>
      <td>Washington</td>
      <td>1950</td>
    </tr>
  </tbody>
</table>
</div>




```python
#updating a perticular colum
inter_org['Founded on'][1] = 1948
inter_org
```

    <ipython-input-5-4c606dab4785>:2: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      inter_org['Founded on'][1] = 1948
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Organization Name</th>
      <th>Headquater</th>
      <th>Founded on</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>FAO</td>
      <td>Rome</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>1</th>
      <td>ICJ</td>
      <td>The Hague</td>
      <td>1948</td>
    </tr>
    <tr>
      <th>2</th>
      <td>IMF</td>
      <td>Washington</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>3</th>
      <td>UNESCO</td>
      <td>Paris</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>4</th>
      <td>UNO</td>
      <td>New York</td>
      <td>1950</td>
    </tr>
    <tr>
      <th>5</th>
      <td>World Bank</td>
      <td>Washington</td>
      <td>1950</td>
    </tr>
  </tbody>
</table>
</div>




```python
movie_rate = pd.read_csv('datasets/imdb_rating.csv')
movie_rate
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
      <th>duration</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>142</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>175</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>200</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>152</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>154</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>96</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>161</td>
    </tr>
    <tr>
      <td>7</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>201</td>
    </tr>
    <tr>
      <td>8</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>195</td>
    </tr>
    <tr>
      <td>9</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>139</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Deletion of a column
del movie_rate['duration']
movie_rate
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
    </tr>
    <tr>
      <td>7</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
    </tr>
    <tr>
      <td>8</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
    </tr>
    <tr>
      <td>9</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Appending of a row
df2 = pd.DataFrame([[9.5, 'ASUR', 'Crime']], columns=list(['star_rating','title','genre']))
movie_rate = movie_rate.append(df2, ignore_index=True)
# movie_rate.reset_index(inplace=True)
```


```python
movie_rate
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
    </tr>
    <tr>
      <td>7</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
    </tr>
    <tr>
      <td>8</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
    </tr>
    <tr>
      <td>9</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
    </tr>
    <tr>
      <td>10</td>
      <td>9.5</td>
      <td>ASUR</td>
      <td>Crime</td>
    </tr>
  </tbody>
</table>
</div>




```python
# adding of a colum
movie_rate["Comment"] = "ITs OK "
movie_rate
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>7</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>8</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>9</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>10</td>
      <td>9.5</td>
      <td>ASUR</td>
      <td>Crime</td>
      <td>ITs OK</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Updating a coulm of specific row using "at" attribute
# df.at[row_indexs,colum_name] = value
# updating rows of those movies whose rating is above 9.0 set the value of the Comment to "Great Movie"
movie_rate.at[
    movie_rate[movie_rate["star_rating"] > 9.0].index, "Comment"
] = "Great Movie"
movie_rate
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>7</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>8</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>9</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>10</td>
      <td>9.5</td>
      <td>ASUR</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Deleting a row - drop() - returns a new dataframe
movie_rate_1 = movie_rate.drop(movie_rate.index[[0,4]])
movie_rate_1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>7</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>8</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>9</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>10</td>
      <td>9.5</td>
      <td>ASUR</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
  </tbody>
</table>
</div>




```python
# setting user defined index
id_x = ['mov_1', 'mov_2', 'mov_3', 'mov_4', 'mov_5', 'mov_6', 'mov_7', 'mov_8', 'mov_9']
movie_rate_1.index = id_x
movie_rate_1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>mov_1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>mov_2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>mov_3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>mov_4</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>mov_5</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>mov_6</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>mov_7</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>mov_8</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>mov_9</td>
      <td>9.5</td>
      <td>ASUR</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
  </tbody>
</table>
</div>




```python
movie_rate_1 = movie_rate_1.reset_index()
movie_rate_1
#each time we executes reset index existing index becomes a new colum 
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>mov_1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>1</td>
      <td>mov_2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>2</td>
      <td>mov_3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>3</td>
      <td>mov_4</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>4</td>
      <td>mov_5</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>5</td>
      <td>mov_6</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>6</td>
      <td>mov_7</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>7</td>
      <td>mov_8</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>8</td>
      <td>mov_9</td>
      <td>9.5</td>
      <td>ASUR</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
  </tbody>
</table>
</div>




```python
movie_rate_1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>mov_1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>1</td>
      <td>mov_2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>2</td>
      <td>mov_3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>3</td>
      <td>mov_4</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>4</td>
      <td>mov_5</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>5</td>
      <td>mov_6</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>6</td>
      <td>mov_7</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>7</td>
      <td>mov_8</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>8</td>
      <td>mov_9</td>
      <td>9.5</td>
      <td>ASUR</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
  </tbody>
</table>
</div>




```python
# you can use del as well for the Colum delete as you have seen in the above
movie_rate_1 = movie_rate_1.drop(columns = ['index'])
movie_rate_1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>3</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>7</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>8</td>
      <td>9.5</td>
      <td>ASUR</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
  </tbody>
</table>
</div>



# Selection and indexing


```python
citi_ride = pd.read_csv('datasets/citibike_tripdata.csv')
citi_ride.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>bikeid</th>
      <th>name_localizedValue</th>
      <th>usertype</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>338</td>
      <td>2018-05-01 00:04:47</td>
      <td>2018-05-01 00:10:25</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>33558</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1482</td>
      <td>2018-05-01 01:31:10</td>
      <td>2018-05-01 01:55:53</td>
      <td>3681</td>
      <td>Grand St</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>33593</td>
      <td>24 Hour</td>
      <td>Customer</td>
    </tr>
    <tr>
      <td>2</td>
      <td>232</td>
      <td>2018-05-01 01:31:29</td>
      <td>2018-05-01 01:35:22</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>29217</td>
      <td>FREE Bonus Month with Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>3</td>
      <td>190</td>
      <td>2018-05-01 02:03:29</td>
      <td>2018-05-01 02:06:40</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>29662</td>
      <td>24 Hour</td>
      <td>Customer</td>
    </tr>
    <tr>
      <td>4</td>
      <td>303</td>
      <td>2018-05-01 04:27:12</td>
      <td>2018-05-01 04:32:16</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>15271</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
  </tbody>
</table>
</div>




```python
citi_ride['start station id'].head(5)
```




    0    3639
    1    3681
    2    3194
    3    3185
    4    3207
    Name: start station id, dtype: int64




```python
citi_ride[['start station id', 'end station id']].head(5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>start station id</th>
      <th>end station id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>3639</td>
      <td>3199</td>
    </tr>
    <tr>
      <td>1</td>
      <td>3681</td>
      <td>3185</td>
    </tr>
    <tr>
      <td>2</td>
      <td>3194</td>
      <td>3193</td>
    </tr>
    <tr>
      <td>3</td>
      <td>3185</td>
      <td>3186</td>
    </tr>
    <tr>
      <td>4</td>
      <td>3207</td>
      <td>3195</td>
    </tr>
  </tbody>
</table>
</div>




```python
print(citi_ride.at[1, 'start station id'])
citi_ride.at[1, 'start station id'] = 32000
citi_ride[['start station id', 'end station id']].head(5)
```

    3681
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>start station id</th>
      <th>end station id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>3639</td>
      <td>3199</td>
    </tr>
    <tr>
      <td>1</td>
      <td>32000</td>
      <td>3185</td>
    </tr>
    <tr>
      <td>2</td>
      <td>3194</td>
      <td>3193</td>
    </tr>
    <tr>
      <td>3</td>
      <td>3185</td>
      <td>3186</td>
    </tr>
    <tr>
      <td>4</td>
      <td>3207</td>
      <td>3195</td>
    </tr>
  </tbody>
</table>
</div>




```python
new_citi_ride = citi_ride[:10]
new_citi_ride
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>bikeid</th>
      <th>name_localizedValue</th>
      <th>usertype</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>338</td>
      <td>2018-05-01 00:04:47</td>
      <td>2018-05-01 00:10:25</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>33558</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1482</td>
      <td>2018-05-01 01:31:10</td>
      <td>2018-05-01 01:55:53</td>
      <td>32000</td>
      <td>Grand St</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>33593</td>
      <td>24 Hour</td>
      <td>Customer</td>
    </tr>
    <tr>
      <td>2</td>
      <td>232</td>
      <td>2018-05-01 01:31:29</td>
      <td>2018-05-01 01:35:22</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>29217</td>
      <td>FREE Bonus Month with Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>3</td>
      <td>190</td>
      <td>2018-05-01 02:03:29</td>
      <td>2018-05-01 02:06:40</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>29662</td>
      <td>24 Hour</td>
      <td>Customer</td>
    </tr>
    <tr>
      <td>4</td>
      <td>303</td>
      <td>2018-05-01 04:27:12</td>
      <td>2018-05-01 04:32:16</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>15271</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>5</td>
      <td>176</td>
      <td>2018-05-01 04:37:05</td>
      <td>2018-05-01 04:40:01</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>29298</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>6</td>
      <td>577</td>
      <td>2018-05-01 05:05:46</td>
      <td>2018-05-01 05:15:23</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>33619</td>
      <td>Annual Membership from Citi Bike App</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>7</td>
      <td>830</td>
      <td>2018-05-01 05:11:50</td>
      <td>2018-05-01 05:25:41</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>33624</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>8</td>
      <td>395</td>
      <td>2018-05-01 05:12:07</td>
      <td>2018-05-01 05:18:42</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>26300</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>9</td>
      <td>170</td>
      <td>2018-05-01 05:13:52</td>
      <td>2018-05-01 05:16:43</td>
      <td>3206</td>
      <td>Hilltop</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>33555</td>
      <td>$25 Off Annual Membership</td>
      <td>Subscriber</td>
    </tr>
  </tbody>
</table>
</div>




```python
ride_id = ['ride_'+str(i) for i in range(1,11)]
new_citi_ride.index = ride_id
new_citi_ride.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>bikeid</th>
      <th>name_localizedValue</th>
      <th>usertype</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ride_1</td>
      <td>338</td>
      <td>2018-05-01 00:04:47</td>
      <td>2018-05-01 00:10:25</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>33558</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_2</td>
      <td>1482</td>
      <td>2018-05-01 01:31:10</td>
      <td>2018-05-01 01:55:53</td>
      <td>32000</td>
      <td>Grand St</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>33593</td>
      <td>24 Hour</td>
      <td>Customer</td>
    </tr>
    <tr>
      <td>ride_3</td>
      <td>232</td>
      <td>2018-05-01 01:31:29</td>
      <td>2018-05-01 01:35:22</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>29217</td>
      <td>FREE Bonus Month with Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_4</td>
      <td>190</td>
      <td>2018-05-01 02:03:29</td>
      <td>2018-05-01 02:06:40</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>29662</td>
      <td>24 Hour</td>
      <td>Customer</td>
    </tr>
    <tr>
      <td>ride_5</td>
      <td>303</td>
      <td>2018-05-01 04:27:12</td>
      <td>2018-05-01 04:32:16</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>15271</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
  </tbody>
</table>
</div>




```python
new_citi_ride.loc['ride_1':'ride_3','tripduration':'stoptime']
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ride_1</td>
      <td>338</td>
      <td>2018-05-01 00:04:47</td>
      <td>2018-05-01 00:10:25</td>
    </tr>
    <tr>
      <td>ride_2</td>
      <td>1482</td>
      <td>2018-05-01 01:31:10</td>
      <td>2018-05-01 01:55:53</td>
    </tr>
    <tr>
      <td>ride_3</td>
      <td>232</td>
      <td>2018-05-01 01:31:29</td>
      <td>2018-05-01 01:35:22</td>
    </tr>
  </tbody>
</table>
</div>




```python
# as you see here the difference of using .loc we cannot use row wise operation without using .loc
new_citi_ride['ride_1':'ride_3','tripduration':'stoptime']
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-92-04d5a2703975> in <module>
          1 # as you see here the difference of using .loc we cannot use row wise operation without using .loc
    ----> 2 new_citi_ride['ride_1':'ride_3','tripduration':'stoptime']
    

    c:\users\melwin\.conda\envs\tutorialdatascience\lib\site-packages\pandas\core\frame.py in __getitem__(self, key)
       2900             if self.columns.nlevels > 1:
       2901                 return self._getitem_multilevel(key)
    -> 2902             indexer = self.columns.get_loc(key)
       2903             if is_integer(indexer):
       2904                 indexer = [indexer]
    

    c:\users\melwin\.conda\envs\tutorialdatascience\lib\site-packages\pandas\core\indexes\base.py in get_loc(self, key, method, tolerance)
       2887             casted_key = self._maybe_cast_indexer(key)
       2888             try:
    -> 2889                 return self._engine.get_loc(casted_key)
       2890             except KeyError as err:
       2891                 raise KeyError(key) from err
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    TypeError: '(slice('ride_1', 'ride_3', None), slice('tripduration', 'stoptime', None))' is an invalid key



```python
new_citi_ride[new_citi_ride['tripduration']>200]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>bikeid</th>
      <th>name_localizedValue</th>
      <th>usertype</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ride_1</td>
      <td>338</td>
      <td>2018-05-01 00:04:47</td>
      <td>2018-05-01 00:10:25</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>33558</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_2</td>
      <td>1482</td>
      <td>2018-05-01 01:31:10</td>
      <td>2018-05-01 01:55:53</td>
      <td>32000</td>
      <td>Grand St</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>33593</td>
      <td>24 Hour</td>
      <td>Customer</td>
    </tr>
    <tr>
      <td>ride_3</td>
      <td>232</td>
      <td>2018-05-01 01:31:29</td>
      <td>2018-05-01 01:35:22</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>29217</td>
      <td>FREE Bonus Month with Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_5</td>
      <td>303</td>
      <td>2018-05-01 04:27:12</td>
      <td>2018-05-01 04:32:16</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>15271</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_7</td>
      <td>577</td>
      <td>2018-05-01 05:05:46</td>
      <td>2018-05-01 05:15:23</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>33619</td>
      <td>Annual Membership from Citi Bike App</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_8</td>
      <td>830</td>
      <td>2018-05-01 05:11:50</td>
      <td>2018-05-01 05:25:41</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>33624</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_9</td>
      <td>395</td>
      <td>2018-05-01 05:12:07</td>
      <td>2018-05-01 05:18:42</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>26300</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
  </tbody>
</table>
</div>




```python
new_citi_ride.loc[new_citi_ride['tripduration']>200, :'end station name':2]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>stoptime</th>
      <th>start station name</th>
      <th>end station name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ride_1</td>
      <td>338</td>
      <td>2018-05-01 00:10:25</td>
      <td>Harborside</td>
      <td>Newport Pkwy</td>
    </tr>
    <tr>
      <td>ride_2</td>
      <td>1482</td>
      <td>2018-05-01 01:55:53</td>
      <td>Grand St</td>
      <td>City Hall</td>
    </tr>
    <tr>
      <td>ride_3</td>
      <td>232</td>
      <td>2018-05-01 01:35:22</td>
      <td>McGinley Square</td>
      <td>Lincoln Park</td>
    </tr>
    <tr>
      <td>ride_5</td>
      <td>303</td>
      <td>2018-05-01 04:32:16</td>
      <td>Oakland Ave</td>
      <td>Sip Ave</td>
    </tr>
    <tr>
      <td>ride_7</td>
      <td>577</td>
      <td>2018-05-01 05:15:23</td>
      <td>Baldwin at Montgomery</td>
      <td>Grove St PATH</td>
    </tr>
    <tr>
      <td>ride_8</td>
      <td>830</td>
      <td>2018-05-01 05:25:41</td>
      <td>Oakland Ave</td>
      <td>City Hall</td>
    </tr>
    <tr>
      <td>ride_9</td>
      <td>395</td>
      <td>2018-05-01 05:18:42</td>
      <td>Baldwin at Montgomery</td>
      <td>Grove St PATH</td>
    </tr>
  </tbody>
</table>
</div>




```python
new_citi_ride.loc[new_citi_ride['tripduration']>200,'start station id']
```




    ride_1     3639
    ride_2    32000
    ride_3     3194
    ride_5     3207
    ride_7     3225
    ride_8     3207
    ride_9     3225
    Name: start station id, dtype: int64




```python
new_citi_ride.iloc[5]
```




    tripduration                           176
    starttime              2018-05-01 04:37:05
    stoptime               2018-05-01 04:40:01
    start station id                      3194
    start station name         McGinley Square
    end station id                        3195
    end station name                   Sip Ave
    bikeid                               29298
    name_localizedValue      Annual Membership
    usertype                        Subscriber
    Name: ride_6, dtype: object




```python
new_citi_ride.iloc[1:5]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>bikeid</th>
      <th>name_localizedValue</th>
      <th>usertype</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ride_2</th>
      <td>1482</td>
      <td>2018-05-01 01:31:10</td>
      <td>2018-05-01 01:55:53</td>
      <td>32000</td>
      <td>Grand St</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>33593</td>
      <td>24 Hour</td>
      <td>Customer</td>
    </tr>
    <tr>
      <th>ride_3</th>
      <td>232</td>
      <td>2018-05-01 01:31:29</td>
      <td>2018-05-01 01:35:22</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>3193</td>
      <td>Lincoln Park</td>
      <td>29217</td>
      <td>FREE Bonus Month with Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <th>ride_4</th>
      <td>190</td>
      <td>2018-05-01 02:03:29</td>
      <td>2018-05-01 02:06:40</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>29662</td>
      <td>24 Hour</td>
      <td>Customer</td>
    </tr>
    <tr>
      <th>ride_5</th>
      <td>303</td>
      <td>2018-05-01 04:27:12</td>
      <td>2018-05-01 04:32:16</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>15271</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
  </tbody>
</table>
</div>




```python
new_citi_ride.iloc[1:5, :6]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>end station id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ride_2</th>
      <td>1482</td>
      <td>2018-05-01 01:31:10</td>
      <td>2018-05-01 01:55:53</td>
      <td>32000</td>
      <td>Grand St</td>
      <td>3185</td>
    </tr>
    <tr>
      <th>ride_3</th>
      <td>232</td>
      <td>2018-05-01 01:31:29</td>
      <td>2018-05-01 01:35:22</td>
      <td>3194</td>
      <td>McGinley Square</td>
      <td>3193</td>
    </tr>
    <tr>
      <th>ride_4</th>
      <td>190</td>
      <td>2018-05-01 02:03:29</td>
      <td>2018-05-01 02:06:40</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>3186</td>
    </tr>
    <tr>
      <th>ride_5</th>
      <td>303</td>
      <td>2018-05-01 04:27:12</td>
      <td>2018-05-01 04:32:16</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3195</td>
    </tr>
  </tbody>
</table>
</div>




```python
new_citi_ride.iloc[1:5, ::2]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>stoptime</th>
      <th>start station name</th>
      <th>end station name</th>
      <th>name_localizedValue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ride_2</th>
      <td>1482</td>
      <td>2018-05-01 01:55:53</td>
      <td>Grand St</td>
      <td>City Hall</td>
      <td>24 Hour</td>
    </tr>
    <tr>
      <th>ride_3</th>
      <td>232</td>
      <td>2018-05-01 01:35:22</td>
      <td>McGinley Square</td>
      <td>Lincoln Park</td>
      <td>FREE Bonus Month with Annual Membership</td>
    </tr>
    <tr>
      <th>ride_4</th>
      <td>190</td>
      <td>2018-05-01 02:06:40</td>
      <td>City Hall</td>
      <td>Grove St PATH</td>
      <td>24 Hour</td>
    </tr>
    <tr>
      <th>ride_5</th>
      <td>303</td>
      <td>2018-05-01 04:32:16</td>
      <td>Oakland Ave</td>
      <td>Sip Ave</td>
      <td>Annual Membership</td>
    </tr>
  </tbody>
</table>
</div>




```python
new_citi_ride.iloc[[0, 4, 6, 9], ::]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>bikeid</th>
      <th>name_localizedValue</th>
      <th>usertype</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ride_1</td>
      <td>338</td>
      <td>2018-05-01 00:04:47</td>
      <td>2018-05-01 00:10:25</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>33558</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_5</td>
      <td>303</td>
      <td>2018-05-01 04:27:12</td>
      <td>2018-05-01 04:32:16</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>15271</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_7</td>
      <td>577</td>
      <td>2018-05-01 05:05:46</td>
      <td>2018-05-01 05:15:23</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>33619</td>
      <td>Annual Membership from Citi Bike App</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <td>ride_10</td>
      <td>170</td>
      <td>2018-05-01 05:13:52</td>
      <td>2018-05-01 05:16:43</td>
      <td>3206</td>
      <td>Hilltop</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>33555</td>
      <td>$25 Off Annual Membership</td>
      <td>Subscriber</td>
    </tr>
  </tbody>
</table>
</div>




```python
new_citi_ride[(new_citi_ride['usertype']== 'Subscriber') & (new_citi_ride['bikeid'] > 30000)]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>tripduration</th>
      <th>starttime</th>
      <th>stoptime</th>
      <th>start station id</th>
      <th>start station name</th>
      <th>end station id</th>
      <th>end station name</th>
      <th>bikeid</th>
      <th>name_localizedValue</th>
      <th>usertype</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ride_1</th>
      <td>338</td>
      <td>2018-05-01 00:04:47</td>
      <td>2018-05-01 00:10:25</td>
      <td>3639</td>
      <td>Harborside</td>
      <td>3199</td>
      <td>Newport Pkwy</td>
      <td>33558</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <th>ride_7</th>
      <td>577</td>
      <td>2018-05-01 05:05:46</td>
      <td>2018-05-01 05:15:23</td>
      <td>3225</td>
      <td>Baldwin at Montgomery</td>
      <td>3186</td>
      <td>Grove St PATH</td>
      <td>33619</td>
      <td>Annual Membership from Citi Bike App</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <th>ride_8</th>
      <td>830</td>
      <td>2018-05-01 05:11:50</td>
      <td>2018-05-01 05:25:41</td>
      <td>3207</td>
      <td>Oakland Ave</td>
      <td>3185</td>
      <td>City Hall</td>
      <td>33624</td>
      <td>Annual Membership</td>
      <td>Subscriber</td>
    </tr>
    <tr>
      <th>ride_10</th>
      <td>170</td>
      <td>2018-05-01 05:13:52</td>
      <td>2018-05-01 05:16:43</td>
      <td>3206</td>
      <td>Hilltop</td>
      <td>3195</td>
      <td>Sip Ave</td>
      <td>33555</td>
      <td>$25 Off Annual Membership</td>
      <td>Subscriber</td>
    </tr>
  </tbody>
</table>
</div>



## Iterators in Panda


```python
movie_rate
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>star_rating</th>
      <th>title</th>
      <th>genre</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9.1</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.9</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.9</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>7</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>8</td>
      <td>8.9</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>9</td>
      <td>8.9</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>ITs OK</td>
    </tr>
    <tr>
      <td>10</td>
      <td>9.5</td>
      <td>ASUR</td>
      <td>Crime</td>
      <td>Great Movie</td>
    </tr>
  </tbody>
</table>
</div>




```python
# for Iterate over the rows
for row in movie_rate.itertuples():
    print(row)
```

    Pandas(Index=0, star_rating=9.3, title='The Shawshank Redemption', genre='Crime', Comment='Great Movie')
    Pandas(Index=1, star_rating=9.2, title='The Godfather', genre='Crime', Comment='Great Movie')
    Pandas(Index=2, star_rating=9.1, title='The Godfather: Part II', genre='Crime', Comment='Great Movie')
    Pandas(Index=3, star_rating=9.0, title='The Dark Knight', genre='Action', Comment='ITs OK ')
    Pandas(Index=4, star_rating=8.9, title='Pulp Fiction', genre='Crime', Comment='ITs OK ')
    Pandas(Index=5, star_rating=8.9, title='12 Angry Men', genre='Drama', Comment='ITs OK ')
    Pandas(Index=6, star_rating=8.9, title='The Good, the Bad and the Ugly', genre='Western', Comment='ITs OK ')
    Pandas(Index=7, star_rating=8.9, title='The Lord of the Rings: The Return of the King', genre='Adventure', Comment='ITs OK ')
    Pandas(Index=8, star_rating=8.9, title="Schindler's List", genre='Biography', Comment='ITs OK ')
    Pandas(Index=9, star_rating=8.9, title='Fight Club', genre='Drama', Comment='ITs OK ')
    Pandas(Index=10, star_rating=9.5, title='ASUR', genre='Crime', Comment='Great Movie')
    


```python
for index, row in movie_rate.iterrows():
    print(index)
    print(row)
    print()
```

    0
    star_rating                         9.3
    title          The Shawshank Redemption
    genre                             Crime
    Comment                     Great Movie
    Name: 0, dtype: object
    
    1
    star_rating              9.2
    title          The Godfather
    genre                  Crime
    Comment          Great Movie
    Name: 1, dtype: object
    
    2
    star_rating                       9.1
    title          The Godfather: Part II
    genre                           Crime
    Comment                   Great Movie
    Name: 2, dtype: object
    
    3
    star_rating                  9
    title          The Dark Knight
    genre                   Action
    Comment                ITs OK 
    Name: 3, dtype: object
    
    4
    star_rating             8.9
    title          Pulp Fiction
    genre                 Crime
    Comment             ITs OK 
    Name: 4, dtype: object
    
    5
    star_rating             8.9
    title          12 Angry Men
    genre                 Drama
    Comment             ITs OK 
    Name: 5, dtype: object
    
    6
    star_rating                               8.9
    title          The Good, the Bad and the Ugly
    genre                                 Western
    Comment                               ITs OK 
    Name: 6, dtype: object
    
    7
    star_rating                                              8.9
    title          The Lord of the Rings: The Return of the King
    genre                                              Adventure
    Comment                                              ITs OK 
    Name: 7, dtype: object
    
    8
    star_rating                 8.9
    title          Schindler's List
    genre                 Biography
    Comment                 ITs OK 
    Name: 8, dtype: object
    
    9
    star_rating           8.9
    title          Fight Club
    genre               Drama
    Comment           ITs OK 
    Name: 9, dtype: object
    
    10
    star_rating            9.5
    title                 ASUR
    genre                Crime
    Comment        Great Movie
    Name: 10, dtype: object
    
    


```python
# Iterate Over the Colum 
for key,val in movie_rate.iteritems():
    print('key', key)
    print(val)
```

    key star_rating
    0     9.3
    1     9.2
    2     9.1
    3     9.0
    4     8.9
    5     8.9
    6     8.9
    7     8.9
    8     8.9
    9     8.9
    10    9.5
    Name: star_rating, dtype: float64
    key title
    0                          The Shawshank Redemption
    1                                     The Godfather
    2                            The Godfather: Part II
    3                                   The Dark Knight
    4                                      Pulp Fiction
    5                                      12 Angry Men
    6                    The Good, the Bad and the Ugly
    7     The Lord of the Rings: The Return of the King
    8                                  Schindler's List
    9                                        Fight Club
    10                                             ASUR
    Name: title, dtype: object
    key genre
    0         Crime
    1         Crime
    2         Crime
    3        Action
    4         Crime
    5         Drama
    6       Western
    7     Adventure
    8     Biography
    9         Drama
    10        Crime
    Name: genre, dtype: object
    key Comment
    0     Great Movie
    1     Great Movie
    2     Great Movie
    3         ITs OK 
    4         ITs OK 
    5         ITs OK 
    6         ITs OK 
    7         ITs OK 
    8         ITs OK 
    9         ITs OK 
    10    Great Movie
    Name: Comment, dtype: object
    


```python

```
