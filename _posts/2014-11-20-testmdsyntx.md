---
layout: post
title:  "Test Md Sytnax"
date:   Fri Nov 21 18:26:46 2014
categories: html
comments: true
---



{% highlight javascirpt linenos %}
$(function () {
    $('#container').highcharts({

        title: {
            text: 'Title floating left',
            floating: true,
            align: 'left',
            x: 200,
            y: 50
        },

        xAxis: {
            categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']
        },

        series: [{
            data: [29.9, 71.5, 106.4, 129.2, 144.0, 176.0, 135.6, 148.5, 216.4, 194.1, 95.6, 54.4]
        }]
    });
    }); 
{% endhighlight %}




~~~~~~~~html  

<nav>
    <ul>
        <li class="item1">list1</li>
        <li class="item2">list2</li>
        <li class="item3">list3</li>
        <li class="item4">list4</li>
        <li class="item5">list5</li>
    </ul>
</nav>
~~~~~~~~