---
Title: Axis Line Label - ScottPlot 5.0 Cookbook
Description: Axis lines have labels that can be used to display arbitrary text on the axes they are attached to.
URL: /cookbook/5.0/AxisLines/AxisLineLabel/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Axis Lines", "Axis Line Label"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/AxisLines", "/cookbook/5.0/AxisLines/AxisLineLabel"]
Date: 2024-10-30
Version: ScottPlot 5.0.42
Version: ScottPlot 5.0.42
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---


<h2 style='border-bottom: 0;'><a href='/cookbook/5.0/AxisLines/AxisLineLabel'>Axis Line Label</a></h2>

<div class="d-flex mb-2">
<a class="btn btn-sm btn-primary me-1" href="/cookbook/5.0/AxisLines/AxisLineLabel">Recipe Permalink</a>
<a class="btn btn-sm btn-success me-1" href="/cookbook/5.0/AxisLines">Category: Axis Lines</a>
</div>

Axis lines have labels that can be used to display arbitrary text on the axes they are attached to.

[![](/cookbook/5.0/images/AxisLineLabel.png?241029205813)](/cookbook/5.0/images/AxisLineLabel.png?241029205813)

{{< recipe-sp5 >}}ScottPlot.Plot myPlot = new();

myPlot.Add.Signal(Generate.Sin());
myPlot.Add.Signal(Generate.Cos());

// by default labels are drawn on the same side as the axis label

var axLine1 = myPlot.Add.VerticalLine(24);
axLine1.Text = "Line 1";

var axLine2 = myPlot.Add.HorizontalLine(0.75);
axLine2.Text = "Line 2";

// labels may be drawn on the side opposite of the axis label

var axLine3 = myPlot.Add.VerticalLine(37);
axLine3.Text = "Line 3";
axLine3.LabelOppositeAxis = true;

var axLine4 = myPlot.Add.HorizontalLine(-.75);
axLine4.Text = "Line 4";
axLine4.LabelOppositeAxis = true;

// extra padding on the right and top ensures labels have room
myPlot.Axes.Right.MinimumSize = 30;
myPlot.Axes.Top.MinimumSize = 30;

myPlot.SavePng("demo.png", 400, 300);
{{< /recipe-sp5 >}}

<hr class='my-5 invisible'>


