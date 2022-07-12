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


<script type="text/javascript">
window.PlotlyConfig = {MathJaxConfig: 'local'};
if (window.MathJax) {MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}
if (typeof require !== 'undefined') {
require.undef("plotly");
requirejs.config({
    paths: {
        'plotly': ['https://cdn.plot.ly/plotly-2.9.0.min']
    }
});
require(['plotly'], function(Plotly) {
    window._Plotly = Plotly;
});
}
</script>




```python
df = pd.read_csv("D:\Documents\india_alcohol_stats.csv")
geojson="https://gist.githubusercontent.com/jbrobst/56c13bbbf9d97d187fea01ca62ea5112/raw/e388c4cae20aa53cb5090210a42ebb9b765c0a36/india_states.geojson",

```


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




```python

```


```python

```


```python

```
