# nada-esta-escrito-demo
Demo emocional navegable para validar la app Nada Esta Escrito
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Nada está escrito</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      padding: 20px;
    }
    section {
      margin-bottom: 30px;
      padding: 15px;
      background-color: #fff;
      border-radius: 8px;
      box-shadow: 0 0 5px rgba(0,0,0,0.1);
    }
    h2 {
      color: #444;
    }
    button {
      padding: 10px 20px;
      font-size: 1em;
      margin-top: 10px;
      cursor: pointer;
      border: none;
      border-radius: 5px;
    }
    #emergencia {
      background-color: crimson;
      color: white;
    }
    #simularApuesta {
      background-color: #0077cc;
      color: white;
    }
    .premium {
      background-color: #e0f7fa;
      border-left: 5px solid #0077cc;
      padding-left: 10px;
    }
  </style>
</head>
<body>

  <h1>Bienvenido a <em>Nada está escrito</em></h1>

  <!-- Sección 1: Estado emocional -->
  <section id="estado-emocional">
    <h2>¿Cómo te sientes hoy?</h2>
    <div id="mensaje"></div>
  </section>

  <!-- Sección 2: Puntos acumulados -->
  <section id="puntos-dia">
    <h2>Tu progreso</h2>
    <div id="puntos"></div>
  </section>

  <!-- Sección 3: Botón de emergencia -->
  <section id="apoyo-emergencia">
    <h2>¿Momento difícil?</h2>
    <button id="emergencia">Botón de emergencia</button>
  </section>

  <!-- Sección 4: Resultados impredecibles -->
  <section id="educacion-apuestas">
    <h2>Lo que no puedes controlar</h2>
    <div id="historico"></div>
  </section>

  <!-- Sección 5: Simulación de intento de apuesta -->
  <section id="advertencia-apuesta">
    <h2>Simular intento de abrir página de apuestas</h2>
    <button id="simularApuesta">Intentar abrir página</button>
    <div id="advertencia"></div>
  </section>

  <!-- Sección 6: Diferencias entre versión gratuita y premium -->
  <section id="versiones-app">
    <h2>Comparación: Gratuita vs Premium</h2>
    <ul>
      <li>✅ Mensajes emocionales básicos <span class="premium">Premium: IA personalizada</span></li>
      <li>✅ Botón de emergencia <span class="premium">Premium: contenido exclusivo</span></li>
      <li>✅ Puntos por día sin apostar <span class="premium">Premium: recompensas desbloqueables</span></li>
      <li>✅ Resultados impredecibles <span class="premium">Premium: análisis emocional</span></li>
      <li>❌ Diario emocional <span class="premium">Premium: historial y evolución</span></li>
      <li>❌ Simulador de apuestas <span class="premium">Premium: estadísticas personalizadas</span></li>
      <li>❌ Red de apoyo <span class="premium">Premium: conexión guiada</span></li>
      <li>❌ Guardado de conversaciones <span class="premium">Premium: historial completo</span></li>
    </ul>
  </section>

  <!-- Sección 7: Historial emocional (simulado) -->
  <section id="historial-emocional">
    <h2>Tu historial emocional (Premium)</h2>
    <div id="historial"></div>
  </section>

  <script>
    const mensaje = document.getElementById('mensaje');
    const puntos = document.getElementById('puntos');
    const historico = document.getElementById('historico');
    const advertencia = document.getElementById('advertencia');
    const historial = document.getElementById('historial');

    let puntosTotales = 0;
    let historialMensajes = [];

    // Pregunta emocional
    const respuesta = prompt("¿Cómo te sientes hoy?");
    const estado = respuesta ? respuesta.toLowerCase().trim() : "";
    let texto = "";

    if (estado.includes("triste")) {
      texto = "Lo siento mucho. No estás solo. Respira, esto también pasará. 💙";
    } else if (estado.includes("ansioso")) {
      texto = "Respira profundo. Estás a salvo aquí. Tu mente merece descanso. 🌿";
    } else if (estado.includes("feliz")) {
      texto = "Qué alegría saberlo. Celebra tu luz, y compártela con quienes la necesitan. ☀️";
    } else if (estado.includes("enojado")) {
      texto = "Es válido sentir enojo. Canalízalo con calma. Tu paz vale más que cualquier impulso. 🔥";
    } else if (estado === "") {
      texto = "No importa si no quieres responder ahora. Aquí estás seguro. 🤍";
    } else {
      texto = `Gracias por compartir. Hoy te sientes: "${respuesta}". Estamos contigo. 🫂`;
    }

    mensaje.textContent = texto;
    historialMensajes.push(`Día 1: ${texto}`);

    // Puntos por día sin apostar
    puntosTotales += 10;
    puntos.textContent = `Hoy evitaste las apuestas. Has ganado +10 puntos. Total acumulado: ${puntosTotales}`;

    // Botón de emergencia
    document.getElementById('emergencia').addEventListener('click', () => {
      alert("Respira. Este momento pasará. Tu impulso no define tu valor. ¿Quieres hablar con alguien?");
    });

    // Resultados impredecibles
    const resultados = [
      "Liverpool perdió contra Chelsea. Tarjeta roja al minuto 12.",
      "Georgia venció a Portugal. Gol en tiempo extra.",
      "Suiza eliminó a Italia en penales. El favorito cayó.",
      "Austria derrotó a Holanda con autogol inesperado.",
      "Brasil fue eliminado por Marruecos. Clima extremo afectó rendimiento."
    ];
    const aleatorio = resultados[Math.floor(Math.random() * resultados.length)];
    historico.textContent = `📉 Resultado impredecible del día: ${aleatorio}`;

    // Simulación de intento de apuesta
    document.getElementById('simularApuesta').addEventListener('click', () => {
      advertencia.textContent = "⚠️ Este impulso no define tu historia. ¿Quieres seguir o tomar un respiro?";
    });

    // Historial emocional (simulado)
    historial.innerHTML = historialMensajes.map(m => `<p>${m}</p>`).join("");
  </script>

</body>
</html>

