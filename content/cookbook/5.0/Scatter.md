---
Title: Scatter Plot - ScottPlot 5.0 Cookbook
Description: Scatter plots display points at X/Y locations in coordinate space.
URL: /cookbook/5.0/Scatter/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Scatter Plot"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/Scatter"]
Date: 2024-07-30
Version: ScottPlot 5.0.37
Version: ScottPlot 5.0.37
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---

# Scatter Plot


<h2><a href='/cookbook/5.0/Scatter/ScatterQuickstart'>Scatter Plot Quickstart</a></h2>

Scatter plots can be created from two arrays containing X and Y values.

[![](/cookbook/5.0/images/ScatterQuickstart.png?240729212327)](/cookbook/5.0/images/ScatterQuickstart.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = { 1, 2, 3, 4, 5 };
double[] ys = { 1, 4, 9, 16, 25 };

myPlot.Add.Scatter(xs, ys);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterCoordinates'>Scatter Plot Coordinates</a></h2>

Scatter plots can be created from a collection of Coordinates.

[![](/cookbook/5.0/images/ScatterCoordinates.png?240729212327)](/cookbook/5.0/images/ScatterCoordinates.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

Coordinates[] coordinates =
{
    new(1, 1),
    new(2, 4),
    new(3, 9),
    new(4, 16),
    new(5, 25),
};

myPlot.Add.Scatter(coordinates);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterDataType'>Scatter Plot Data Type</a></h2>

Scatter plots can be created from any numeric data type, not just double.

[![](/cookbook/5.0/images/ScatterDataType.png?240729212327)](/cookbook/5.0/images/ScatterDataType.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

float[] xs = { 1, 2, 3, 4, 5 };
int[] ys = { 1, 4, 9, 16, 25 };

myPlot.Add.Scatter(xs, ys);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterList'>Scatter Plot of List Data</a></h2>

Scatter plots can be created from Lists, but be very cafeful not to add or remove items while a render is occurring or you may throw an index exception. See documentation about the Render Lock system for details.

[![](/cookbook/5.0/images/ScatterList.png?240729212327)](/cookbook/5.0/images/ScatterList.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

List<double> xs = new() { 1, 2, 3, 4, 5 };
List<double> ys = new() { 1, 4, 9, 16, 25 };

myPlot.Add.Scatter(xs, ys);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterLine'>Scatter Plot with Lines Only</a></h2>

The `ScatterLine()` method can be used to create a scatter plot with a line only (marker size is set to 0).

[![](/cookbook/5.0/images/ScatterLine.png?240729212327)](/cookbook/5.0/images/ScatterLine.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] sin = Generate.Sin(51);
double[] cos = Generate.Cos(51);

myPlot.Add.ScatterLine(xs, sin);
myPlot.Add.ScatterLine(xs, cos);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterPoints'>Scatter Plot with Points Only</a></h2>

The `ScatterPoints()` method can be used to create a scatter plot with markers only (line width is set to 0).

[![](/cookbook/5.0/images/ScatterPoints.png?240729212327)](/cookbook/5.0/images/ScatterPoints.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] sin = Generate.Sin(51);
double[] cos = Generate.Cos(51);

myPlot.Add.ScatterPoints(xs, sin);
myPlot.Add.ScatterPoints(xs, cos);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterStyling'>Scatter Plot Styling</a></h2>

Scatter plots can be extensively styled by interacting with the object that is returned after a scatter plot is added. Assign text to a scatter plot's Label property to allow it to appear in the legend.

[![](/cookbook/5.0/images/ScatterStyling.png?240729212327)](/cookbook/5.0/images/ScatterStyling.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

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

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterLinePatterns'>Scatter Line Patterns</a></h2>

Several line patterns are available

[![](/cookbook/5.0/images/ScatterLinePatterns.png?240729212327)](/cookbook/5.0/images/ScatterLinePatterns.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

LinePattern[] patterns = Enum.GetValues<LinePattern>();
ScottPlot.Palettes.ColorblindFriendly palette = new();

for (int i = 0; i < patterns.Length; i++)
{
    double yOffset = patterns.Length - i;
    double[] xs = Generate.Consecutive(51);
    double[] ys = Generate.Sin(51, offset: yOffset);

    var sp = myPlot.Add.Scatter(xs, ys);
    sp.LineWidth = 2;
    sp.MarkerSize = 0;
    sp.LinePattern = patterns[i];
    sp.Color = palette.GetColor(i);

    var txt = myPlot.Add.Text(patterns[i].ToString(), 51, yOffset);
    txt.LabelFontColor = sp.Color;
    txt.LabelFontSize = 22;
    txt.LabelBold = true;
    txt.LabelAlignment = Alignment.MiddleLeft;
}

myPlot.Axes.Margins(.05, .5, .05, .05);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterGeneric'>Scatter Generic</a></h2>

Scatter plots support generic data types, although double is typically the most performant.

[![](/cookbook/5.0/images/ScatterGeneric.png?240729212327)](/cookbook/5.0/images/ScatterGeneric.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

int[] xs = { 1, 2, 3, 4, 5 };
float[] ys = { 1, 4, 9, 16, 25 };

myPlot.Add.Scatter(xs, ys);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterDateTime'>Scatter DateTime</a></h2>

A scatter plot may use DateTime units but be sure to setup the respective axis to display using DateTime format.

[![](/cookbook/5.0/images/ScatterDateTime.png?240729212327)](/cookbook/5.0/images/ScatterDateTime.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

DateTime[] xs = Generate.ConsecutiveDays(100);
double[] ys = Generate.RandomWalk(xs.Length);

myPlot.Add.Scatter(xs, ys);
myPlot.Axes.DateTimeTicksBottom();

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterStep'>Step Plot</a></h2>

Scatter plots can be created using a step plot display where points are connected with right angles instead of diagnal lines. The direction of the steps can be customized.

[![](/cookbook/5.0/images/ScatterStep.png?240729212327)](/cookbook/5.0/images/ScatterStep.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(20);
double[] ys1 = Generate.Consecutive(20, first: 10);
double[] ys2 = Generate.Consecutive(20, first: 5);
double[] ys3 = Generate.Consecutive(20, first: 0);

var sp1 = myPlot.Add.Scatter(xs, ys1);
sp1.ConnectStyle = ConnectStyle.Straight;
sp1.LegendText = "Straight";

var sp2 = myPlot.Add.Scatter(xs, ys2);
sp2.ConnectStyle = ConnectStyle.StepHorizontal;
sp2.LegendText = "StepHorizontal";

var sp3 = myPlot.Add.Scatter(xs, ys3);
sp3.ConnectStyle = ConnectStyle.StepVertical;
sp3.LegendText = "StepVertical";

myPlot.ShowLegend();

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterWithGaps'>Scatter with Gaps</a></h2>

NaN values in a scatter plot's data will appear as gaps in the line.

[![](/cookbook/5.0/images/ScatterWithGaps.png?240729212327)](/cookbook/5.0/images/ScatterWithGaps.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] ys = Generate.Sin(51);

// long stretch of empty data
for (int i = 10; i < 20; i++)
    ys[i] = double.NaN;

// single missing data point
ys[30] = double.NaN;

// single floating data point
for (int i = 35; i < 40; i++)
    ys[i] = double.NaN;
for (int i = 40; i < 45; i++)
    ys[i] = double.NaN;

myPlot.Add.Scatter(xs, ys);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterSmooth'>Scatter Plot with Smooth Lines</a></h2>

Scatter plots draw straight lines between points by default, but setting the Smooth property allows the scatter plot to connect points with smooth lines. Lines are smoothed using cubic spline interpolation.

[![](/cookbook/5.0/images/ScatterSmooth.png?240729212327)](/cookbook/5.0/images/ScatterSmooth.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(10);
double[] ys = Generate.RandomSample(10, 5, 15);

var sp = myPlot.Add.Scatter(xs, ys);
sp.Smooth = true;
sp.LegendText = "Smooth";
sp.LineWidth = 2;
sp.MarkerSize = 10;

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterSmoothTension'>Smooth Line Tension</a></h2>

Tension of smooth lines can be adjusted for some smoothing strategies. Low tensions lead to 'overshoot' and high tensions produce curveswhich appear more like straight lines.

[![](/cookbook/5.0/images/ScatterSmoothTension.png?240729212327)](/cookbook/5.0/images/ScatterSmoothTension.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.RandomWalk(10);
double[] ys = Generate.RandomWalk(10);

var mk = myPlot.Add.Markers(xs, ys);
mk.MarkerShape = MarkerShape.OpenCircle;
mk.Color = Colors.Black;

double[] tensions = { 0.3, 0.5, 1.0, 3.0 };

foreach (double tension in tensions)
{
    var sp = myPlot.Add.ScatterLine(xs, ys);
    sp.Smooth = true;
    sp.SmoothTension = tension;
    sp.LegendText = $"Tension {tension}";
    sp.LineWidth = 2;
}

myPlot.ShowLegend(Alignment.UpperLeft);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterQuad'>Smooth Scatter without Overshoot</a></h2>

The quadratic half point path strategy allows scatter plots to be displayed with smooth lines connecting points, but lines are eased in and out of points so they never 'overshoot' the values vertically.

[![](/cookbook/5.0/images/ScatterQuad.png?240729212327)](/cookbook/5.0/images/ScatterQuad.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(10);
double[] ys = Generate.RandomSample(10, 5, 15);

var sp = myPlot.Add.Scatter(xs, ys);
sp.PathStrategy = new ScottPlot.PathStrategies.QuadHalfPoint();
sp.LegendText = "Smooth";
sp.LineWidth = 2;
sp.MarkerSize = 10;

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterLimitIndex'>Limiting Display with Render Indexes</a></h2>

Although a scatter plot may contain a very large amount of data, much of it may be unpopulated. The user can define min and max render indexes, and only values within that range will be displayed when the scatter plot is rendered.

[![](/cookbook/5.0/images/ScatterLimitIndex.png?240729212327)](/cookbook/5.0/images/ScatterLimitIndex.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] ys = Generate.Sin(51);

var sp = myPlot.Add.Scatter(xs, ys);
sp.MinRenderIndex = 10;
sp.MaxRenderIndex = 40;

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterFill'>Scatter Plot with Fill</a></h2>

The area beneath a scatter plot can be filled.

[![](/cookbook/5.0/images/ScatterFill.png?240729212327)](/cookbook/5.0/images/ScatterFill.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] ys = Generate.Sin(51);

var sp = myPlot.Add.Scatter(xs, ys);
sp.FillY = true;
sp.FillYColor = sp.Color.WithAlpha(.2);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterFillValue'>Scatter Plot Filled to a Value</a></h2>

The base of the fill can be defined.

[![](/cookbook/5.0/images/ScatterFillValue.png?240729212327)](/cookbook/5.0/images/ScatterFillValue.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] ys = Generate.Sin(51);

var sp = myPlot.Add.Scatter(xs, ys);
sp.FillY = true;
sp.FillYColor = sp.Color.WithAlpha(.2);
sp.FillYValue = 0.6;

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterFillAboveBelow'>Scatter Plot Filled Above and Below</a></h2>

Filled areas above and below the FillY value can be individually customized

[![](/cookbook/5.0/images/ScatterFillAboveBelow.png?240729212327)](/cookbook/5.0/images/ScatterFillAboveBelow.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] ys = Generate.Sin(51);

var sp = myPlot.Add.Scatter(xs, ys);
sp.FillY = true;
sp.FillYValue = 0;
sp.FillYAboveColor = Colors.Green.WithAlpha(.2);
sp.FillYBelowColor = Colors.Red.WithAlpha(.2);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterFillGradient'>Scatter Plot with Gradient Fill</a></h2>

The area beneath a scatter plot can be filled with a custom gradient of colors.

[![](/cookbook/5.0/images/ScatterFillGradient.png?240729212327)](/cookbook/5.0/images/ScatterFillGradient.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] ys = Generate.Sin(51);

var poly = myPlot.Add.ScatterLine(xs, ys);

poly.FillY = true;
poly.ColorPositions.Add(new(Colors.Red, 0));
poly.ColorPositions.Add(new(Colors.Orange, 10));
poly.ColorPositions.Add(new(Colors.Yellow, 20));
poly.ColorPositions.Add(new(Colors.Green, 30));
poly.ColorPositions.Add(new(Colors.Blue, 40));
poly.ColorPositions.Add(new(Colors.Violet, 50));

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/ScatterScaleAndOffset'>Scatter Scale and Offset</a></h2>

Scatter plot points can be multiplied by custom X and Y scale factors, or shifted horizontally or vertically using X and Y offset values.

[![](/cookbook/5.0/images/ScatterScaleAndOffset.png?240729212327)](/cookbook/5.0/images/ScatterScaleAndOffset.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

double[] xs = Generate.Consecutive(51);
double[] ys = Generate.Sin(51);
var sp = myPlot.Add.Scatter(xs, ys);
sp.ScaleX = 100;
sp.ScaleY = 10;
sp.OffsetX = 500;
sp.OffsetY = 5;

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>


<h2><a href='/cookbook/5.0/Scatter/StackedFilledLinePlot'>Stacked Filled Line Plot</a></h2>

A stacked filled line plot effect can be achieved by overlapping ScatterLines that fill area.

[![](/cookbook/5.0/images/StackedFilledLinePlot.png?240729212327)](/cookbook/5.0/images/StackedFilledLinePlot.png?240729212327)

{{< code-sp5 >}}

```cs
ScottPlot.Plot myPlot = new();

// create sample data
double[] xs = { 1, 2, 3, 4 };
double[] ys1 = { 1, 3, 1, 2 };
double[] ys2 = { 3, 7, 3, 1 };
double[] ys3 = { 5, 2, 5, 6 };

// shift each plot vertically by the sum of all plots before it
ys2 = Enumerable.Range(0, ys2.Length).Select(x => ys2[x] + ys1[x]).ToArray();
ys3 = Enumerable.Range(0, ys2.Length).Select(x => ys3[x] + ys2[x]).ToArray();

// plot the padded data points as ScatterLine
var sp3 = myPlot.Add.ScatterLine(xs, ys3, Colors.Black);
var sp2 = myPlot.Add.ScatterLine(xs, ys2, Colors.Black);
var sp1 = myPlot.Add.ScatterLine(xs, ys1, Colors.Black);

// set plot style
sp1.LineWidth = 2;
sp2.LineWidth = 2;
sp3.LineWidth = 2;
sp1.FillY = true;
sp2.FillY = true;
sp3.FillY = true;
sp1.FillYColor = Colors.Green;
sp2.FillYColor = Colors.Orange;
sp3.FillYColor = Colors.Blue;

// use tight margins so data goes to the edge of the plot
myPlot.Axes.Margins(0, 0, 0, 0.1);

myPlot.SavePng("demo.png", 400, 300);

```

{{< /code-sp5 >}}

<hr class='my-5 invisible'>

