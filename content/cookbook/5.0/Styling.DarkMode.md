---
Title: Dark Mode - ScottPlot 5.0 Cookbook
Description: Plots can be created using dark mode by setting the colors of major plot components to ones consistent with a dark theme.
URL: /cookbook/5.0/Styling/DarkMode/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Styling Plots", "Dark Mode"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/Styling", "/cookbook/5.0/Styling/DarkMode"]
Date: 2024-09-02
Version: ScottPlot 5.0.38
Version: ScottPlot 5.0.38
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---

# Dark Mode


Plots can be created using dark mode by setting the colors of major plot components to ones consistent with a dark theme.

[![](/cookbook/5.0/images/DarkMode.png?240902145058)](/cookbook/5.0/images/DarkMode.png?240902145058)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

// set the color palette used when coloring new items added to the plot
myPlot.Add.Palette = new ScottPlot.Palettes.Penumbra();

// add things to the plot
for (int i = 0; i < 5; i++)
{
    var sig = myPlot.Add.Signal(Generate.Sin(51, phase: -.05 * i));
    sig.LineWidth = 3;
    sig.LegendText = $"Line {i + 1}";
}
myPlot.XLabel("Horizontal Axis");
myPlot.YLabel("Vertical Axis");
myPlot.Title("ScottPlot 5 in Dark Mode");
myPlot.ShowLegend();

// change figure colors
myPlot.FigureBackground.Color = Color.FromHex("#181818");
myPlot.DataBackground.Color = Color.FromHex("#1f1f1f");

// change axis and grid colors
myPlot.Axes.Color(Color.FromHex("#d7d7d7"));
myPlot.Grid.MajorLineColor = Color.FromHex("#404040");

// change legend colors
myPlot.Legend.BackgroundColor = Color.FromHex("#404040");
myPlot.Legend.FontColor = Color.FromHex("#d7d7d7");
myPlot.Legend.OutlineColor = Color.FromHex("#d7d7d7");

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<a href='https://github.com/ScottPlot/ScottPlot/blob/main/src/ScottPlot5/ScottPlot5%20Cookbook/Recipes/Introduction/Styling.cs'><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="mb-1 bi bi-github" viewBox="0 0 16 16">
  <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/>
</svg> Edit on GitHub</a>

