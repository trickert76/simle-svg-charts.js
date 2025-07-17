# simple-svg-charts.js - pretty time-series line graphs

This library provides a very simple API for drawing line, bar, area and donut charts in JS. It is based up on [morris.js06](https://github.com/pierresh/morris.js) which is based on the original [morris.js](https://github.com/morrisjs/morris.js). The original version was written in CoffeeScript and compiled to JavaScript. Because the original scripts used a very old
CoffeeScript syntax, which I didn't understand, I switched to develop the generated JavaScript. So I renamed the project from the original morris.js to simple-svg-charts.js to be more generic.

This library makes heavy use of [Raphael.js](https://github.com/DmitryBaranovskiy/raphael), which is a library for javascript based SVG object rendering. So, the simple-svg-charts library is much lightweight. 

Because of the small footprint the library can be used by newer and older browser. The browser only needs a useful SVG implementation. There is no JQuery or other dependency necessary.

# HowTo

To use this library, you need this 3 lines in your HTML file.

```
<html>
 <head>
  ...
   <link rel='stylesheet' href='simple-svg-charts.css'>
  ...
 </head>
 <body>
  ...
  <script src='raphael.min.js'></script>
  <script src='simple-svg-charts.js'></script>
 </body>
</html>
```

Now you need to define a HTML container, which is used to create the SVG chart, like

```
  ...
  <div id="example"></div>
  ...
```

Then, you need to define the chart itself


```
  ...
  <script>
    Morris.Line({
      element: 'example',
      data: [
        {year: '1958', nb: 1},
        {year: '1962', nb: 2},
        {year: '1970', nb: 3},
        {year: '1994', nb: 4},
        {year: '2002', nb: 5},
      ],
      xkey: 'year',
      ykeys: ['nb'],
      labels: ['Editions Wins']
    });
  </script>
  ...
```

Thats it. There are a lot of properties and options available. More can be found on the [Github Pages](https://trickert76.github.io/simple-svg-charts.js/).

# Examples

![examples](docs/examples.png)


# Installation

You can either download the latest version of simple-svg-charts.js here from the [GitHub releases](https://github.com/trickert76/simple-svg-charts.js/releases/latest).

Or as an alternative install it via npm:

```bash
npm install simple-svg-charts.js
```

# Requirements

- [Raphael.js](http://raphaeljs.com/) (>= 2.3)
- [Regression.js](https://github.com/Tom-Alexander/regression-js/releases/tag/1.4.0) (1.4.0) for trendline type polynomial, logarithmic, exponential
