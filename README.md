Read multiple JSON files into a directory to convert into a dataset.
I have files text1, text2, text3 in the directory JSON.
Ans.
library(jsonlite)
library(dplyr)

ls &lt;- list(&quot;E:\\Acadgild\\Assignment\\JSON\\text1.json&quot;,
&quot;E:\\Acadgild\\Assignment\\JSON\\text2.json&quot;,
&quot;E:\\Acadgild\\Assignment\\JSON\\text3.json&quot;)

for (i in ls){
z &lt;- data.frame()
a &lt;- read_json(i, simplifyVector = TRUE)
z &lt;- cbind(z,a)
}

2. Parse the following JSON into a data frame.
Ans.
js&lt;-&#39;{
&quot;name&quot;: null, &quot;release_date_local&quot;: null, &quot;title&quot;: &quot;3 (2011)&quot;,
&quot;opening_weekend_take&quot;: 1234, &quot;year&quot;: 2011,
&quot;release_date_wide&quot;: &quot;2011-09-16&quot;, &quot;gross&quot;: 59954
}&#39;
json &lt;- &#39;[
{&quot;name&quot; : NULL,
&quot;release_date_local&quot; : NULL,
&quot;title&quot; : 3(2011),
&quot;opening_weekend_take&quot; : 1234,

&quot;year&quot; : 2011,
&quot;release_date_wide&quot; : [2011-09-16],
&quot;gross&quot; : 59954
}
]&#39;

mydf &lt;- fromJSON(json, simplifyVector = TRUE, simplifyDataFrame = simplifyVector)
mydf

3. Write a script for Variable Binning using R.
bin &lt;- c(1:100)
bin

binning &lt;- function(x)
{
for(i in c(1:100))
{
ifelse(i &lt;= 25, paste(i,&quot;group1&quot;),
ifelse(i &lt;= 50, paste(i,&quot;group2&quot;),
ifelse(i &lt;= 75, paste(i,&quot;group3&quot;),
paste(i,&quot;group4&quot;))))
break
}
}

binning(bin)
