---
Title: Grid Fill Colors - ScottPlot 5.0 Cookbook
Description: Regions between alternating pairs of major grid lines may be filled with a color specified by the user
URL: /cookbook/5.0/CustomizingGrids/GridAlternatingColors/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Customizing Grids", "Grid Fill Colors"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/CustomizingGrids", "/cookbook/5.0/CustomizingGrids/GridAlternatingColors"]
Date: 2024-09-02
Version: ScottPlot 5.0.38
Version: ScottPlot 5.0.38
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---

# Grid Fill Colors


Regions between alternating pairs of major grid lines may be filled with a color specified by the user

[![](/cookbook/5.0/images/GridAlternatingColors.png?240902145058)](/cookbook/5.0/images/GridAlternatingColors.png?240902145058)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

myPlot.Add.Signal(Generate.Sin());
myPlot.Add.Signal(Generate.Cos());

// shade regions between major grid lines
myPlot.Grid.XAxisStyle.FillColor1 = Colors.Gray.WithOpacity(0.1);
myPlot.Grid.XAxisStyle.FillColor2 = Colors.Gray.WithOpacity(0.2);
myPlot.Grid.YAxisStyle.FillColor1 = Colors.Gray.WithOpacity(0.1);
myPlot.Grid.YAxisStyle.FillColor2 = Colors.Gray.WithOpacity(0.2);

// show minor grid lines too
myPlot.Grid.XAxisStyle.MinorLineStyle.Width = 1;
myPlot.Grid.YAxisStyle.MinorLineStyle.Width = 1;

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<a href='https://github.com/ScottPlot/ScottPlot/blob/main/src/ScottPlot5/ScottPlot5%20Cookbook/Recipes/Axis/CustomizingGrids.cs'><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="mb-1 bi bi-github" viewBox="0 0 16 16">
  <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/>
</svg> Edit on GitHub</a>
