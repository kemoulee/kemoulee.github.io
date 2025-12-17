<h2 id="publications" style="margin: 2px 0px -15px;">Publications <small style="font-size: 60%; color: #888;">(* = Equal Contribution)</small></h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if link.image %} 
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
    {% if link.conference_short %} 
    <abbr class="badge">{{ link.conference_short }}</abbr>
    {% endif %}
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="pub-badge pub-badge--link" target="_blank" rel="noopener">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
      {% endif %}
      {% if link.bibtex %} 
      <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
      {% endif %}
      {% if link.badges %}
        {% for badge in link.badges %}
          {% assign badge_last = badge | split: ' ' | last | upcase %}
          <span class="pub-badge pub-badge--rank{% if badge_last == 'A' %} pub-badge--a{% elsif badge_last == 'B' %} pub-badge--b{% endif %}">{{ badge }}</span>
        {% endfor %}
      {% elsif link.ccf == "A" or link.ccf == "B" %}
        <span class="pub-badge pub-badge--rank{% if link.ccf == 'A' %} pub-badge--a{% else %} pub-badge--b{% endif %}">CCF {{ link.ccf }}</span>
      {% endif %}
      {% if link.notes %} 
      <span class="pub-badge pub-badge--note">{{ link.notes }}</span>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>
<br>

{% endfor %}

</ol>
</div>

