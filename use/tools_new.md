---
active: use
---

# Tools for Genetic Improvement

Search operates within all fields available.
Clicking on data links in the table will query all similar entries.

- [list of general GI tools](#general-gi-tools)
- [list of specialised GI tools](#specialised-gi-tools)
- [list of other optimisation framework used in GI](#other-optimisation-tools)

See also [program-repair.org/benchmarks](https://program-repair.org/benchmarks) for program repair specifically.

---
## General GI Tools

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon1">Query:</span>
  </div>
  <input type="text" id="search_general" class="form-control" placeholder="..." onkeyup="search('general')">
  <div class="input-group-append">
    <input type="reset" class="btn btn-outline-secondary" onclick="force('general','')">
  </div>
</div>

<div>
  Showing <span id="counter_general">{{ site.data.survey.tools_general.size }}</span> of {{ site.data.tools_general.size }} entries.
</div>

<table id="survey_general" class="table table-responsive" style="max-width: 100%">
  <thead>
    <tr>
      <th>Name</th>
      <th>Date</th>
      <th>Implementation</th>
      <th>Targets</th>
      <th>Fitness</th>
      <th>Links</th>
      <th>Uses</th>
    </tr>
  </thead>{% assign tmp = site.data.survey.tools_general | sort: "name" | reverse | sort: "year" | sort: "last_use" | reverse %}
  <tbody>{% for entry in tmp %}
    <tr data-search="{{ entry.name }} {% for implem in entry.implem %}implem={{ implem }} {% endfor %} {% for target in entry.targets %}target={{ target }} {% endfor %} {% for fit in entry.fitness %}fit={{ fit }} {% endfor %} {% for col in entry.collection %}col={{ col }} {% endfor %} {% for use in entry.uses %}use={{ uses }} {% endfor %}">
      <td>{% if entry.name %}{{ entry.name }}{% endif %}</td>
      <td>{{ entry.year }}&ndash;{{ entry.last_use }}</td>
      <td>{% for implem in entry.implem %}{% if forloop.first == false %}, {% endif %}<a href="#search_general" class="text-nowrap" onclick="force('general','implem=&quot;{{ implem }}&quot;')">{{ implem }}</a>{% endfor %}</td>
      <td>{% for target in entry.targets %}<a href="#search_general" class="text-nowrap" onclick="force('general', 'target=&quot;{{ target }}&quot;')">#{{ target }}</a> {% endfor %}</td>
      <td>{% for fit in entry.fitness %}<a href="#search_tool" class="text-nowrap" onclick="force('general', 'fit=&quot;{{ fit }}&quot;')">#{{ fit }}</a> {% endfor %}</td>
      <td>{% for url in entry.url %}<a class="badge badge-warning" target="_blank" href="{{ url }}">URL</a> {% endfor %}</td>
      <td>{% for use in entry.uses %}<a target="_blank" href="{{ site.baseurl }}/learn/survey?q={{ use }}"><i class="fa fa-external-link-alt" style="font-size: 0.8rem" title="{{ use }}" ></i></a> {% endfor %}</td>
    </tr>{% endfor %}
  </tbody>
</table>


---
## Specialised GI Tools

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon1">Query:</span>
  </div>
  <input type="text" id="search_spec" class="form-control" placeholder="..." onkeyup="search('spec')">
  <div class="input-group-append">
    <input type="reset" class="btn btn-outline-secondary" onclick="force('spec','')">
  </div>
</div>

<div>
  Showing <span id="counter_spec">{{ site.data.survey.tools_spec.size }}</span> of {{ site.data.tools_spec.size }} entries.
</div>

<table id="survey_spec" class="table table-responsive" style="max-width: 100%">
  <thead>
    <tr>
      <th>Name</th>
      <th>Date</th>
      <th>Implementation</th>
      <th>Targets</th>
      <th>Fitness</th>
      <th>Links</th>
      <th>Uses</th>
    </tr>
  </thead>{% assign tmp = site.data.survey.tools_spec | sort: "name" | reverse | sort: "year" | sort: "last_use" | reverse %}
  <tbody>{% for entry in tmp %}
    <tr data-search="{{ entry.name }} {% for implem in entry.implem %}implem={{ implem }} {% endfor %} {% for target in entry.targets %}target={{ target }} {% endfor %} {% for fit in entry.fitness %}fit={{ fit }} {% endfor %} {% for col in entry.collection %}col={{ col }} {% endfor %} {% for use in entry.uses %}use={{ uses }} {% endfor %}">
      <td>{% if entry.name %}{{ entry.name }}{% endif %}</td>
      <td>{{ entry.year }}&ndash;{{ entry.last_use }}</td>
      <td>{% for implem in entry.implem %}{% if forloop.first == false %}, {% endif %}<a href="#search_spec" class="text-nowrap" onclick="force('spec','implem=&quot;{{ implem }}&quot;')">{{ implem }}</a>{% endfor %}</td>
      <td>{% for target in entry.targets %}<a href="#search_spec" class="text-nowrap" onclick="force('spec', 'target=&quot;{{ target }}&quot;')">#{{ target }}</a> {% endfor %}</td>
      <td>{% for fit in entry.fitness %}<a href="#search_tool" class="text-nowrap" onclick="force('spec', 'fit=&quot;{{ fit }}&quot;')">#{{ fit }}</a> {% endfor %}</td>
      <td>{% for url in entry.url %}<a class="badge badge-warning" target="_blank" href="{{ url }}">URL</a> {% endfor %}</td>
      <td>{% for use in entry.uses %}<a target="_blank" href="{{ site.baseurl }}/learn/survey?q={{ use }}"><i class="fa fa-external-link-alt" style="font-size: 0.8rem" title="{{ use }}" ></i></a> {% endfor %}</td>
    </tr>{% endfor %}
  </tbody>
</table>


---
## Other Optimisation Framework

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon1">Query:</span>
  </div>
  <input type="text" id="search_opti" class="form-control" placeholder="..." onkeyup="search('opti')">
  <div class="input-group-append">
    <input type="reset" class="btn btn-outline-secondary" onclick="force('opti','')">
  </div>
</div>

<div>
  Showing <span id="counter_opti">{{ site.data.survey.tools_opti.size }}</span> of {{ site.data.tools_opti.size }} entries.
</div>

<table id="survey_opti" class="table table-responsive" style="max-width: 100%">
  <thead>
    <tr>
      <th>Name</th>
      <th>Date</th>
      <th>Implementation</th>
      <th>Targets</th>
      <th>Fitness</th>
      <th>Links</th>
      <th>Uses</th>
    </tr>
  </thead>{% assign tmp = site.data.survey.tools_opti | sort: "name" | reverse | sort: "year" | sort: "last_use" | reverse %}
  <tbody>{% for entry in tmp %}
    <tr data-search="{{ entry.name }} {% for implem in entry.implem %}implem={{ implem }} {% endfor %} {% for target in entry.targets %}target={{ target }} {% endfor %} {% for fit in entry.fitness %}fit={{ fit }} {% endfor %} {% for col in entry.collection %}col={{ col }} {% endfor %} {% for use in entry.uses %}use={{ uses }} {% endfor %}">
      <td>{% if entry.name %}{{ entry.name }}{% endif %}</td>
      <td>{{ entry.year }}&ndash;{{ entry.last_use }}</td>
      <td>{% for implem in entry.implem %}{% if forloop.first == false %}, {% endif %}<a href="#search_opti" class="text-nowrap" onclick="force('opti','implem=&quot;{{ implem }}&quot;')">{{ implem }}</a>{% endfor %}</td>
      <td>{% for target in entry.targets %}<a href="#search_opti" class="text-nowrap" onclick="force('opti', 'target=&quot;{{ target }}&quot;')">#{{ target }}</a> {% endfor %}</td>
      <td>{% for fit in entry.fitness %}<a href="#search_tool" class="text-nowrap" onclick="force('opti', 'fit=&quot;{{ fit }}&quot;')">#{{ fit }}</a> {% endfor %}</td>
      <td>{% for url in entry.url %}<a class="badge badge-warning" target="_blank" href="{{ url }}">URL</a> {% endfor %}</td>
      <td>{% for use in entry.uses %}<a target="_blank" href="{{ site.baseurl }}/learn/survey?q={{ use }}"><i class="fa fa-external-link-alt" style="font-size: 0.8rem" title="{{ use }}" ></i></a> {% endfor %}</td>
    </tr>{% endfor %}
  </tbody>
</table>




<script>
function search(type) {
  var chunks = $("input#search_"+type).val().toUpperCase().match(/(?:[^\s"]+|"[^"]*")+/g)
  if (chunks) {
    chunks = chunks.map(c => c.replace(/\"/g, ""));
  }

  var counter = 0
  $("#survey_"+type+" tbody tr").each(function() {
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
    $("span#counter_"+type).text(counter);
  });
}

function force(type, s) {
  $("input#search_"+type).val(s);
  search(type);
  return false;
}

function force_general(s) { return force("general", s) }
function force_spec(s) { return force("spec", s) }
function force_opti(s) { return force("opti", s) }
</script>
