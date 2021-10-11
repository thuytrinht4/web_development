# Plotly
## What is Plotly?
Plotly is a chart library, frequently used to build front end for M and data science model.

## Other Chart Libraries
There are many web chart libraries out there for all types of use cases. When choosing a library, you should consider checking whether or not the library is still being actively developed.

[d3.js](https://d3js.org/) is one of the most popular (and complex!) javascript data visualization libraries. This library is still actively being developed, which you can tell because the latest commit to the [d3 GitHub repository](https://github.com/d3/d3) is fairly recent.

Other options include [chart.js](https://www.chartjs.org/), [Google Charts](https://developers.google.com/chart/), and [nvd3.js](https://nvd3.org/), which is built on top of d3.js

## Why Plotly?
For this project, I've chosen plotly for a specific reason: [Plotly](https://plotly.com/), although a private company, provides open source libraries for both JavaScript and Python.

Because the web app we're developing will have a Python back-end, we can use the Python library to create your charts. Rather than having you learn more JavaScript syntax, we can use the Python syntax that we already know. However, we haven't built a back-end yet, so for now, we'll see the basics of how Plotly works using the JavaScript library. The syntax between the Python and Javascript versions is similar.

Later in the lesson, we'll switch to the Python version of the Plotly library so that we can prepare visualizations on the back-end of your web app. Yet we could write all the visualization code in JavaScript if we wanted to. Watch the screencast below to learn the basics of how Plotly works, and then continue on to the Plotly exercise.

Here are a few links to some helpful parts of the plotly documentation:
+ [javascript examples](https://plotly.com/javascript/)
+ [getting started](https://plotly.com/javascript/getting-started/)
+ [linking to the plotly library](https://plotly.com/javascript/getting-started/#plotlyjs-cdn)