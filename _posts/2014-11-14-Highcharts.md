---
layout: post
title:  "HighCharts  学习 "
date:   2014-11-14 09:28:51
categories: wiki
---



## Highchart gem
    gem 'lazy_high_charts'
    
## 插件demo
[demo](https://stormy-reaches-4050.herokuapp.com)

## rails Highchars 插件是生成一个json代码串

## Highcharts 是一个JS插件，调用方法highcarts（Json）即可显示图像

~~~~~~~~javascript  
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
~~~~~~~~
