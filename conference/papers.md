---
layout: default_sparse
title: Papers
permalink: /conference/papers/
index: 0
---




<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.4.0/dist/umd/popper.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tippy.js@6/dist/tippy-bundle.umd.min.js"></script>

<script src="static/js/icons.js"></script>
<script src="https://cdn.jsdelivr.net/npm/js-cookie@2/src/js.cookie.min.js"></script>











<!-- User Overrides -->
 

<div class="container">
  <!-- Tabs -->
  <div class="tabs">
    
	<ul class="nav nav-pills justify-content-center">
	<li class="nav-item active">
	<a
	  class="nav-link text-muted active"
	  data-toggle="tab"
	  href="#tab-browse"
	  role="tab"
	  aria-controls="nav-home"
	  aria-selected="true"
	  >Browse
	</a>
	</li>
	<li class="nav-item">
	<a class="nav-link text-muted" href="paper_vis.html">Visualization</a>
	</li>
	</ul>


	  </div>
	  <!-- Content -->
	  <div class="content">
	    
	<div class="row p-3"></div>

	<!-- Session -->
	<div class="row d-none session_notice">
	<div
	class="alert alert-warning alert-dismissible fade show col-12"
	role="alert"
	>
	Showing papers for
	<span id="session_name" style="font-weight: bold;"></span>.
	<button
	  type="button"
	  class="close remove_session"
	  data-dismiss="alert"
	  aria-label="Close"
	>
	  <span aria-hidden="true">&times;</span>
	</button>
	</div>
</div>

<!-- Buttons -->
<div class="row">
<div class="col-12 col-sm-12 col-md-6 col-lg-4">
<div class="input-group mb-3">
  <input
    type="text"
    class="form-control typeahead_all"
    placeholder="Search"
  />
  <div class="input-group-append">
    <button
      class="btn btn-outline-secondary typeahead_all_clear"
      type="button"
    >
      &times;
    </button>
  </div>
</div>
</div>
<div
class="col-12 col-sm-6 col-md-6 col-lg-4 text-center"
style="margin-bottom: 10px;"
>
<div class="btn-group btn-group-toggle filter_option">
  <label
    class="btn btn-outline-secondary"
    data-tippy-content="Search for papers titles"
  >
    <input
      type="radio"
      name="options"
      value="titles"
      autocomplete="off"
      checked
    />
    title
  </label>
  <label
    class="btn btn-outline-secondary"
    data-tippy-content="Search for papers with specific keywords"
  >
    <input
      type="radio"
      name="options"
      value="keywords"
      autocomplete="off"
    />
    keyword
  </label>
  <label
    class="btn btn-outline-secondary active"
    data-tippy-content="Search for papers from specific authors"
  >
    <input type="radio" name="options" value="authors" autocomplete="off" />
    author
  </label>
</div>
</div>
<div class="col-12 col-lg-4">
<button class="btn btn-outline-secondary reshuffle">shuffle</button>
<div class="float-right">
  <div
    class="btn-group btn-group-toggle render_option"
    data-toggle="buttons"
  >
    <label class="btn btn-outline-secondary active">
      <input type="radio" name="options" value="list" autocomplete="off" />
      list
    </label>
    <label class="btn btn-outline-secondary active">
      <input
        type="radio"
        name="options"
        value="compact"
        autocomplete="off"
        checked
      />
      compact
    </label>
    <label class="btn btn-outline-secondary">
      <input
        type="radio"
        name="options"
        value="detail"
        autocomplete="off"
      />
      detail
    </label>
  </div>
</div>
</div>
</div>

<!-- Cards -->
<div class="cards row"></div>
<script src="static/js/little_helpers.js"></script>
<script src="static/js/lazy_load.js"></script>
<script src="static/js/persistor.js"></script>
<script src="static/js/papers.js"></script>
<script>
$(document).ready(function () {
tippy("[data-tippy-content]", { trigger: "mouseenter focus" });
start();
});
</script>


  </div>
