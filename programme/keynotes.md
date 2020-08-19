---
layout: default_sparse
title: Keynotes
permalink: /programme/keynotes/
---

<div class="row justify-content-around pl-4 pr-4">

{% assign sorted_keynotes = site.data.programme.keynotes | sort: "id" %}

{% for person in sorted_keynotes %}
	{% capture keynote_day %}
		{% for day in site.data.schedule.schedule %}
			{% for session in day.contents %}
				{% if session.keynote-id == person.id %}
					{{ day.day }}
					{% assign details = session %}
				{% endif %}
			{% endfor %}
		{% endfor %}
	{% endcapture %}
	<div class="col-12" id="{{ person.id }}"><div class="row pb-2">
	    <div class="col-12 col-md-4 col-lg-3">
	        <div class="text-center">
	            <img src="{{ site.baseurl }}{{ person.img }}" class="rounded-circle img-fluid" style="max-width: 125px;">
	            <h4 class="pt-2"><a href="{{ person.url }}">{{ person.name }}</a></h4>
	            <p class=""><!--<span><b>{{ person.title }}</b></span><br/>-->
	            <span class=""><small>{{ person.job }}</small></span></p>
	        </div>
	    </div>
	    <div class="col-12 col-md-8 col-lg-9">
	        <div class="">
	            <h4 class="pt-1 text-center">{{ person.title }}</h4>
	            <p class="text-center mb-1"><small >({{keynote_day | strip}}: {{details.start-time}} - {{details.end-time}} BST)</small></p>
	            <p class="pb-2">{{ person.abstract }}</p>
	        </div>
	    </div>
	</div></div>
{% endfor %}

</div>

