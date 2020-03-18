---
layout: default
---

<div class="padding-2">
  <h1 class="font-sans-3xl text-normal">Los Angeles Coronavirus Cases</h1>
  <p>Source: <a href="http://www.publichealth.lacounty.gov/phcommon/public/media/mediapubhpdetail.cfm?prid=2271">March 17, 2020 News Release</a>, <a href="http://www.publichealth.lacounty.gov/media/Coronavirus/">LA County Public Health</a></p>
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
  <p>Last updated: {{ site.time }}</p>
</div>
