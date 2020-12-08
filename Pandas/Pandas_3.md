```python
import pandas as pd
```

## Sorting a dataframe


```python
unsort_movie_rate = pd.read_csv('datasets/unsorted_imdb_rating.csv')
unsort_movie_rate.head()
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
      <td>9.1</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>175</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9.2</td>
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
  </tbody>
</table>
</div>




```python
unsort_movie_rate.index = [8,7,1,9,0,6,5,3,4,2]
unsort_movie_rate
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
      <td>8</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>142</td>
    </tr>
    <tr>
      <td>7</td>
      <td>9.1</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>175</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>200</td>
    </tr>
    <tr>
      <td>9</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>152</td>
    </tr>
    <tr>
      <td>0</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>154</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.8</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>96</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.7</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>161</td>
    </tr>
    <tr>
      <td>3</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>201</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.3</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>195</td>
    </tr>
    <tr>
      <td>2</td>
      <td>8.1</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>139</td>
    </tr>
  </tbody>
</table>
</div>




```python
unsort_movie_rate.sort_index()
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
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>154</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>200</td>
    </tr>
    <tr>
      <td>2</td>
      <td>8.1</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>139</td>
    </tr>
    <tr>
      <td>3</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>201</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.3</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>195</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.7</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>161</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.8</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>96</td>
    </tr>
    <tr>
      <td>7</td>
      <td>9.1</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>175</td>
    </tr>
    <tr>
      <td>8</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>142</td>
    </tr>
    <tr>
      <td>9</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>152</td>
    </tr>
  </tbody>
</table>
</div>




```python
unsort_movie_rate.sort_index(ascending = False)
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
      <td>9</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>152</td>
    </tr>
    <tr>
      <td>8</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>142</td>
    </tr>
    <tr>
      <td>7</td>
      <td>9.1</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>175</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.8</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>96</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.7</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>161</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.3</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>195</td>
    </tr>
    <tr>
      <td>3</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>201</td>
    </tr>
    <tr>
      <td>2</td>
      <td>8.1</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>139</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>200</td>
    </tr>
    <tr>
      <td>0</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>154</td>
    </tr>
  </tbody>
</table>
</div>




```python
unsort_movie_rate.sort_index(ascending = False)
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
      <td>9</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>152</td>
    </tr>
    <tr>
      <td>8</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>142</td>
    </tr>
    <tr>
      <td>7</td>
      <td>9.1</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>175</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.8</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>96</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.7</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>161</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.3</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>195</td>
    </tr>
    <tr>
      <td>3</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>201</td>
    </tr>
    <tr>
      <td>2</td>
      <td>8.1</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>139</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>200</td>
    </tr>
    <tr>
      <td>0</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>154</td>
    </tr>
  </tbody>
</table>
</div>




```python
unsort_movie_rate['genre'].sort_index()
```




    0        Crime
    1        Crime
    2        Drama
    3    Adventure
    4    Biography
    5      Western
    6        Drama
    7        Crime
    8        Crime
    9       Action
    Name: genre, dtype: object




```python
unsort_movie_rate.sort_values(by = 'title')
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
      <td>6</td>
      <td>8.8</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>96</td>
    </tr>
    <tr>
      <td>2</td>
      <td>8.1</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>139</td>
    </tr>
    <tr>
      <td>0</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>154</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.3</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>195</td>
    </tr>
    <tr>
      <td>9</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>152</td>
    </tr>
    <tr>
      <td>7</td>
      <td>9.1</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>175</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>200</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.7</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>161</td>
    </tr>
    <tr>
      <td>3</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>201</td>
    </tr>
    <tr>
      <td>8</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>142</td>
    </tr>
  </tbody>
</table>
</div>




```python
unsort_movie_rate # It will not be able to update in the actual one
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
      <td>8</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>142</td>
    </tr>
    <tr>
      <td>7</td>
      <td>9.1</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>175</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>200</td>
    </tr>
    <tr>
      <td>9</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>152</td>
    </tr>
    <tr>
      <td>0</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>154</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.8</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>96</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.7</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>161</td>
    </tr>
    <tr>
      <td>3</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>201</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.3</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>195</td>
    </tr>
    <tr>
      <td>2</td>
      <td>8.1</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>139</td>
    </tr>
  </tbody>
</table>
</div>




```python
unsort_movie_rate.sort_values(by = ['genre', 'star_rating'])
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
      <td>9</td>
      <td>9.0</td>
      <td>The Dark Knight</td>
      <td>Action</td>
      <td>152</td>
    </tr>
    <tr>
      <td>3</td>
      <td>8.9</td>
      <td>The Lord of the Rings: The Return of the King</td>
      <td>Adventure</td>
      <td>201</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8.3</td>
      <td>Schindler's List</td>
      <td>Biography</td>
      <td>195</td>
    </tr>
    <tr>
      <td>0</td>
      <td>8.9</td>
      <td>Pulp Fiction</td>
      <td>Crime</td>
      <td>154</td>
    </tr>
    <tr>
      <td>7</td>
      <td>9.1</td>
      <td>The Godfather</td>
      <td>Crime</td>
      <td>175</td>
    </tr>
    <tr>
      <td>1</td>
      <td>9.2</td>
      <td>The Godfather: Part II</td>
      <td>Crime</td>
      <td>200</td>
    </tr>
    <tr>
      <td>8</td>
      <td>9.3</td>
      <td>The Shawshank Redemption</td>
      <td>Crime</td>
      <td>142</td>
    </tr>
    <tr>
      <td>2</td>
      <td>8.1</td>
      <td>Fight Club</td>
      <td>Drama</td>
      <td>139</td>
    </tr>
    <tr>
      <td>6</td>
      <td>8.8</td>
      <td>12 Angry Men</td>
      <td>Drama</td>
      <td>96</td>
    </tr>
    <tr>
      <td>5</td>
      <td>8.7</td>
      <td>The Good, the Bad and the Ugly</td>
      <td>Western</td>
      <td>161</td>
    </tr>
  </tbody>
</table>
</div>




```python
s = unsort_movie_rate.style.set_properties(**{'text-align': 'center'})
s
```




