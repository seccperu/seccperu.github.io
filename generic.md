---
layout: post
title: Cronograma
description: Cronograma del Evento
image: 
nav-menu: true
permalink : '/cronograma/'
---

<h4>Cronograma - 20 de Diciembre del 2019</h4>
<div class="table-wrapper">
	<table>
		<thead>
			<tr>
				<th>Hora</th>
				<th>Evento</th>
			</tr>
		</thead>
		<tbody id="tableCron">
		</tbody>
	</table>
</div>

<script type="text/javascript">

function populateThis(data){
	let imageURL = "";
	let expositorName = "";
	let topic = "";
	let bio = "";
	let templateText = ""
	let fullBioLink = "";

	let current = null;
	data = JSON.parse(data)
	for (let ii = 0; ii < data.length; ii++){
		current = data[ii]

		hora = current["0"];
		evento = current["1"];

		templateText += '<tr>\n    <td>';
		templateText += hora
		templateText += '</td>\n    <td>'
		templateText += evento;
		templateText += '</td>\n</tr>';
	}
	document.querySelector('#tableCron').innerHTML = templateText
}

loadJSON(populateThis, "https://gist.githubusercontent.com/seccperu/03c78edf094b280e6011648f9c0d3bbd/raw/dbf3f49fd98741e95af7681adde7b83eb7daabaf/cronograma.JSON");
</script>

