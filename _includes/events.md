## Events

<p>Interviews, outreach, and other moments I am glad to have shared.</p>

<div class="event-list">
{% for event in site.data.events %}
  <article class="event-card">
    <div class="event-figure">
      <img src="{{ event.image }}" alt="{{ event.image_alt | escape }}" width="720" height="405" loading="lazy">
    </div>
    <div class="event-body">
      <div class="event-meta">{{ event.date }} · {{ event.type }}</div>
      <h3>{{ event.title }}</h3>
      <p>{{ event.description }}</p>
      <a class="event-link" href="{{ event.link }}" target="_blank" rel="noopener">{{ event.link_text | default: "View post" }}</a>
    </div>
  </article>
{% endfor %}
</div>
