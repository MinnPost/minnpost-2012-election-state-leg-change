# 2012 Election State Leg Change

Visualization for the State Legislature makeup change after the 2012 elections.

## Data Conversion

```
csvjson visualizations/data/2013-house.csv > visualizations/data/2013-house.json; csvjson visualizations/data/2013-senate.csv > visualizations/data/2013-senate.json; csvjson visualizations/data/2011-house.csv > visualizations/data/2011-house.json; csvjson visualizations/data/2011-senate.csv > visualizations/data/2011-senate.json;
```

```
echo 'legCallback({' > visualizations/data/data.jsonp;
echo '"house-2013": ' >> visualizations/data/data.jsonp;
cat visualizations/data/2013-house.json >> visualizations/data/data.jsonp;
echo ', "house-2011": ' >> visualizations/data/data.jsonp; 
cat visualizations/data/2011-house.json >> visualizations/data/data.jsonp;
echo ', "senate-2013": ' >> visualizations/data/data.jsonp;
cat visualizations/data/2013-senate.json >> visualizations/data/data.jsonp;
echo ', "senate-2011": ' >> visualizations/data/data.jsonp;
cat visualizations/data/2011-senate.json >> visualizations/data/data.jsonp;
echo '});' >> visualizations/data/data.jsonp;
```