---
layout: post
title:  "Does beer affect life expectancy?"
date:   2018-07-30 18:10:30 +0100
categories: beer, data science
---

{% include analytics.html %}

Is beer bad for you? A question often discussed in pubs, bars, restaurants, and cafés, but without clear results.

Data Science to the rescue! There is enormous variation between the average per-capita beer consumption among countries of the world, so let's see if there is correlation between beer consumption and life expectancy.

Both source of data are simply Wikipiedia tables<sup>[1](#beer)</sup><sup>[2](#age)</sup>

By formatting the data to a simple csv table, it can be loaded into Matlab, and visualised with the following code:

```matlab
fid=fopen('Desktop/beer consumption and life expectancy.csv')
out=textscan(fid,'%s%f%f','delimiter',',')
beer = out{2}
age = out{3}
scatter(beer,age)
text(beer+dx, age+dy, out{1})
title('Beer consumption vs Life expectancy per Country')
xlabel('liters of beer per capita per year')
ylabel('life expectancy for both genders')
```

And this is what we get:

![Belarus]({{ site.url }}/images/beer_vs_age.png)

No clear correlation, right? That's easy to quantify with `corr(beer,age)`. This data gives us a correlation of 0.2129, which means 'not much correlation'. In fact, the p-value is 0.1086, meaning 'not significant'.

<a name="beer">1</a>: [Wikipedia's list of landlocked countries](https://en.wikipedia.org/wiki/Landlocked_country), every country's [highest and lowest points](https://en.wikipedia.org/wiki/List_of_elevation_extremes_by_country)
<a name="age">2</a>: [Wikipedia's list of landlocked countries](https://en.wikipedia.org/wiki/Landlocked_country), every country's [highest and lowest points](https://en.wikipedia.org/wiki/List_of_elevation_extremes_by_country)
