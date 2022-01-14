<html>

<head>
<meta http-equiv=Content-Type content="text/html; charset=windows-1252">
<meta name=Generator content="Microsoft Word 15 (filtered)">
<style>
<!--
 /* Font Definitions */
 @font-face
	{font-family:Wingdings;
	panose-1:5 0 0 0 0 0 0 0 0 0;}
@font-face
	{font-family:"Cambria Math";
	panose-1:2 4 5 3 5 4 6 3 2 4;}
@font-face
	{font-family:Calibri;
	panose-1:2 15 5 2 2 2 4 3 2 4;}
@font-face
	{font-family:Georgia;
	panose-1:2 4 5 2 5 4 5 2 3 3;}
@font-face
	{font-family:"var\(--jp-code-font-family\)";
	panose-1:0 0 0 0 0 0 0 0 0 0;}
 /* Style Definitions */
 p.MsoNormal, li.MsoNormal, div.MsoNormal
	{margin:0cm;
	text-autospace:none;
	font-size:11.0pt;
	font-family:"Georgia",serif;}
h1
	{margin-top:4.95pt;
	margin-right:0cm;
	margin-bottom:0cm;
	margin-left:31.0pt;
	text-indent:-27.3pt;
	text-autospace:none;
	font-size:12.0pt;
	font-family:"Georgia",serif;}
p.MsoTitle, li.MsoTitle, div.MsoTitle
	{margin-top:3.85pt;
	margin-right:47.25pt;
	margin-bottom:0cm;
	margin-left:46.4pt;
	text-align:center;
	text-autospace:none;
	font-size:16.0pt;
	font-family:"Georgia",serif;}
p.MsoBodyText, li.MsoBodyText, div.MsoBodyText
	{margin:0cm;
	text-autospace:none;
	font-size:10.0pt;
	font-family:"Georgia",serif;}
a:link, span.MsoHyperlink
	{color:blue;
	text-decoration:underline;}
pre
	{mso-style-link:"HTML Preformatted Char";
	margin:0cm;
	margin-bottom:.0001pt;
	font-size:10.0pt;
	font-family:"Courier New";}
p.IOPAbsText, li.IOPAbsText, div.IOPAbsText
	{mso-style-name:IOPAbsText;
	mso-style-link:"IOPAbsText Char";
	margin-top:0cm;
	margin-right:127.6pt;
	margin-bottom:0cm;
	margin-left:0cm;
	line-height:107%;
	font-size:10.0pt;
	font-family:"Times New Roman",serif;}
span.IOPAbsTextChar
	{mso-style-name:"IOPAbsText Char";
	mso-style-link:IOPAbsText;
	font-family:"Times New Roman",serif;}
p.IOPH3, li.IOPH3, div.IOPH3
	{mso-style-name:IOPH3;
	mso-style-link:"IOPH3 Char";
	margin-top:10.0pt;
	margin-right:0cm;
	margin-bottom:0cm;
	margin-left:0cm;
	line-height:107%;
	font-size:11.0pt;
	font-family:"Calibri",sans-serif;
	font-style:italic;}
span.IOPH3Char
	{mso-style-name:"IOPH3 Char";
	mso-style-link:IOPH3;
	font-family:"Calibri",sans-serif;
	font-style:italic;}
span.HTMLPreformattedChar
	{mso-style-name:"HTML Preformatted Char";
	mso-style-link:"HTML Preformatted";
	font-family:"Courier New";}
.MsoChpDefault
	{font-family:"Calibri",sans-serif;}
.MsoPapDefault
	{text-autospace:none;}
 /* Page Definitions */
 @page WordSection1
	{size:612.0pt 792.0pt;
	margin:1.0cm 64.0pt 14.0pt 65.0pt;}
div.WordSection1
	{page:WordSection1;}
@page WordSection2
	{size:612.0pt 792.0pt;
	margin:35.45pt 64.0pt 14.0pt 65.0pt;}
div.WordSection2
	{page:WordSection2;}
 /* List Definitions */
 ol
	{margin-bottom:0cm;}
ul
	{margin-bottom:0cm;}
-->
</style>

</head>

<body lang=EN-ZA link=blue vlink=purple style='word-wrap:break-word'>

<div class=WordSection1>

<p class=MsoTitle><a name="_Hlk92906414"><span style='font-family:"Arial",sans-serif'>Predicting
Sales and Foot Traffic of an Anonymous US Based Company Using LightGBM and
Ridge Models</span></a></p>

<p class=MsoTitle><span style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoNormal align=center style='margin-top:0cm;margin-right:47.25pt;
margin-bottom:0cm;margin-left:46.35pt;margin-bottom:.0001pt;text-align:center'><span
style='font-family:"Arial",sans-serif'>Andrew Schleiss</span></p>

<h1 style='margin-left:32.55pt;text-indent:-25.6pt'><span lang=EN-US
style='font-size:16.0pt;font-family:"Arial",sans-serif'>1<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span>

<table cellpadding=0 cellspacing=0>
 <tr>
  <td width=96 height=0></td>
 </tr>
 <tr>
  <td></td>
  <td><img width=627 height=1
  src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image001.gif"></td>
 </tr>
