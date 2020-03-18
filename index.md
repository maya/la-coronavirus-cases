---
layout: default
---

<div class="padding-2 tablet:padding-x-4">
  <h1 class="font-sans-3xl text-normal margin-bottom-0 margin-top-05">Los Angeles Coronavirus Cases</h1>
  <p>Source: <a class="usa-link" href="http://www.publichealth.lacounty.gov/phcommon/public/media/mediapubhpdetail.cfm?prid=2271">March 17, 2020 News Release</a>, <a class="usa-link" href="http://www.publichealth.lacounty.gov/media/Coronavirus/">LA Public Health</a></p>

  <div class="display-block margin-y-3">
    <div class="display-inline-block">
      <p class="margin-y-0 font-sans-3xs text-ls-2 text-uppercase">Total cases</p>
      <p class="font-sans-3xl text-bold margin-y-0 text-secondary-dark">144</p>
    </div>
    <div class="display-inline-block margin-left-2">
      <p class="margin-y-0 font-sans-3xs text-ls-2 text-uppercase">Total deaths</p>
      <p class="font-sans-3xl text-bold margin-y-0">1</p>
    </div>
  </div>

  <iframe class="border-2px border-base-lighter" width="600" height="371" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcjzQb44BEhNlZU8oQxvh8VWjGcf5y8NOx53WvWo2bVaEGjmrynQwnN9FaJxl8yzDEXmzb5Emc1cM8/pubchart?oid=1931319394&amp;format=interactive"></iframe>

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
  </table>

  <table class="usa-table">
    <caption>By City</caption>
    <thead>
      <tr>
        <th scope="col">City</th>
        <th scope="col">Cases</th>
      </tr>
    </thead>
    <tbody>
      {% for case in site.data.cases.by_city %}
      <tr>
        <th scope="row">{{ case.city }}</th>
        <td>{{ case.number }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
  <p>Site last updated: <span class="font-mono-xs">{{ site.time | date: "%x %r" }}</span></p>
</div>
