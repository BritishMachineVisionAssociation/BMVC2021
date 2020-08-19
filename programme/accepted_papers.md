---
layout: default_sparse
title: Accepted Papers
permalink: /programme/accepted-papers/
---

<div class="row pl-2 pr-2 pt-2 pb-2 mx-auto justify-content-left">
	<table class="table table-striped table-bordered" style="max-width: 1000px;">
		<tbody>
		{% for paper in site.data.camera_ready.papers %}
		<tr id="paper-{{paper.id}}">
			<td>[{{paper.id}}]</td>
			<td><strong>{{paper.title}}</strong><br>{{paper.all_authors}}</td>
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
