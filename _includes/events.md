## Events

<p>Interviews, outreach, and other moments I am glad to have shared.</p>

<div class="event-list">
{% for event in site.data.events %}
  <article class="event-card">
    <div class="event-thumb">
      <img src="{{ event.image }}" alt="{{ event.image_alt | escape }}" width="720" height="405" loading="lazy">
    </div>
    <div class="event-head">
      <div class="event-meta">
        <span class="event-date">{{ event.date }}</span>
        <span class="event-type">{{ event.type }}</span>
        {% if event.source %}<span class="event-source">{% if event.source_icon %}<i class="{{ event.source_icon }}" aria-hidden="true"></i> {% endif %}<span class="event-source-label">{{ event.source }}</span></span>{% endif %}
      </div>
      <h3 class="event-title"><a href="{{ event.link }}" target="_blank" rel="noopener">{{ event.title }}</a></h3>
    </div>
    <p class="event-desc">{{ event.description }}</p>
  </article>
{% endfor %}
</div>
