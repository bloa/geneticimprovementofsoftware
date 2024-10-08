---
title: "GI @ ICSE 2025"
disable_alerts: true

chairs:
- name: Aymeric Blot
  desc: "%%NAME%% is a Senior Lecturer at the University of Rennes.
  He is a member of the IRISA research centre in the joint Inria/IRISA DiverSE team.
  He received his doctorate in 2018 from the University of Lille, focusing on automated algorithm design for multi-objective combinatorial optimisation.
  Following his PhD, he moved to University College London to work on software specialization using genetic improvement.
  His research interests include genetic improvement, automated machine learning, algorithm configuration, and evolutionary computation.
  He leads the development of the <a href='https://github.com/bloa/magpie'>Magpie</a> automated software improvement framework."
- name: Vesna Nowack
  desc: "%%NAME%% received her PhD in Computer Architecture at UPC, Spain (2016).
  Recently, she worked on APR in academia (Queen Mary University of London, Lancaster University) and industry (Bloomberg).
  She is currently a Research Associate at Imperial College London with a focus on human-in-the-loop ML systems."
- name: Oliver Krauss
  desc: "%%NAME%% received his doctorate in 2022 in Pattern Mining and Genetic Improvement in Compilers and Interpeters.
  His research focuses on mining patterns in software, as well as data, to improve runtime performance and energy consumption.
  He maintains several open source frameworks, such as <a href='https://amaru.dev'>Amaru</a>)."
- name: Justyna Petke
  desc: "%%NAME%% is a Professor of Software Engineering at the Department of Computer Science, University College London. She is a member of the CREST centre and the SOLAR group. Her current research focuses on Genetic Improvement. She also has expertise in Combinatorial Interaction Testing, Constraint Satisfaction and Search-Based Software Engineering. She held an EPSRC Early Career Fellowship on Automated Software Specialisation Using Genetic Improvement (2017-2023).
  She serves on the Editorial Board for the Journal of Systems and Software, Empirical Software Engineering, Genetic Programming and Evolvable Machines, Engineering Applications of Artificial Intelligence, and as Deputy Editor-in-Chief for the Automated Software Engineering journal."
- name: Penn Rainford
  desc: "%%NAME%% test text"

  

reviewers:
- TBD
- TBD
- TBD
- TBD
- TBD
---

# The 14th International Workshop on Genetic Improvement @[ICSE 2025](https://conf.researchr.org/home/icse-2025)


<figure class="figure">
  <img class="figure-img img-fluid" src="https://upload.wikimedia.org/wikipedia/commons/6/6e/Ottawa_skyline.jpg">
  <figcaption class="figure-caption text-right">Ottawa and Gatineau, Canada (Michel Gagnon, CC BY-SA 3.0, via Wikimedia Commons)</figcaption>
</figure>


## Event

The 14th instalment of the GI workshop is is expected to place in Ottawa, collocated with the 47th International Conference on Software Engineering, [ICSE 2025](https://conf.researchr.org/home/icse-2025).

The workshop is expected to be held in-person.
In case of a virtual or hybrid event, virtual presentations may be possible.


## Important Dates

- **Submission Deadline**: 11 November 2024 (Mon)
- **Notification**: 1 December 2024 (Sun)
- **Camera-ready**: 5 February 2025 (Wed)
- **Workshop**: 26 April--4 May 2025 (TBD)

Keep up to date with the latest event news via our Twitter: <https://twitter.com/gi_of_software>.


## <a name="CFP"></a> Call For Submissions

We invite submissions that discuss recent developments in all areas of research on, and applications of, Genetic Improvement.
The International Workshop on Genetic Improvement is the premier workshop in the field and provides an opportunity for researchers interested in automated program repair and software optimisation to disseminate their work, exchange ideas, and discover new research directions.

Topics of interest include both the theory and practice of Genetic Improvement.
Applications of GI include, but are not limited to, using GI to:
- Improve runtime efficiency
- Decrease memory consumption
- Decrease energy consumption
- Transplant new functionality
- Specialise software
- Generate multiple versions of software
- Improve low level or binary code
- Use of AI/large language models with GI
- Repair bugs
- GI techniques in industrial settings

The workshop emphasises interaction and discussion between participants.  
Authors are encouraged to submit early and in-progress work.

We invite two types of submissions:
- Research papers (eight page limit, including references)
- Position papers (two page limit, including references)

Papers should be submitted electronically and must conform to the IEEE conference proceedings template as per the [ICSE submission process](https://conf.researchr.org/track/icse-2025/icse-2025-research-track) .

Accepted papers must be presented at GI 2025 and will appear in the ICSE workshops volume.
The official publication date of the workshop proceedings is the date the proceedings are made available by IEEE.
This date may be up to two weeks prior to the first day of ICSE 2025.
The official publication date affects the deadline for any patent filings related to published work.

The **<i class="fa-solid fa-award"></i> best paper** and **<i class="fa-solid fa-award"></i> best presentation** will be awarded during the workshop.


## <a name="chairs"></a> Workshop Chairs

{% for chair in page.chairs %}{% assign match = nil %}{% for p in site.data.people %}{% if p.name == chair.name %}{% assign match = p %}{% break %}{% else %}{% for aka in p.aka %}{% if aka == chair.name %}{% assign match = p %}{% break %}{% endif %}{% endfor %}{% endif %}{% endfor %}
<figure class="figure float-left" style="width:150px; margin: auto 0.8em;">
  <div class="float-right">
    <img class="figure-img rounded img-thumbnail" style="max-width: 150px; max-height: 150px;" src="{{ match.img | relative_url }}" onerror="this.onerror=null; this.src='{{ "/profile_images/blank.jpg" | relative_url }}'">
    <figcaption class="figure-caption text-right">{{ chair.name }}</figcaption>
  </div>
</figure>

{% capture chair_name %}<b>{% if match.homepage %}<a href="{{ match.homepage }}">{{ match.name }}</a>{% else %}{{ chair.name }}{% endif %}</b>{% endcapture %}
<p class="clearfix">
  {{ chair.desc | replace: '%%NAME%%', chair_name }}
</p>
{% endfor %}
