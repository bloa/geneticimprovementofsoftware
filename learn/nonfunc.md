---
active: learn
---

# Survey on Improvement of Non-Functional Properties of Software

Search operates within all fields available.
Magic queries include <a href="#" onclick="force('venue=&quot;IEEE TEVC&quot;')">venues</a>, <a href="#" onclick="force('type=Workshop')">type of venue</a>, or <a href="#" onclick="force('year=2020')">publication year</a>.
Clicking on data links in the table will query all similar entries.

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon1">Query:</span>
      </div>
  <input type="text" id="search" class="form-control" placeholder="..." onkeyup="search()">
  <div class="input-group-append">
    <input type="reset" class="btn btn-outline-secondary" onclick="force('')">
  </div>
</div>

<div>
  Showing <span id="counter">{{ site.data.survey.nonfunc.size }}</span> of {{ site.data.survey.nonfunc.size }} entries.
</div>

<div class="custom-control custom-switch custom-control-inline">
  <input class="custom-control-input" type="checkbox" role="switch" id="flexSwitchCheckSource" onclick="$('.hid1').toggle();cloneWidth();" checked>
  <label class="custom-control-label" for="flexSwitchCheckSource">Source</label>
</div>
<div class="custom-control custom-switch custom-control-inline">
  <input class="custom-control-input" type="checkbox" role="switch" id="flexSwitchCheckVenue" onclick="$('.hid2').toggle();cloneWidth();" checked>
  <label class="custom-control-label" for="flexSwitchCheckVenue">Venue</label>
</div>
<div class="custom-control custom-switch custom-control-inline">
  <input class="custom-control-input" type="checkbox" role="switch" id="flexSwitchCheckAuthors" onclick="$('.hid25').toggle();cloneWidth();">
  <label class="custom-control-label" for="flexSwitchCheckAuthors">Authors</label>
</div>
<div class="custom-control custom-switch custom-control-inline">
  <input class="custom-control-input" type="checkbox" role="switch" id="flexSwitchCheckFitness" onclick="$('.hid3').toggle();cloneWidth();">
  <label class="custom-control-label" for="flexSwitchCheckFitness">Fitness</label>
</div>
<div class="custom-control custom-switch custom-control-inline">
  <input class="custom-control-input" type="checkbox" role="switch" id="flexSwitchCheckApproach" onclick="$('.hid4').toggle();cloneWidth();">
  <label class="custom-control-label" for="flexSwitchCheckApproach">Approach</label>
</div>
<div class="custom-control custom-switch custom-control-inline">
  <input class="custom-control-input" type="checkbox" role="switch" id="flexSwitchCheckBenchmark" onclick="$('.hid5').toggle();cloneWidth();">
  <label class="custom-control-label" for="flexSwitchCheckBenchmark">Benchmark</label>
</div>
<div class="custom-control custom-switch custom-control-inline">
  <input class="custom-control-input" type="checkbox" role="switch" id="flexSwitchCheckSoftware" onclick="$('.hid6').toggle();cloneWidth();">
  <label class="custom-control-label" for="flexSwitchCheckSoftware">Software properties</label>
</div>

<div class="wrapper1" style="overflow-x: scroll;">
    <div class="div1" style="width: 100%; height: 20px;">
    </div>
