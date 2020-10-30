<h1 align="center">Fit Chart</h1>
<h4 align="center">Android Library</h4>

<p align="center">
  <a target="_blank" href="https://android-arsenal.com/api?level=14"><img src="https://img.shields.io/badge/API-14%2B-orange.svg"></a>
</p>

<p align="center">Fit Chart is an Android view similar to Google Fit wheel chart. This library is a fork from the original <a href="https://github.com/txusballesteros/fit-chart">FitChart library</a> by Txus Ballesteros and includes an option to enable/disable the animation progress.
</p>

<p align="center"><img src="assets/overdraw_animation_mode.gif" /><img src="assets/linear_animation_mode.gif" /></p>

## How to include

Add the repository to your project **build.gradle**:
```Javascript
repositories {
    maven {
        url "https://jitpack.io"
    }
}
```

And add the library to your module **build.gradle**:
```Javascript
dependencies {
    compile 'com.github.javiersantos:FitChart:1.1.1'
}
```

## Usage
### Adding the View to your layout

```xml
<com.txusballesteros.widgets.FitChart
  android:layout_width="200dp"
  android:layout_height="200dp" />
```

### Styling the View

If you want to customize the view, you can set the next attributes.

```xml
<com.txusballesteros.widgets.FitChart
  ...
  app:strokeSize="10dp"
  app:valueStrokeColor="#ff0000"
  app:backStrokeColor="#00ff00"
  app:animationMethod="overdraw" />
```

### Setting the values

Setting the minimum and maximum values of the scale of the chart.

```java
FitChart fitChart = (FitChart)findViewById(R.id.fitChart);
fitChart.setMinValue(0f);
fitChart.setMaxValue(100f);
```

Setting a single progress value with animation.

```java
FitChart fitChart = (FitChart)findViewById(R.id.fitChart);
fitChart.setValue(80f);
```

Or without the progress animation.

```java
FitChart fitChart = (FitChart)findViewById(R.id.fitChart);
fitChart.setValue(80f, false);
```


Setting a some progress values with animation.

```java
// Create a list with the values
List<FitChartValue> values = new ArrayList<>();
values.add(new FitChartValue(30f, ContextCompat.getColor(this, R.color.chart_value_1)));
values.add(new FitChartValue(20f, ContextCompat.getColor(this, R.color.chart_value_2)));
values.add(new FitChartValue(15f, ContextCompat.getColor(this, R.color.chart_value_3)));
values.add(new FitChartValue(10f, ContextCompat.getColor(this, R.color.chart_value_4)));

// Add the Collection to the wheel chart
FitChart fitChart = (FitChart)findViewById(R.id.fitChart);
fitChart.setValues(values);
```

Or without the progress animation.

```java
// Create a list with the values
List<FitChartValue> values = new ArrayList<>();
values.add(new FitChartValue(30f, ContextCompat.getColor(this, R.color.chart_value_1)));
values.add(new FitChartValue(20f, ContextCompat.getColor(this, R.color.chart_value_2)));
values.add(new FitChartValue(15f, ContextCompat.getColor(this, R.color.chart_value_3)));
values.add(new FitChartValue(10f, ContextCompat.getColor(this, R.color.chart_value_4)));

// Add the list to the wheel chart
FitChart fitChart = (FitChart)findViewById(R.id.fitChart);
fitChart.setValues(values, false);
```

## License

Copyright Txus Ballesteros 2015 (@txusballesteros)

This file is part of some open source application.

Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.

Contact: Txus Ballesteros <txus.ballesteros@gmail.com>
