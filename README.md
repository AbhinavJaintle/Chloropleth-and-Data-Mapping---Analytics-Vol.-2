# Chloropleth-and-Data-Mapping---Analytics-Vol.-2

```python
from chart_studio import plotly
import plotly.graph_objs as go 
from plotly.offline import download_plotlyjs, init_notebook_mode, plot, iplot
import plotly.express as px
import pandas as pd
```


```python
init_notebook_mode(connected=True) 
```






```python
df = pd.read_csv("D:\Documents\india_alcohol_stats.csv")
geojson="https://gist.githubusercontent.com/jbrobst/56c13bbbf9d97d187fea01ca62ea5112/raw/e388c4cae20aa53cb5090210a42ebb9b765c0a36/india_states.geojson",

```


```python
df
```




<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>state</th>
      <th>consumption</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Andaman &amp; Nicobar</td>
      <td>25.4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Andhra Pradesh</td>
      <td>13.7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arunachal Pradesh</td>
      <td>28.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Assam</td>
      <td>8.8</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Bihar</td>
      <td>7.9</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Chandigarh</td>
      <td>17.5</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Chhattisgarh</td>
      <td>35.6</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Dadra and Nagar Haveli and Daman and Diu</td>
      <td>15.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Delhi</td>
      <td>21.3</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Goa</td>
      <td>26.4</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Gujarat</td>
      <td>3.9</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Haryana</td>
      <td>21.6</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Himachal Pradesh</td>
      <td>8.9</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Jammu &amp; Kashmir</td>
      <td>3.5</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Jharkhand</td>
      <td>6.5</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Karnataka</td>
      <td>6.4</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Kerala</td>
      <td>12.4</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Ladakh</td>
      <td>27.4</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Madhya Pradesh</td>
      <td>17.7</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Maharashtra</td>
      <td>5.7</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Manipur</td>
      <td>22.4</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Meghalaya</td>
      <td>3.4</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Mizoram</td>
      <td>7.8</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Nagaland</td>
      <td>8.1</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Odisha</td>
      <td>16.4</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Puducherry</td>
      <td>9.5</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Punjab</td>
      <td>28.5</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Rajasthan</td>
      <td>2.1</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Sikkim</td>
      <td>15.7</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Tamil Nadu</td>
      <td>14.2</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Telangana</td>
      <td>16.8</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Tripura</td>
      <td>34.7</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Uttarakhand</td>
      <td>18.8</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Uttar Pradesh</td>
      <td>23.8</td>
    </tr>
    <tr>
      <th>34</th>
      <td>West Bengal</td>
      <td>16.7</td>
    </tr>
  </tbody>
</table>
</div>




```python
fig = px.choropleth(
    df,
    geojson="https://gist.githubusercontent.com/jbrobst/56c13bbbf9d97d187fea01ca62ea5112/raw/e388c4cae20aa53cb5090210a42ebb9b765c0a36/india_states.geojson",
    featureidkey='properties.ST_NM',
    locations='state',
    
    color='consumption',
    color_continuous_scale='reds'
)
```


```python
fig.update_geos(fitbounds="locations", scope="asia", resolution=110, visible=False, showsubunits=True, subunitcolor="White", subunitwidth=0)
```





```python
plot(fig)
```




    'temp-plot.html'



![brewing(3)](https://user-images.githubusercontent.com/86119205/178465050-58db7c18-577f-40f2-88a5-d41afa50fd8c.png)

