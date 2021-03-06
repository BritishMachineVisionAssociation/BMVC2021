---
layout: default_miniconf
title: Papers Visualisation
permalink: /conference/papers-visualisation/
index: 20
---


<!-- User Overrides -->
     

<div class="container">
  <!-- Tabs -->
  <div class="tabs">
        
  	<ul class="nav nav-pills justify-content-center">
  		<li class="nav-item">
  			<a class="nav-link text-muted" href="{{site.baseurl}}/conference/schedule/">Schedule</a>
  		</li>
  		<li class="nav-item">
		        <a class="nav-link text-muted" href="{{site.baseurl}}/conference/announcements/">Announcements</a>
		    </li>
  		<li class="nav-item">
        <a class="nav-link text-muted" href="{{site.baseurl}}/conference/livestream/">Livestream</a>
    </li>
  		<li class="nav-item">
  			<a class="nav-link text-muted" href="{{site.baseurl}}/conference/papers/">Papers</a>
  		</li>
  		<li class="nav-item active">
  			<a
  			class="nav-link text-muted active"
  			data-toggle="tab"
  			href="#"
  			role="tab"
  			aria-controls="nav-home"
  			aria-selected="true"
  			>Visualization
  		</a>
  	</li>
  	<li class="nav-item">
  		<a class="nav-link text-muted" href="{{site.baseurl}}/conference/chat/">Discussion</a>
  	</li>
  </ul>


      </div>
      <!-- Content -->
      <div class="content">
        
<div class="container-lg" id="container" style="padding-top: 20px;">
  <div class="row py-3">
    <div class="col-12 col-sm-6 col-lg-4">
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
      class="col-12 col-sm-6 col-lg-4 text-center"
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
          />
          title
        </label>
        <label
          class="btn btn-outline-secondary active"
          data-tippy-content="Search for papers from specific authors"
        >
          <input
            type="radio"
            name="options"
            value="authors"
            autocomplete="off"
            checked
          />
          author
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
      </div>
    </div>
  </div>
  <div class="row py-3" style="margin-top: 10px; text-align: center;">
    <div class="card" style="margin-right: -40px;">
      <div class="card-header">
        <div id="outer_svg" style="display: inline-block; vertical-align: top;">
          <svg class="plot" style="display: block;"></svg>
        </div>
        <div
          class="results"
          style="display: inline-block; vertical-align: top; text-align: left;"
        >
          <div style="display: block; overflow-y: auto;" id="table_info">
            <div id="explain_text_plot">
              <p>
                Each dot represents a paper. They are arranged by a measure of
                similarity.
              </p>
              <p>If you <b>hover</b> over a dot, you see the related paper.</p>
              <p>
                If you <b>click</b> on a dot, you go to the related paper page.
              </p>
              <p>
                You can <b>search</b> for papers by author, keyword, or title
              </p>
              <p><b>Drag a rectangle </b> to summarize an area of the plot.</p>
            </div>
            <div id="summary_selection" style=""></div>
            <div style="overflow-y: auto; bottom: 0; margin-top: 5pt;">
              <div id="sel_papers"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<script src="{{site.baseurl}}/static/js/little_helpers.js"></script>
<script src="{{site.baseurl}}/static/js/persistor.js"></script>
<script src="{{site.baseurl}}/static/js/paper_vis.js"></script>

<script>
  $(document).ready(function () {
    start();
    tippy("[data-tippy-content]", { trigger: "mouseenter focus" });
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
<script src="{{site.baseurl}}/static/js/gdpr_cookies.js"></script>