</table>

<br clear=ALL>
<span style='font-family:"Arial",sans-serif'>Problem<span style='letter-spacing:
-.05pt'> </span>Introduction</span></h1>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif'>The
problem is split into two parts, the prediction of both Sales as well as foot
Traffic* for the company at 1-hour intervals for the following month. </span></p>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif'>An
initial exploration of the data was completed to understand seasonality, trends
and correlations as well conceptualize the methods for data engineering/extracting
and modelling techniques. </span></p>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif'>Date
engineering techniques used can be surmised under two formats: temporal feature
extraction (day, month, year, etc.) and Fourier decomposition extraction (sine
and cosine expressions). </span></p>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif'>The
two models selected include a linear regularised model (Ridge) and a tree based
gradient boosting model (LightGBM). The Traffic data was initially modelled and
predicted to be used in the prediction of the Sales data which ultimately
improved the accuracy of the prediction. </span></p>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif'>LightGBM
outperformed Ridge with highest R-squared scores for both Sales and Traffic
data, with a value of 0.96 and 0.86 respectively for one month validation.</span></p>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='font-size:8.0pt;
line-height:107%;font-family:"Arial",sans-serif'>*All data and requirements
were provided by REPL </span></p>

<p class=MsoBodyText style='margin-top:.3pt'><span style='font-size:10.5pt;
font-family:"Arial",sans-serif'>&nbsp;</span></p>

<h1 style='margin-top:0cm;margin-right:0cm;margin-bottom:0cm;margin-left:33.75pt;
margin-bottom:.0001pt;text-indent:-26.8pt'><span lang=EN-US style='font-size:
16.0pt;font-family:"Arial",sans-serif'>2<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span>

<table cellpadding=0 cellspacing=0>
 <tr>
  <td width=94 height=0></td>
 </tr>
 <tr>
  <td></td>
  <td><img width=628 height=1
  src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image002.gif"></td>
 </tr>
</table>

<br clear=ALL>
<span style='font-family:"Arial",sans-serif'>Datasets</span></h1>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'>Training Data</span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:13.05pt;margin-bottom:
.3pt;margin-left:7.0pt;line-height:115%'><span style='font-family:"Arial",sans-serif'>Training</span><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'> </span><span
style='font-family:"Arial",sans-serif'>data</span><span style='font-family:
"Arial",sans-serif'> <span style='letter-spacing:-.05pt'>fr</span><span
style='letter-spacing:.1pt'>o</span>m<span style='letter-spacing:-.05pt'> </span>REPL
was received, which included two training files in csv format for Sales and
Traffic values against their captured dates. A sample of the Sales data can be
seen below: </span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><span
style='font-family:"Arial",sans-serif'><img width=135 height=138
id="Picture 421"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image003.jpg"
alt="Text, table&#10;&#10;Description automatically generated"></span></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>Sample
of the Sales data at 15min intervals</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:13.05pt;margin-bottom:
.3pt;margin-left:7.0pt;line-height:115%'><span style='font-family:"Arial",sans-serif'>The
values were captured at 15-minute intervals during business hours (assumption).
There were multiple timeframes missing or not captured for specific periods as
well as 0* values captured for Traffic data.</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'>Test Data</span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:13.05pt;margin-bottom:
.3pt;margin-left:7.0pt;line-height:115%'><span style='font-family:"Arial",sans-serif'>1-month
prediction timeframes were extrapolated using the Sales and Traffic data respectively
for each prediction. As such, the Test data contains the same hourly intervals
as that of the previous month.</span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><span
style='font-family:"Arial",sans-serif'><img width=352 height=44 id="Picture 422"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image004.jpg"
alt="Graphical user interface, text&#10;&#10;Description automatically generated"></span></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>Code
for the creation of Sales Test data at 15min intervals</span></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='font-size:8.0pt;
line-height:107%;font-family:"Arial",sans-serif'>*Assumed to be the missing
values as outlined in the exercise document  </span></p>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='font-size:8.0pt;
line-height:107%;font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'>Additional Data</span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>Yearly Gross Domestic Product (<b>GDP</b>)
values were obtained as these values were expected to relate to spending power,
and as a result, Sales; however the feature importance of the models show this
is not the case, albeit with additional location information about the company
we could improve this dataset at a state/city level.   </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=IOPAbsText style='margin-top:0cm;margin-right:1.35pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt'><span style='line-height:107%;
font-family:"Arial",sans-serif'>US federal <b>holidays</b> were merged to
training data as they should indicate days where customers would be more likely
to make purchases. </span></p>

<p class=MsoBodyText style='margin-top:.5pt'><i><span style='font-size:7.0pt;
font-family:"Arial",sans-serif'>&nbsp;</span></i></p>

<h1 style='margin-left:32.1pt;text-indent:-25.15pt'><span lang=EN-US
style='font-size:16.0pt;font-family:"Arial",sans-serif'>3<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span>

<table cellpadding=0 cellspacing=0>
 <tr>
  <td width=96 height=0></td>
 </tr>
 <tr>
  <td></td>
  <td><img width=627 height=1
  src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image001.gif"></td>
 </tr>
