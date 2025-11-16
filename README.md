<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Juego: ¿Qué tipo de griego arcaico eres?</title>
<style>
    body { font-family: Arial, sans-serif; background: #f7f3e8; margin: 0; padding: 20px; }
    .card { background: white; padding: 20px; border-radius: 12px; max-width: 700px; margin: auto; box-shadow: 0 2px 8px rgba(0,0,0,0.1); }
    h1, h2 { text-align: center; }
    .question { margin-bottom: 25px; }
    button { padding: 10px 20px; border-radius: 8px; border: none; cursor: pointer; background: #b6935b; color: white; font-size: 1rem; }
    select { width: 100%; padding: 8px; border-radius: 8px; margin-top: 10px; }
    #result { margin-top: 30px; padding: 20px; background: #fff4d6; border-radius: 10px; }
</style>
</head>
<body>
<div class="card">
<h1>¿Qué tipo de griego arcaico serías?</h1>
<p>Responde según lo que harías en escenas inspiradas en la Ilíada y la Grecia arcaica. Cada pregunta ahora incluye un pequeño contexto narrativo para sumergirte en el mundo homérico.<\/p>

<form id="gameForm">

<div class=\"question\">
<p><em>"Como cuando Atenea se acerca a Aquiles para contener su furia, recuerda que los dioses influyen en el ánimo de los héroes."</em></p>
<h3>1. En el campo de batalla, cuando los dioses intervienen como en la Ilíada, ¿a qué deidad acudirías en tu mente?</h3>
<select id="dios">
<option value="Atenea">Atenea (sabiduría, estrategia)</option>
<option value="Ares">Ares (furia y valor guerrero)</option>
<option value="Apolo">Apolo (armonía, poesía, destino)</option>
<option value="Afrodita">Afrodita (belleza, impulso, deseo)</option>
<option value="Poseidón">Poseidón (fuerza indomable, emociones profundas)</option>
</select>
</div>

<div class="question">
<h3>2. Como los héroes homéricos, ¿cuál es tu virtud dominante?</h3>
<select id="virtud">
<option value="areté">Areté (excelencia)</option>
<option value="andreia">Andreia (coraje)</option>
<option value="sophrosyne">Sophrosyne (mesura)</option>
<option value="dikaiosyne">Dikaiosyne (justicia)</option>
<option value="xenia">Xenia (hospitalidad)</option>
</select>
</div>

<div class="question">
<h3>3. Ante un conflicto como el de Aquiles y Agamenón, ¿cómo actuarías?</h3>
<select id="accion">
<option value="ira">Responderías con ira inmediata</option>
<option value="dialogo">Buscarías mediación y diálogo</option>
<option value="retiro">Te retirarías para reflexionar</option>
<option value="sacrificio">Harías un sacrificio para pedir guía divina</option>
</select>
</div>

<div class="question">
<h3>4. ¿Qué rol tendrías dentro de la polis?</h3>
<select id="rol">
<option value="militar">Militar (hoplita)</option>
<option value="campesino">Campesino</option>
<option value="artesano">Artesano</option>
<option value="poeta">Aedo o poeta</option>
<option value="consejero">Consejero o anciano</option>
</select>
</div>

<div class="question">
<h3>5. ¿Qué rasgo psicológico predominante te describe?</h3>
<select id="rasgo">
<option value="colerico">Colérico (impulso, intensidad)</option>
<option value="apolineo">Apolíneo (orden, claridad)</option>
<option value="dionisiaco">Dionisíaco (pasión, creatividad)</option>
<option value="flematico">Flemático (calma y estabilidad)</option>
<option value="melancolico">Melancólico (profundidad reflexiva)</option>
</select>
</div>

<div class="question">
<h3>6. ¿Qué ciudad griega resuena más contigo?</h3>
<select id="ciudad">
<option value="atenas">Atenas</option>
<option value="esparta">Esparta</option>
<option value="argos">Argos</option>
<option value="corinto">Corinto</option>
<option value="itaca">Ítaca</option>
</select>
</div>

<div style="text-align:center;">
<button type="button" onclick="calcular()">Descubrir mi tipo de griego</button>
</div>
</form>

<div id="result"></div>
</div>

<script>
function calcular() {
    const dios = document.getElementById('dios').value;
    const virtud = document.getElementById('virtud').value;
    const accion = document.getElementById('accion').value;
    const rol = document.getElementById('rol').value;
    const rasgo = document.getElementById('rasgo').value;
    const ciudad = document.getElementById('ciudad').value;

    let tipo = "";
    let descripcion = "";
    let cita = "";
    let reflexion = "";

    if (dios === "Atenea" && virtud === "sophrosyne" && rol === "consejero") {
        tipo = "El estratega ateniense";
        descripcion = "Tu identidad combina sabiduría, mesura y visión política. Como Atenea en la Ilíada, tu fortaleza reside en pensar antes de actuar y en guiar a otros.";
        cita = "\"Atenea se colocó junto a él y lo tomó por el cabello dorado.\" (Ilíada I)";
        reflexion = "Tu personalidad refleja la idea de que el verdadero poder en la Grecia arcaica no era solo la fuerza, sino la inteligencia divina que ordena el caos.";
    } else if (dios === "Ares" && accion === "ira" && rasgo === "colerico") {
        tipo = "Guerrero homérico";
        descripcion = "Eres intensidad pura, como los grandes héroes aqueos. La ira es para ti una fuerza casi sagrada, vehículo del honor y motor del combate.";
        cita = "\"Canta, oh Musa, la cólera del Pelida Aquiles\" (Ilíada I)";
        reflexion = "Tu combinación sugiere que, en tu espíritu, el honor prevalece sobre la vida misma, tal como el kléos era más valioso que el aliento.";
    } else if (dios === "Apolo" && rasgo === "melancolico" && rol === "poeta") {
        tipo = "Aedo inspirado por Apolo";
        descripcion = "Tu alma vive entre versos, música y presagios. Apolo guía tu sensibilidad, orientada a transformar la experiencia humana en relato y memoria.";
        cita = "\"Apolo, que hiere de lejos, descendió irritado desde lo alto del Olimpo.\" (Ilíada I)";
        reflexion = "Representas la dimensión más profunda del mundo homérico: la memoria cultural y la belleza que preserva a los hombres del olvido.";
    } else if (ciudad === "esparta" && virtud === "andreia" && rol === "militar") {
        tipo = "Hoplita espartano";
        descripcion = "El valor es tu eje. Tienes disciplina, fuerza y un sentido férreo de pertenencia a la comunidad. Tu vida responde al ideal guerrero de la areté espartana.";
        cita = "\"Sin abandonar su puesto, firme, resistió.\" (Ilíada XV)";
        reflexion = "Tu identidad revela una ética centrada en el deber y en la cohesión del grupo, tan fundamental en la mentalidad arcaica como el propio destino.";
    } else {
        tipo = "Ciudadano de la Grecia arcaica";
        descripcion = "Eres una mezcla equilibrada entre lo humano y lo divino, entre virtud y destino. Como en la Ilíada, tu identidad surge del diálogo constante entre impulsos, valores y tu lugar en la polis.";
        cita = "\"Así discuten los dioses sobre los hombres, cuya vida es breve pero intensa.\" (Ilíada)";
        reflexion = "Tu camino está marcado por la convivencia entre lo sagrado y lo cotidiano, mostrando la complejidad del alma arcaica.";
    }

    document.getElementById('result').innerHTML = `<h2>${tipo}</h2><p>${descripcion}</p><p><strong>Cita homérica:</strong> ${cita}</p><p><em>${reflexion}</em></p>`;
}
</script>

</body>
</html>
