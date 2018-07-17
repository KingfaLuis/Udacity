

```python
import pandas as pd

wine_df = pd.read_csv('winequality_edited.csv')
wine_df.head()
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
      <th>fixed acidity</th>
      <th>volatile acidity</th>
      <th>citric acid</th>
      <th>residual sugar</th>
      <th>chlorides</th>
      <th>free sulfur dioxide</th>
      <th>total sulfur dioxide</th>
      <th>density</th>
      <th>pH</th>
      <th>sulphates</th>
      <th>alcohol</th>
      <th>quality</th>
      <th>color</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7.4</td>
      <td>0.70</td>
      <td>0.00</td>
      <td>1.9</td>
      <td>0.076</td>
      <td>11.0</td>
      <td>34.0</td>
      <td>0.9978</td>
      <td>3.51</td>
      <td>0.56</td>
      <td>9.4</td>
      <td>5</td>
      <td>red</td>
    </tr>
    <tr>
      <th>1</th>
      <td>7.8</td>
      <td>0.88</td>
      <td>0.00</td>
      <td>2.6</td>
      <td>0.098</td>
      <td>25.0</td>
      <td>67.0</td>
      <td>0.9968</td>
      <td>3.20</td>
      <td>0.68</td>
      <td>9.8</td>
      <td>5</td>
      <td>red</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7.8</td>
      <td>0.76</td>
      <td>0.04</td>
      <td>2.3</td>
      <td>0.092</td>
      <td>15.0</td>
      <td>54.0</td>
      <td>0.9970</td>
      <td>3.26</td>
      <td>0.65</td>
      <td>9.8</td>
      <td>5</td>
      <td>red</td>
    </tr>
    <tr>
      <th>3</th>
      <td>11.2</td>
      <td>0.28</td>
      <td>0.56</td>
      <td>1.9</td>
      <td>0.075</td>
      <td>17.0</td>
      <td>60.0</td>
      <td>0.9980</td>
      <td>3.16</td>
      <td>0.58</td>
      <td>9.8</td>
      <td>6</td>
      <td>red</td>
    </tr>
    <tr>
      <th>4</th>
      <td>7.4</td>
      <td>0.70</td>
      <td>0.00</td>
      <td>1.9</td>
      <td>0.076</td>
      <td>11.0</td>
      <td>34.0</td>
      <td>0.9978</td>
      <td>3.51</td>
      <td>0.56</td>
      <td>9.4</td>
      <td>5</td>
      <td>red</td>
    </tr>
  </tbody>
</table>
</div>




```python
wine_df.mean()
```




    fixed acidity             7.215307
    volatile acidity          0.339666
    citric acid               0.318633
    residual sugar            5.443235
    chlorides                 0.056034
    free sulfur dioxide      30.525319
    total sulfur dioxide    115.744574
    density                   0.994697
    pH                        3.218501
    sulphates                 0.531268
    alcohol                  10.491801
    quality                   5.818378
    dtype: float64



# 找出每种质量评分的PH平均值，我们可以使用groupby结合mean 来达到这个效果


```python
wine_df.groupby('quality').mean()
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
      <th>fixed acidity</th>
      <th>volatile acidity</th>
      <th>citric acid</th>
      <th>residual sugar</th>
      <th>chlorides</th>
      <th>free sulfur dioxide</th>
      <th>total sulfur dioxide</th>
      <th>density</th>
      <th>pH</th>
      <th>sulphates</th>
      <th>alcohol</th>
    </tr>
    <tr>
      <th>quality</th>
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
      <th>3</th>
      <td>7.853333</td>
      <td>0.517000</td>
      <td>0.281000</td>
      <td>5.140000</td>
      <td>0.077033</td>
      <td>39.216667</td>
      <td>122.033333</td>
      <td>0.995744</td>
      <td>3.257667</td>
      <td>0.506333</td>
      <td>10.215000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>7.288889</td>
      <td>0.457963</td>
      <td>0.272315</td>
      <td>4.153704</td>
      <td>0.060056</td>
      <td>20.636574</td>
      <td>103.432870</td>
      <td>0.994833</td>
      <td>3.231620</td>
      <td>0.505648</td>
      <td>10.180093</td>
    </tr>
    <tr>
      <th>5</th>
      <td>7.326801</td>
      <td>0.389614</td>
      <td>0.307722</td>
      <td>5.804116</td>
      <td>0.064666</td>
      <td>30.237371</td>
      <td>120.839102</td>
      <td>0.995849</td>
      <td>3.212189</td>
      <td>0.526403</td>
      <td>9.837783</td>
    </tr>
    <tr>
      <th>6</th>
      <td>7.177257</td>
      <td>0.313863</td>
      <td>0.323583</td>
      <td>5.549753</td>
      <td>0.054157</td>
      <td>31.165021</td>
      <td>115.410790</td>
      <td>0.994558</td>
      <td>3.217726</td>
      <td>0.532549</td>
      <td>10.587553</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7.128962</td>
      <td>0.288800</td>
      <td>0.334764</td>
      <td>4.731696</td>
      <td>0.045272</td>
      <td>30.422150</td>
      <td>108.498610</td>
      <td>0.993126</td>
      <td>3.228072</td>
      <td>0.547025</td>
      <td>11.386006</td>
    </tr>
    <tr>
      <th>8</th>
      <td>6.835233</td>
      <td>0.291010</td>
      <td>0.332539</td>
      <td>5.382902</td>
      <td>0.041124</td>
      <td>34.533679</td>
      <td>117.518135</td>
      <td>0.992514</td>
      <td>3.223212</td>
      <td>0.512487</td>
      <td>11.678756</td>
    </tr>
    <tr>
      <th>9</th>
      <td>7.420000</td>
      <td>0.298000</td>
      <td>0.386000</td>
      <td>4.120000</td>
      <td>0.027400</td>
      <td>33.400000</td>
      <td>116.000000</td>
      <td>0.991460</td>
      <td>3.308000</td>
      <td>0.466000</td>
      <td>12.180000</td>
    </tr>
  </tbody>
