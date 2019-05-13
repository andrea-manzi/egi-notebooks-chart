# EGI Notebooks helm charts

## Docs...

In progress

## Stable releases

{% assign accounting = site.data.index.entries.notebooks-accounting | sort: 'created' | reverse %}
{% assign monitor = site.data.index.entries.notebooks-monitor | sort: 'created' | reverse %}
{% assign all_charts = accounting | concat: monitor %}
<table>
  <tr>
    <th>release</th>
    <th>date</th>
  </tr>
  {% for chart in all_charts %}
    {% unless chart.version contains "-"%}
    <tr>
      <td>
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version | remove_first: "v" }}
      </a>
      </td>
      <td>
      <span class='date'>{{ chart.created | date_to_rfc822 }}</span>
      </td>
    </tr>
    {% endunless %}
  {% endfor %}
</table>


## accounting releases

<table>
  <tr>
    <th>release</th>
    <th>date</th>
  </tr>
  {% for chart in accounting %}
    <tr>
      <td>
      {% unless chart.version contains "-" %}<b>{% endunless %}
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version | remove_first: "v" }}
      </a>
      {% unless chart.version contains "-" %}</b>{% endunless %}
      </td>
      <td>
      <span class='date'>{{ chart.created | date_to_rfc822 }}</span>
      </td>
    </tr>
  {% endfor %}
</table>


## monitor releases

<table>
  <tr>
    <th>release</th>
    <th>date</th>
  </tr>
  {% for chart in monitor %}
    <tr>
      <td>
      {% unless chart.version contains "-" %}<b>{% endunless %}
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version | remove_first: "v" }}
      </a>
      {% unless chart.version contains "-" %}</b>{% endunless %}
      </td>
      <td>
      <span class='date'>{{ chart.created | date_to_rfc822 }}</span>
      </td>
    </tr>
  {% endfor %}
</table>