<style  type="text/css" >
    #T_b9d11adc_382d_11eb_af65_b05adae69476row0_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row0_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row0_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row0_col3 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row1_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row1_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row1_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row1_col3 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row2_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row2_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row2_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row2_col3 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row3_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row3_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row3_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row3_col3 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row4_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row4_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row4_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row4_col3 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row5_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row5_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row5_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row5_col3 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row6_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row6_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row6_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row6_col3 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row7_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row7_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row7_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row7_col3 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row8_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row8_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row8_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row8_col3 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row9_col0 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row9_col1 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row9_col2 {
            text-align:  center;
        }    #T_b9d11adc_382d_11eb_af65_b05adae69476row9_col3 {
            text-align:  center;
        }</style><table id="T_b9d11adc_382d_11eb_af65_b05adae69476" ><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >star_rating</th>        <th class="col_heading level0 col1" >title</th>        <th class="col_heading level0 col2" >genre</th>        <th class="col_heading level0 col3" >duration</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row0" class="row_heading level0 row0" >8</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row0_col0" class="data row0 col0" >9.3</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row0_col1" class="data row0 col1" >The Shawshank Redemption</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row0_col2" class="data row0 col2" >Crime</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row0_col3" class="data row0 col3" >142</td>
            </tr>
            <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row1" class="row_heading level0 row1" >7</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row1_col0" class="data row1 col0" >9.1</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row1_col1" class="data row1 col1" >The Godfather</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row1_col2" class="data row1 col2" >Crime</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row1_col3" class="data row1 col3" >175</td>
            </tr>
            <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row2" class="row_heading level0 row2" >1</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row2_col0" class="data row2 col0" >9.2</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row2_col1" class="data row2 col1" >The Godfather: Part II</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row2_col2" class="data row2 col2" >Crime</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row2_col3" class="data row2 col3" >200</td>
            </tr>
            <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row3" class="row_heading level0 row3" >9</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row3_col0" class="data row3 col0" >9</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row3_col1" class="data row3 col1" >The Dark Knight</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row3_col2" class="data row3 col2" >Action</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row3_col3" class="data row3 col3" >152</td>
            </tr>
            <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row4" class="row_heading level0 row4" >0</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row4_col0" class="data row4 col0" >8.9</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row4_col1" class="data row4 col1" >Pulp Fiction</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row4_col2" class="data row4 col2" >Crime</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row4_col3" class="data row4 col3" >154</td>
            </tr>
            <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row5" class="row_heading level0 row5" >6</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row5_col0" class="data row5 col0" >8.8</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row5_col1" class="data row5 col1" >12 Angry Men</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row5_col2" class="data row5 col2" >Drama</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row5_col3" class="data row5 col3" >96</td>
            </tr>
            <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row6" class="row_heading level0 row6" >5</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row6_col0" class="data row6 col0" >8.7</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row6_col1" class="data row6 col1" >The Good, the Bad and the Ugly</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row6_col2" class="data row6 col2" >Western</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row6_col3" class="data row6 col3" >161</td>
            </tr>
            <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row7" class="row_heading level0 row7" >3</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row7_col0" class="data row7 col0" >8.9</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row7_col1" class="data row7 col1" >The Lord of the Rings: The Return of the King</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row7_col2" class="data row7 col2" >Adventure</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row7_col3" class="data row7 col3" >201</td>
            </tr>
            <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row8" class="row_heading level0 row8" >4</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row8_col0" class="data row8 col0" >8.3</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row8_col1" class="data row8 col1" >Schindler's List</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row8_col2" class="data row8 col2" >Biography</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row8_col3" class="data row8 col3" >195</td>
            </tr>
            <tr>
                        <th id="T_b9d11adc_382d_11eb_af65_b05adae69476level0_row9" class="row_heading level0 row9" >2</th>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row9_col0" class="data row9 col0" >8.1</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row9_col1" class="data row9 col1" >Fight Club</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row9_col2" class="data row9 col2" >Drama</td>
                        <td id="T_b9d11adc_382d_11eb_af65_b05adae69476row9_col3" class="data row9 col3" >139</td>
            </tr>
    </tbody></table>



## Reshape in the Colum


