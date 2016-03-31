---
layout: page
title: collapseBlockMargins
parent_title: mPDF Variables
permalink: /reference/mpdf-variables/collapseblockmargins.html
modification_time: 2015-08-05T12:01:47+00:00
---

<p>(mPDF &gt;= 4.2)</p>
<p>collapseBlockMargins – Specify whether to collapse (vertical) margins between block elements</p>

# Description

<p class="manual_block">void <b>collapseBlockMargins</b></p>
<p>Specify whether to collapse (vertical) margins between block elements. In line with CSS specification, the top/bottom margins of adjoining block-style elements are collapsed to the larger of the two. This works between all block elements such as DIV, P, H1-6 etc. and also lists and tables.</p>
<p>NB Firefox does not collapse margins above and below tables, but IE8 does.</p>

# Values

<p class="manual_param_dt"><span class="parameter">collapseBlockMargins</span> =&nbsp; <span class="smallblock">TRUE </span>| <span class="smallblock">FALSE</span></p>
<p class="manual_param_dd"><b>Values</b>

<span class="smallblock">TRUE </span>: enable collapse

<span class="smallblock">FALSE</span>: disable collapse

<span class="smallblock">DEFAULT</span>: <span class="smallblock">TRUE</span></p>

# Changelog

<table class="table"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>4.2</td>
<td>Variable was added.</td>
</tr>
</tbody> </table>

# Examples

{% highlight php %}
Example #1

{% endhighlight %}

{% highlight php %}
<?php

<?php

include("../mpdf.php");

$mpdf=new mPDF();

$html = '

<div style="margin-bottom: 3em;">This DIV has a bottom margin defined as 3em</div>

<div style="margin-top: 2em;">This DIV has a top margin defined as 2em. The space between these DIVs will collapse to 3em</div>';

$mpdf->WriteHTML($html);

$mpdf->Output();

?>
{% endhighlight %}

<div class="alert alert-info" role="alert"><strong>Note:</strong> The collapse of margins at the top and bottom of the page is unaffected by this variable. This is set by the custom CSS property <code>margin-collapse: collapse|none</code> which can be defined in the <code>defaultCSS</code> variable in <span class="filename">config.php</span> or elsewhere.</div>
