# Publications

## {{ site.data.paperlist.papers.size }} conference papers, journal articles, and online preprints 

<i>Click on each title to display more information.</i>

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

[Algorithms for Adaptive Game-playing Agents](njustesen/publications/justesen-dissertation.pdf)

### Abstract
Several games have been promoted by researchers as key challenges in the research field of Artificial Intelligence (AI) through the years, with the ultimate goal of defeating the best human players in these games. Recent developments in deep learning have enabled computers to learn strong policies for many games, where previous methods have fallen short. However, the most complex games, such as the Real-time Strategy (RTS) game StarCraft (Blizzard Entertainment, 1998), are still not mastered by AI. We identify three properties of adaptivity that we believe are required to fully master the most difficult games with AI. These properties are: (1) intra-game adaptivity: the ability to adapt to opponent strategies within a game, (2) inter-game adaptivity: the ability to intelligently switch strategy in-between games, and (3) generality: the ability to generalize to many different, and most likely unseen, variations (such as different levels). We analyze the shortcomings of state-of-the-art game-playing algorithms in regards to adaptation and present novel algorithmic approaches to each property. Several of the presented approaches also attempt to overcome the difficulty of learning adaptive policies in games with sparse rewards. The main contributions in this dissertation are: (a) a continual evolutionary planning algorithm that performs online adaptive build-order planning in StarCraft, (b) an imitation learning approach to intra-game adaptive build-order planning in StarCraft, resulting in the first (to the best of our knowledge) neural-network-based bot that plays the full game, (c) a novel imitation learning method for learning behavioral repertoires from demonstrations, which allows for inter-game adaptivity, (d) an automatic reward shaping technique for reinforcement learning that automatically assigns feedback values based on the temporal rarity of pre-defined events, that works as a form of curriculum learning and regularization technique to avoid overfitted behaviors in games with sparse rewards, (e) a new reinforcement learning framework that incorporates procedural content generation to generate new training levels each episode that get progressively harder as the agent improves, which is shown to overcome sparse rewards and increase the generality of the learned policy, (f) a pragmatic way of evaluating the fairness of game competitions between humans and AI that further highlights the importance of adaptation, and (g) a new challenge and competition for AI that is based on the board game Blood Bowl, which is orders of magnitude more complex than the game go and requires a high level of generality. These contributions bring a new perspective on the AI challenge of playing complex games that has a focus on adaptation. We believe this perspective is crucial to achieving strong and robust game-playing AI. Our contributions may potentially have an impact on many important real-world problems beyond games, such as robotic tasks in changing environments with complex interactions that require a high level of adaptivity.

## Master Thesis

[Artificial Intelligence for Hero Academy](njustesen/publications/justesen-masterthesis.pdf)

### Abstract
In many competitive video games it is possible for players to compete against a computer controlled opponent. It is important that such opponents are able to play at a worthy level to keep players engaged. A great deal of research has been done on Artificial Intelligence (AI) in games to create intelligent computer controlled players, more commonly referred to as AI agents, for a large collection of game genres. In this thesis we have focused on how to create an intelligent AI agent for the tactical turn-based game Hero Academy, using our own open source game engine Hero AIcademy. In this game, players can perform five sequential actions resulting in millions of possible outcomes each turn. We have implemented and compared several AI methods mainly based on Monte Carlo Tree Search (MCTS) and evolutionary algorithms. A novel progressive pruning strategy is introduced that significantly improves MCTS in Hero Academy. Another approach to MCTS is introduced, in which the exploration constant is set to zero and greedy rollouts are used, that also gives significant improvement. An online evolutionary algorithm that evolves plans during each turn achieved the best results. The fitness function of the evolution is based on depth-limited rollouts to determine the value of plans. It did, however, not increase the performance significantly. The online evolution agent was able to play Hero Academy competitively against human beginners but was easily beaten by intermediate and expert players. Aside from searching for possible plans it is critical to evaluate the outcome of these intelligently. We evolved a neural network, using NEAT, that outperforms our own manually designed evaluator for small game boards, while more work is needed to obtain similar results for larger game boards.
