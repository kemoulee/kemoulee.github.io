<div class="publications awards">
<ol class="bibliography">

{% for award in site.data.awards.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if award.image %}
    <img src="{{ award.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
    {% if award.badge %}
    <abbr class="badge">{{ award.badge }}</abbr>
    {% endif %}
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="{{ award.url }}" target="_blank" rel="noopener">{{ award.title }}</a></div>
      <div class="author">{{ award.subtitle1 }}</div>
      <div class="periodical"><em>{{ award.subtitle2 }}</em></div>
    <div class="links">
      {% if award.pdf %}
      <a href="{{ award.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if award.code %}
      <a href="{{ award.code }}" class="pub-badge pub-badge--link" target="_blank" rel="noopener">CODE</a>
      {% endif %}
      {% if award.news %}
      <a href="{{ award.news }}" class="pub-badge pub-badge--link pub-badge--news" target="_blank" rel="noopener">NEWS</a>
      {% endif %}
      {% if award.others %}
      {{ award.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>
<br>

{% endfor %}

</ol>
</div>
