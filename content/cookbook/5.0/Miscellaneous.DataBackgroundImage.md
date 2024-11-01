---
Title: Data Area Background Image - ScottPlot 5.0 Cookbook
Description: An image can be used for the background of the data area.
URL: /cookbook/5.0/Miscellaneous/DataBackgroundImage/
BreadcrumbNames: ["ScottPlot 5.0 Cookbook", "Miscellaneous", "Data Area Background Image"]
BreadcrumbUrls: ["/cookbook/5.0/", "/cookbook/5.0/Miscellaneous", "/cookbook/5.0/Miscellaneous/DataBackgroundImage"]
Date: 2024-10-30
Version: ScottPlot 5.0.42
Version: ScottPlot 5.0.42
SearchUrl: "/cookbook/5.0/search/"
ShowEditLink: false
---


<h2 style='border-bottom: 0;'><a href='/cookbook/5.0/Miscellaneous/DataBackgroundImage'>Data Area Background Image</a></h2>

<div class="d-flex mb-2">
<a class="btn btn-sm btn-primary me-1" href="/cookbook/5.0/Miscellaneous/DataBackgroundImage">Recipe Permalink</a>
<a class="btn btn-sm btn-success me-1" href="/cookbook/5.0/Miscellaneous">Category: Miscellaneous</a>
</div>

An image can be used for the background of the data area.

[![](/cookbook/5.0/images/DataBackgroundImage.png?241029205813)](/cookbook/5.0/images/DataBackgroundImage.png?241029205813)

{{< recipe-sp5 >}}ScottPlot.Plot myPlot = new();

// plot sample data
var sig1 = myPlot.Add.Signal(Generate.Sin());
var sig2 = myPlot.Add.Signal(Generate.Cos());
sig1.LineWidth = 3;
sig2.LineWidth = 3;

// One could load an image from a file...
// Image bgImage = new("background.png");

// But in this example we will use a sample image:
Image bgImage = SampleImages.ScottPlotLogo();
myPlot.DataBackground.Image = bgImage;

myPlot.SavePng("demo.png", 400, 300);
{{< /recipe-sp5 >}}

<hr class='my-5 invisible'>