</div>
    
    

<div
  class="gdpr bg-dark text-light"
  style="padding: 10pt; position: fixed; bottom: 0; display: none;"
>
  We use cookies to store which papers have been visited.
  <div class="gdpr-btn btn btn-sm btn-info" style="margin-left: 15pt;">
    I agree
  </div>
</div>
<script src="static/js/gdpr_cookies.js"></script>









{% assign sorted-papers = site.data.camera_ready.papers | sort: "order" %}

<div class="row pl-2 pr-2 pt-2 pb-2 mx-auto justify-content-left">
	<table class="table table-striped table-bordered" style="">
		<tbody>
		<a style="visibility: hidden;">{% decrement current-session %}</a>
		{% for paper in sorted-papers %}
		{% if current-session != paper.session_id %}
			</tbody><thead class="thead-dark"><tr><th colspan="2">
				<a class="anchor" id="session-id-{{paper.session_id}}"></a>
				{% capture which-day %}
					{% for day in site.data.schedule.schedule %}
						{% for session in day.contents %}
							{% if session.session-id == paper.session_id %}
								{{-day.day-}}{% break %}
							{% endif %}
						{% endfor %}
					{% endfor %}
				{% endcapture %}
				{% if paper.oral_session %}
					{% capture title %}
						{% for day in site.data.schedule.schedule %}
							{% for session in day.contents %}
								{% if session.session-id == paper.session_id %}
									{{ session.title }}
								{% endif %}
							{% endfor %}
						{% endfor %}
					{% endcapture %}
					{{-which-day-}}: Oral Session {{paper.oral_session}}: {{ title }}
				{% else %}
					{{-which-day-}}: Poster Session {{paper.poster_session}}
				{% endif %}
			</th></tr></thead><tbody>
			<a style="visibility: hidden;">{% increment current-session %}</a>
		{% endif %}
		<tr id="paper-{{paper.id}}">
			<td class="text-center"><strong>{{paper.order}}</strong><br><span style="opacity: 0.5;">[{{paper.id}}]</span></td>
			<td>
				<strong>{{paper.title}}</strong><br>{{paper.all_authors}}<br>
				<a class="btn btn-info btn-sm mt-1" href="https://www.bmvc2020-conference.com/assets/{{paper.paper}}" role="button">Paper</a>&nbsp;
				{% if paper.supp > '' %}<a class="btn btn-info btn-sm mt-1" href="https://www.bmvc2020-conference.com/assets/{{paper.supp}}" role="button">Supplemental</a>&nbsp;{% endif %}
				{% if paper.supp2 > '' %}<a class="btn btn-info btn-sm mt-1" href="https://www.bmvc2020-conference.com/assets/{{paper.supp2}}" role="button">Supplemental</a>&nbsp;{% endif %}
				{% if paper.code > '' %}<a class="btn btn-info btn-sm mt-1" href="{{paper.code}}" role="button">Code</a>&nbsp;{% endif %}
				{% if paper.oral_session > 0 %}<a class="btn btn-primary btn-sm mt-1" href="{{site.baseurl}}{% link programme/schedule.md %}#session-id-{{paper.session_id}}" role="button">Oral Session {{paper.oral_session}}</a>&nbsp;{% endif %}
				<a class="btn btn-primary btn-sm mt-1" href="{{site.baseurl}}{% link programme/schedule.md %}#poster-session-id-{{paper.poster_session}}" role="button">Poster Session {{paper.poster_session}}</a>
			</td>
		</tr>
		{% endfor %}
		</tbody>
	</table>
</div>

<!--
{% for paper in site.data.camera_ready.papers %}

<p id="paper-{{paper.id}}">
	<span>[{{paper.id}}]</span>
	<span><strong>{{paper.title}}</strong></span><br>
	<span>{{paper.all_authors}}</span>
</p>

{% endfor %}
-->