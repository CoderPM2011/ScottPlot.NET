---
Title: Scatter Plot Styling - ScottPlot 5.0 Cookbook
Description: Scatter plots can be extensively styled by interacting with the object that is returned after a scatter plot is added. Assign text to a scatter plot's Label property to allow it to appear in the legend.
URL: /cookbook/5.0/Scatter/ScatterStyling/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Scatter Plot", "Scatter Plot Styling"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/Scatter", "/cookbook/5.0/Scatter/ScatterStyling"]
Date: 2024-10-30
Version: ScottPlot 5.0.42
Version: ScottPlot 5.0.42
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---


<h2 style='border-bottom: 0;'><a href='/cookbook/5.0/Scatter/ScatterStyling'>Scatter Plot Styling</a></h2>

<div class="d-flex mb-2">
<a class="btn btn-sm btn-primary me-1" href="/cookbook/5.0/Scatter/ScatterStyling">Recipe Permalink</a>
<a class="btn btn-sm btn-success me-1" href="/cookbook/5.0/Scatter">Category: Scatter Plot</a>
</div>

Scatter plots can be extensively styled by interacting with the object that is returned after a scatter plot is added. Assign text to a scatter plot's Label property to allow it to appear in the legend.

[![](/cookbook/5.0/images/ScatterStyling.png?241029205813)](/cookbook/5.0/images/ScatterStyling.png?241029205813)

{{< recipe-sp5 >}}ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] ys1 = Generate.Sin(51);
double[] ys2 = Generate.Cos(51);

var sp1 = myPlot.Add.Scatter(xs, ys1);
sp1.LegendText = "Sine";
sp1.LineWidth = 3;
sp1.Color = Colors.Magenta;
sp1.MarkerSize = 15;

var sp2 = myPlot.Add.Scatter(xs, ys2);
sp2.LegendText = "Cosine";
sp2.LineWidth = 2;
sp2.Color = Colors.Green;
sp2.MarkerSize = 10;

myPlot.ShowLegend();

myPlot.SavePng("demo.png", 400, 300);
{{< /recipe-sp5 >}}

<hr class='my-5 invisible'>


