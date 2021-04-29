---
active: use
---

# Benchmarks for Genetic Improvement

Search operates within all fields available.
Clicking on data links in the table will query all similar entries.

- [list of target software](#target-software)
- [list of benchmark data](#benchmark-data)
- [list of collections of software for GI](#collections)

See also [program-repair.org/benchmarks](https://program-repair.org/benchmarks) for program repair specifically.

---
## Target Software

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon1">Query:</span>
  </div>
  <input type="text" id="search_soft" class="form-control" placeholder="..." onkeyup="search('soft')">
  <div class="input-group-append">
    <input type="reset" class="btn btn-outline-secondary" onclick="force('soft','')">
  </div>
</div>

<div>
  Showing <span id="counter_soft">{{ site.data.survey.software.size }}</span> of {{ site.data.survey.software.size }} entries.
</div>

<table id="benchmark_soft" class="table table-responsive" style="max-width: 100%">
  <thead>
    <tr>
      <th>Name</th>
      <th>Language</th>
      <th>Tags</th>
      <th>Fitness</th>
      <th>Collection</th>
      <th>Links</th>
      <th>Uses</th>
    </tr>
  </thead>{% assign tmp = site.data.survey.software | sort: "name" %}
  <tbody>{% for entry in tmp %}
    <tr data-search="{{ entry.name }} {% for lang in entry.language %}lang={{ lang }} {% endfor %} {% for tag in entry.tags %}tag={{ tag }} {% endfor %} {% for fit in entry.fitness %}fit={{ fit }} {% endfor %} {% for col in entry.collection %}col={{ col }} {% endfor %} {% for use in entry.uses %}use={{ use }} {% endfor %}">
      <td>{% if entry.name %}{{ entry.name }}{% endif %}</td>
      <td>{% for lang in entry.language %}{% if forloop.first == false %}, {% endif %}<a href="#search_soft" class="text-nowrap" onclick="force('soft','lang=&quot;{{ lang }}&quot;')">{{ lang }}</a>{% endfor %}</td>
      <td>{% for tag in entry.tags %}<a href="#search_soft" class="text-nowrap" onclick="force('soft', 'tag=&quot;{{ tag }}&quot;')">#{{ tag }}</a> {% endfor %}</td>
      <td>{% for fit in entry.fitness %}<a href="#search_soft" class="text-nowrap" onclick="force('soft', 'fit=&quot;{{ fit }}&quot;')">#{{ fit }}</a> {% endfor %}</td>
      <td>{% for col in entry.collection %}<a href="#search_soft" class="text-nowrap" onclick="force('soft', 'col=&quot;{{ col }}&quot;')">{{ col }}</a> {% endfor %}</td>
      <td>{% for url in entry.urls %}<a class="badge badge-warning" target="_blank" href="{{ url }}">URL</a> {% endfor %}</td>
      <td>{% for use in entry.uses %}<a target="_blank" href="{{ site.baseurl }}/learn/survey?q={{ use }}"><i class="fa fa-external-link-alt" style="font-size: 0.8rem" title="{{ use }}" ></i></a> {% endfor %}</td>
    </tr>{% endfor %}
  </tbody>
</table>


---
## Benchmack Data

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon1">Query:</span>
  </div>
  <input type="text" id="search_data" class="form-control" placeholder="..." onkeyup="search('data')">
  <div class="input-group-append">
    <input type="reset" class="btn btn-outline-secondary" onclick="force('data','')">
  </div>
</div>

<div>
  Showing <span id="counter_data">{{ site.data.benchmark_data.size }}</span> of {{ site.data.benchmark_data.size }} entries.
</div>

<table id="benchmark_data" class="table table-responsive" style="max-width: 100%">
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Tags</th>
      <th>collection</th>
      <th>Links</th>
      <th>Uses</th>
    </tr>
  </thead>{% assign tmp = site.data.survey.data | sort: "name" %}
  <tbody>{% for entry in tmp %}
    <tr data-search="{{ entry.name }} {% for tag in entry.tags %}tag={{ tag }} {% endfor %} {% for col in entry.collection %}col={{ col }} {% endfor %} {% for use in entry.uses %}use={{ use }} {% endfor %}">
      <td>{% if entry.name %}{{ entry.name }}{% endif %}</td>
      <td>{% for type in entry.type %}<a href="#search_data" class="text-nowrap" onclick="force('data', 'type=&quot;{{ type }}&quot;')">#{{ type }}</a> {% endfor %}</td>
      <td>{% for tag in entry.tags %}<a href="#search_data" class="text-nowrap" onclick="force('data', 'tag=&quot;{{ tag }}&quot;')">#{{ tag }}</a> {% endfor %}</td>
      <td>{% for col in entry.collection %}<a href="#search_data" class="text-nowrap" onclick="force('data', 'col=&quot;{{ col }}&quot;')">#{{ col }}</a> {% endfor %}</td>
      <td>{% for url in entry.urls %}<a class="badge badge-warning" target="_blank" href="{{ url }}">URL</a> {% endfor %}</td>
      <td>{% for use in entry.uses %}<a target="_blank" href="{{ site.baseurl }}/learn/survey?q={{ use }}"><i class="fa fa-external-link-alt" style="font-size: 0.8rem" title="{{ use }}" ></i></a> {% endfor %}</td>
    </tr>{% endfor %}
  </tbody>
</table>


---
## Collections

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon1">Query:</span>
  </div>
  <input type="text" id="search_cols" class="form-control" placeholder="..." onkeyup="search('cols')">
  <div class="input-group-append">
    <input type="reset" class="btn btn-outline-secondary" onclick="force('cols','')">
  </div>
</div>

<div>
  Showing <span id="counter_cols">{{ site.data.benchmark_cols.size }}</span> of {{ site.data.benchmark_cols.size }} entries.
</div>

<table id="benchmark_cols" class="table table-responsive" style="max-width: 100%">
  <thead>
    <tr>
      <th>Name</th>
      <th>Language</th>
      <th>Type</th>
      <th>Tags</th>
      <th>Fitness</th>
      <th>Links</th>
      <th>Uses</th>
    </tr>
  </thead>{% assign tmp = site.data.survey.collections | sort: "name" %}
  <tbody>{% for entry in tmp %}
    <tr data-search="{{ entry.name }} {% for lang in entry.language %}lang={{ lang }} {% endfor %}  {% for type in entry.type %}lang={{ type }} {% endfor %} {% for tag in entry.tag %}tag={{ tag }} {% endfor %} {% for fit in entry.fitness %}fit={{ fit }} {% endfor %} {% for col in entry.collection %}col={{ col }} {% endfor %} {% for use in entry.uses %}use={{ use }} {% endfor %}">
      <td>{% if entry.name %}{{ entry.name }}{% endif %}</td>
      <td>{% for lang in entry.language %}{% if forloop.first == false %}, {% endif %}<a href="#search_cols" class="text-nowrap" onclick="force('cols', 'lang=&quot;{{ lang }} &quot;')">{{ lang }}</a>{% endfor %}</td>
      <td>{% for type in entry.type %}{% if forloop.first == false %}, {% endif %}<a href="#search_cols" class="text-nowrap" onclick="force('cols', 'type=&quot;{{ type }} &quot;')">#{{ type }}</a>{% endfor %}</td>
      <td>{% for tag in entry.tag %}<a href="#search_col" class="text-nowrap" onclick="force('cols', 'tag=&quot;{{ tag }} &quot;')">#{{ tag }}</a> {% endfor %}</td>
      <td>{% for fit in entry.fitness %}<a href="#search_cols" class="text-nowrap" onclick="force('cols', 'fit=&quot;{{ fit }} &quot;')">#{{ fit }}</a> {% endfor %}</td>
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
  $("#benchmark_"+type+" tbody tr").each(function() {
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

function force_soft(s) { return force("soft", s) }
function force_data(s) { return force("data", s) }
function force_cols(s) { return force("cols", s) }
</script>
