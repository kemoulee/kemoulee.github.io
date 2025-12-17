
<h2 id="awards" style="margin: 2px 0px -15px;">Awards &amp; Honors</h2>

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
      {% assign award_subtitle1 = award.subtitle1 | replace: 'Champion', '<span class="award-champion"><i class="fa-solid fa-trophy" aria-hidden="true"></i> <strong>Champion</strong></span>' %}
      <div class="author">{{ award_subtitle1 }}</div>
      {% assign award_subtitle2 = award.subtitle2 | replace: 'Champion', '<span class="award-champion"><i class="fa-solid fa-trophy" aria-hidden="true"></i> <strong>Champion</strong></span>' %}
      <div class="periodical"><em>{{ award_subtitle2 }}</em></div>
    <div class="links">
      {% if award.pdf %}
      <a href="{{ award.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if award.code %}
      <a href="{{ award.code }}" class="pub-badge pub-badge--link" target="_blank" rel="noopener">Code</a>
      {% endif %}
      {% if award.news %}
      <a href="{{ award.news }}" class="pub-badge pub-badge--link pub-badge--news" target="_blank" rel="noopener">News</a>
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