</table>
</div>




```python
wine_df.groupby('color').mean()
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
      <th>fixed acidity</th>
      <th>volatile acidity</th>
      <th>citric acid</th>
      <th>residual sugar</th>
      <th>chlorides</th>
      <th>free sulfur dioxide</th>
      <th>total sulfur dioxide</th>
      <th>density</th>
      <th>pH</th>
      <th>sulphates</th>
      <th>alcohol</th>
      <th>quality</th>
    </tr>
    <tr>
      <th>color</th>
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
      <th>red</th>
      <td>8.319637</td>
      <td>0.527821</td>
      <td>0.270976</td>
      <td>2.538806</td>
      <td>0.087467</td>
      <td>15.874922</td>
      <td>46.467792</td>
      <td>0.996747</td>
      <td>3.311113</td>
      <td>0.658149</td>
      <td>10.422983</td>
      <td>5.636023</td>
    </tr>
    <tr>
      <th>white</th>
      <td>6.854788</td>
      <td>0.278241</td>
      <td>0.334192</td>
      <td>6.391415</td>
      <td>0.045772</td>
      <td>35.308085</td>
      <td>138.360657</td>
      <td>0.994027</td>
      <td>3.188267</td>
      <td>0.489847</td>
      <td>10.514267</td>
      <td>5.877909</td>
    </tr>
  </tbody>
</table>
</div>




```python
wine_df.groupby(['quality','color']).mean()
#同时分组的列，设置为索引
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
      <th>fixed acidity</th>
      <th>volatile acidity</th>
      <th>citric acid</th>
      <th>residual sugar</th>
      <th>chlorides</th>
      <th>free sulfur dioxide</th>
      <th>total sulfur dioxide</th>
      <th>density</th>
      <th>pH</th>
      <th>sulphates</th>
      <th>alcohol</th>
    </tr>
    <tr>
      <th>quality</th>
      <th>color</th>
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
      <th rowspan="2" valign="top">3</th>
      <th>red</th>
      <td>8.360000</td>
      <td>0.884500</td>
      <td>0.171000</td>
      <td>2.635000</td>
      <td>0.122500</td>
      <td>11.000000</td>
      <td>24.900000</td>
      <td>0.997464</td>
      <td>3.398000</td>
      <td>0.570000</td>
      <td>9.955000</td>
    </tr>
    <tr>
      <th>white</th>
      <td>7.600000</td>
      <td>0.333250</td>
      <td>0.336000</td>
      <td>6.392500</td>
      <td>0.054300</td>
      <td>53.325000</td>
      <td>170.600000</td>
      <td>0.994884</td>
      <td>3.187500</td>
      <td>0.474500</td>
      <td>10.345000</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">4</th>
      <th>red</th>
      <td>7.779245</td>
      <td>0.693962</td>
      <td>0.174151</td>
      <td>2.694340</td>
      <td>0.090679</td>
      <td>12.264151</td>
      <td>36.245283</td>
      <td>0.996542</td>
      <td>3.381509</td>
      <td>0.596415</td>
      <td>10.265094</td>
    </tr>
    <tr>
      <th>white</th>
      <td>7.129448</td>
      <td>0.381227</td>
      <td>0.304233</td>
      <td>4.628221</td>
      <td>0.050098</td>
      <td>23.358896</td>
      <td>125.279141</td>
      <td>0.994277</td>
      <td>3.182883</td>
      <td>0.476135</td>
      <td>10.152454</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">5</th>
      <th>red</th>
      <td>8.167254</td>
      <td>0.577041</td>
      <td>0.243686</td>
      <td>2.528855</td>
      <td>0.092736</td>
      <td>16.983847</td>
      <td>56.513950</td>
      <td>0.997104</td>
      <td>3.304949</td>
      <td>0.620969</td>
      <td>9.899706</td>
    </tr>
    <tr>
      <th>white</th>
      <td>6.933974</td>
      <td>0.302011</td>
      <td>0.337653</td>
      <td>7.334969</td>
      <td>0.051546</td>
      <td>36.432052</td>
      <td>150.904598</td>
      <td>0.995263</td>
      <td>3.168833</td>
      <td>0.482203</td>
      <td>9.808840</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">6</th>
      <th>red</th>
      <td>8.347179</td>
      <td>0.497484</td>
      <td>0.273824</td>
      <td>2.477194</td>
      <td>0.084956</td>
      <td>15.711599</td>
      <td>40.869906</td>
      <td>0.996615</td>
      <td>3.318072</td>
      <td>0.675329</td>
      <td>10.629519</td>
    </tr>
    <tr>
      <th>white</th>
      <td>6.837671</td>
      <td>0.260564</td>
      <td>0.338025</td>
      <td>6.441606</td>
      <td>0.045217</td>
      <td>35.650591</td>
      <td>137.047316</td>
      <td>0.993961</td>
      <td>3.188599</td>
      <td>0.491106</td>
      <td>10.575372</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">7</th>
      <th>red</th>
      <td>8.872362</td>
      <td>0.403920</td>
      <td>0.375176</td>
      <td>2.720603</td>
      <td>0.076588</td>
      <td>14.045226</td>
      <td>35.020101</td>
      <td>0.996104</td>
      <td>3.290754</td>
      <td>0.741256</td>
      <td>11.465913</td>
    </tr>
    <tr>
      <th>white</th>
      <td>6.734716</td>
      <td>0.262767</td>
      <td>0.325625</td>
      <td>5.186477</td>
      <td>0.038191</td>
      <td>34.125568</td>
      <td>125.114773</td>
      <td>0.992452</td>
      <td>3.213898</td>
      <td>0.503102</td>
      <td>11.367936</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">8</th>
      <th>red</th>
      <td>8.566667</td>
      <td>0.423333</td>
      <td>0.391111</td>
      <td>2.577778</td>
      <td>0.068444</td>
      <td>13.277778</td>
      <td>33.444444</td>
      <td>0.995212</td>
      <td>3.267222</td>
      <td>0.767778</td>
      <td>12.094444</td>
    </tr>
    <tr>
      <th>white</th>
      <td>6.657143</td>
      <td>0.277400</td>
      <td>0.326514</td>
      <td>5.671429</td>
      <td>0.038314</td>
      <td>36.720000</td>
      <td>126.165714</td>
      <td>0.992236</td>
      <td>3.218686</td>
      <td>0.486229</td>
      <td>11.636000</td>
    </tr>
    <tr>
      <th>9</th>
      <th>white</th>
      <td>7.420000</td>
      <td>0.298000</td>
      <td>0.386000</td>
      <td>4.120000</td>
      <td>0.027400</td>
      <td>33.400000</td>
      <td>116.000000</td>
      <td>0.991460</td>
      <td>3.308000</td>
      <td>0.466000</td>
      <td>12.180000</td>
    </tr>
  </tbody>
