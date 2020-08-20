---
layout: default_sparse
title: Accepted Papers
permalink: /programme/accepted-papers/
index: 20
---

{% assign sorted-papers = site.data.camera_ready.papers | sort: "order" %}

<div class="row pl-2 pr-2 pt-2 pb-2 mx-auto justify-content-left">
	<table class="table table-striped table-bordered" style="">
		<tbody>
		<a style="visibility: hidden;">{% decrement current-session %}</a>
		{% for paper in sorted-papers %}
		{% if current-session != paper.session_id %}
			</tbody><thead class="thead-dark"><tr><th colspan="2">
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
				{% if paper.oral_session > 0 %}<a class="btn btn-primary btn-sm" href="{{site.baseurl}}{% link programme/schedule.md %}#session-id-{{paper.session_id}}" role="button">Oral Session {{paper.oral_session}}</a>&nbsp;{% endif %}
				<a class="btn btn-primary btn-sm" href="{{site.baseurl}}{% link programme/schedule.md %}#poster-session-id-{{paper.poster_session}}" role="button">Poster Session {{paper.poster_session}}</a>
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