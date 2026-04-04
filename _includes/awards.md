<h2>Awards &amp; Honors</h2>

<div class="publications awards">
  <ol class="bibliography">
    {% for award in site.data.awards.main %}
    <li class="publication-entry">
      <article class="pub-row{% unless award.image %} pub-row--text-only{% endunless %}">
        {% if award.image %}
        <div class="pub-media">
          <img src="{{ award.image }}" class="teaser" alt="{{ award.title }}">
          {% if award.badge %}
          <abbr class="badge">{{ award.badge }}</abbr>
          {% endif %}
        </div>
        {% endif %}

        <div class="pub-copy">
          <div class="title">
            <a href="{{ award.url }}" target="_blank" rel="noopener">{{ award.title }}</a>
          </div>
          {% assign award_subtitle1 = award.subtitle1 | replace: 'Champion', '<span class="award-champion"><i class="fa-solid fa-trophy" aria-hidden="true"></i> <strong>Champion</strong></span>' %}
          <div class="author">{{ award_subtitle1 }}</div>
          {% assign award_subtitle2 = award.subtitle2 | replace: 'Champion', '<span class="award-champion"><i class="fa-solid fa-trophy" aria-hidden="true"></i> <strong>Champion</strong></span>' %}
          <div class="periodical"><em>{{ award_subtitle2 }}</em></div>

          <div class="links">
            {% if award.pdf %}
            <a href="{{ award.pdf }}" class="pub-badge pub-badge--pdf" target="_blank" rel="noopener">PDF</a>
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
      </article>
    </li>
    {% endfor %}
  </ol>
</div>
