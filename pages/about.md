---
  layout: code_for_new_orleans
  title: About Code for New Orleans
  menu_tag: About
  category: main_nav
  leadership:
    -
      name: Ryan Harvey
      title: Co-Captain and Data Wrangler
      image: /img/people/ryan.jpg
      bio: |
        Ryan Harvey got involved in the civic tech and open government movements from their start, helping to start the Open Government and Open Data programs at Social Security Administration between 2009 and 2012, and helping to coordinate Data.gov submissions for the White House Office of Management and Budget while working in Budget Systems from 2012 through 2016. While living in the DC area, Ryan was an active participant in the civic tech community, including the Data Community DC and Code for DC.

        Ryan grew up in the New Orleans area, graduated from Loyola University in uptown, and works remotely as a data engineer for TED Conferences. He also serves as an adjunct lecturer in computer science at Loyola. Ryan lives in a multi-generational home in Mandeville, and has two amazing kids.
    -
      name: Marc Cenac
      title: Co-Captain and Community Organizer
      image: https://baconmockup.com/200/300/
      bio: |
        Marc Cenac started Code for New Orleans in 2016 in an effort to be more involved in creating the life he wanted in New Orleans. Since then, he's taken part in numerous projects to improve the city.
        
        Marc grew up here in New Orleans, attended college at Loyola University in uptown, and works remotely from New Orleans as a software engineer for Boundless Spatial. Marc participated in the Civic Leadership Academy program run by the City of New Orleans in 2017.
    -
      name: Kris Gerig
      title: Storyteller
      image: /img/people/kris.jpg
      bio: |
        Kris Gerig first attended Code for New Orleans Meetups starting in late 2016 with an interest in geospatial analysis and mapping data for New Orelans neighborhoods. He spent over five years working as a data analyst for a Public Health nonprofit organization, and started working as a crime data analyst for the New Orleans Police Department in early 2018.
        Kris moved to New Orleans in 2010 for graduate school and later found a job and much later found a wife, who is a native of NOLA, so he's probably never leaving.
    -
      name: Ben Eckel
      title: Delivery Lead
      image: https://baconmockup.com/200/300/
      bio: |
        Bio of Ben Eckel...
---
Code for New Orleans is a group of local volunteers focused on making city services accessible and easy to use and improving the lives of residents.

We're a brigade of [Code for America](https://www.codeforamerica.org/), a national non-profit focused on civic activism with technology in local contexts across our nation.

## Events
We meet monthly on the second Thursday of the month at 7:00 PM for Project Nights at Launch Pad on Poydras Street.

In addition, we host bigger events for days of action:

* National Day of Civic Hacking
* CodeAcross
* CityCamp
* International Open Data Day

## Leadership

{% for person in page.leadership %}
<div class="person">
  <div class="person-photo">
    <img src="{{ person.image }}" alt="Photo of {{ person.name }}" title="Photo of {{ person.name }}"/>
  </div>
  <div class="person-details">
    <p class="person-name">{{ person.name }}</p>
    <p class="person-title">{{ person.title }}</p>
    {{ person.bio | markdownify }}
  </div>
</div>
{% endfor %}