```python
avo_df = pd.read_csv('datasets/avocado.csv')
avo_df.head()
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
      <th>Region</th>
      <th>Type</th>
      <th>Small Bags</th>
      <th>Large Bags</th>
      <th>Total Bags</th>
      <th>Total Volume</th>
      <th>AveragePrice</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Atlanta</td>
      <td>organic</td>
      <td>89424.11</td>
      <td>207.08</td>
      <td>89631.19</td>
      <td>190257.38</td>
      <td>1.70</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Atlanta</td>
      <td>conventional</td>
      <td>102717.50</td>
      <td>153.00</td>
      <td>102870.50</td>
      <td>202790.74</td>
      <td>1.75</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Boston</td>
      <td>organic</td>
      <td>120465.39</td>
      <td>18.83</td>
      <td>120484.22</td>
      <td>236822.98</td>
      <td>1.58</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Boston</td>
      <td>conventional</td>
      <td>136877.43</td>
      <td>60.60</td>
      <td>136938.03</td>
      <td>239135.67</td>
      <td>1.57</td>
      <td>2018-03-04</td>
    </tr>
    <tr>
      <td>4</td>
      <td>California</td>
      <td>organic</td>
      <td>66273.89</td>
      <td>46.58</td>
      <td>66320.47</td>
      <td>179041.72</td>
      <td>1.82</td>
      <td>2018-02-25</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Remember in the pivote while setting there must not be duplicate entery in the combination of the index and colums
# Melwin Consides it as an Super key combining two or more colums there must not be duplicates like that
avo_df.pivot(index = 'Region', columns = 'Type')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="2" halign="left">Small Bags</th>
      <th colspan="2" halign="left">Large Bags</th>
      <th colspan="2" halign="left">Total Bags</th>
      <th colspan="2" halign="left">Total Volume</th>
      <th colspan="2" halign="left">AveragePrice</th>
      <th colspan="2" halign="left">Date</th>
    </tr>
    <tr>
      <th>Type</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
    </tr>
    <tr>
      <th>Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Atlanta</td>
      <td>102717.50</td>
      <td>89424.11</td>
      <td>153.00</td>
      <td>207.08</td>
      <td>102870.50</td>
      <td>89631.19</td>
      <td>202790.74</td>
      <td>190257.38</td>
      <td>1.75</td>
      <td>1.70</td>
      <td>2018-03-18</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>Boston</td>
      <td>136877.43</td>
      <td>120465.39</td>
      <td>60.60</td>
      <td>18.83</td>
      <td>136938.03</td>
      <td>120484.22</td>
      <td>239135.67</td>
      <td>236822.98</td>
      <td>1.57</td>
      <td>1.58</td>
      <td>2018-03-04</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>California</td>
      <td>103033.73</td>
      <td>66273.89</td>
      <td>186.20</td>
      <td>46.58</td>
      <td>106984.89</td>
      <td>66320.47</td>
      <td>1203274.11</td>
      <td>179041.72</td>
      <td>1.01</td>
      <td>1.82</td>
      <td>2018-03-25</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td>NewYork</td>
      <td>193813.92</td>
      <td>119694.95</td>
      <td>196.57</td>
      <td>92.29</td>
      <td>197281.89</td>
      <td>124214.59</td>
      <td>904333.98</td>
      <td>777300.99</td>
      <td>1.29</td>
      <td>1.38</td>
      <td>2018-03-11</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>SanFrancisco</td>
      <td>162913.33</td>
      <td>231913.11</td>
      <td>609.20</td>
      <td>1286.43</td>
      <td>166836.16</td>
      <td>236417.93</td>
      <td>984000.13</td>
      <td>1051308.50</td>
      <td>1.17</td>
      <td>1.16</td>
      <td>2018-02-25</td>
      <td>2018-03-04</td>
    </tr>
  </tbody>
</table>
</div>




```python
avo_df.pivot(index = 'Region', columns = 'Type', values = ['AveragePrice', 'Total Volume'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="2" halign="left">AveragePrice</th>
      <th colspan="2" halign="left">Total Volume</th>
    </tr>
    <tr>
      <th>Type</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
    </tr>
    <tr>
      <th>Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Atlanta</td>
      <td>1.75</td>
      <td>1.70</td>
      <td>202790.74</td>
      <td>190257.38</td>
    </tr>
    <tr>
      <td>Boston</td>
      <td>1.57</td>
      <td>1.58</td>
      <td>239135.67</td>
      <td>236822.98</td>
    </tr>
    <tr>
      <td>California</td>
      <td>1.01</td>
      <td>1.82</td>
      <td>1203274.11</td>
      <td>179041.72</td>
    </tr>
    <tr>
      <td>NewYork</td>
      <td>1.29</td>
      <td>1.38</td>
      <td>904333.98</td>
      <td>777300.99</td>
    </tr>
    <tr>
      <td>SanFrancisco</td>
      <td>1.17</td>
      <td>1.16</td>
      <td>984000.13</td>
      <td>1051308.50</td>
    </tr>
  </tbody>
</table>
</div>




```python
avo_multi = pd.read_csv('datasets/avocado.csv', index_col = ['Region', 'Type'])
avo_multi
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
      <th></th>
      <th>Small Bags</th>
      <th>Large Bags</th>
      <th>Total Bags</th>
      <th>Total Volume</th>
      <th>AveragePrice</th>
      <th>Date</th>
    </tr>
    <tr>
      <th>Region</th>
      <th>Type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2" valign="top">Atlanta</td>
      <td>organic</td>
      <td>89424.11</td>
      <td>207.08</td>
      <td>89631.19</td>
      <td>190257.38</td>
      <td>1.70</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>102717.50</td>
      <td>153.00</td>
      <td>102870.50</td>
      <td>202790.74</td>
      <td>1.75</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">Boston</td>
      <td>organic</td>
      <td>120465.39</td>
      <td>18.83</td>
      <td>120484.22</td>
      <td>236822.98</td>
      <td>1.58</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>136877.43</td>
      <td>60.60</td>
      <td>136938.03</td>
      <td>239135.67</td>
      <td>1.57</td>
      <td>2018-03-04</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">California</td>
      <td>organic</td>
      <td>66273.89</td>
      <td>46.58</td>
      <td>66320.47</td>
      <td>179041.72</td>
      <td>1.82</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>103033.73</td>
      <td>186.20</td>
      <td>106984.89</td>
      <td>1203274.11</td>
      <td>1.01</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">NewYork</td>
      <td>organic</td>
      <td>119694.95</td>
      <td>92.29</td>
      <td>124214.59</td>
      <td>777300.99</td>
      <td>1.38</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>193813.92</td>
      <td>196.57</td>
      <td>197281.89</td>
      <td>904333.98</td>
      <td>1.29</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">SanFrancisco</td>
      <td>organic</td>
      <td>231913.11</td>
      <td>1286.43</td>
      <td>236417.93</td>
      <td>1051308.50</td>
      <td>1.16</td>
      <td>2018-03-04</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>162913.33</td>
      <td>609.20</td>
      <td>166836.16</td>
      <td>984000.13</td>
      <td>1.17</td>
      <td>2018-02-25</td>
    </tr>
  </tbody>
</table>
</div>



## Melt
function is used to change the DataFrame format from wide to long. It's used to create a specific format of the DataFrame object where one or more columns work as identifiers. All the remaining columns are treated as values and unpivoted to the row axis and only two columns – variable and value.


```python
temp = pd.read_csv('datasets/us_temp.csv')
```


```python
temp
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
      <th>months_name</th>
      <th>Atlanta</th>
      <th>Buffalo</th>
      <th>New York City</th>
      <th>San Francisco</th>
      <th>Washington</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>January</td>
      <td>52</td>
      <td>31</td>
      <td>38</td>
      <td>57</td>
      <td>43</td>
    </tr>
    <tr>
      <td>1</td>
      <td>February</td>
      <td>57</td>
      <td>33</td>
      <td>42</td>
      <td>60</td>
      <td>47</td>
    </tr>
    <tr>
      <td>2</td>
      <td>March</td>
      <td>65</td>
      <td>42</td>
      <td>50</td>
      <td>62</td>
      <td>56</td>
    </tr>
    <tr>
      <td>3</td>
      <td>April</td>
      <td>73</td>
      <td>55</td>
      <td>61</td>
      <td>63</td>
      <td>67</td>
    </tr>
    <tr>
      <td>4</td>
      <td>May</td>
      <td>80</td>
      <td>67</td>
      <td>71</td>
      <td>64</td>
      <td>75</td>
    </tr>
    <tr>
      <td>5</td>
      <td>June</td>
      <td>86</td>
      <td>75</td>
      <td>79</td>
      <td>66</td>
      <td>84</td>
    </tr>
    <tr>
      <td>6</td>
      <td>July</td>
      <td>89</td>
      <td>80</td>
      <td>84</td>
      <td>67</td>
      <td>88</td>
    </tr>
    <tr>
      <td>7</td>
      <td>August</td>
      <td>88</td>
      <td>78</td>
      <td>83</td>
      <td>68</td>
      <td>87</td>
    </tr>
    <tr>
      <td>8</td>
      <td>September</td>
      <td>82</td>
      <td>71</td>
      <td>75</td>
      <td>70</td>
      <td>80</td>
    </tr>
    <tr>
      <td>9</td>
      <td>October</td>
      <td>73</td>
      <td>59</td>
      <td>64</td>
      <td>69</td>
      <td>68</td>
    </tr>
    <tr>
      <td>10</td>
      <td>November</td>
      <td>64</td>
      <td>48</td>
      <td>54</td>
      <td>63</td>
      <td>58</td>
    </tr>
    <tr>
      <td>11</td>
      <td>December</td>
      <td>54</td>
      <td>36</td>
      <td>43</td>
      <td>57</td>
      <td>47</td>
    </tr>
  </tbody>
</table>
</div>




```python
temp_melt = pd.melt(temp, id_vars=['months_name'])
temp_melt.head()
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
      <th>months_name</th>
      <th>variable</th>
      <th>value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>January</td>
      <td>Atlanta</td>
      <td>52</td>
    </tr>
    <tr>
      <td>1</td>
      <td>February</td>
      <td>Atlanta</td>
      <td>57</td>
    </tr>
    <tr>
      <td>2</td>
      <td>March</td>
      <td>Atlanta</td>
      <td>65</td>
    </tr>
    <tr>
      <td>3</td>
      <td>April</td>
      <td>Atlanta</td>
      <td>73</td>
    </tr>
    <tr>
      <td>4</td>
      <td>May</td>
      <td>Atlanta</td>
      <td>80</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Remanimg the Colum Nale
temp_melt = pd.melt(temp, id_vars=['months_name'], var_name = 'City', value_name = 'Temperature') 
temp_melt.head()
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
      <th>months_name</th>
      <th>City</th>
      <th>Temperature</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>January</td>
      <td>Atlanta</td>
      <td>52</td>
    </tr>
    <tr>
      <td>1</td>
      <td>February</td>
      <td>Atlanta</td>
      <td>57</td>
    </tr>
    <tr>
      <td>2</td>
      <td>March</td>
      <td>Atlanta</td>
      <td>65</td>
    </tr>
    <tr>
      <td>3</td>
      <td>April</td>
      <td>Atlanta</td>
      <td>73</td>
    </tr>
    <tr>
      <td>4</td>
      <td>May</td>
      <td>Atlanta</td>
      <td>80</td>
    </tr>
  </tbody>
</table>
</div>



## Stacking and Unstacking 
Closely related to the pivot() method are the related stack() and unstack() methods available on Series and DataFrame. These methods are designed to work together with MultiIndex objects (see the section on hierarchical indexing). Here are essentially what these methods do:<br>

stack: “pivot” a level of the (possibly hierarchical) column labels, returning a DataFrame with an index with a new inner-most level of row labels.<br>

unstack: (inverse operation of stack) “pivot” a level of the (possibly hierarchical) row index to the column axis, producing a reshaped DataFrame with a new inner-most level of column labels.<br>
Stacking Converts<br>
check this https://medium.com/swlh/reshaping-in-pandas-with-stack-and-unstack-functions-bb169f64467d


```python
# stack converts Inner Most Colums to Rows 
# unstack the Opposit
```


```python
avo_df = pd.read_csv('datasets/avocado.csv')
avo_df_piv = avo_df.pivot(index = 'Region', columns = 'Type')
avo_df_piv
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="2" halign="left">Small Bags</th>
      <th colspan="2" halign="left">Large Bags</th>
      <th colspan="2" halign="left">Total Bags</th>
      <th colspan="2" halign="left">Total Volume</th>
      <th colspan="2" halign="left">AveragePrice</th>
      <th colspan="2" halign="left">Date</th>
    </tr>
    <tr>
      <th>Type</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
    </tr>
    <tr>
      <th>Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Atlanta</td>
      <td>102717.50</td>
      <td>89424.11</td>
      <td>153.00</td>
      <td>207.08</td>
      <td>102870.50</td>
      <td>89631.19</td>
      <td>202790.74</td>
      <td>190257.38</td>
      <td>1.75</td>
      <td>1.70</td>
      <td>2018-03-18</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>Boston</td>
      <td>136877.43</td>
      <td>120465.39</td>
      <td>60.60</td>
      <td>18.83</td>
      <td>136938.03</td>
      <td>120484.22</td>
      <td>239135.67</td>
      <td>236822.98</td>
      <td>1.57</td>
      <td>1.58</td>
      <td>2018-03-04</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>California</td>
      <td>103033.73</td>
      <td>66273.89</td>
      <td>186.20</td>
      <td>46.58</td>
      <td>106984.89</td>
      <td>66320.47</td>
      <td>1203274.11</td>
      <td>179041.72</td>
      <td>1.01</td>
      <td>1.82</td>
      <td>2018-03-25</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td>NewYork</td>
      <td>193813.92</td>
      <td>119694.95</td>
      <td>196.57</td>
      <td>92.29</td>
      <td>197281.89</td>
      <td>124214.59</td>
      <td>904333.98</td>
      <td>777300.99</td>
      <td>1.29</td>
      <td>1.38</td>
      <td>2018-03-11</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>SanFrancisco</td>
      <td>162913.33</td>
      <td>231913.11</td>
      <td>609.20</td>
      <td>1286.43</td>
      <td>166836.16</td>
      <td>236417.93</td>
      <td>984000.13</td>
      <td>1051308.50</td>
      <td>1.17</td>
      <td>1.16</td>
      <td>2018-02-25</td>
      <td>2018-03-04</td>
    </tr>
  </tbody>
</table>
</div>




```python
avo_df_piv.stack()
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
      <th></th>
      <th>Small Bags</th>
      <th>Large Bags</th>
      <th>Total Bags</th>
      <th>Total Volume</th>
      <th>AveragePrice</th>
      <th>Date</th>
    </tr>
    <tr>
      <th>Region</th>
      <th>Type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2" valign="top">Atlanta</td>
      <td>conventional</td>
      <td>102717.50</td>
      <td>153.00</td>
      <td>102870.50</td>
      <td>202790.74</td>
      <td>1.75</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>organic</td>
      <td>89424.11</td>
      <td>207.08</td>
      <td>89631.19</td>
      <td>190257.38</td>
      <td>1.70</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">Boston</td>
      <td>conventional</td>
      <td>136877.43</td>
      <td>60.60</td>
      <td>136938.03</td>
      <td>239135.67</td>
      <td>1.57</td>
      <td>2018-03-04</td>
    </tr>
    <tr>
      <td>organic</td>
      <td>120465.39</td>
      <td>18.83</td>
      <td>120484.22</td>
      <td>236822.98</td>
      <td>1.58</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">California</td>
      <td>conventional</td>
      <td>103033.73</td>
      <td>186.20</td>
      <td>106984.89</td>
      <td>1203274.11</td>
      <td>1.01</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>organic</td>
      <td>66273.89</td>
      <td>46.58</td>
      <td>66320.47</td>
      <td>179041.72</td>
      <td>1.82</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">NewYork</td>
      <td>conventional</td>
      <td>193813.92</td>
      <td>196.57</td>
      <td>197281.89</td>
      <td>904333.98</td>
      <td>1.29</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>organic</td>
      <td>119694.95</td>
      <td>92.29</td>
      <td>124214.59</td>
      <td>777300.99</td>
      <td>1.38</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">SanFrancisco</td>
      <td>conventional</td>
      <td>162913.33</td>
      <td>609.20</td>
      <td>166836.16</td>
      <td>984000.13</td>
      <td>1.17</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td>organic</td>
      <td>231913.11</td>
      <td>1286.43</td>
      <td>236417.93</td>
      <td>1051308.50</td>
      <td>1.16</td>
      <td>2018-03-04</td>
    </tr>
  </tbody>
</table>
</div>




```python
avo_df_piv.stack().unstack()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="2" halign="left">Small Bags</th>
      <th colspan="2" halign="left">Large Bags</th>
      <th colspan="2" halign="left">Total Bags</th>
      <th colspan="2" halign="left">Total Volume</th>
      <th colspan="2" halign="left">AveragePrice</th>
      <th colspan="2" halign="left">Date</th>
    </tr>
    <tr>
      <th>Type</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
    </tr>
    <tr>
      <th>Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Atlanta</td>
      <td>102717.50</td>
      <td>89424.11</td>
      <td>153.00</td>
      <td>207.08</td>
      <td>102870.50</td>
      <td>89631.19</td>
      <td>202790.74</td>
      <td>190257.38</td>
      <td>1.75</td>
      <td>1.70</td>
      <td>2018-03-18</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>Boston</td>
      <td>136877.43</td>
      <td>120465.39</td>
      <td>60.60</td>
      <td>18.83</td>
      <td>136938.03</td>
      <td>120484.22</td>
      <td>239135.67</td>
      <td>236822.98</td>
      <td>1.57</td>
      <td>1.58</td>
      <td>2018-03-04</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>California</td>
      <td>103033.73</td>
      <td>66273.89</td>
      <td>186.20</td>
      <td>46.58</td>
      <td>106984.89</td>
      <td>66320.47</td>
      <td>1203274.11</td>
      <td>179041.72</td>
      <td>1.01</td>
      <td>1.82</td>
      <td>2018-03-25</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td>NewYork</td>
      <td>193813.92</td>
      <td>119694.95</td>
      <td>196.57</td>
      <td>92.29</td>
      <td>197281.89</td>
      <td>124214.59</td>
      <td>904333.98</td>
      <td>777300.99</td>
      <td>1.29</td>
      <td>1.38</td>
      <td>2018-03-11</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>SanFrancisco</td>
      <td>162913.33</td>
      <td>231913.11</td>
      <td>609.20</td>
      <td>1286.43</td>
      <td>166836.16</td>
      <td>236417.93</td>
      <td>984000.13</td>
      <td>1051308.50</td>
      <td>1.17</td>
      <td>1.16</td>
      <td>2018-02-25</td>
      <td>2018-03-04</td>
    </tr>
  </tbody>
</table>
</div>




```python
# what happens when there is Colum level multi Index
avo_multi = pd.read_csv('datasets/avocado.csv', index_col = ['Region', 'Type'])
avo_multi
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
      <th></th>
      <th>Small Bags</th>
      <th>Large Bags</th>
      <th>Total Bags</th>
      <th>Total Volume</th>
      <th>AveragePrice</th>
      <th>Date</th>
    </tr>
    <tr>
      <th>Region</th>
      <th>Type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2" valign="top">Atlanta</td>
      <td>organic</td>
      <td>89424.11</td>
      <td>207.08</td>
      <td>89631.19</td>
      <td>190257.38</td>
      <td>1.70</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>102717.50</td>
      <td>153.00</td>
      <td>102870.50</td>
      <td>202790.74</td>
      <td>1.75</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">Boston</td>
      <td>organic</td>
      <td>120465.39</td>
      <td>18.83</td>
      <td>120484.22</td>
      <td>236822.98</td>
      <td>1.58</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>136877.43</td>
      <td>60.60</td>
      <td>136938.03</td>
      <td>239135.67</td>
      <td>1.57</td>
      <td>2018-03-04</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">California</td>
      <td>organic</td>
      <td>66273.89</td>
      <td>46.58</td>
      <td>66320.47</td>
      <td>179041.72</td>
      <td>1.82</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>103033.73</td>
      <td>186.20</td>
      <td>106984.89</td>
      <td>1203274.11</td>
      <td>1.01</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">NewYork</td>
      <td>organic</td>
      <td>119694.95</td>
      <td>92.29</td>
      <td>124214.59</td>
      <td>777300.99</td>
      <td>1.38</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>193813.92</td>
      <td>196.57</td>
      <td>197281.89</td>
      <td>904333.98</td>
      <td>1.29</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td rowspan="2" valign="top">SanFrancisco</td>
      <td>organic</td>
      <td>231913.11</td>
      <td>1286.43</td>
      <td>236417.93</td>
      <td>1051308.50</td>
      <td>1.16</td>
      <td>2018-03-04</td>
    </tr>
    <tr>
      <td>conventional</td>
      <td>162913.33</td>
      <td>609.20</td>
      <td>166836.16</td>
      <td>984000.13</td>
      <td>1.17</td>
      <td>2018-02-25</td>
    </tr>
  </tbody>
</table>
</div>




```python
avo_multi.stack()
```




    Region        Type                      
    Atlanta       organic       Small Bags          89424.1
                                Large Bags           207.08
                                Total Bags          89631.2
                                Total Volume         190257
                                AveragePrice            1.7
                                Date             2018-03-25
                  conventional  Small Bags           102718
                                Large Bags              153
                                Total Bags           102870
                                Total Volume         202791
                                AveragePrice           1.75
                                Date             2018-03-18
    Boston        organic       Small Bags           120465
                                Large Bags            18.83
                                Total Bags           120484
                                Total Volume         236823
                                AveragePrice           1.58
                                Date             2018-03-11
                  conventional  Small Bags           136877
                                Large Bags             60.6
                                Total Bags           136938
                                Total Volume         239136
                                AveragePrice           1.57
                                Date             2018-03-04
    California    organic       Small Bags          66273.9
                                Large Bags            46.58
                                Total Bags          66320.5
                                Total Volume         179042
                                AveragePrice           1.82
                                Date             2018-02-25
                  conventional  Small Bags           103034
                                Large Bags            186.2
                                Total Bags           106985
                                Total Volume    1.20327e+06
                                AveragePrice           1.01
                                Date             2018-03-25
    NewYork       organic       Small Bags           119695
                                Large Bags            92.29
                                Total Bags           124215
                                Total Volume         777301
                                AveragePrice           1.38
                                Date             2018-03-18
                  conventional  Small Bags           193814
                                Large Bags           196.57
                                Total Bags           197282
                                Total Volume         904334
                                AveragePrice           1.29
                                Date             2018-03-11
    SanFrancisco  organic       Small Bags           231913
                                Large Bags          1286.43
                                Total Bags           236418
                                Total Volume    1.05131e+06
                                AveragePrice           1.16
                                Date             2018-03-04
                  conventional  Small Bags           162913
                                Large Bags            609.2
                                Total Bags           166836
                                Total Volume         984000
                                AveragePrice           1.17
                                Date             2018-02-25
    dtype: object




```python
print(avo_multi.head())
avo_multi.unstack()
```

                             Small Bags  Large Bags  Total Bags  Total Volume  \
    Region     Type                                                             
    Atlanta    organic         89424.11      207.08    89631.19     190257.38   
               conventional   102717.50      153.00   102870.50     202790.74   
    Boston     organic        120465.39       18.83   120484.22     236822.98   
               conventional   136877.43       60.60   136938.03     239135.67   
    California organic         66273.89       46.58    66320.47     179041.72   
    
                             AveragePrice        Date  
    Region     Type                                    
    Atlanta    organic               1.70  2018-03-25  
               conventional          1.75  2018-03-18  
    Boston     organic               1.58  2018-03-11  
               conventional          1.57  2018-03-04  
    California organic               1.82  2018-02-25  
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="2" halign="left">Small Bags</th>
      <th colspan="2" halign="left">Large Bags</th>
      <th colspan="2" halign="left">Total Bags</th>
      <th colspan="2" halign="left">Total Volume</th>
      <th colspan="2" halign="left">AveragePrice</th>
      <th colspan="2" halign="left">Date</th>
    </tr>
    <tr>
      <th>Type</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
      <th>conventional</th>
      <th>organic</th>
    </tr>
    <tr>
      <th>Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Atlanta</td>
      <td>102717.50</td>
      <td>89424.11</td>
      <td>153.00</td>
      <td>207.08</td>
      <td>102870.50</td>
      <td>89631.19</td>
      <td>202790.74</td>
      <td>190257.38</td>
      <td>1.75</td>
      <td>1.70</td>
      <td>2018-03-18</td>
      <td>2018-03-25</td>
    </tr>
    <tr>
      <td>Boston</td>
      <td>136877.43</td>
      <td>120465.39</td>
      <td>60.60</td>
      <td>18.83</td>
      <td>136938.03</td>
      <td>120484.22</td>
      <td>239135.67</td>
      <td>236822.98</td>
      <td>1.57</td>
      <td>1.58</td>
      <td>2018-03-04</td>
      <td>2018-03-11</td>
    </tr>
    <tr>
      <td>California</td>
      <td>103033.73</td>
      <td>66273.89</td>
      <td>186.20</td>
      <td>46.58</td>
      <td>106984.89</td>
      <td>66320.47</td>
      <td>1203274.11</td>
      <td>179041.72</td>
      <td>1.01</td>
      <td>1.82</td>
      <td>2018-03-25</td>
      <td>2018-02-25</td>
    </tr>
    <tr>
      <td>NewYork</td>
      <td>193813.92</td>
      <td>119694.95</td>
      <td>196.57</td>
      <td>92.29</td>
      <td>197281.89</td>
      <td>124214.59</td>
      <td>904333.98</td>
      <td>777300.99</td>
      <td>1.29</td>
      <td>1.38</td>
      <td>2018-03-11</td>
      <td>2018-03-18</td>
    </tr>
    <tr>
      <td>SanFrancisco</td>
      <td>162913.33</td>
      <td>231913.11</td>
      <td>609.20</td>
      <td>1286.43</td>
      <td>166836.16</td>
      <td>236417.93</td>
      <td>984000.13</td>
      <td>1051308.50</td>
      <td>1.17</td>
      <td>1.16</td>
      <td>2018-02-25</td>
      <td>2018-03-04</td>
    </tr>
  </tbody>
</table>
</div>



## Group By


```python
vehicle_data = pd.read_csv('datasets/cars_data.csv')
vehicle_data
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
      <th>car_name</th>
      <th>mpg</th>
      <th>cylinders</th>
      <th>displacement</th>
      <th>horsepower</th>
      <th>weight</th>
      <th>acceleration</th>
      <th>model</th>
      <th>origin_city</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Chevrolet Chevelle Malibu</td>
      <td>18</td>
      <td>8</td>
      <td>307</td>
      <td>130</td>
      <td>3504</td>
      <td>12.0</td>
      <td>70</td>
      <td>US</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Buick Skylark 320</td>
      <td>15</td>
      <td>8</td>
      <td>350</td>
      <td>165</td>
      <td>3693</td>
      <td>11.5</td>
      <td>70</td>
      <td>US</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Plymouth Satellite</td>
      <td>18</td>
      <td>8</td>
      <td>318</td>
      <td>150</td>
      <td>3436</td>
      <td>11.0</td>
      <td>70</td>
      <td>US</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Citroen DS-21 Pallas</td>
      <td>0</td>
      <td>4</td>
      <td>133</td>
      <td>115</td>
      <td>3090</td>
      <td>17.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Toyota Corolla Mark ii</td>
      <td>24</td>
      <td>4</td>
      <td>113</td>
      <td>95</td>
      <td>2372</td>
      <td>15.0</td>
      <td>70</td>
      <td>Japan</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Datsun PL510</td>
      <td>27</td>
      <td>4</td>
      <td>97</td>
      <td>88</td>
      <td>2130</td>
      <td>14.5</td>
      <td>70</td>
      <td>Japan</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Volkswagen 1131 Deluxe Sedan</td>
      <td>26</td>
      <td>4</td>
      <td>97</td>
      <td>46</td>
      <td>1835</td>
      <td>20.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Peugeot 504</td>
      <td>25</td>
      <td>4</td>
      <td>110</td>
      <td>87</td>
      <td>2672</td>
      <td>17.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Audi 100 LS</td>
      <td>24</td>
      <td>4</td>
      <td>107</td>
      <td>90</td>
      <td>2430</td>
      <td>14.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Saab 99e</td>
      <td>25</td>
      <td>4</td>
      <td>104</td>
      <td>95</td>
      <td>2375</td>
      <td>17.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>10</td>
      <td>BMW 2002</td>
      <td>26</td>
      <td>4</td>
      <td>121</td>
      <td>113</td>
      <td>2234</td>
      <td>12.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Datsun PL510</td>
      <td>27</td>
      <td>4</td>
      <td>97</td>
      <td>88</td>
      <td>2130</td>
      <td>14.5</td>
      <td>71</td>
      <td>Japan</td>
    </tr>
    <tr>
      <td>12</td>
      <td>Chevrolet Vega 2300</td>
      <td>28</td>
      <td>4</td>
      <td>140</td>
      <td>90</td>
      <td>2264</td>
      <td>15.5</td>
      <td>71</td>
      <td>US</td>
    </tr>
  </tbody>
</table>
</div>




```python
or_city = vehicle_data.groupby('origin_city')
# output will be a DataFrameGroupBy object
# to get the output you have to loop throught it
```


```python
list(or_city)
```




    [('Europe',
                              car_name  mpg  cylinders  displacement  horsepower  \
      3           Citroen DS-21 Pallas    0          4           133         115   
      6   Volkswagen 1131 Deluxe Sedan   26          4            97          46   
      7                    Peugeot 504   25          4           110          87   
      8                    Audi 100 LS   24          4           107          90   
      9                       Saab 99e   25          4           104          95   
      10                      BMW 2002   26          4           121         113   
      
          weight  acceleration  model origin_city  
      3     3090          17.5     70      Europe  
      6     1835          20.5     70      Europe  
      7     2672          17.5     70      Europe  
      8     2430          14.5     70      Europe  
      9     2375          17.5     70      Europe  
      10    2234          12.5     70      Europe  ),
     ('Japan',
                        car_name  mpg  cylinders  displacement  horsepower  weight  \
      4   Toyota Corolla Mark ii   24          4           113          95    2372   
      5             Datsun PL510   27          4            97          88    2130   
      11            Datsun PL510   27          4            97          88    2130   
      
          acceleration  model origin_city  
      4           15.0     70       Japan  
      5           14.5     70       Japan  
      11          14.5     71       Japan  ),
     ('US',
                           car_name  mpg  cylinders  displacement  horsepower  \
      0   Chevrolet Chevelle Malibu   18          8           307         130   
      1           Buick Skylark 320   15          8           350         165   
      2          Plymouth Satellite   18          8           318         150   
      12        Chevrolet Vega 2300   28          4           140          90   
      
          weight  acceleration  model origin_city  
      0     3504          12.0     70          US  
      1     3693          11.5     70          US  
      2     3436          11.0     70          US  
      12    2264          15.5     71          US  )]




```python
vehicle_data.groupby('origin_city').get_group("Europe")
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
      <th>car_name</th>
      <th>mpg</th>
      <th>cylinders</th>
      <th>displacement</th>
      <th>horsepower</th>
      <th>weight</th>
      <th>acceleration</th>
      <th>model</th>
      <th>origin_city</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>3</td>
      <td>Citroen DS-21 Pallas</td>
      <td>0</td>
      <td>4</td>
      <td>133</td>
      <td>115</td>
      <td>3090</td>
      <td>17.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Volkswagen 1131 Deluxe Sedan</td>
      <td>26</td>
      <td>4</td>
      <td>97</td>
      <td>46</td>
      <td>1835</td>
      <td>20.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Peugeot 504</td>
      <td>25</td>
      <td>4</td>
      <td>110</td>
      <td>87</td>
      <td>2672</td>
      <td>17.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Audi 100 LS</td>
      <td>24</td>
      <td>4</td>
      <td>107</td>
      <td>90</td>
      <td>2430</td>
      <td>14.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Saab 99e</td>
      <td>25</td>
      <td>4</td>
      <td>104</td>
      <td>95</td>
      <td>2375</td>
      <td>17.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
    <tr>
      <td>10</td>
      <td>BMW 2002</td>
      <td>26</td>
      <td>4</td>
      <td>121</td>
      <td>113</td>
      <td>2234</td>
      <td>12.5</td>
      <td>70</td>
      <td>Europe</td>
    </tr>
  </tbody>
</table>
</div>




```python
vehicle_data.groupby('origin_city').get_group("Japan")
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
      <th>car_name</th>
      <th>mpg</th>
      <th>cylinders</th>
      <th>displacement</th>
      <th>horsepower</th>
      <th>weight</th>
      <th>acceleration</th>
      <th>model</th>
      <th>origin_city</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>4</td>
      <td>Toyota Corolla Mark ii</td>
      <td>24</td>
      <td>4</td>
      <td>113</td>
      <td>95</td>
      <td>2372</td>
      <td>15.0</td>
      <td>70</td>
      <td>Japan</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Datsun PL510</td>
      <td>27</td>
      <td>4</td>
      <td>97</td>
      <td>88</td>
      <td>2130</td>
      <td>14.5</td>
      <td>70</td>
      <td>Japan</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Datsun PL510</td>
      <td>27</td>
      <td>4</td>
      <td>97</td>
      <td>88</td>
      <td>2130</td>
      <td>14.5</td>
      <td>71</td>
      <td>Japan</td>
    </tr>
  </tbody>
</table>
</div>




```python
vehicle_data.groupby('origin_city').get_group("US")
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
      <th>car_name</th>
      <th>mpg</th>
      <th>cylinders</th>
      <th>displacement</th>
      <th>horsepower</th>
      <th>weight</th>
      <th>acceleration</th>
      <th>model</th>
      <th>origin_city</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Chevrolet Chevelle Malibu</td>
      <td>18</td>
      <td>8</td>
      <td>307</td>
      <td>130</td>
      <td>3504</td>
      <td>12.0</td>
      <td>70</td>
      <td>US</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Buick Skylark 320</td>
      <td>15</td>
      <td>8</td>
      <td>350</td>
      <td>165</td>
      <td>3693</td>
      <td>11.5</td>
      <td>70</td>
      <td>US</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Plymouth Satellite</td>
      <td>18</td>
      <td>8</td>
      <td>318</td>
      <td>150</td>
      <td>3436</td>
      <td>11.0</td>
      <td>70</td>
      <td>US</td>
    </tr>
    <tr>
      <td>12</td>
      <td>Chevrolet Vega 2300</td>
      <td>28</td>
      <td>4</td>
      <td>140</td>
      <td>90</td>
      <td>2264</td>
      <td>15.5</td>
      <td>71</td>
      <td>US</td>
    </tr>
  </tbody>
</table>
</div>



### idxmax


```python
# to get the id of the maximum value we can use idxmax()
print(vehicle_data.groupby('origin_city')["horsepower"].idxmax())
print(type(vehicle_data.groupby('origin_city')["horsepower"].idxmax()))
vehicle_data.groupby('origin_city')["horsepower"].max()
```

    origin_city
    Europe    3
    Japan     4
    US        1
    Name: horsepower, dtype: int64
    <class 'pandas.core.series.Series'>
    




    origin_city
    Europe    115
    Japan      95
    US        165
    Name: horsepower, dtype: int64




```python
for x,y in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).items():
    print(vehicle_data[(vehicle_data["origin_city"] == x) & (vehicle_data["horsepower"] == y)].index)    
# dict(vehicle_data.groupby('origin_city')["horsepower"].max())       
```

    Int64Index([3], dtype='int64')
    Int64Index([4], dtype='int64')
    Int64Index([1], dtype='int64')
    


```python
# Melwin check the doubt section
# for x,y in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).items():
#     print(vehicle_data[(vehicle_data["origin_city"] == x) & (vehicle_data["horsepower"] == y)]) 
# "Europe" in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).keys()
vehicle_data[(vehicle_data["origin_city"] in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).keys()) &
              (vehicle_data["origin_city"] in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).values())  ]    
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-81-0cb524fc2a9a> in <module>
          3 #     print(vehicle_data[(vehicle_data["origin_city"] == x) & (vehicle_data["horsepower"] == y)])
          4 # "Europe" in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).keys()
    ----> 5 vehicle_data[(vehicle_data["origin_city"] in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).keys()) &
          6               (vehicle_data["origin_city"] in dict(vehicle_data.groupby('origin_city')["horsepower"].max()).values())  ]    
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\generic.py in __hash__(self)
       1884         raise TypeError(
       1885             "{0!r} objects are mutable, thus they cannot be"
    -> 1886             " hashed".format(self.__class__.__name__)
       1887         )
       1888 
    

    TypeError: 'Series' objects are mutable, thus they cannot be hashed


