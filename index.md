---
layout: default
title: Marian Cheek Jackson Center Sound Clip Juke Box
---

<div class="container-lg">
	{% for item in site.data.clips.sound-clips %}
		{% for theme in item.theme %}
			<div class="row">
				{% for person in item.people %}	
					<div class="col-6 {% if forloop.first == true %}right-border{% endif %}">
						{% for clip in person.clips %}
							<div class="row" style="height:70px;">						
								{% if clip.id contains "A" %}							
									<div class="col-2">
										<button class="btn btn-lg" onclick="this.firstChild.play()"><audio src="./clips/{{ clip.file }}"></audio>{{ clip.id }}</button>
									</div>
									<div class="col-sm-10 {% if forloop.first == true %}top-border{% else %}bottom-border{% endif %}">
										<div class="song-name">"{{ clip.title }}"</div>
											{% if forloop.first == true %}
												<div class="person-name">{{ person.name }}</div>
											{% endif %}
										</div>
								{% else %}
									<div class="col-sm-10 {% if forloop.first == true %}top-border{% else %}bottom-border{% endif %}">
										<div class="song-name">"{{ clip.title }}"</div>
										{% if forloop.first == true %}
												<div class="person-name">{{ person.name }}</div>
										{% endif %}
									</div>
									<div class="col-2">
										<button class="btn btn-lg"  onclick="this.firstChild.play()"><audio src="./clips/{{ clip.file }}"></audio>{{ clip.id }}</button>
									</div>
								{% endif %}
							</div>
						{% endfor %} <!-- clip -->
					</div>
				{% endfor %} <!-- person -->
			</div>
		{% endfor %} <!-- end theme -->
	{% endfor %}
</div>