</table>
</div>




```python
#如果不想把分组的列设置为索引
wine_df.groupby(['quality','color'],as_index=False).mean()
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
      <th>quality</th>
      <th>color</th>
      <th>fixed acidity</th>
      <th>volatile acidity</th>
      <th>citric acid</th>
      <th>residual sugar</th>
      <th>chlorides</th>
      <th>free sulfur dioxide</th>
      <th>total sulfur dioxide</th>
      <th>density</th>
      <th>pH</th>
      <th>sulphates</th>
      <th>alcohol</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>red</td>
      <td>8.360000</td>
      <td>0.884500</td>
      <td>0.171000</td>
      <td>2.635000</td>
      <td>0.122500</td>
      <td>11.000000</td>
      <td>24.900000</td>
      <td>0.997464</td>
      <td>3.398000</td>
      <td>0.570000</td>
      <td>9.955000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>white</td>
      <td>7.600000</td>
      <td>0.333250</td>
      <td>0.336000</td>
      <td>6.392500</td>
      <td>0.054300</td>
      <td>53.325000</td>
      <td>170.600000</td>
      <td>0.994884</td>
      <td>3.187500</td>
      <td>0.474500</td>
      <td>10.345000</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>red</td>
      <td>7.779245</td>
      <td>0.693962</td>
      <td>0.174151</td>
      <td>2.694340</td>
      <td>0.090679</td>
      <td>12.264151</td>
      <td>36.245283</td>
      <td>0.996542</td>
      <td>3.381509</td>
      <td>0.596415</td>
      <td>10.265094</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>white</td>
      <td>7.129448</td>
      <td>0.381227</td>
      <td>0.304233</td>
      <td>4.628221</td>
      <td>0.050098</td>
      <td>23.358896</td>
      <td>125.279141</td>
      <td>0.994277</td>
      <td>3.182883</td>
      <td>0.476135</td>
      <td>10.152454</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>red</td>
      <td>8.167254</td>
      <td>0.577041</td>
      <td>0.243686</td>
      <td>2.528855</td>
      <td>0.092736</td>
      <td>16.983847</td>
      <td>56.513950</td>
      <td>0.997104</td>
      <td>3.304949</td>
      <td>0.620969</td>
      <td>9.899706</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>white</td>
      <td>6.933974</td>
      <td>0.302011</td>
      <td>0.337653</td>
      <td>7.334969</td>
      <td>0.051546</td>
      <td>36.432052</td>
      <td>150.904598</td>
      <td>0.995263</td>
      <td>3.168833</td>
      <td>0.482203</td>
      <td>9.808840</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>red</td>
      <td>8.347179</td>
      <td>0.497484</td>
      <td>0.273824</td>
      <td>2.477194</td>
      <td>0.084956</td>
      <td>15.711599</td>
      <td>40.869906</td>
      <td>0.996615</td>
      <td>3.318072</td>
      <td>0.675329</td>
      <td>10.629519</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6</td>
      <td>white</td>
      <td>6.837671</td>
      <td>0.260564</td>
      <td>0.338025</td>
      <td>6.441606</td>
      <td>0.045217</td>
      <td>35.650591</td>
      <td>137.047316</td>
      <td>0.993961</td>
      <td>3.188599</td>
      <td>0.491106</td>
      <td>10.575372</td>
    </tr>
    <tr>
      <th>8</th>
      <td>7</td>
      <td>red</td>
      <td>8.872362</td>
      <td>0.403920</td>
      <td>0.375176</td>
      <td>2.720603</td>
      <td>0.076588</td>
      <td>14.045226</td>
      <td>35.020101</td>
      <td>0.996104</td>
      <td>3.290754</td>
      <td>0.741256</td>
      <td>11.465913</td>
    </tr>
    <tr>
      <th>9</th>
      <td>7</td>
      <td>white</td>
      <td>6.734716</td>
      <td>0.262767</td>
      <td>0.325625</td>
      <td>5.186477</td>
      <td>0.038191</td>
      <td>34.125568</td>
      <td>125.114773</td>
      <td>0.992452</td>
      <td>3.213898</td>
      <td>0.503102</td>
      <td>11.367936</td>
    </tr>
    <tr>
      <th>10</th>
      <td>8</td>
      <td>red</td>
      <td>8.566667</td>
      <td>0.423333</td>
      <td>0.391111</td>
      <td>2.577778</td>
      <td>0.068444</td>
      <td>13.277778</td>
      <td>33.444444</td>
      <td>0.995212</td>
      <td>3.267222</td>
      <td>0.767778</td>
      <td>12.094444</td>
    </tr>
    <tr>
      <th>11</th>
      <td>8</td>
      <td>white</td>
      <td>6.657143</td>
      <td>0.277400</td>
      <td>0.326514</td>
      <td>5.671429</td>
      <td>0.038314</td>
      <td>36.720000</td>
      <td>126.165714</td>
      <td>0.992236</td>
      <td>3.218686</td>
      <td>0.486229</td>
      <td>11.636000</td>
    </tr>
    <tr>
      <th>12</th>
      <td>9</td>
      <td>white</td>
      <td>7.420000</td>
      <td>0.298000</td>
      <td>0.386000</td>
      <td>4.120000</td>
      <td>0.027400</td>
      <td>33.400000</td>
      <td>116.000000</td>
      <td>0.991460</td>
      <td>3.308000</td>
      <td>0.466000</td>
      <td>12.180000</td>
    </tr>
  </tbody>
</table>
</div>




```python
#https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.groupby.html
```


```python
#如果不想把分组的列设置为索引,并且从数据集中得出结论，对比红酒和白酒的ph值，
#那个的质量更高？
wine_df.groupby(['quality','color'],as_index=False)['pH'].mean()
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
      <th>quality</th>
      <th>color</th>
      <th>pH</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>red</td>
      <td>3.398000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>white</td>
      <td>3.187500</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>red</td>
      <td>3.381509</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>white</td>
      <td>3.182883</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>red</td>
      <td>3.304949</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>white</td>
      <td>3.168833</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>red</td>
      <td>3.318072</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6</td>
      <td>white</td>
      <td>3.188599</td>
    </tr>
    <tr>
      <th>8</th>
      <td>7</td>
      <td>red</td>
      <td>3.290754</td>
    </tr>
    <tr>
      <th>9</th>
      <td>7</td>
      <td>white</td>
      <td>3.213898</td>
    </tr>
    <tr>
      <th>10</th>
      <td>8</td>
      <td>red</td>
      <td>3.267222</td>
    </tr>
    <tr>
      <th>11</th>
      <td>8</td>
      <td>white</td>
      <td>3.218686</td>
    </tr>
    <tr>
      <th>12</th>
      <td>9</td>
      <td>white</td>
      <td>3.308000</td>
    </tr>
  </tbody>
</table>
</div>


