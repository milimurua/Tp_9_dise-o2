# Tp_9_dise-o2
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MusicMood - Detección de Emociones</title>
    <style>
        /* Estilos Generales */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            background-color: #f7f9fc;
        }
        .pantalla {
            display: none;
            flex-direction: column;
            align-items: center;
            text-align: center;
            max-width: 400px;
            padding: 20px;
            border-radius: 8px;
            background-color: #ffffff;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
            margin: 20px;
        }
        .visible {
            display: flex;
        }
        h1, h2 {
            color: #333;
            margin-bottom: 16px;
        }
        p {
            color: #555;
            margin-bottom: 20px;
        }
        button {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 1rem;
            color: #fff;
            background-color: #007bff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #0056b3;
        }
        .opciones button {
            margin: 10px;
            padding: 8px 12px;
            font-size: 1.2rem;
            background-color: #e0e0e0;
            color: #333;
        }
        #video-container {
            width: 300px;
            height: 200px;
            background-color: #000;
            margin: 20px 0;
            display: flex;
            justify-content: center;
            align-items: center;
            color: #fff;
        }
        .recomendaciones ul, #historial ul {
            list-style: none;
            padding: 0;
        }
        .recomendaciones li, #historial li {
            margin: 8px 0;
            font-size: 1rem;
            color: #333;
        }
    </style>
</head>
<body>

    <!-- Pantalla de Inicio -->
    <section id="inicio" class="pantalla visible">
        <h1>Bienvenido a MusicMood</h1>
        <p>Detecta tu emoción y descubre música personalizada para ti.</p>
        <button onclick="irA('encuesta')">Comenzar</button>
    </section>

    <!-- Encuesta de Estado de Ánimo -->
    <section id="encuesta" class="pantalla">
        <h2>¿Cómo te sientes hoy?</h2>
        <div class="opciones">
            <button onclick="seleccionarEstado('feliz')">😊 Feliz</button>
            <button onclick="seleccionarEstado('triste')">😢 Triste</button>
            <button onclick="seleccionarEstado('energetico')">💪 Enérgico</button>
            <button onclick="seleccionarEstado('relajado')">😌 Relajado</button>
        </div>
        <button onclick="irA('deteccion')">Continuar</button>
    </section>

    <!-- Detección Facial de Emoción -->
    <section id="deteccion" class="pantalla">
        <h2>Detección de Emociones en Tiempo Real</h2>
        <div id="video-container">
            <video id="video" autoplay></video>
            <p>🎥 Cámara Activa</p>
        </div>
        <p>Estamos analizando tu expresión facial...</p>
        <button onclick="irA('recomendaciones')">Ver Recomendaciones</button>
    </section>

    <!-- Pantalla de Recomendaciones -->
    <section id="recomendaciones" class="pantalla">
        <h2>Recomendaciones de Música</h2>
        <div class="recomendaciones">
            <p>Basado en tu estado de ánimo, te sugerimos:</p>
            <ul>
                <li>Canción 1 - Artista</li>
                <li>Canción 2 - Artista</li>
                <li>Canción 3 - Artista</li>
            </ul>
        </div>
        <button onclick="irA('historial')">Ver Historial</button>
    </section>

    <!-- Historial de Estados de Ánimo -->
    <section id="historial" class="pantalla">
        <h2>Historial de Estados de Ánimo</h2>
        <ul>
            <li>📅 [Fecha] - Estado: Feliz - Recomendación: Canción 1</li>
            <li>📅 [Fecha] - Estado: Triste - Recomendación: Canción 2</li>
            <li>📅 [Fecha] - Estado: Enérgico - Recomendación: Canción 3</li>
        </ul>
    </section>

    <script>
        function irA(pantallaId) {
            document.querySelectorAll('.pantalla').forEach(p => p.classList.remove('visible'));
            document.getElementById(pantallaId).classList.add('visible');
        }

        function seleccionarEstado(estado) {
            console.log("Estado seleccionado:", estado);
            // Aquí se puede guardar el estado en una variable o base de datos
        }
    </script>

</body>
</html>
