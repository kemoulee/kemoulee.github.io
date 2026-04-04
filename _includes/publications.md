<h2>Selected Publications <small>(* = Equal Contribution)</small></h2>

<div class="publications">
  <ol class="bibliography">
    {% for link in site.data.publications.main %}
    <li class="publication-entry">
      <article class="pub-row{% unless link.image %} pub-row--text-only{% endunless %}">
        {% if link.image %}
        <div class="pub-media">
          <img src="{{ link.image }}" class="teaser" alt="{{ link.title | strip_html }}">
          {% if link.conference_short %}
          <abbr class="badge">{{ link.conference_short }}</abbr>
          {% endif %}
        </div>
        {% endif %}

        <div class="pub-copy">
          <div class="title">
            {% if link.pdf %}
            <a href="{{ link.pdf }}" target="_blank" rel="noopener">{{ link.title }}</a>
            {% else %}
            {{ link.title }}
            {% endif %}
          </div>
          <div class="author">{{ link.authors }}</div>
          <div class="periodical"><em>{{ link.conference }}</em></div>

          <div class="links">
            {% if link.pdf %}
            <a href="{{ link.pdf }}" class="pub-badge pub-badge--pdf" target="_blank" rel="noopener">PDF</a>
            {% endif %}
            {% if link.code %}
            <a href="{{ link.code }}" class="pub-badge pub-badge--link" target="_blank" rel="noopener">Code</a>
            {% endif %}
            {% if link.page %}
            <a href="{{ link.page }}" class="pub-badge pub-badge--link" target="_blank" rel="noopener">Project Page</a>
            {% endif %}
            {% if link.bibtex %}
            <a href="{{ link.bibtex }}" class="pub-badge pub-badge--link" target="_blank" rel="noopener">BibTeX</a>
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
      </article>
    </li>
    {% endfor %}
  </ol>
</div>