## Concate and Merge


```python
students = pd.DataFrame({'id_number' : [204, 202, 264, 136, 238],
                               'Name' : ['James Smith',
                                        'Maria Rodriguez',
                                        'David Smith', 
                                        'Patricia Garcia',
                                        'Jessica Hernandez'],
                               'Age' : [26, 22 ,24, 21, 25],
                            'Gender' : ['M', 'F', 'M', 'F', 'F'],
                    
                        })
students
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
      <th>id_number</th>
      <th>Name</th>
      <th>Age</th>
      <th>Gender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>204</td>
      <td>James Smith</td>
      <td>26</td>
      <td>M</td>
    </tr>
    <tr>
      <td>1</td>
      <td>202</td>
      <td>Maria Rodriguez</td>
      <td>22</td>
      <td>F</td>
    </tr>
    <tr>
      <td>2</td>
      <td>264</td>
      <td>David Smith</td>
      <td>24</td>
      <td>M</td>
    </tr>
    <tr>
      <td>3</td>
      <td>136</td>
      <td>Patricia Garcia</td>
      <td>21</td>
      <td>F</td>
    </tr>
    <tr>
      <td>4</td>
      <td>238</td>
      <td>Jessica Hernandez</td>
      <td>25</td>
      <td>F</td>
    </tr>
  </tbody>
</table>
</div>




```python
professors = pd.DataFrame({'Prof_name' : ['Thomas Smith',
                                          'Margaret Garcia',
                                          'James Johnson', 
                                          'Richard Miller',
                                          'Margaret MOORE'],
                      'id_number' : [204, 264, 108, 238, 136],
                     'Department' : ['ECE', 'EE' ,'CSE', 'ME', 'CE'],
                      
                         })