</div>
<div class="wrapper2">
<table id="survey" class="table table-responsive survey wrapper2" style="width: 100%; overflow: auto;">
  <thead>
    <tr>
      <th>Link</th>
      <th>Title</th>
      <th class="hid1">Source</th>
      <th class="hid2">Venue/Issue</th>
      <th class="hid2">Venue Type/Issue</th>
      <th class="hid2">Year</th>
      <th class="hid25">Authors</th>
      <th class="hid3">Fitness (primary)</th>
      <th class="hid3">Fitness (secondary)</th>
      <th class="hid3">Fitness (multi-objective)</th>
      <th class="hid4">Search</th>
      <th class="hid4">Approach</th>
      <th class="hid5">Benchmark name</th>
      <th class="hid5">Software name</th>
      <th class="hid6">Programming language</th>
      <th class="hid6">Code size</th>
      <th class="hid6">Platform</th>
    </tr>
  </thead>
  <tbody class="div2">{% for entry in site.data.survey.nonfunc %}
    <tr data-search="id={{ entry.id }}$ {{ entry.title | xml_escape }} {% for source in entry.source %}{{ source }} {% endfor %} venue={{ entry.venue }} venue_type={{ entry.venue_type }} year={{ entry.year }} {% for author in entry.author %}author={{ author }} {% endfor %}{% for fitness in entry.fitness %}fitness={{ fitness }} {% endfor %}{% for fitness in entry.fitness_secondary %}fitness={{ fitness }} {% endfor %} {% if entry.fitness_multi %}fitness_multi={{ entry.fitness_multi }}{% else %}fitness_multi=False{% endif %}{% if entry.type %}type={{ entry.type }} {% endif %} {% for search in entry.tool_search %}search={{ search }} {% endfor %} {% for approach in entry.tool_approach %}approach={{ approach }} {% endfor %} {% for bench in entry.software_set_name %}benchmark_set={{ bench }} {% endfor %} {% for soft in entry.software_name %}benchmark={{ soft }} {% endfor %} {% for lang in entry.software_lang %}lang={{ lang }} {% endfor %} {% for size in entry.software_size %}size={{ size }} {% endfor %} {% for platform in entry.software_platform %}platform={{ platform }} {% endfor %}">
      <td>{% if entry.doi %}<a class="badge badge-primary" target="_blank" href="{{ entry.doi }}">DOI</a>{% endif %} {% for url in entry.pdfs %}<a class="badge badge-success" target="_blank" href="{{ url }}">PDF</a> {% endfor %} {% for url in entry.url %}<a class="badge badge-warning" target="_blank" href="{{ url }}">URL</a> {% endfor %}</td>
      <td title="{{ entry.id }}">{% if entry.title %}{{ entry.title }}{% if entry.subtitle %} &mdash; <i>{{ entry.subtitle }}</i>{% endif %}{% endif %} <a target="_blank" href="{{ site.baseurl }}/learn/survey2?q={{ entry.id }}$" class="perma"><i class="fa fa-link" style="font-size: 0.75rem" aria-hidden="true"></i></a></td>
      <td class="hid1">{% for source in entry.source %}{% if forloop.first == false %}, {% endif %}<a href="#search" class="slink text-nowrap" onclick="force('&quot;{{ source }}&quot;')">{{ source }}</a>{% endfor %}</td>
      <td class="hid2"><a href="#search" class="slink" onclick="force('venue=&quot;{{ entry.venue }}&quot;')">{{ entry.venue }}</a></td>
      <td class="hid2"><a href="#search" class="slink" onclick="force('venue_type=&quot;{{ entry.venue_type }}&quot;')">{{ entry.venue_type }}</a></td>
      <td class="hid2">{% if entry.year %}<a href="#search" class="slink text-nowrap" onclick="force('year=&quot;{{ entry.year }}&quot;')">{{ entry.year }}</a>{% endif %}</td>
      <td class="hid25">{% for author in entry.author %}{% if forloop.first == false %}{% if forloop.last %}{% if forloop.index > 2 %},{% endif %} and {% else %}, {% endif %}{% endif %}<a href="#search" class="slink text-nowrap" onclick="force('author=&quot;{{ author }}&quot;')">{{ author }}</a>{% endfor %}</td>
      <td class="hid3">{% for fitness in entry.fitness %}<a href="#search" class="slink text-nowrap" onclick="force('fitness={{ fitness }}')">#{{ fitness }}</a> {% endfor %}</td>
      <td class="hid3">{% for fitness in entry.fitness_secondary %}<a href="#search" class="slink text-nowrap" onclick="force('fitness={{ fitness }}')">#{{ fitness }}</a> {% endfor %}</td>
      <td class="hid3">{% if entry.fitness_multi %}<a href="#search" class="slink text-nowrap" onclick="force('fitness_multi={{ entry.fitness_multi }}')">#{{ entry.fitness_multi }}</a>{% endif %}</td>
      <td class="hid4">{% for search in entry.tool_search %}<a href="#search" class="slink text-nowrap" onclick="force('search={{ search }}')">#{{ search }}</a> {% endfor %}</td>
      <td class="hid4">{% for approach in entry.tool_approach %}<a href="#search" class="slink text-nowrap" onclick="force('approach={{ approach }}')">#{{ approach }}</a> {% endfor %}</td>
      <td class="hid5">{% for benchmark_set in entry.software_set_name %}{% if forloop.first == false %}, {% endif %}<a href="#search" class="slink text-nowrap" onclick="force('benchmark_set=&quot;{{ benchmark_set }}&quot;')">{{ benchmark_set }}</a>{% endfor %}</td>
      <td class="hid5">{{ entry.software_nb }}: {% for benchmark in entry.software_name %}{% if forloop.first == false %}, {% endif %}<a href="#search" class="slink text-nowrap" onclick="force('benchmark=&quot;{{ benchmark }}&quot;')">{{ benchmark }}</a>{% endfor %}</td>
      <td class="hid6">{% for lang in entry.software_lang %}{% if forloop.first == false %}, {% endif %}<a href="#search" class="slink text-nowrap" onclick="force('lang={{ lang }}')">{{ lang }}</a>{% endfor %}</td>
      <td class="hid6">{% for size in entry.software_size %}{% if forloop.first == false %}, {% endif %}<a href="#search" class="slink text-nowrap" onclick="force('size={{ size }}')">{{ size }}</a>{% endfor %}</td>
      <td class="hid6">{% for platform in entry.software_platform %}{% if forloop.first == false %}, {% endif %}<a href="#search" class="slink text-nowrap" onclick="force('platform={{ platform }}')">{{ platform }}</a>{% endfor %}</td>
    </tr>{% endfor %}
  </tbody>
