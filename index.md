---
layout: default
---

<div class="padding-2 tablet:padding-x-4">
  <h1 class="font-sans-3xl text-normal margin-bottom-0 margin-top-05">Los Angeles Coronavirus Cases</h1>
  <p>Source: <a class="usa-link" href="https://twitter.com/lapublichealth/status/1240375141231546368/photo/2">March 18, 2020 News Release</a>, <a class="usa-link" href="http://www.publichealth.lacounty.gov/media/Coronavirus/">LA Public Health</a></p>

  <div class="display-block margin-y-3">
    <div class="display-inline-block">
      <p class="margin-y-0 font-sans-3xs text-ls-2 text-uppercase">Total cases</p>
      <p class="font-sans-3xl text-bold margin-y-0 text-secondary-dark">190</p>
    </div>
    <div class="display-inline-block margin-left-2">
      <p class="margin-y-0 font-sans-3xs text-ls-2 text-uppercase">Total deaths</p>
      <p class="font-sans-3xl text-bold margin-y-0">1</p>
    </div>
  </div>

  <iframe class="border-2px border-base-lighter" width="600" height="371" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcjzQb44BEhNlZU8oQxvh8VWjGcf5y8NOx53WvWo2bVaEGjmrynQwnN9FaJxl8yzDEXmzb5Emc1cM8/pubchart?oid=1931319394&amp;format=interactive"></iframe>
<!--
  <table class="usa-table">
    <caption>Laboratory Confirmed Cases</caption>
    <thead>
      <tr>
        <th scope="col">City</th>
        <th scope="col">Cases</th>
      </tr>
    </thead>
    <tbody>
      {% for case in site.data.cases.total %}
      <tr>
        <th scope="row">{{ case.city }}</th>
        <td>{{ case.number }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table> -->

  <style type="text/css">
    .table-sorted {display: none;}
    .toggle-me.active + .table-unsorted {display: none;}
    .active.table-sorted {display: block;}
  </style>

  <div class="clearfix"></div>
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
  <p class="font-sans-2xs">Note: This table includes Pasadena and Long Beach which are part of LA County, but outside of LA City.</p>
  <p class="font-sans-2xs">Site last updated: <span class="font-mono-2xs">{{ site.time | date: "%x %r" }}</span> <span class="margin-x-1">|</span> <a class="usa-link" href="https://github.com/maya/la-coronavirus-cases">Contribute to this project on GitHub</a></p>
</div>


<script type="text/javascript">
var el = document.querySelector('.toggle-me');
var table = document.querySelector('.table-sorted');

el.onclick = function() {
  el.classList.toggle('active');
  table.classList.toggle('active');
}
</script>
