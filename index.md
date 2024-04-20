---
layout: default
title: Marian Cheek Jackson Center Sound Clip Juke Box
---

<div class="container-fluid">
	{% for item in site.data.clips.sound-clips %}
		{% for theme in item.theme %}
			<div class="row">
				{% for person in item.people %}	
					<div class="col">
						{% for clip in person.clips %}
							<div class="row">					
								{% if clip.id contains "A" %}
									<div class="col-2">
										<button onclick="this.firstChild.play()"><audio src="../clips/{{ clip.file }}"></audio>{{ clip.id }}</button>
									</div>
									<div class="col-4">
										<div class="song-name">{{ clip.title }}</div>
									</div>
								{% elsif clip.id contains "B" %}
									<div class="col-4">
										<div class="song-name">{{ clip.title }}</div>
									</div>
									<div class="col-2">
										<button onclick="this.firstChild.play()"><audio src="../clips/{{ clip.file }}"></audio>{{ clip.id }}</button>
									</div>
								{% else %}
									<div class="col-6">
										<div>NAME {{ person.name }}</div>
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


