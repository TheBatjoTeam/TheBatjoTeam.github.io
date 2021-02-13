---
layout: r-ingredients
title: Data Walk
language: en
slug: data-walk


materials: 6
material1: "11 plywood sheets (500 x 250 x 2 cm). Note that such dimensions are ideal only if you have access to a professional CNC machine that can deal with sheets so big. If not, you should use more, smaller, sheets and assemble them back together once they are cut by the CNC. It is of uttermost importance that you seek advice from the person operating the machines to know the specs of the machine you will have access to, so that you can plan accordingly the size of wood sheets needed and receive guidance on how to prepare the GCode files accordingly."
material2: "~30 screws (10mm diameter)"
material3: "~30 bolts (10mm diameter)"
material4: "~30 washers (20mm thick, 10mm diameter)"
material5: "Wood paint (optional)"
material6: "Wood Glue"

hardware: 3
hardware1: "CNC Milling Machine"
hardware2: "Laser cutter (optional)"
hardware3: "Screwdrivers"


software: 2
software1: "FreeCAD"
software2: "Inkscape"

estimated-time-modeling: "~ 1 work day / 8h"
estimated-time-fabrication: "depends greatly on the machine and its operators"
estimated-time-assembly: "~ 1 work day / 8h"

estimated-cost-material: "€200"
estimated-cost-machines: "If you don’t own the machines, consider renting them at your local lab - estimate to book time slots for approximately 16 hours in total, but discuss the project first with the lab manager / machine operator because it will vary greatly depending on the specs of the available machine."
---
<p style="font-size: 12px"><em>These estimates refer to the creation of 2 side-by-side walkable wooden line charts with 10 datapoints each. Scale appropriately to have an idea of how much time and material you need depending on your situation.</em></p>

### What data to start with
Dataset should be a time series with a first column containing dates and two other columns containing values for two different variables. The data should be in a .TSV format, although the filename extension should be .CSV (yes, not intuitive, but this is how the software accepts it). 

For our prototype, we used data on number of men and women killed by an intimate partner or ex-partner. The data was extracted from the PDF report "[Hearing of the President of the National Institute of Statistics (ISTAT), Giorgio Allieva. Parliamentary Commission for Inquiry on feminicide and on all forms of gender-based violence (2016)](https://www.istat.it/it/files//2017/09/Audizione-femminicidio-11-gennaio-2018.pdf)".
The following table is what the extracted data looks like and the first three columns are the ones used to generate the data curves of the 3D line chart. You can find the actual .CSV file in the GitHub repo for this project.

<table style="font-size: 10px; border-collapse: collapse;">
<thead>
<tr>
<th align="center" style="color: white; background-color:black; padding: 5px; border: 0.2px solid black; border-collapse: collapse">year</th>
<th align="center" style="color: white; background-color:black; padding: 5px; border: 0.2px solid black; border-collapse: collapse">women killed by partner or ex</th>
<th align="center" style="color: white; background-color:black; padding: 5px; border: 0.2px solid black; border-collapse: collapse">men killed by partner or ex</th>
<th align="center" style="color: white; background-color:black; padding: 5px; border: 0.2px solid black; border-collapse: collapse">total women killed</th>
<th align="center" style="color: white; background-color:black; padding: 5px; border: 0.2px solid black; border-collapse: collapse">total men killed</th>
<th align="center" style="color: white; background-color:black; padding: 5px; border: 0.2px solid black; border-collapse: collapse">total killed</th>
<th align="center" style="color: white; background-color:black; padding: 5px; border: 0.2px solid black; border-collapse: collapse">women killed by partner or ex - of total killed</th>
<th align="center" style="color: white; background-color:black; padding: 5px; border: 0.2px solid black; border-collapse: collapse">men killed by partner or ex - of total killed</th>
</tr></thead>
<tbody><tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2002</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">72</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">10</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">187</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">455</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">642</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">39%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2003</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">79</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">17</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">192</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">524</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">716</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">41%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">3%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2004</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">72</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">26</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">186</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">525</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">711</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">39%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">5%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2005</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">54</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">21</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">132</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">468</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">600</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">41%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">4%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2006</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">91</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">11</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">181</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">439</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">620</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">50%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">3%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2007</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">64</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">17</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">150</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">482</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">632</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">43%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">4%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2008</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">66</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">22</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">149</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">464</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">613</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">44%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">5%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2009</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">83</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">16</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">172</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">417</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">589</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">48%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">4%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2010</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">62</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">14</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">158</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">370</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">528</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">39%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">4%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2011</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">82</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">10</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">170</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">381</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">551</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">48%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">3%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2012</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">74</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">8</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">160</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">368</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">528</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">46%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2013</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">76</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">8</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">179</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">323</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">502</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">42%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2014</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">81</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">11</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">148</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">328</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">476</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">55%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">3%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2015</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">70</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">10</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">141</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">328</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">469</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">50%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">3%</td>
</tr>
<tr>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">2016</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">76</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">7</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">149</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">251</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">400</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">51%</td>
<td align = "center" style="padding: 5px; border: 0.2px solid black; border-collapse: collapse">3%</td>
</tr>
</tbody></table>