professors
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
      <th>Prof_name</th>
      <th>id_number</th>
      <th>Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Thomas Smith</td>
      <td>204</td>
      <td>ECE</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Margaret Garcia</td>
      <td>264</td>
      <td>EE</td>
    </tr>
    <tr>
      <td>2</td>
      <td>James Johnson</td>
      <td>108</td>
      <td>CSE</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Richard Miller</td>
      <td>238</td>
      <td>ME</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Margaret MOORE</td>
      <td>136</td>
      <td>CE</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([students, professors], sort = True)
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
      <th>Age</th>
      <th>Department</th>
      <th>Gender</th>
      <th>Name</th>
      <th>Prof_name</th>
      <th>id_number</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>26.0</td>
      <td>NaN</td>
      <td>M</td>
      <td>James Smith</td>
      <td>NaN</td>
      <td>204</td>
    </tr>
    <tr>
      <td>1</td>
      <td>22.0</td>
      <td>NaN</td>
      <td>F</td>
      <td>Maria Rodriguez</td>
      <td>NaN</td>
      <td>202</td>
    </tr>
    <tr>
      <td>2</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>M</td>
      <td>David Smith</td>
      <td>NaN</td>
      <td>264</td>
    </tr>
    <tr>
      <td>3</td>
      <td>21.0</td>
      <td>NaN</td>
      <td>F</td>
      <td>Patricia Garcia</td>
      <td>NaN</td>
      <td>136</td>
    </tr>
    <tr>
      <td>4</td>
      <td>25.0</td>
      <td>NaN</td>
      <td>F</td>
      <td>Jessica Hernandez</td>
      <td>NaN</td>
      <td>238</td>
    </tr>
    <tr>
      <td>0</td>
      <td>NaN</td>
      <td>ECE</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Thomas Smith</td>
      <td>204</td>
    </tr>
    <tr>
      <td>1</td>
      <td>NaN</td>
      <td>EE</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Margaret Garcia</td>
      <td>264</td>
    </tr>
    <tr>
      <td>2</td>
      <td>NaN</td>
      <td>CSE</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>James Johnson</td>
      <td>108</td>
    </tr>
    <tr>
      <td>3</td>
      <td>NaN</td>
      <td>ME</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Richard Miller</td>
      <td>238</td>
    </tr>
    <tr>
      <td>4</td>
      <td>NaN</td>
      <td>CE</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Margaret MOORE</td>
      <td>136</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([students, professors], sort = True, ignore_index = True)
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
      <th>Age</th>
      <th>Department</th>
      <th>Gender</th>
      <th>Name</th>
      <th>Prof_name</th>
      <th>id_number</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>26.0</td>
      <td>NaN</td>
      <td>M</td>
      <td>James Smith</td>
      <td>NaN</td>
      <td>204</td>
    </tr>
    <tr>
      <td>1</td>
      <td>22.0</td>
      <td>NaN</td>
      <td>F</td>
      <td>Maria Rodriguez</td>
      <td>NaN</td>
      <td>202</td>
    </tr>
    <tr>
      <td>2</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>M</td>
      <td>David Smith</td>
      <td>NaN</td>
      <td>264</td>
    </tr>
    <tr>
      <td>3</td>
      <td>21.0</td>
      <td>NaN</td>
      <td>F</td>
      <td>Patricia Garcia</td>
      <td>NaN</td>
      <td>136</td>
    </tr>
    <tr>
      <td>4</td>
      <td>25.0</td>
      <td>NaN</td>
      <td>F</td>
      <td>Jessica Hernandez</td>
      <td>NaN</td>
      <td>238</td>
    </tr>
    <tr>
      <td>5</td>
      <td>NaN</td>
      <td>ECE</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Thomas Smith</td>
      <td>204</td>
    </tr>
    <tr>
      <td>6</td>
      <td>NaN</td>
      <td>EE</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Margaret Garcia</td>
      <td>264</td>
    </tr>
    <tr>
      <td>7</td>
      <td>NaN</td>
      <td>CSE</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>James Johnson</td>
      <td>108</td>
    </tr>
    <tr>
      <td>8</td>
      <td>NaN</td>
      <td>ME</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Richard Miller</td>
      <td>238</td>
    </tr>
    <tr>
      <td>9</td>
      <td>NaN</td>
      <td>CE</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Margaret MOORE</td>
      <td>136</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(students, professors)
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
      <th>id_number</th>
      <th>Name</th>
      <th>Age</th>
      <th>Gender</th>
      <th>Prof_name</th>
      <th>Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>204</td>
      <td>James Smith</td>
      <td>26</td>
      <td>M</td>
      <td>Thomas Smith</td>
      <td>ECE</td>
    </tr>
    <tr>
      <td>1</td>
      <td>264</td>
      <td>David Smith</td>
      <td>24</td>
      <td>M</td>
      <td>Margaret Garcia</td>
      <td>EE</td>
    </tr>
    <tr>
      <td>2</td>
      <td>136</td>
      <td>Patricia Garcia</td>
      <td>21</td>
      <td>F</td>
      <td>Margaret MOORE</td>
      <td>CE</td>
    </tr>
    <tr>
      <td>3</td>
      <td>238</td>
      <td>Jessica Hernandez</td>
      <td>25</td>
      <td>F</td>
      <td>Richard Miller</td>
      <td>ME</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(students, professors, on = 'id_number') # I recommend to give on all the time
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
      <th>id_number</th>
      <th>Name</th>
      <th>Age</th>
      <th>Gender</th>
      <th>Prof_name</th>
      <th>Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>204</td>
      <td>James Smith</td>
      <td>26</td>
      <td>M</td>
      <td>Thomas Smith</td>
      <td>ECE</td>
    </tr>
    <tr>
      <td>1</td>
      <td>264</td>
      <td>David Smith</td>
      <td>24</td>
      <td>M</td>
      <td>Margaret Garcia</td>
      <td>EE</td>
    </tr>
    <tr>
      <td>2</td>
      <td>136</td>
      <td>Patricia Garcia</td>
      <td>21</td>
      <td>F</td>
      <td>Margaret MOORE</td>
      <td>CE</td>
    </tr>
    <tr>
      <td>3</td>
      <td>238</td>
      <td>Jessica Hernandez</td>
      <td>25</td>
      <td>F</td>
      <td>Richard Miller</td>
      <td>ME</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(students, professors, on = 'id_number', how = 'left')
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
      <th>id_number</th>
      <th>Name</th>
      <th>Age</th>
      <th>Gender</th>
      <th>Prof_name</th>
      <th>Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>204</td>
      <td>James Smith</td>
      <td>26</td>
      <td>M</td>
      <td>Thomas Smith</td>
      <td>ECE</td>
    </tr>
    <tr>
      <td>1</td>
      <td>202</td>
      <td>Maria Rodriguez</td>
      <td>22</td>
      <td>F</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>2</td>
      <td>264</td>
      <td>David Smith</td>
      <td>24</td>
      <td>M</td>
      <td>Margaret Garcia</td>
      <td>EE</td>
    </tr>
    <tr>
      <td>3</td>
      <td>136</td>
      <td>Patricia Garcia</td>
      <td>21</td>
      <td>F</td>
      <td>Margaret MOORE</td>
      <td>CE</td>
    </tr>
    <tr>
      <td>4</td>
      <td>238</td>
      <td>Jessica Hernandez</td>
      <td>25</td>
      <td>F</td>
      <td>Richard Miller</td>
      <td>ME</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(students, professors, on = 'id_number', how = 'right')
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
      <th>id_number</th>
      <th>Name</th>
      <th>Age</th>
      <th>Gender</th>
      <th>Prof_name</th>
      <th>Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>204</td>
      <td>James Smith</td>
      <td>26.0</td>
      <td>M</td>
      <td>Thomas Smith</td>
      <td>ECE</td>
    </tr>
    <tr>
      <td>1</td>
      <td>264</td>
      <td>David Smith</td>
      <td>24.0</td>
      <td>M</td>
      <td>Margaret Garcia</td>
      <td>EE</td>
    </tr>
    <tr>
      <td>2</td>
      <td>136</td>
      <td>Patricia Garcia</td>
      <td>21.0</td>
      <td>F</td>
      <td>Margaret MOORE</td>
      <td>CE</td>
    </tr>
    <tr>
      <td>3</td>
      <td>238</td>
      <td>Jessica Hernandez</td>
      <td>25.0</td>
      <td>F</td>
      <td>Richard Miller</td>
      <td>ME</td>
    </tr>
    <tr>
      <td>4</td>
      <td>108</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>James Johnson</td>
      <td>CSE</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(students, professors, on = 'id_number', how = 'inner')
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
      <th>id_number</th>
      <th>Name</th>
      <th>Age</th>
      <th>Gender</th>
      <th>Prof_name</th>
      <th>Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>204</td>
      <td>James Smith</td>
      <td>26</td>
      <td>M</td>
      <td>Thomas Smith</td>
      <td>ECE</td>
    </tr>
    <tr>
      <td>1</td>
      <td>264</td>
      <td>David Smith</td>
      <td>24</td>
      <td>M</td>
      <td>Margaret Garcia</td>
      <td>EE</td>
    </tr>
    <tr>
      <td>2</td>
      <td>136</td>
      <td>Patricia Garcia</td>
      <td>21</td>
      <td>F</td>
      <td>Margaret MOORE</td>
      <td>CE</td>
    </tr>
    <tr>
      <td>3</td>
      <td>238</td>
      <td>Jessica Hernandez</td>
      <td>25</td>
      <td>F</td>
      <td>Richard Miller</td>
      <td>ME</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(students, professors, on = 'id_number', how = 'outer')
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
      <th>id_number</th>
      <th>Name</th>
      <th>Age</th>
      <th>Gender</th>
      <th>Prof_name</th>
      <th>Department</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>204</td>
      <td>James Smith</td>
      <td>26.0</td>
      <td>M</td>
      <td>Thomas Smith</td>
      <td>ECE</td>
    </tr>
    <tr>
      <td>1</td>
      <td>202</td>
      <td>Maria Rodriguez</td>
      <td>22.0</td>
      <td>F</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>2</td>
      <td>264</td>
      <td>David Smith</td>
      <td>24.0</td>
      <td>M</td>
      <td>Margaret Garcia</td>
      <td>EE</td>
    </tr>
    <tr>
      <td>3</td>
      <td>136</td>
      <td>Patricia Garcia</td>
      <td>21.0</td>
      <td>F</td>
      <td>Margaret MOORE</td>
      <td>CE</td>
    </tr>
    <tr>
      <td>4</td>
      <td>238</td>
      <td>Jessica Hernandez</td>
      <td>25.0</td>
      <td>F</td>
      <td>Richard Miller</td>
      <td>ME</td>
    </tr>
    <tr>
      <td>5</td>
      <td>108</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>James Johnson</td>
      <td>CSE</td>
    </tr>
  </tbody>
</table>
</div>




```python
students.to_csv('students.csv')
print('Exporting completed')
```

    Exporting completed
    


```python
professors.to_excel('prof.xlsx', sheet_name = 'prof', index = False)
print('Exporting completed')
```

    Exporting completed
    


```python

```
