---
layout: default_sparse
title: Conference Schedule
permalink: /programme/schedule/
---


<div class="row pl-2 pr-2 pt-2 pb-2 mx-auto justify-content-center">
{% for day in site.data.schedule.schedule %}
	<table class="table table-striped table-bordered" style="max-width: 750px;">

	  	<thead class="thead-dark">
		  	<!--<tr><th scope="col" colspan="4">{{ day.day }}</th></tr>
		    <tr><th scope="col">Session</th>
		        <th scope="col">UK Time<br>(UTC + 1)</th>
		        <th scope="col">EDT Time<br>(UTC - 4)</th>
		        <th scope="col">CST Time<br>(UTC + 8)</th>
		    </tr>-->
		    <tr><th scope="col">{{ day.day }}</th>
		        <th scope="col">UK Time<br>(UTC + 1)</th>
		        <th scope="col">EDT Time<br>(UTC - 4)</th>
		        <th scope="col">CST Time<br>(UTC + 8)</th>
		    </tr>
	    </thead>
        <tbody>
        	{% for session in day.contents %}
        		{% capture start-mins %}{{ session.start-time | split: ":" | last }}{% endcapture %}
        		{% capture end-mins %}{{ session.end-time | split: ":" | last }}{% endcapture %}
            <tr>
                <td>{{ session.session }}</td>
                <td>{{ session.start-time | append: ":" | append: start-mins | date: "%H:%M" }} - 
                    {{ session.end-time   | append: ":" | append: end-mins | date: "%H:%M" }}</td>
                <td>{{ session.start-time | plus: -5 | append: ":" | append: start-mins | date: "%H:%M" }} - 
                    {{ session.end-time   | plus: -5 | append: ":" | append: end-mins | date: "%H:%M" }}</td>
                <td>{{ session.start-time | plus: 6 | append: ":" | append: start-mins | date: "%H:%M" }} - 
                    {{ session.end-time   | plus: 6 | append: ":" | append: end-mins | date: "%H:%M" }}</td>
            </tr>
            {% endfor %}
        </tbody>
    </table>
{% endfor %}
</div>