</table>

<br clear=ALL>
<span style='font-family:"Arial",sans-serif'>Features and<span
style='letter-spacing:-.25pt'> </span>Processing</span></h1>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'><span style='text-decoration:none'>&nbsp;</span></span></u></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'>Missing Values</span></u></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>The initial assumption was that the
missing values were those values identified as 0 (zero) </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>Upon further investigation the missing
values are those with missing 15-minute time intervals. These intervals are
assumed missing because there were no sales or traffic during these time (i.e.,
after business hours) </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>These missing values were set to 0
through the 1-hour <b>resampling</b> method, as such, these values do not need
to be interpolated. The previous method for interpolation still holds true for
time series and I will keep the section below for reference: </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:50.65pt;margin-bottom:
0cm;margin-left:35.45pt;margin-bottom:.0001pt;line-height:115%'><b><i><span
style='font-family:"Arial",sans-serif'>Prior</span></i></b><i><span
style='font-family:"Arial",sans-serif'> to resampling, the missing values were
imputed using interpolation, either with <b>linear</b> or the <b>cubic spline</b>
methodologies. Linear interpolation, as it suggests, creates a linear
polynomial line between the points before and after the missing value, with a value
identified between the two. Cubic spline uses all the features in its
prediction and creates <b>n</b> polynomial lines (spline) through data of
polynomial degree 3 (cubic). Although there were several other methods for
interpolation these two methods should give sufficient varied results. </span></i></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:50.65pt;margin-bottom:
0cm;margin-left:35.45pt;margin-bottom:.0001pt;line-height:115%'><i><span
style='font-family:"Arial",sans-serif'>One downside to interpolation relates to
missing values present in the initial or first points in the dataset, as seen
in the supplied data. This is because there are no prior values to use in the
calculation.</span></i></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:50.65pt;margin-bottom:
0cm;margin-left:35.45pt;margin-bottom:.0001pt;line-height:115%'><i><span
style='font-family:"Arial",sans-serif'>As a result, backfill <b>interpolation</b>
can be used to set these values. </span></i></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'><span style='text-decoration:none'>&nbsp;</span></span></u></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'>Resampling </span></u></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>Predictions were required at hour
intervals however the training data was at 15-minute intervals; the data was therefore
resampled with summation at 1-hour intervals. The resampling process causes
several 0 values as it created intervals even where there was nothing captured
in that hour.</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>These 0 values must not be confused with
the missing values present in the data.</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'>Date Decomposition </span></u></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><b><span
style='font-family:"Arial",sans-serif'>Temporal features</span></b><span
style='font-family:"Arial",sans-serif'> were extracted and extrapolated into
fields: </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><i><span
style='font-family:"Arial",sans-serif'>hour, day, month, year month start
indicator, month end indicator, day of the week, week in year, day of year,
days in month </span></i><span style='font-family:"Arial",sans-serif'>and<i>
inverse day of year</i></span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>Additional temporal features were
created to indicate specific months at the end of the year, as high variances
in the data were identified during these periods (<i>October, November,
December, and January</i>) as they hold the most holidays dates, New Years and
Christmas. </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>Days falling on <i>Friday, Saturday </i>and<i>
Sunday</i> were also extracted as well as each <i>quarter</i> of the year.</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><b><span
style='font-family:"Arial",sans-serif'>Fourier decomposition (linear features)</span></b><span
style='font-family:"Arial",sans-serif'> was applied using Sine and Cosine
functions on the minute, hour, day and month values to extract seasonality. </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'>Next Holiday</span></u></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>Using the holiday values (obtained from
the federal holiday data) the number of days until the <i>next holiday </i>was
calculated; this was calculated as a ramp up of sales/traffic leading up to
important holidays would be expected. </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<h1 style='margin-top:.05pt;margin-right:0cm;margin-bottom:0cm;margin-left:
33.65pt;margin-bottom:.0001pt;text-indent:-26.7pt'><span lang=EN-US
style='font-size:16.0pt;font-family:"Arial",sans-serif'>4<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span>

<table cellpadding=0 cellspacing=0>
 <tr>
  <td width=94 height=0></td>
 </tr>
 <tr>
  <td></td>
  <td><img width=628 height=1
  src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image002.gif"></td>
 </tr>
</table>

<br clear=ALL>
<span style='font-family:"Arial",sans-serif'>Metrics </span></h1>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>The metrics used in this exercise
included two metrics used for training and analysis:</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:43.0pt;margin-bottom:.0001pt;text-indent:-18.0pt;line-height:
115%'><span style='font-family:Symbol'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif'>Root Mean Square
Error (RMSE) – needed to minimize</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:43.0pt;margin-bottom:.0001pt;text-indent:-18.0pt;line-height:
115%'><span style='font-family:Symbol'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif'>R-squared (R2) – needed
to maximize </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>RMSE was used as the intrinsic model
evaluation metric (if required) and for performance analysis with R2. These two
metrics were selected together as they give an overall indication of the trend
and error rate of the resulting predictions. </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>R-squared measures the predictions
against a horizontal null hypothesis. This reveals whether the predictions are
‘trending’ away from a general horizontal line and towards the overall
direction of the true values.</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>RMSE indicates the error rate or
difference between the actual and predicted values. </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>In isolation, RMSE is a good indicator
for model performance, however, where there are very large or very small
outliers in the training data this value could be exacerbated and may give a
bad indication of the model’s performance, therefore R2 was used to counter
this as it will follow the over ‘trend’ of the predictions to the actual values.
</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:.3pt'><span style='font-size:8.5pt;
font-family:"Arial",sans-serif'>&nbsp;</span></p>

