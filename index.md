---
layout: default
title: Marian Cheek Jackson Center Sound Clip Juke Box
---

<div class="container-fluid">
	{% for item in site.data.clips.sound-clips %}
		{% for theme in item.theme %}
			<h1>{{ item.theme }}</h1>
			{% for person in item.people %}				
				<h2>{{ person.name }}</h2>
				{% for clip in person.clips %}
					<div class="song-name">{{ clip.title }}</div>
					<div class="song-name">{{ clip.file }}</div>
					<a onclick="this.firstChild.play()"><audio src="../clips/{{ clip.file }}"></audio>▸</a>
				{% endfor %}
			{% endfor %}
		{% endfor %}
	{% endfor %}




</div>


