---
layout: default_sparse
title: Paper Awards
permalink: /programme/paper-awards/
index: 25
---

We are delighted to announce the following paper awards. Papers were nominated by (non-conflicted) area chairs and programme chairs to create a shortlist. This shortlist was then sent to an independent awards committee who made the final recommendations.

The BMVC Awards Committee was composed of Prof. Lourdes Agapito (University College London), Dr Dima Damen (University of Bristol) and Dr Andrew Fitzgibbon (Microsoft Research).

{% assign sorted-awards = site.data.prizes.prizes | reverse %}

{% for item in sorted-awards %}

{% assign paper = site.data.camera_ready.papers | where: "id", item.id | first %}

<h3 class="mt-3 mb-2">{{item.award}}</h3>

<p class="pb-3"><strong>{{paper.title}}</strong><br>{{paper.all_authors}}<br>
<a class="btn btn-primary btn-sm mt-1" href="{{site.baseurl}}/conference/papers/{{item.link}}.html" role="button">Paper Page</a>
</p>

{% endfor %}

### Sponsors

<p class="mb-3" align="center"><strong>We are very grateful to our sponsors for supporting the conference and awards this year:</strong></p>

{% assign grouped_sponsors = site.data.sponsors.sponsors | group_by:"type" %}
<!--<div class="container mb-3">-->
{% for group in grouped_sponsors %}
<div class="row mt-1 mb-1 justify-content-around align-items-center">
  <div class="col-12 mt-3 mb-3">
    <h3>{{-group.name-}}&nbsp;Sponsors</h3>
  </div>
{% for item in group.items %}
  <div class="col mb-1 text-center">
    <a href="{{item.url}}"><img src="{{ site.baseurl }}/assets/images/sponsors/{{item.logo}}" class="img-fluid" alt="{{ item.id }}" style="max-height: 100px;"></a>
  </div>
{% endfor %}
</div>
{% endfor %}
<!--</div>-->

