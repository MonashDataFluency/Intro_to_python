---
layout: workshop      # DON'T CHANGE THIS.
root: .
#carpentry: "dc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "Monash University"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Sir Louis Matheson Library, Clayton, Australia"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "au"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: ""       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use http://www.latlong.net/)
humandate: "March 23, 2018"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "1:00 pm - 5:00 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2018-03-23      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2018-03-23        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Anup Shah", "Kiril Tsyganov"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Simon Michnowicz", "Micheal See"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["anup.shah@monash.edu", "kirill.tsyganov@monash.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% comment %}
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 align="center"> Introduction to Python </h2>

<h4>This hands-on workshop aims to equip participants with the fundamentals of programming and give them skills needed to computational analysis approaches to research questions </h4>

<h2 id="general">General Information</h2>
<p>
  The workshop will be taught in a similar style to Data Carpentry workshops. <a href="{{site.dc_site}}">Data Carpentry</a>'s mission
   is to help scientists and engineers get more research done in less
   time and with less pain by teaching them basic lab skills for
   scientific computing.
</p>
{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% endcomment %}
{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
{% comment %}
{% if page.carpentry == "swc" %}
 # {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}
{% endcomment %}

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}

<p>
<strong> Who:</strong>
The course is aimed at begginers to programming.
<strong>You don't need to have any previous knowledge of the tools that will
    be presented at the workshop.</strong>
</p>

{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Setup Requirements:</strong> BYO Laptop. No software installation required. Tools and material will be provided on the day.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>
{% endcomment%}
{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<div class="row">
  <div class="col-md-6">
    <h3>Schedule</h3>
    <table class="table table-striped">
      <tr> <td>13:00</td>  <td>Welcome and Setup</td> </tr>
      <tr> <td>13:30</td> <td>Session 1</td> </tr>
      <tr> <td>15:00</td>  <td>Break</td> </tr>
      <tr> <td>15:30</td>  <td>Session 2</td> </tr>
      <tr> <td>16:45</td>  <td>Wrap-up</td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Syllabus</h3>
    <ul>
      <li>Introduction to Python</li>
      <li>Working with Data</li>
      <li>Introduction to Libraries</li>
      <li>Indexing and Slicing DataFrames</li>
      <li>Workflows and Automation</li>
      <li>Ploting in Python</li>
      <li><a href="datacarpentry.github.io/python-ecology-lesson/reference/">Reference...</a></li>
    </ul>
  </div>    
</div>
