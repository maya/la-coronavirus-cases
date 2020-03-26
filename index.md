---
layout: default
press_release: http://publichealth.lacounty.gov/phcommon/public/media/mediapubhpdetail.cfm?prid=2284
date: 26
total_cases: 1216
total_deaths: 21
---

<div class="padding-2 tablet:padding-x-4 bg-primary-dark">
  <p class="margin-0 font-sans-2xs text-white">Learn the importance of <a class="text-white" href="https://covid19.ca.gov/">practicing social distancing and good public health hygiene</a> to help <a class="text-white" href="https://www.flattenthecurve.com/">flatten the curve</a>.</p>
</div>
<div class="padding-2 tablet:padding-x-4">
  <h1 class="font-sans-3xl text-normal margin-bottom-0 margin-top-05">Los Angeles Coronavirus Cases</h1>
  <p>Source: <a class="usa-link" href="{{ page.press_release }}">March {{ page.date }}, 2020 News Release</a>, <a class="usa-link" href="http://www.publichealth.lacounty.gov/media/Coronavirus/">LA Public Health</a></p>

  <div class="display-block margin-y-3">
    <div class="display-inline-block">
      <p class="margin-y-0 font-sans-3xs text-ls-2 text-uppercase">Cases</p>
      <p class="font-sans-3xl text-bold margin-y-0 text-primary-dark">{{ page.total_cases }}</p>
    </div>
    <div class="display-inline-block margin-left-2">
      <p class="margin-y-0 font-sans-3xs text-ls-2 text-uppercase">Deaths</p>
      <p class="font-sans-3xl text-bold margin-y-0">{{ page.total_deaths }}</p>
    </div>
  </div>

  <iframe class="border-2px border-base-lighter" width="600" height="371" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcjzQb44BEhNlZU8oQxvh8VWjGcf5y8NOx53WvWo2bVaEGjmrynQwnN9FaJxl8yzDEXmzb5Emc1cM8/pubchart?oid=1931319394&amp;format=interactive"></iframe>
  <p class="font-sans-3xs">
    <a class="usa-link" href="https://docs.google.com/spreadsheets/d/1b72cOI-GFZkkp8jbdjTj9ZBkRCinCyCWHJh50Ud_yN4/edit?usp=sharing">Google Spreadsheet Data</a>
  </p>

<h2 class="margin-top-4 margin-bottom-2">LA neighborhood cases</h2>
<div class="maxw-tablet">
<iframe width="100%" height="520" frameborder="0" src="https://mbenari.carto.com/builder/0bfef6d9-97eb-484d-bf88-412aa82b904e/embed" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
</div>

  <style type="text/css">
    .table-sorted {display: none;}
    .toggle-me.active + .table-unsorted {display: none;}
    .active.table-sorted {display: block;}
  </style>

  <div class="clearfix margin-top-4"></div>
  <button class="toggle-me usa-button margin-top-4">Sort table</button>
  {% assign case = site.data.cases.by_city %}
  <table class="usa-table table-unsorted">
    <caption>By City</caption>
    <thead>
      <tr>
        <th scope="col">City</th>
        <th scope="col">Cases</th>
      </tr>
    </thead>
    <tbody>
      {% for item in case %}
      <tr>
        <th scope="row">{{ item.city }}</th>
        <td>{{ item.number }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>

  {% assign case = site.data.cases.by_city | sort: 'number' | reverse %}
  <table class="usa-table table-sorted">
    <caption>By City</caption>
    <thead>
      <tr>
        <th scope="col">City</th>
        <th scope="col">Cases</th>
      </tr>
    </thead>
    <tbody>
      {% for item in case %}
      <tr>
        <th scope="row">{{ item.city }}</th>
        <td>{{ item.number }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
<div class="usa-prose" markdown="1">
  <p class="font-sans-2xs">*These numbers are subject to change based on further investigation.</p>
  <p class="font-sans-2xs">This table includes Pasadena and Long Beach which are part of LA County, but outside of LA City.</p>
  <p class="font-sans-2xs">This uses LA County language. “Total” implies that we know the full extent of the problem, but it’s limited to tests administered. “Positive tests” or “cumulative cases” would be more accurate.</p>

Always check with trusted sources for the latest accurate information about novel coronavirus:
- [Los Angeles County Department of Public Health](http://publichealth.lacounty.gov/media/Coronavirus/)
- [California Department of Public Health](https://cdph.ca.gov/Programs/CID/DCDC/Pages/Immunization/ncov2019.aspx)
- [Centers for Disease Control and Prevention (CDC)](https://cdc.gov/coronavirus/2019-ncov/index.html)  [Spanish](https://cdc.gov/coronavirus/2019-ncov/index-sp.html)
- [World Health Organization](https://who.int/health-topics/coronavirus)
- LA County residents can also call 2-1-1
</div>

<h2 class="font-sans-lg margin-top-4 margin-bottom-2">Resources</h2>
<div class="usa-prose" markdown="1">
[California Coronavirus (COVID-19) Response (CA.gov)](https://covid19.ca.gov/)
</div>

<h2 class="font-sans-lg margin-top-4 margin-bottom-2">Data update cadence</h2>
<div class="usa-prose" markdown="1">
Data will be refreshed manually at least every few days and will try for every day. If I can find a reliably updating data source to pull from or automate this, I will use switch to using that. Reach out or [contribute to updating the data](https://github.com/maya/la-coronavirus-cases).
</div>
  <p class="font-sans-2xs margin-top-4 margin-bottom-0">Site last updated: <span class="font-mono-2xs">{{ site.time | date: "%x %r" }}</span> <span class="margin-x-1">|</span> <a class="usa-link" href="https://github.com/maya/la-coronavirus-cases">Contribute to this project on GitHub</a></p>
</div>


<script type="text/javascript">
var el = document.querySelector('.toggle-me');
var table = document.querySelector('.table-sorted');

el.onclick = function() {
  el.classList.toggle('active');
  table.classList.toggle('active');
}
</script>
