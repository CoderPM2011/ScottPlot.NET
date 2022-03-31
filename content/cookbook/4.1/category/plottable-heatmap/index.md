---
Title: Heatmap - ScottPlot 4.1 Cookbook
Description: Plottable - Heatmap recipes
Source: https://github.com/ScottPlot/ScottPlot/tree/master/src/cookbook
---

## Heatmap Quickstart

Heatmaps display a 2D array using a colormap.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] data2D = { { 1, 2, 3 },
         { 4, 5, 6 } };

plt.SaveFig("heatmap_quickstart.png");
```

<div class='text-center'>
<a href='../../images/heatmap_quickstart.png'><img src='../../images/heatmap_quickstart.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Heatmap with Tight Margins

The heatmap can fit the plot area exactly if margins are set to zero and the square axis lock is disabled.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] data2D = { { 1, 2, 3 },
         { 4, 5, 6 } };

plt.AddHeatmap(data2D, lockScales: false);
plt.Margins(0, 0);

plt.SaveFig("heatmap_margins.png");
```

<div class='text-center'>
<a href='../../images/heatmap_margins.png'><img src='../../images/heatmap_margins.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Heatmap with Colorbar

Colorbars are often added when heatmaps are used.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] data2D = { { 1, 2, 3 },
         { 4, 5, 6 } };

var hm = plt.AddHeatmap(data2D, lockScales: false);
var cb = plt.AddColorbar(hm);
plt.Margins(0, 0);

plt.SaveFig("heatmap_colorbar.png");
```

<div class='text-center'>
<a href='../../images/heatmap_colorbar.png'><img src='../../images/heatmap_colorbar.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Smooth Heatmap

Heatmaps display values as rectangles with sharp borders by default. Enabling the Smooth feature uses bicubic interpolation to display the heatmap as a smooth gradient between values.

```cs
var plt = new ScottPlot.Plot(600, 400);

var rand = new Random(0);
double[,] data2D = DataGen.Random2D(rand, 5, 4);

var hm = plt.AddHeatmap(data2D, lockScales: false);
hm.Smooth = true;

plt.SaveFig("heatmap_smooth.png");
```

<div class='text-center'>
<a href='../../images/heatmap_smooth.png'><img src='../../images/heatmap_smooth.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Heatmap Image

Image data can be plotted using the heatmap plot type.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] imageData = DataGen.SampleImageData();
plt.AddHeatmap(imageData);

plt.SaveFig("heatmap_image.png");
```

<div class='text-center'>
<a href='../../images/heatmap_image.png'><img src='../../images/heatmap_image.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## 2D Waveform

This example demonstrates a heatmap with 1000 tiles

```cs
var plt = new ScottPlot.Plot(600, 400);

int width = 100;
int height = 100;

double[,] intensities = new double[width, height];

for (int x = 0; x < width; x++)
    for (int y = 0; y < height; y++)
        intensities[x, y] = (Math.Sin(x * .2) + Math.Cos(y * .2)) * 100;

var hm = plt.AddHeatmap(intensities);
var cb = plt.AddColorbar(hm);

plt.SaveFig("heatmap_2dWaveform.png");
```

<div class='text-center'>
<a href='../../images/heatmap_2dwaveform.png'><img src='../../images/heatmap_2dwaveform.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Colormap

Viridis is the default colormap, but several alternatives are available.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] intensities = new double[100, 100];
for (int x = 0; x < 100; x++)
    for (int y = 0; y < 100; y++)
        intensities[x, y] = (Math.Sin(x * .2) + Math.Cos(y * .2)) * 100;

var hm = plt.AddHeatmap(intensities, Drawing.Colormap.Turbo);
var cb = plt.AddColorbar(hm);

plt.SaveFig("heatmap_colormap.png");
```

<div class='text-center'>
<a href='../../images/heatmap_colormap.png'><img src='../../images/heatmap_colormap.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Styled Colormap

Viridis is the default colormap, but several alternatives are available.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] intensities = new double[100, 100];
for (int x = 0; x < 100; x++)
    for (int y = 0; y < 100; y++)
        intensities[x, y] = (Math.Sin(x * .2) + Math.Cos(y * .2)) * 100;

var hm = plt.AddHeatmap(intensities, Drawing.Colormap.Turbo);
var cb = plt.AddColorbar(hm);

plt.Style(Style.Black);

plt.SaveFig("styled_heatmap_colormap.png");
```

<div class='text-center'>
<a href='../../images/styled_heatmap_colormap.png'><img src='../../images/styled_heatmap_colormap.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Scale Limits

Heatmap colormap scale can use a defined min/max value.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] intensities = new double[100, 100];
for (int x = 0; x < 100; x++)
    for (int y = 0; y < 100; y++)
        intensities[x, y] = (Math.Sin(x * .2) + Math.Cos(y * .2)) * 100;

// scale the colors between 0 and 200
var hm = plt.AddHeatmap(intensities);
hm.Update(intensities, min: 0, max: 200);

