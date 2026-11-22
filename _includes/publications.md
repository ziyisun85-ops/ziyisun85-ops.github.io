<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if link.video %}
    <div class="teaser-video">
      <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" alt="">
      <div class="teaser-video-clip{% if link.video_crop_top %} crop-top{% endif %}">
        <video src="{{ link.video }}" poster="{{ link.image }}" autoplay muted loop playsinline preload="metadata" aria-label="{{ link.title | escape }}"></video>
      </div>
    </div>
    {% elsif link.image %}
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
    {% endif %}
    {% if link.conference_short %}
    <abbr class="badge">{{ link.conference_short }}</abbr>
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
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
