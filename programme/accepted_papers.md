---
layout: default_sparse
title: Accepted Papers
permalink: /programme/accepted-papers/
---

{% assign sorted_papers = site.data.camera_ready.papers | sort: "order" %}

<div class="row pl-2 pr-2 pt-2 pb-2 mx-auto justify-content-left">
	<table class="table table-striped table-bordered" style="max-width: 1000px;">
		<tbody>
		{% for paper in sorted_papers %}
		<tr id="paper-{{paper.id}}">
			<td class="text-center"><strong>{{paper.order}}</strong><br>[{{paper.id}}]<br>{{paper.session_id}}</td>
			<td>
				<strong>{{paper.title}}</strong><br>{{paper.all_authors}}<br>
				{% if paper.oral_session > 0 %}<a class="btn btn-primary btn-sm" href="{{site.baseurl}}{% link programme/schedule.md %}#session-id-{{paper.session_id}}" role="button">Oral Session {{paper.oral_session}}</a>&nbsp;{% endif %}
				<a class="btn btn-secondary btn-sm" href="{{site.baseurl}}{% link programme/schedule.md %}#poster-session-id-{{paper.poster_session}}" role="button">Poster Session {{paper.poster_session}}</a>
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