<h1 style='margin-top:.05pt;margin-right:0cm;margin-bottom:0cm;margin-left:
33.65pt;margin-bottom:.0001pt;text-indent:-26.7pt'><span lang=EN-US
style='font-size:16.0pt;font-family:"Arial",sans-serif'>5<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span>

<table cellpadding=0 cellspacing=0>
 <tr>
  <td width=94 height=0></td>
 </tr>
 <tr>
  <td></td>
  <td><img width=628 height=1
  src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image002.gif"></td>
 </tr>
</table>

<br clear=ALL>
<span style='font-family:"Arial",sans-serif'>Modelling Techniques</span></h1>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>&nbsp;</span></b></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Initial Model Selection</span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>During the initial EDA process an auto-ml package called
Pycaret was used to run multiple machine learning models on the Sales data.
This provided an indication of the types of models to be used. The results are
below:</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><img width=644 height=376
id="Picture 446"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image005.jpg"
alt="Table&#10;&#10;Description automatically generated with medium confidence"></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>Pycaret
run on raw Sales data </span></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>The above shows that gradient boosting trees could be
potential models for this problem, however, this baseline doesn’t include
several additional features and processing which is required in the final
models. It also wasn’t run for Traffic; therefore a Linear model will be
selected as well.</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>LightGBM</span></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'> - was used for predicting Traffic and Sales, as this
model has done well in several recent competitions [1] due to its fast
processing and highly accurate results. </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Ridge</span></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'> </span><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Regression</span></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'> – multiple linear models were tested (Huber, Tweedie)
with the best being Ridge Regression. It was hypothesised that this was a
result of the model’s ability to apply <i>regularization</i>. Regularization was
beneficial as there were multiple extracted additional features; this may result
in a noisy dataset if not weighted correctly.</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Merge of Traffic and Sales</span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>It was assumed that Sales is the primary prediction
required as Sales has a direct impact on company revenue, as such and from the
feature importance from the pycaret baseline, Traffic data was added to the
Sales data. </span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><img
width=354 height=194 id="Picture 445"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image006.jpg"
alt="Chart&#10;&#10;Description automatically generated"></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><span
style='font-size:7.0pt;font-family:"Arial",sans-serif'>Pycaret baseline feature
importance </span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Hyperparameter Tuning </span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>The process for hyperparameter tuning was either done by
</span><b><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Optuna</span></b><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'> for LightGBM or
via an </span><b><span style='font-family:"Arial",sans-serif;letter-spacing:
-.05pt'>iterative</span></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'> process of trial-and-error for Ridge.</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Optuna a hyperparameter optimization framework was setup
with a range of influential LightGBM parameters [2] and run for 300 trials with
a pruning callback stop poor trials. The output of Optuna provided optimal
parameters to minimize RMSE.</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Validation Hold-Out </span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Hold-out validation method was used, with 1 month of
training data being held for validation purposes as this is the same timeframe
required for prediction. </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Note</span></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>: Poor performance has been experienced with timeseries
cross validation testing as initial folds with poor performance dilute the
additional folds (with better performance). </span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><img
width=644 height=184 id="Picture 435"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image007.jpg"
alt="Chart&#10;&#10;Description automatically generated"></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><span
style='font-size:7.0pt;font-family:"Arial",sans-serif'>Traffic training and
validation hold-out</span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Experimental Runs </span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>A number of ‘experiments’ were run, and their resulting
RMSE and R2 score recorded. A full list of these runs can be provided on
request with a number of important runs stated in their relative notebooks.  </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>A set of experiments were to test: </span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Temporal
and Linear Features </span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Adding
public holidays </span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Adding
GDP </span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Adding
Traffic data (Sales prediction only)</span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Split
of train, validation data at different time intervals </span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Interpolation
methods – linear, cubic spline, backfill </span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Scaling
methods – Standard, MinMax or Robust Scaling </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Traffic Modelling Process </span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>The modelling technique involved training and predicting
Traffic data. This data would then be used in the prediction of Sales with the
assumption that a higher number of customers in store will equate to higher
sales. </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>                                                      </span></b><img
width=317 height=292 id="Picture 433"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image008.jpg"
alt="Diagram&#10;&#10;Description automatically generated"></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><span
style='font-size:7.0pt;font-family:"Arial",sans-serif'>Traffic model process</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>LightGBM</span></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'> had better performance in predicting the </span><b><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>future</span></b><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'> Traffic values
and </span><b><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Ridge</span></b><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'> predicted better
on </span><b><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>historical
values</span></b><span style='font-family:"Arial",sans-serif;letter-spacing:
-.05pt'>,</span><b><span style='font-family:"Arial",sans-serif;letter-spacing:
-.05pt'> </span></b><span style='font-family:"Arial",sans-serif;letter-spacing:
-.05pt'>as such Traffic data was split into three:</span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Historical
data – predicted by Ridge </span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Actual
data – provided by REPL </span></p>

