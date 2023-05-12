- ### Analyzing data with R

### installing libs


```python
install.packages("plotly")
install.packages("magrittr")
install.packages("ggplot2")
library(ggplot2)
library(magrittr)
library(plotly)
```

### reading csv and exploring data


```python
# Load the CSV file into a data frame
df <- read.csv("/content/sample_data/BTC-USD.csv")

# Display the first few rows of the data frame
head(df,8)
```


<table class="dataframe">
<caption>A data.frame: 8 × 7</caption>
<thead>
	<tr><th></th><th scope=col>Date</th><th scope=col>Open</th><th scope=col>High</th><th scope=col>Low</th><th scope=col>Close</th><th scope=col>Adj.Close</th><th scope=col>Volume</th></tr>
	<tr><th></th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;dbl&gt;</th><th scope=col>&lt;dbl&gt;</th><th scope=col>&lt;dbl&gt;</th><th scope=col>&lt;dbl&gt;</th><th scope=col>&lt;dbl&gt;</th><th scope=col>&lt;dbl&gt;</th></tr>
</thead>
<tbody>
	<tr><th scope=row>1</th><td>2022-01-22</td><td>36471.59</td><td>36688.81</td><td>34349.25</td><td>35030.25</td><td>35030.25</td><td>39714385405</td></tr>
	<tr><th scope=row>2</th><td>2022-01-23</td><td>35047.36</td><td>36433.31</td><td>34784.97</td><td>36276.80</td><td>36276.80</td><td>26017975951</td></tr>
	<tr><th scope=row>3</th><td>2022-01-24</td><td>36275.73</td><td>37247.52</td><td>33184.06</td><td>36654.33</td><td>36654.33</td><td>41856658597</td></tr>
	<tr><th scope=row>4</th><td>2022-01-25</td><td>36654.80</td><td>37444.57</td><td>35779.43</td><td>36954.00</td><td>36954.00</td><td>26428189594</td></tr>
	<tr><th scope=row>5</th><td>2022-01-26</td><td>36950.52</td><td>38825.41</td><td>36374.91</td><td>36852.12</td><td>36852.12</td><td>31324598034</td></tr>
	<tr><th scope=row>6</th><td>2022-01-27</td><td>36841.88</td><td>37148.32</td><td>35629.28</td><td>37138.23</td><td>37138.23</td><td>25041426629</td></tr>
	<tr><th scope=row>7</th><td>2022-01-28</td><td>37128.45</td><td>37952.88</td><td>36211.11</td><td>37784.33</td><td>37784.33</td><td>22238830523</td></tr>
	<tr><th scope=row>8</th><td>2022-01-29</td><td>37780.71</td><td>38576.26</td><td>37406.47</td><td>38138.18</td><td>38138.18</td><td>17194183075</td></tr>
</tbody>
</table>



- ##### dataset summary


```python
summary(df)
```


         Date                Open            High            Low       
     Length:20          Min.   :35047   Min.   :36433   Min.   :33184  
     Class :character   1st Qu.:36919   1st Qu.:37395   1st Qu.:36103  
     Mode  :character   Median :37850   Median :38736   Median :36963  
                        Mean   :38910   Mean   :39915   Mean   :37989  
                        3rd Qu.:41456   3rd Qu.:42011   3rd Qu.:41090  
                        Max.   :44348   Max.   :45661   Max.   :43403  
         Close         Adj.Close         Volume         
     Min.   :35030   Min.   :35030   Min.   :1.464e+10  
     1st Qu.:36954   1st Qu.:36954   1st Qu.:1.953e+10  
     Median :38028   Median :38028   Median :2.414e+10  
     Mean   :39265   Mean   :39265   Mean   :2.528e+10  
     3rd Qu.:41729   3rd Qu.:41729   3rd Qu.:2.989e+10  
     Max.   :44339   Max.   :44339   Max.   :4.186e+10  


- ##### standard deviation


```python
print(paste('close std', sd(df$Close)))
print(paste('whole std', sd(c(df$Open, df$Close))))
```

    [1] "close std 3023.49461954453"
    [1] "whole std 2932.60435461045"
