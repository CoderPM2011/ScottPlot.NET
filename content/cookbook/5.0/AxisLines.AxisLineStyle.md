---
Title: Axis Line Style - ScottPlot 5.0 Cookbook
Description: Axis lines have extensive customization options.
URL: /cookbook/5.0/AxisLines/AxisLineStyle/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Axis Lines", "Axis Line Style"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/AxisLines", "/cookbook/5.0/AxisLines/AxisLineStyle"]
Date: 2024-10-28
Version: ScottPlot 5.0.41
Version: ScottPlot 5.0.41
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---

# Axis Line Style


Axis lines have extensive customization options.

[![](/cookbook/5.0/images/AxisLineStyle.png?241027221943)](/cookbook/5.0/images/AxisLineStyle.png?241027221943)

{{< recipe-sp5 >}}ScottPlot.Plot myPlot = new();

myPlot.Add.Signal(Generate.Sin());
myPlot.Add.Signal(Generate.Cos());

var vl1 = myPlot.Add.VerticalLine(24);
vl1.LineWidth = 3;
vl1.Color = Colors.Magenta;

var hl1 = myPlot.Add.HorizontalLine(0.75);
hl1.LineWidth = 2;
hl1.Color = Colors.Green;
hl1.LinePattern = LinePattern.Dashed;

var hl2 = myPlot.Add.HorizontalLine(-.23);
hl2.LineColor = Colors.Navy;
hl2.LineWidth = 5;
hl2.Text = "Hello";
hl2.LabelFontSize = 24;
hl2.LabelBackgroundColor = Colors.Blue;
hl2.LabelFontColor = Colors.Yellow;
hl2.LinePattern = LinePattern.DenselyDashed;

myPlot.SavePng("demo.png", 400, 300);
{{< /recipe-sp5 >}}

<a href='https://github.com/ScottPlot/ScottPlot/blob/main/src/ScottPlot5/ScottPlot5%20Cookbook/Recipes/PlotTypes/AxisLines.cs'><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="mb-1 bi bi-github" viewBox="0 0 16 16">
  <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/>
</svg> Edit on GitHub</a>