</table>
</div>


---


<script>
// https://stackoverflow.com/questions/3160277/jquery-table-sort
$('th').each(function (col) {
  $(this).hover(
    function () {$(this).addClass('focus');},
    function () {$(this).removeClass('focus');}
  );
  $(this).click(function () {
    if ($(this).is('.asc')) {
      $(this).removeClass('asc');
      $(this).addClass('desc selected');
      sortOrder = -1;
    } else {
      $(this).addClass('asc selected');
      $(this).removeClass('desc');
      sortOrder = 1;
    }
    $(this).siblings().removeClass('asc selected');
    $(this).siblings().removeClass('desc selected');
    var arrData = $('table').find('tbody >tr:has(td)').get();
    $.each(arrData, function (index, row) {
      $(row).data('sort', $(row).children('td').eq(col).text().toUpperCase());
    });
    arrData.sort(function (a, b) {
      var val1 = $(a).data('sort');
      var val2 = $(b).data('sort');
      if ($.isNumeric(val1) && $.isNumeric(val2))
        return sortOrder == 1 ? val1 - val2 : val2 - val1;
      else
        return (val1 < val2) ? -sortOrder : (val1 > val2) ? sortOrder : 0;
    });
    $.each(arrData, function (index, row) {
      $('tbody').append(row);
    });
  });
});

function search() {
  var chunks = $("input#search").val().toUpperCase().match(/(?:[^\s"]+|"[^"]*")+/g)
  if (chunks) {
    chunks = chunks.map(c => c.replace(/\"/g, ""));
  }

  var counter = 0
  $("tbody tr").each(function() {
    var s = $(this).data("search");
    var show = true;
    if (chunks) {
      for (c of chunks) {
        if (s.toUpperCase().indexOf(c) == -1) {
          show = false;
        }
      }
      if (show) {
        $(this).show();
        counter += 1;
      } else {
        $(this).hide();
      }
    } else {
      $(this).show();
      counter += 1;
    }
    $("span#counter").text(counter);
  });
}

function force(s) {
  $("input#search").val(s);
  search();
  return false;
}

var query = (new URLSearchParams(window.location.search)).get("q");
if (query) {
  force(query)
}

$('.hid25').toggle();
$('.hid3').toggle();
$('.hid4').toggle();
$('.hid5').toggle();
$('.hid6').toggle();

function cloneWidth() {
  $(".div1").width($(".div2").width());
}

$(function() {
  cloneWidth();
  var running = false;
  $(".wrapper1").scroll(function(){
    cloneWidth();
    $(".div1").width($(".div2").width());
    if (running) {
      running = false;
      return;
    }
    running = true;
    $(".wrapper2").scrollLeft($(".wrapper1").scrollLeft());
  });
  $(".wrapper2").scroll(function(){
    cloneWidth();
    if (running) {
      running = false;
      return;
    }
    running = true;
    $(".wrapper1").scrollLeft($(".wrapper2").scrollLeft());
  });
});
</script>
