---
title: People
permalink: /people/
---

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign role_array = "pi|gradstudent|researchstaff|visiting|others|alumni" | split: "|" %}

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
<h3>Honorary Members</h3>
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
</div>
<hr>

{% else %}

<br>

| Who are they | When were they here | Where they went |
| :------------- |:-------------| :-----------|
| [Steve Antos](http://kordinglab.com/people/steve_antos/index.html) | Graduate Student (2012 - 2019) | - |
| [Sofia Triantafillou](https://www.dbmi.pitt.edu/node/54091) | Postdoc (2016 - 2018) | Asst Prof. at University of Pittsburgh |
| [Gaiqing Kong](https://gaiqingkong.github.io/) | Visiting Scholar (2016 - 2018) | Postdoc at UCL |
| Claire Chambers | Postdoc (2015 - 2018) | - |
| [Josh Glaser](https://jglaser2.github.io) | Graduate Student (2012 - 2018) | Postdoc at Columbia
| [Daniel Wood](http://kordinglab.com/people/daniel_wood/index.html) | Postdoc (2014 - 2017) | Postdoc at Northwestern |
| [Bahram Yoosefizonooz](http://kordinglab.com/people/bahram_yoosefizonooz/index.html) | Visiting (2017) | Postdoc at U Montreal
| Elahe Arani | Visiting (2017) | Postdoc at U Montreal
| [Luca Lonini](http://kordinglab.com/people/luca_lonini/index.html) | Postdoc (2017) | Postdoc with Arun at Northwestern U
| [Ravi Garg](http://kordinglab.com/people/ravi_garg/index.html) | Undergrad Research | Researcher at Northwestern U
| [Sohrob Saeb](http://kordinglab.com/people/sohrob_saeb/index.html) | Postdoc (2014 - 2017) | Neuroscience in Bay Area
| [Eva Dyer](http://kordinglab.com/people/eva_dyer/index.html) | Postdoc (2017) | Assistant Professor, Dept of Biomedical Engineering at Georgia Tech and Emory U
| [Pavan Ramkumar](http://kordinglab.com/people/pavan_ramkumar/index.html) | Postdoc (2017) | A secret startup in bay area
| [Ted Cybulski](http://kordinglab.com/people/ted_cybulski/index.html) | Graduate Student (2012 - 2017) | Medical resident at Northwestern |
| Xuelong Zhao | Postdoc (2016) | Postdoc at [Brian Litt  lab](http://littlab.seas.upenn.edu/), U Penn
| [Pat Lawlor](http://kordinglab.com/people/pat_lawlor/index.html) | Graduate student (2016) | Northwestern Medical school
| [Hugo Fernandes](http://kordinglab.com/people/hugo_fernandes/index.html) | Postdoc (2016) | [rockets of awesome](https://www.rocketsofawesome.com/)
| [Torben Noto](http://kordinglab.com/people/torben_noto/index.html) | Rotation Student (2016) | Northwestern
| [Vivek Sagar](http://kordinglab.com/people/vivek_sagar/index.html) | Rotation Student (2016) | Northwestern
| [David Brandfonbrener](http://kordinglab.com/people/david_brandfonbrener/index.html) | Visiting Scholar (2016)  | PhD Student, Yale university

{% endif %}
{% endfor %}
