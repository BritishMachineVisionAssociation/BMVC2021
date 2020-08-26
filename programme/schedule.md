---
layout: default_sparse
title: Conference Schedule
permalink: /programme/schedule/
index: 0
---

Details of the conference timetable over the four days are provided below. <strong>Please note that papers for poster presentation are allocated a specific day and will be presented during both morning and afternoon sessions along with the oral papers for the sessions on the same day.</strong>

<div class="row pl-2 pr-2 pt-2 pb-2 mx-auto justify-content-center">

	<table class="table table-striped table-bordered" style="max-width: 1000px;">
{% for day in site.data.schedule.schedule %}
	  	<thead class="thead-dark">
		  	<!--<tr><th scope="col" colspan="4">{{ day.day }}</th></tr>
		    <tr><th scope="col">Session</th>
		        <th scope="col">UK Time<br>(UTC + 1)</th>
		        <th scope="col">EDT Time<br>(UTC - 4)</th>
		        <th scope="col">CST Time<br>(UTC + 8)</th>
		    </tr>-->
		    <tr><th scope="col">{{ day.day }}</th>
		        <th scope="col" style="text-align: center;">UK BST<br>(UTC + 1)</th>
		        <th scope="col" style="text-align: center;">Eastern DT<br>(UTC - 4)</th>
		        <th scope="col" style="text-align: center;">China ST<br>(UTC + 8)</th>
		    </tr>
	    </thead>
        <tbody>
        	{% for session in day.contents %}
        		{% capture start-mins %}{{ session.start-time | split: ":" | last }}{% endcapture %}
        		{% capture end-mins %}{{ session.end-time | split: ":" | last }}{% endcapture %}
            <tr >
                <td><a class="anchor" id="session-id-{{session.session-id}}"></a>
                	{% if session.poster-session-id %}<a class="anchor" id="poster-session-id-{{session.poster-session-id}}"></a>{% endif %}
                	{% if session.keynote-id %}
                		{% assign keynote-details = site.data.programme.keynotes | where: "id", session.keynote-id | first %}
                		<a href="{{site.baseurl}}/programme/keynotes/#{{session.keynote-id}}">Keynote: {{ keynote-details.name }}</a><br><strong>{{keynote-details.title}}</strong>
                	{% elsif session.title %}
                		<a href="{{site.baseurl}}/programme/accepted-papers/#session-id-{{session.session-id}}">{{-session.session-}}</a><br><strong>{{-session.title-}}</strong>
                	{% else %}
                		<a href="{{site.baseurl}}/programme/accepted-papers/#session-id-{{session.session-id}}">{{ session.session }}</a>
                	{% endif %}
            	</td>
                <td style="text-align: center;">
                	{{ session.start-time | append: ":" | append: start-mins | date: "%H:%M" }} - 
                    {{ session.end-time   | append: ":" | append: end-mins | date: "%H:%M" }}</td>
                <td style="text-align: center;">
                	{{ session.start-time | plus: -5 | append: ":" | append: start-mins | date: "%H:%M" }} - 
                    {{ session.end-time   | plus: -5 | append: ":" | append: end-mins | date: "%H:%M" }}</td>
                <td style="text-align: center;">
                	{{ session.start-time | plus: 7 | modulo: 24 | append: ":" | append: start-mins | date: "%H:%M" }} - 
                    {{ session.end-time   | plus: 7 | modulo: 24 | append: ":" | append: end-mins | date: "%H:%M" }}</td>
            </tr>
            {% endfor %}
        </tbody>
        <tbody >
        	
        </tbody>
{% endfor %}
    </table>

</div>




