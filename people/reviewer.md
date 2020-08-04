---
layout: default_sparse
title: Reviewers
permalink: /people/reviewers
---

The conference [organisers]({{site.baseurl}}{% link people/organisers.md %}) would like to extend their gradititude to all the reviewers who worked very hard to review and discuss all the conference submissions.

<div class="row justify-content-around pl-4 pr-4">

{% for person in site.data.people.reviewers %}
    <div class="col-3"><!--col-6 col-md-4 col-lg-3">-->
        <div class="text-center">
            <p class="">{{ person.name }}</p>
        </div>
    </div>
{% endfor %}

</div>

