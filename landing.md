---
title: Ponentes y Ponencias
layout: landing
description: 'Ponencias a presentarse en el evento'
image: ../assets/images/trux.jpg
permalink: '/ponencias/'
nav-menu: true
---

<!-- Main -->
<div id="main">

<!-- One -->
<!-- <section id="one">
	<div class="inner">
		<header class="major">
			<h2>Ponencias y Ponentes</h2>
		</header>
		<p>Mostramos los trabajos a ser expuesto durante el evento y sus expositores</p>
	</div>
</section> -->

<!-- Two -->
<div id="future">
</div>

<script type="text/javascript">

function populateThis(data){
	let imageURL = "";
	let expositorName = "";
	let topic = "";
	let bio = "";
	let templateText = '<section id="one" class="spotlights">\n';
	let fullBioLink = "";

	let current = null;
	data = JSON.parse(data)
	for (let ii = 0; ii < data.length; ii++){
		current = data[ii]

		imageURL = current.Foto;
		expositorName = current.Nombre;
		topic = current.Tema;
		bio = current.Resumen;
		fullBioLink = current["Bio completa"];

		altTemp = `<section>
			<a href="${fullBioLink}" class="image">
				<img src="${imageURL}" alt="" data-position="center center" />
			</a>
			<div class="content">
				<div class="inner">
					<header class="major">
 						<h3>${expositorName}</h3>
					</header>
					<h6><b>Ponencia</b></h6>
					<header class="minor">
						<h4 stlye="text-align:left;">${topic}</h4>
					</header>
					<p>${bio}</p>
				</div>
			</div>
		</section>`

		templateText += altTemp
	}

	templateText += '</section>';
	document.querySelector('#future').innerHTML = templateText
}

loadJSON(populateThis, "https://gist.githubusercontent.com/seccperu/03c78edf094b280e6011648f9c0d3bbd/raw/5b9597f9c765034480fad379169459f4bf47dc83/ponentes.JSON");
</script>

</div>