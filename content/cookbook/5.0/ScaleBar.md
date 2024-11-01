---
Title: Scale Bar - ScottPlot 5.0 Cookbook
Description: Scalebars display a horizontal and/or vertical range using a line segment and may be used to convey axis scale as a minimal alternative to using axis frames, ticks, and tick labels.
URL: /cookbook/5.0/ScaleBar/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Scale Bar"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/ScaleBar"]
Date: 2024-10-30
Version: ScottPlot 5.0.42
Version: ScottPlot 5.0.42
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---

<h1>Scale Bar</h1>


<h2 style='border-bottom: 0;'><a href='/cookbook/5.0/ScaleBar/ScaleBarQuickstart'>ScaleBar Quickstart</a></h2>

<div class="d-flex mb-2">
<a class="btn btn-sm btn-primary me-1" href="/cookbook/5.0/ScaleBar/ScaleBarQuickstart">Recipe Permalink</a>
<a class="btn btn-sm btn-success me-1" href="/cookbook/5.0/ScaleBar">Category: Scale Bar</a>
</div>

A ScaleBar can be added to a plot to convey scale information allowing axis frames, ticks, and labels to be hidden.

[![](/cookbook/5.0/images/ScaleBarQuickstart.png?241029205813)](/cookbook/5.0/images/ScaleBarQuickstart.png?241029205813)

{{< recipe-sp5 >}}ScottPlot.Plot myPlot = new();

// plot sample data
myPlot.Add.Signal(Generate.Sin());
myPlot.Add.Signal(Generate.Cos());

// add a scale bar
myPlot.Add.ScaleBar(5, 0.25);

// disable the grid and axis labels
myPlot.HideGrid();
myPlot.Axes.Frameless();

myPlot.SavePng("demo.png", 400, 300);
{{< /recipe-sp5 >}}

<hr class='my-5 invisible'>



<h2 style='border-bottom: 0;'><a href='/cookbook/5.0/ScaleBar/ScaleBarLabels'>ScaleBar Labels</a></h2>

<div class="d-flex mb-2">
<a class="btn btn-sm btn-primary me-1" href="/cookbook/5.0/ScaleBar/ScaleBarLabels">Recipe Permalink</a>
<a class="btn btn-sm btn-success me-1" href="/cookbook/5.0/ScaleBar">Category: Scale Bar</a>
</div>

Text may be added to each dimension of an L shaped scalebar

[![](/cookbook/5.0/images/ScaleBarLabels.png?241029205813)](/cookbook/5.0/images/ScaleBarLabels.png?241029205813)

{{< recipe-sp5 >}}ScottPlot.Plot myPlot = new();

// plot sample data
myPlot.Add.Signal(Generate.Sin());
myPlot.Add.Signal(Generate.Cos());

// add a scale bar
var scalebar = myPlot.Add.ScaleBar(5, 0.25);
scalebar.XLabel = "5 mV";
scalebar.YLabel = "1 µF";

// disable the grid and axis labels
myPlot.HideGrid();
myPlot.Axes.Frameless();

myPlot.SavePng("demo.png", 400, 300);
{{< /recipe-sp5 >}}

<hr class='my-5 invisible'>



<h2 style='border-bottom: 0;'><a href='/cookbook/5.0/ScaleBar/ScaleBarStyling'>ScaleBar Styling</a></h2>

<div class="d-flex mb-2">
<a class="btn btn-sm btn-primary me-1" href="/cookbook/5.0/ScaleBar/ScaleBarStyling">Recipe Permalink</a>
<a class="btn btn-sm btn-success me-1" href="/cookbook/5.0/ScaleBar">Category: Scale Bar</a>
</div>

The ScaleBar has many properties which may be customized 

[![](/cookbook/5.0/images/ScaleBarStyling.png?241029205813)](/cookbook/5.0/images/ScaleBarStyling.png?241029205813)

{{< recipe-sp5 >}}ScottPlot.Plot myPlot = new();

// plot sample data
myPlot.Add.Signal(Generate.Sin());
myPlot.Add.Signal(Generate.Cos());

// add a scale bar
var scalebar = myPlot.Add.ScaleBar(5, 0.25);
scalebar.LineWidth = 5;
scalebar.LineColor = Colors.Magenta;

// disable the grid and axis labels
myPlot.HideGrid();
myPlot.Axes.Frameless();

myPlot.SavePng("demo.png", 400, 300);
{{< /recipe-sp5 >}}

<hr class='my-5 invisible'>



<h2 style='border-bottom: 0;'><a href='/cookbook/5.0/ScaleBar/ScaleBarSingleDimension'>ScaleBar Single Dimension</a></h2>

<div class="d-flex mb-2">
<a class="btn btn-sm btn-primary me-1" href="/cookbook/5.0/ScaleBar/ScaleBarSingleDimension">Recipe Permalink</a>
<a class="btn btn-sm btn-success me-1" href="/cookbook/5.0/ScaleBar">Category: Scale Bar</a>
</div>

Set Width or Height to 0 to cause the ScaleBar to use a single axis only

[![](/cookbook/5.0/images/ScaleBarSingleDimension.png?241029205813)](/cookbook/5.0/images/ScaleBarSingleDimension.png?241029205813)

{{< recipe-sp5 >}}ScottPlot.Plot myPlot = new();

// plot sample data
myPlot.Add.Signal(Generate.Sin());
myPlot.Add.Signal(Generate.Cos());

// add a scale bar
var scalebar = myPlot.Add.ScaleBar(7, 0);
scalebar.LineWidth = 2;
scalebar.XLabel = "70 ms";
scalebar.XLabelStyle.Bold = true;
scalebar.LabelPadding = new(0);

// disable the grid and axis labels
myPlot.HideGrid();
myPlot.Axes.Frameless();

myPlot.SavePng("demo.png", 400, 300);
{{< /recipe-sp5 >}}

<hr class='my-5 invisible'>