<p class=MsoBodyText style='margin-top:0cm;margin-right:10.55pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt'><span
style='font-family:Symbol;letter-spacing:-.05pt'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Future
prediction – predicted by LightGBM and used as submission </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>See results section for details. </span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><img
width=416 height=319 id="Picture 432"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image009.jpg"
alt="Chart&#10;&#10;Description automatically generated"></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><span
style='font-size:7.0pt;font-family:"Arial",sans-serif'>Traffic and Sales data
overlap and prediction indicator(green)</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Due to the mismatch in timeseries of Traffic and Sales
data, historical and future predictions for Traffic values were predicted and
added to the Sales data (for prediction of Sales). </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'><span style='text-decoration:none'>&nbsp;</span></span></u></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt;line-height:115%'><u><span
style='font-family:"Arial",sans-serif'>Sales modelling process</span></u></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>Sales were predicted using the same features
extracted for Traffic as well as comparing the two models. </span></p>

<p class=MsoBodyText align=center style='margin-top:5.25pt;margin-right:13.05pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center;
line-height:115%'><img width=138 height=233 id="Picture 434"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image010.jpg"
alt="Diagram&#10;&#10;Description automatically generated"></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><span
style='font-size:7.0pt;font-family:"Arial",sans-serif'>Sales model process</span></p>

<p class=MsoBodyText align=center style='margin-top:5.25pt;margin-right:13.05pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center;
line-height:115%'><span style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>LightGBM performed better than Ridge, with
the assumption that LightGBM performs better in short term predictions and
future values whereas Ridge preforms better in longer prediction horizons and
historical predictions. </span></p>

<p class=MsoNormal><span style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoNormal><u><span style='font-family:"Arial",sans-serif'>Ensembling </span></u></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>Two ensembling techniques were used for
predicting Sales data*</span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt;line-height:
115%'><span style='font-family:Symbol'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif'>Arithmetic mean </span></p>

<p class=MsoBodyText style='margin-top:5.25pt;margin-right:13.05pt;margin-bottom:
0cm;margin-left:36.0pt;margin-bottom:.0001pt;text-indent:-18.0pt;line-height:
115%'><span style='font-family:Symbol'>·<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-family:"Arial",sans-serif'>Geometric mean </span></p>

<p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif'>Arithmetic
mean sums the prediction values from each model’s submission and divides this
by the number of submissions. </span></p>

<p class=MsoNormal align=center style='text-align:center'><img width=145
height=98 id="Picture 436"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image011.jpg"
alt="Diagram, schematic&#10;&#10;Description automatically generated with medium confidence"></p>

<p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif'>Geometric
mean takes the nth root of the multiplicative of the predictions where n is the
number of submissions.</span></p>

<p class=MsoNormal align=center style='text-align:center'><img width=171
height=112 id="Picture 437"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image012.jpg"
alt="Diagram&#10;&#10;Description automatically generated"></p>

<p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif'>Geometric
mean is preferred when the values are exponential and have constant growth,
otherwise arithmetic mean is preferred.</span></p>

<p class=MsoNormal><span style='font-size:10.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>

<p class=MsoNormal><span style='font-size:8.0pt;font-family:"Arial",sans-serif'>*Only
LightGBM was used to predict Sales data as Ridge did not perform well on future
values </span></p>

</div>

<span style='font-size:11.0pt;font-family:"Arial",sans-serif'><br clear=all
style='page-break-before:always'>
</span>

<div class=WordSection2>

<p class=MsoBodyText style='margin-top:.05pt'><span style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<h1 style='margin-top:0cm;margin-right:0cm;margin-bottom:0cm;margin-left:34.25pt;
margin-bottom:.0001pt'><span lang=EN-US style='font-size:16.0pt;font-family:
"Arial",sans-serif'>6<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span>

<table cellpadding=0 cellspacing=0>
 <tr>
  <td width=96 height=0></td>
 </tr>
 <tr>
  <td></td>
  <td><img width=627 height=1
  src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image001.gif"></td>
 </tr>
</table>

<br clear=ALL>
<span style='font-family:"Arial",sans-serif'>Results and<span style='letter-spacing:
-.1pt'> </span>Discussion</span></h1>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>The best performing experiments are below for each model
and dataset.</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Best Validation Testing Results</span></u></p>

