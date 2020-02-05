# Publications

## {{ site.data.paperlist.papers.size }} conference papers, journal articles, and online preprints 

<i>Click on each title to display more information.</i>

{% comment %} tags:
<span class="badge review">Reinforcement Learning</span>
<span class="badge deep-learning">Deep Learning</span>
<span class="badge pcg">Procedural Content Generation</span>
<span class="badge evolutionary-algorithms">Evolutionary Algorithms</span>
<span class="badge mcts">MCTS</span>
<span class="badge all">All</span> ––>
{% endcomment %}

{% assign paperlist = site.data.paperlist.papers | group_by: 'year' | sort:"name"  %}
{% for yeargroup in paperlist reversed %}
{% if yeargroup.name == "" %}
   <h3>Undated: {{ yeargroup.size }} Papers</h3>
{% else %}
   <h3>{{ yeargroup.name }}: {{ yeargroup.size }} Papers</h3>
{% endif %}
<ul>
	{% assign sortedgroup = yeargroup.items | sort:"title"  %}
	{% for item in sortedgroup %}
	{% if item.title %}
	<li>
		<details><summary><b>{{ item.title }}</b>
		</summary>
		<blockquote>
		{% if item.authors %}
		   <h4>Authors:</h4>
		   <ul>
		   {% for author in item.authors %}
		      <li>{{ author }}</li>
		   {% endfor %}
		   </ul>
		{% endif %}

		{% if item.abstract %}
		   <h4>Abstract:</h4>
		   {{ item.abstract }}
		{% endif %}

		{% if item.pdfurl or item.codeurl or item.webpageurl %}
		   <h4>Links:</h4>
		   <ul>
		   {% if item.pdfurl %}
		   <li><a href="{{ item.pdfurl }}">Paper</a></li>
		   {% endif %}
		   {% if item.codeurl %}
		   <li><a href="{{ item.codeurl }}">Source-code</a></li>
		   {% endif %}
		   {% if item.webpageurl %}
		   <li><a href="{{ item.webpageurl }}">Webpage</a></li>
		   {% endif %}
		   </ul>
		{% endif %}

		{% if item.bibtex %}	 
		   <h4>Bibtex:</h4>
		   <pre><code>{{ item.bibtex }}</code></pre>
		{% endif %}

		<hr>
		
		 </blockquote>
		</details>
	</li>
	{% endif %}
	{% endfor %}
</ul>
{% endfor %}

## PhD Dissertation

[Algorithms for Adaptive Game-playing Agents](/publications/justesen-dissertation.pdf)

## Master Thesis

[Artificial Intelligence for Hero Academy](/publications/justesen-masterthesis.pdf)