// add a colorbar with custom ticks
var cb = plt.AddColorbar(hm);
double[] tickPositions = ScottPlot.DataGen.Range(0, 200, 25, true);
string[] tickLabels = tickPositions.Select(x => x.ToString()).ToArray();
cb.SetTicks(tickPositions, tickLabels, min: 0, max: 200);

plt.SaveFig("heatmap_limitScale.png");
```

<div class='text-center'>
<a href='../../images/heatmap_limitscale.png'><img src='../../images/heatmap_limitscale.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Color Clipping

The value range displayed by the colormap can restricted to a narrow subset of the full data range. Tick labels at the edges of the colorbar can be made to show inequality symbols to indicate the range of data is being clipped when translating values to colors.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] imageData = DataGen.SampleImageData();
var heatmap = plt.AddHeatmap(imageData);
heatmap.Update(imageData, min: 75, max: 125);

var cb = plt.AddColorbar(heatmap);

// configure the colorbar to display inequality operators at the edges
cb.MaxIsClipped = true;
cb.MinIsClipped = true;

plt.SaveFig("heatmap_clip.png");
```

<div class='text-center'>
<a href='../../images/heatmap_clip.png'><img src='../../images/heatmap_clip.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Interpolation by Density

Heatmaps can be created from random 2D data points using the count within a square of fixed size.

```cs
var plt = new ScottPlot.Plot(600, 400);

Random rand = new Random(0);
int[] xs = DataGen.RandomNormal(rand, 10000, 25, 10).Select(x => (int)x).ToArray();
int[] ys = DataGen.RandomNormal(rand, 10000, 25, 10).Select(y => (int)y).ToArray();

double[,] intensities = Tools.XYToIntensities(mode: IntensityMode.Density,
    xs: xs, ys: ys, width: 50, height: 50, sampleWidth: 4);

var hm = plt.AddHeatmap(intensities);
var cb = plt.AddColorbar(hm);

plt.SaveFig("heatmap_density.png");
```

<div class='text-center'>
<a href='../../images/heatmap_density.png'><img src='../../images/heatmap_density.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Gaussian Interpolation

Heatmaps can be created from 2D data points using bilinear interpolation with Gaussian weighting. This option results in a heatmap with a standard deviation of 4.

```cs
var plt = new ScottPlot.Plot(600, 400);

Random rand = new Random(0);
int[] xs = DataGen.RandomNormal(rand, 10000, 25, 10).Select(x => (int)x).ToArray();
int[] ys = DataGen.RandomNormal(rand, 10000, 25, 10).Select(y => (int)y).ToArray();

double[,] intensities = Tools.XYToIntensities(mode: IntensityMode.Gaussian,
    xs: xs, ys: ys, width: 50, height: 50, sampleWidth: 4);

var hm = plt.AddHeatmap(intensities);
var cb = plt.AddColorbar(hm);

plt.SaveFig("heatmap_gaussian.png");
```

<div class='text-center'>
<a href='../../images/heatmap_gaussian.png'><img src='../../images/heatmap_gaussian.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Custom Dimensions

By default heatmaps start at the origin and each rectangle (cell) is 1 unit in size, but heatmap offset and cell size can be customized.

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] data2D = { { 1, 2, 3 },
         { 4, 5, 6 } };

var hm = plt.AddHeatmap(data2D, lockScales: false);
hm.OffsetX = 10;
hm.OffsetY = 20;
hm.CellWidth = 5;
hm.CellHeight = 10;

plt.SaveFig("heatmap_dimensions.png");
```

<div class='text-center'>
<a href='../../images/heatmap_dimensions.png'><img src='../../images/heatmap_dimensions.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Heatmap with Empty Squares

You can use a 2D array of nullable doubles to indicate some squares do not contain data. This allows the user to display heatmaps with transparency and implement non-rectangular heatmaps.

```cs
var plt = new ScottPlot.Plot(600, 400);

double?[,] intensities = {
    { 1, 7, 4, null },
    { 9, null, 2, 4 },
    { 1, 4, null, 8 },
    { null, 2, 4, null }
};

var hmc = plt.AddHeatmap(intensities);
var cb = plt.AddColorbar(hmc);

plt.SaveFig("heatmap_transparent.png");
```

<div class='text-center'>
<a href='../../images/heatmap_transparent.png'><img src='../../images/heatmap_transparent.png' /></a>
</div>


<div class='m-2'>&nbsp;</div>

## Size and Placement

Edges of the heatmap can be defined as an alternative to defining offset and cell size,

```cs
var plt = new ScottPlot.Plot(600, 400);

double[,] imageData = DataGen.SampleImageData();
var hm = plt.AddHeatmap(imageData, lockScales: false);

hm.XMin = -100;
hm.XMax = 100;
hm.YMin = -10;
hm.YMax = 10;

plt.SaveFig("heatmap_placement.png");
```

<div class='text-center'>
<a href='../../images/heatmap_placement.png'><img src='../../images/heatmap_placement.png' /></a>
</div>