<table class=MsoTableGrid border=1 cellspacing=0 cellpadding=0 align=left
 style='border-collapse:collapse;border:none;margin-left:6.75pt;margin-right:
 6.75pt'>
 <tr>
  <td width=150 valign=top style='width:112.25pt;border:solid windowtext 1.0pt;
  background:#0070C0;padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span
  style='font-family:"Arial",sans-serif;color:white;letter-spacing:-.05pt'>Data
  </span></b></p>
  </td>
  <td width=167 valign=top style='width:125.15pt;border:solid windowtext 1.0pt;
  border-left:none;background:#0070C0;padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span
  style='font-family:"Arial",sans-serif;color:white;letter-spacing:-.05pt'>Model</span></b></p>
  </td>
  <td width=168 style='width:125.8pt;border:solid windowtext 1.0pt;border-left:
  none;background:#0070C0;padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText align=right style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:right'><b><span
  style='font-family:"Arial",sans-serif;color:white;letter-spacing:-.05pt'>RMSE</span></b></p>
  </td>
  <td width=159 style='width:119.3pt;border:solid windowtext 1.0pt;border-left:
  none;background:#0070C0;padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText align=right style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:right'><b><span
  style='font-family:"Arial",sans-serif;color:white;letter-spacing:-.05pt'>R-Squared</span></b></p>
  </td>
 </tr>
 <tr style='height:14.55pt'>
  <td width=150 style='width:112.25pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0cm 5.4pt 0cm 5.4pt;height:14.55pt'>
  <p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt'><span
  style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Traffic</span></p>
  </td>
  <td width=167 style='width:125.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.55pt'><pre style='background:white;
  word-break:break-all'><span style='font-family:"Arial",sans-serif;color:black;
  letter-spacing:-.05pt'>LightGBM</span><span style='font-family:"var(--jp-code-font-family)",serif;
  color:black'> </span></pre></td>
  <td width=168 style='width:125.8pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.55pt'><pre style='text-align:right;
  background:white;word-break:break-all'><span style='font-family:"Arial",sans-serif;
  color:black;letter-spacing:-.05pt'>3.56</span></pre></td>
  <td width=159 style='width:119.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt;height:14.55pt'><pre style='text-align:right;
  background:white;word-break:break-all'><b><span style='font-family:"Arial",sans-serif;
  color:black;letter-spacing:-.05pt'>0.87</span></b></pre></td>
 </tr>
 <tr>
  <td width=150 style='width:112.25pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt'><span
  style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Traffic</span></p>
  </td>
  <td width=167 style='width:125.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt'><span
  style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Ridge</span> </p>
  </td>
  <td width=168 style='width:125.8pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt'><pre style='text-align:right;background:white;
  word-break:break-all'><span style='font-family:"Arial",sans-serif;color:black;
  letter-spacing:-.05pt'>5.95</span></pre></td>
  <td width=159 style='width:119.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt'><pre style='text-align:right;background:white;
  word-break:break-all'><span style='font-family:"Arial",sans-serif;color:black;
  letter-spacing:-.05pt'>0.65</span></pre></td>
 </tr>
 <tr>
  <td width=150 style='width:112.25pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt'><span
  style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Sales</span></p>
  </td>
  <td width=167 style='width:125.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt'><span
  style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>LightGBM</span></p>
  </td>
  <td width=168 style='width:125.8pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt'><pre style='text-align:right;background:white;
  word-break:break-all'><span style='font-family:"Arial",sans-serif;color:black;
  letter-spacing:-.05pt'>275.92</span></pre></td>
  <td width=159 style='width:119.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt'><pre style='text-align:right;background:white;
  word-break:break-all'><b><span style='font-family:"Arial",sans-serif;
  color:black;letter-spacing:-.05pt'>0.97</span></b></pre></td>
 </tr>
 <tr>
  <td width=150 style='width:112.25pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt'><span
  style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Sales</span></p>
  </td>
  <td width=167 style='width:125.15pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt'>
  <p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;
  margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt'><span
  style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>Ridge</span></p>
  </td>
  <td width=168 style='width:125.8pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt'><pre style='text-align:right;background:white;
  word-break:break-all'><span style='font-family:"Arial",sans-serif;color:black;
  letter-spacing:-.05pt'>608.20 </span></pre></td>
  <td width=159 style='width:119.3pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0cm 5.4pt 0cm 5.4pt'><pre style='text-align:right;background:white;
  word-break:break-all'><span style='font-family:"Arial",sans-serif;color:black;
  letter-spacing:-.05pt'>0.84</span></pre></td>
 </tr>
