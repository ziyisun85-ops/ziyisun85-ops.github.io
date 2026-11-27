<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<style>
@media screen and (max-width: 600px) {
  .publications ol.bibliography li .pub-row--contained-teaser {
    display: flex;
    flex-direction: column;
    align-items: stretch;
    gap: 12px;
    margin-inline: 15px;
  }

  .publications ol.bibliography li .pub-row--contained-teaser > .abbr,
  .publications ol.bibliography li .pub-row--contained-teaser > .col-sm-9 {
    box-sizing: border-box;
    width: 100%;
    min-width: 0;
    padding-inline: 0 !important;
  }

  .publications ol.bibliography li .pub-row--contained-teaser > .abbr {
    height: auto;
    margin: 0;
  }

  .publications ol.bibliography li .pub-row--contained-teaser .abbr .badge {
    display: none; /* The review status is already shown below the authors. */
  }

  .publications ol.bibliography li .pub-row--contained-teaser .teaser {
    display: block;
    width: 100%;
    height: auto;
    margin: 0;
    box-shadow: none;
  }
}
</style>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row{% if link.image_contain %} pub-row--contained-teaser{% endif %}">
  {% if link.image or link.video or link.conference_short %}
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if link.video %}
    <div class="teaser-video">
      <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" alt="">
      <div class="teaser-video-clip{% if link.video_crop_top %} crop-top{% endif %}">
        <video src="{{ link.video }}" poster="{{ link.image }}" autoplay muted loop playsinline preload="metadata" aria-label="{{ link.title | escape }}"></video>
      </div>
    </div>
    {% elsif link.image %}
    {% if link.image_contain %}
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" alt="{{ link.image_alt | escape }}" style="height:auto;max-width:100%;object-fit:contain">
    {% else %}
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
    {% endif %}
    {% endif %}
    {% if link.conference_short %}
    <abbr class="badge">{{ link.conference_short }}</abbr>
    {% endif %}
  </div>
  {% endif %}
  <div class="{% if link.image or link.video or link.conference_short %}col-sm-9{% else %}col-sm-12{% endif %}" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title">
        {% if link.paper %}
        <a href="{{ link.paper }}" target="_blank" rel="noopener">{{ link.title }}</a>
        {% elsif link.pdf %}
        <a href="{{ link.pdf }}">{{ link.title }}</a>
        {% elsif link.arxiv %}
        <a href="{{ link.arxiv }}" target="_blank" rel="noopener">{{ link.title }}</a>
        {% else %}
        {{ link.title }}
        {% endif %}
      </div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    {% if link.description %}<div class="manuscript-description">{{ link.description | escape }}</div>{% endif %}
    <div class="links">
      {% if link.paper %}
      <a href="{{ link.paper }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">Paper</a>
      {% endif %}
      {% if link.pdf %}
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if link.arxiv %}
      <a href="{{ link.arxiv }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">arXiv</a>
      {% endif %}
      {% if link.code %}
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.page %}
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
      {% endif %}
      {% if link.project %}
      <a href="{{ link.project }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project</a>
      {% endif %}
      {% if link.notes %}
      <strong> <i style="color:#e74d3c">{{ link.notes }}</i></strong>
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

<h3 style="margin: 18px 0 8px;">Patents and Software</h3>

<ul style="margin-top: 0;">
  <li><strong>Invention Patent:</strong> A High-Stability PTO System for Duck-Type Wave Energy Converters. <em>First student inventor.</em></li>
  <li><strong>Software Copyright:</strong> Underwater Polarized Light Field Prediction Software for Biomimetic Navigation V1.0 (Registration No. 2024SR0140235).</li>
</ul>
