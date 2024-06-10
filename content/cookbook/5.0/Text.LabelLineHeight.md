---
Title: Line Height - ScottPlot 5.0 Cookbook
Description: Multiline labels have a default line height estimated from the typeface and font size, however line height may be manually defined by the user.
URL: /cookbook/5.0/Text/LabelLineHeight/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Text", "Line Height"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/Text", "/cookbook/5.0/Text/LabelLineHeight"]
Date: 2024-06-10
Version: ScottPlot 5.0.35
Version: ScottPlot 5.0.35
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---

# Line Height


Multiline labels have a default line height estimated from the typeface and font size, however line height may be manually defined by the user.

[![](/cookbook/5.0/images/LabelLineHeight.png?240610190353)](/cookbook/5.0/images/LabelLineHeight.png?240610190353)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

var label1 = myPlot.Add.Text($"line\nheight", 0, 0);
label1.LabelLineSpacing = 0;
label1.LabelFontColor = Colors.Red;
label1.LabelBorderColor = Colors.Black;

var label2 = myPlot.Add.Text($"can\nbe", 1, 0);
label2.LabelLineSpacing = 10;
label2.LabelFontColor = Colors.Orange;
label2.LabelBorderColor = Colors.Black;

var label3 = myPlot.Add.Text($"automatic\nor", 2, 0);
label3.LabelLineSpacing = null;
label3.LabelFontColor = Colors.Green;
label3.LabelBorderColor = Colors.Black;

var label4 = myPlot.Add.Text($"set\nmanually", 3, 0);
label4.LabelLineSpacing = 15;
label4.LabelFontColor = Colors.Blue;
label4.LabelBorderColor = Colors.Black;

myPlot.HideGrid();
myPlot.Axes.SetLimitsX(-.5, 4);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<a href='https://github.com/ScottPlot/ScottPlot/blob/main/src/ScottPlot5/ScottPlot5%20Cookbook/Recipes/PlotTypes/Text.cs'><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="mb-1 bi bi-github" viewBox="0 0 16 16">
  <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/>
</svg> Edit on GitHub</a>