</table>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>&nbsp;</span></b></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Traffic Predictions</span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Traffic predictions were split into two parts for the
future (submission) predictions and the historical predictions.</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>&nbsp;</span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:7.0pt;margin-bottom:.0001pt;text-align:center'><span
style='font-family:"Arial",sans-serif'><img width=481 height=186 id="Picture 1"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image013.jpg"
alt="Chart, bar chart, histogram&#10;&#10;Description automatically generated"></span></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><b><u><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>Ridge</span></u></b><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>
predictions for Traffic data  </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>&nbsp;</span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><img
width=470 height=183 id="Picture 439"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image014.jpg"
alt="Chart, histogram&#10;&#10;Description automatically generated"></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><b><u><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>LightGBM</span></u></b><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>
predictions for Traffic data  </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>For the 1-month validation test, Ridge performed worse
than LightGBM on </span><b><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>future</span></u></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'> predictions, however when visualizing the historical predictions,
Ridge was able to interpret the data better for longer periods.</span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:7.0pt;margin-bottom:.0001pt;text-align:center'><span
style='font-family:"Arial",sans-serif'><img width=457 height=182
id="Picture 424"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image015.jpg"
alt="Chart, histogram&#10;&#10;Description automatically generated"></span></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><b><u><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>Ridge</span></u></b><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'> and <b>LightGBM</b>
predictions for Traffic data  </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Therefore, Ridge was used to predict the historical
values and LightGBM to predict the future (submission) values.</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'><span style='text-decoration:none'>&nbsp;</span></span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Sales Predictions</span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>LightGBM bested Ridge with a higher R-Squared and lower
RMSE. The main differing influences being LightGBM preferred temporal features
(linear features removed), whereas Ridge preferred the Fourier features (temporal
features removed).</span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:7.0pt;margin-bottom:.0001pt;text-align:center'><img
width=424 height=168 id="Picture 438"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image016.jpg"
alt="Chart, bar chart&#10;&#10;Description automatically generated"></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><b><u><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>LightGBM</span></u></b><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>
predictions for Sales data  </span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:7.0pt;margin-bottom:.0001pt;text-align:center'><img
width=471 height=186 id="Picture 440"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image017.jpg"
alt="Chart, bar chart&#10;&#10;Description automatically generated"></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><b><u><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>Ridge</span></u></b><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'> predictions
for Sales data  </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:7.0pt;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>&nbsp;</span></b></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><u><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Ensembling Results</span></u></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Sales final predictions were ensembled using the
submissions of the Ridge model and LightGBM model. </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Arithmetic mean</span></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'> ensembling was used as the final submission as it
predicted higher than geometric mean ensembling, due to the assumption that all
models are underpredicting. </span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><img
width=454 height=188 id="Picture 447"
src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image018.jpg"
alt="Chart, bar chart&#10;&#10;Description automatically generated"></p>

<p class=MsoBodyText align=center style='margin-top:0cm;margin-right:13.05pt;
margin-bottom:.3pt;margin-left:7.0pt;text-align:center;line-height:115%'><b><span
style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>Arithmetic
</span></b><span style='font-size:7.0pt;line-height:115%;font-family:"Arial",sans-serif'>Ensemble
with LightGBM reference </span></p>

<p class=MsoBodyText align=center style='margin-top:8.35pt;margin-right:10.55pt;
margin-bottom:0cm;margin-left:0cm;margin-bottom:.0001pt;text-align:center'><b><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>&nbsp;</span></b></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>Note</span></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'> this was not an optimal ensembling technique and was
used for demonstration purposes only.</span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>To improve on this technique, multiple submissions
should be saved and used for </span><b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'>each model</span></b><span style='font-family:"Arial",sans-serif;
letter-spacing:-.05pt'> and then ensembled. </span></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt'><span style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<h1 style='margin-top:0cm;margin-right:0cm;margin-bottom:0cm;margin-left:32.55pt;
margin-bottom:.0001pt;text-indent:-25.6pt'><span lang=EN-US style='font-size:
16.0pt;font-family:"Arial",sans-serif'>7<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span>

<table cellpadding=0 cellspacing=0>
 <tr>
  <td width=96 height=0></td>
 </tr>
 <tr>
  <td></td>
  <td><img width=627 height=1
  src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image001.gif"></td>
 </tr>
</table>

<br clear=ALL>
<span style='font-family:"Arial",sans-serif'>Reflection</span></h1>

<p class=IOPH3><span style='font-size:10.0pt;line-height:107%;font-family:"Arial",sans-serif;
font-style:normal'>This was an interesting and challenging exercise which I
enjoyed tremendously; the biggest hurdles were getting the Traffic data into a
format for Sales to use as well as resampling the data into hour intervals.</span></p>

<p class=IOPH3><span style='font-size:10.0pt;line-height:107%;font-family:"Arial",sans-serif;
font-style:normal'>If time allowed, I would have also attempted the below to
improve performance:</span></p>

<p class=IOPH3 style='margin-left:36.0pt;text-indent:-18.0pt'><span
style='font-size:10.0pt;line-height:107%;font-family:Symbol;font-style:normal'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:10.0pt;line-height:107%;font-family:"Arial",sans-serif;
font-style:normal'>Multi-step recursive prediction on a 7-day horizon </span></p>

<p class=IOPH3 style='margin-left:36.0pt;text-indent:-18.0pt'><span
style='font-size:10.0pt;line-height:107%;font-family:Symbol;font-style:normal'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:10.0pt;line-height:107%;font-family:"Arial",sans-serif;
font-style:normal'>7-day value lags (shift Sales and Traffic values) </span></p>

<p class=IOPH3 style='margin-left:36.0pt;text-indent:-18.0pt'><span
style='font-size:10.0pt;line-height:107%;font-family:Symbol;font-style:normal'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:10.0pt;line-height:107%;font-family:"Arial",sans-serif;
font-style:normal'>Further ensembling with additional models and submissions  </span></p>

<h1 style='margin-left:32.45pt;text-indent:0cm'><u><span style='font-family:
"Arial",sans-serif'><span style='text-decoration:none'>&nbsp;</span></span></u></h1>

