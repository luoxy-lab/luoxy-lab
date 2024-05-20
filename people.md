---
title: People
permalink: /people/
---

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign role_array = "pi|postdoc|gradstudent|researchstaff|visiting|others|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'postdoc' %}
<h3>Postdoctoral Fellows</h3>
 {% elsif role == 'pi' %}
<h3>Principal Investigator</h3>
 {% elsif role == 'gradstudent' %}
<h3>Graduate Students</h3>
 {% elsif role == 'researchstaff' %}
<h3>Research Staff</h3>
 {% elsif role == 'visiting' %}
<h3>Visiting Scholars</h3>
 {% elsif role == 'others' %}
<h3>Alumni Members</h3>
 {% elsif role == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

{% if role != 'alumni' %}
<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains role %}
      <div class="list-item-people">
        <p class="list-post-title">
          {% if profile.avatar %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
          {% else %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
          {% endif %}
          <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
        </p>
      </div>    
    {% endif %}
  {% endfor %}
<hr>
</div>

{% endif %}
{% endfor %}

<div class="content list people">
<h3>Alumnus</h3>
<table>
  <thead>
    <tr>
      <th style="text-align: center;">Who are they</th>
      <th style="text-align: center;">When were they here</th>
      <th style="text-align: center;">Where they went</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://scholar.google.com/citations?hl=en&user=4sXuGXAAAAAJ">Yutao Hu</a></td>
      <td>Graduate Student (2021-2023)</td>
      <td>Postdoc, The University of Hong Kong</td>
    </tr>
    <tr>
      <td>Sen Li</td>
      <td>Graduate Student (2017-2023)</td>
      <td></td>
    </tr>
    <tr>
      <td>Yalin Li</td>
      <td>Graduate Student (2021-2023)</td>
      <td>美团</td>
    </tr>
    <tr>
      <td>Peixin Gan</td>
      <td>Graduate Student (2021-2023)</td>
      <td></td>
    </tr>
    <tr>
      <td>Chengxi Wu</td>
      <td>Graduate Student (2020-2022)</td>
      <td>理想</td>
    </tr>
    <tr>
      <td>Yang Yu</td>
      <td>Graduate Student (2020-2022)</td>
      <td></td>
    </tr>
  </tbody>
</table>
<hr>
<br>
</div>