<p class=MsoBodyText style='margin-top:.05pt'><span style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<h1 style='margin-top:0cm;margin-right:0cm;margin-bottom:0cm;margin-left:32.55pt;
margin-bottom:.0001pt;text-indent:-25.6pt'><span lang=EN-US style='font-size:
16.0pt;font-family:"Arial",sans-serif'>8<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span>

<table cellpadding=0 cellspacing=0>
 <tr>
  <td width=96 height=0></td>
 </tr>
 <tr>
  <td></td>
  <td><img width=627 height=1
  src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image001.gif"></td>
 </tr>
</table>

<br clear=ALL>
<span style='font-family:"Arial",sans-serif'>Assumptions</span></h1>

<p class=IOPH3><span style='font-size:10.0pt;line-height:107%;font-family:"Arial",sans-serif;
font-style:normal'>There were some questions related to the exercise requirements.
The below assumptions were requested for clarification however clarity wasn’t
provided as of writing this document. </span></p>

<p class=IOPH3 style='margin-left:14.2pt;text-indent:-18.0pt'><span
style='font-size:10.0pt;line-height:107%;font-family:Symbol;font-style:normal'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:10.0pt;line-height:107%;font-family:"Arial",sans-serif;
font-style:normal'>Data was presented at 15-minute intervals, the exercise
asked for 1-hour intervals. As such the data was resampled to 1-hour intervals.</span></p>

<p class=IOPH3 style='margin-left:14.2pt;text-indent:-18.0pt'><span
style='font-size:10.0pt;line-height:107%;font-family:Symbol;font-style:normal'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:10.0pt;line-height:107%;font-family:"Arial",sans-serif;
font-style:normal'>1 month prediction was required however the training data
did not end at 1 month, therefore the prediction timeframe was created and
projected 1-month from the last day of the training.</span></p>

<p class=IOPH3 style='margin-left:14.2pt;text-indent:-18.0pt'><span
style='font-size:10.0pt;line-height:107%;font-family:Symbol;font-style:normal'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span style='font-size:10.0pt;line-height:107%;font-family:"Arial",sans-serif;
font-style:normal'>Missing values were said to be present in the datasets and
were assumed to be all intervals not present in the 15-minute timeframe</span></p>

<p class=MsoBodyText style='margin-right:13.05pt;line-height:115%'><span
style='font-family:"Arial",sans-serif'>&nbsp;</span></p>

<h1 style='margin-top:0cm;margin-right:0cm;margin-bottom:0cm;margin-left:32.55pt;
margin-bottom:.0001pt;text-indent:-25.6pt'><span lang=EN-US style='font-size:
16.0pt;font-family:"Arial",sans-serif'>9<span style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span>

<table cellpadding=0 cellspacing=0>
 <tr>
  <td width=96 height=0></td>
 </tr>
 <tr>
  <td></td>
  <td><img width=627 height=1
  src="Predicting%20Sales%20and%20foot%20Traffic%20-%20Andrew%20Schleiss_files/image001.gif"></td>
 </tr>
</table>

<br clear=ALL>
<span style='font-family:"Arial",sans-serif'>References</span></h1>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt;text-indent:-14.2pt'><span
lang=EN-US style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>[1]<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp; </span></span><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>LightGBM in 2nd
place in M5 competition </span><a
href="https://www.kaggle.com/c/m5-forecasting-accuracy/discussion/164599"><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>https://www.kaggle.com/c/m5-forecasting-accuracy/discussion/164599</span></a></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt;text-indent:-14.2pt'><span
lang=EN-US style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>[2]<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp; </span></span><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>LightGBM parameter
tuning </span><a
href="https://lightgbm.readthedocs.io/en/latest/Parameters-Tuning.html"><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>https://lightgbm.readthedocs.io/en/latest/Parameters-Tuning.html</span></a></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt;text-indent:-14.2pt'><span
lang=EN-US style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>[3]<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp; </span></span><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>GDP Data </span><a
href="https://data.worldbank.org/indicator/NY.GDP.MKTP.CD" target="_blank"><span
style='font-size:10.5pt;font-family:"Arial",sans-serif;background:white'>https://data.worldbank.org/indicator/NY.GDP.MKTP.CD</span></a></p>

<p class=MsoBodyText style='margin-top:8.35pt;margin-right:10.55pt;margin-bottom:
0cm;margin-left:6.95pt;margin-bottom:.0001pt;text-indent:-14.2pt'><span
lang=EN-US style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>[4]<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp; </span></span><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>US federal
Holidays </span><a
href="https://data.world/sudipta/us-federal-holidays-2011-2020"><span
style='font-family:"Arial",sans-serif;letter-spacing:-.05pt'>https://data.world/sudipta/us-federal-holidays-2011-2020</span></a></p>

<p class=MsoNormal style='margin-top:9.75pt;margin-right:12.15pt;margin-bottom:
0cm;margin-left:0cm;margin-bottom:.0001pt;line-height:115%'><span
style='font-size:10.0pt;line-height:115%;font-family:"Arial",sans-serif;
color:#242424'>&nbsp;</span></p>

</div>

</body>

</html>
