
<html>
<head>
    <title>Temporizador</title>
    <style>
        body {
            text-align: center;
            font-family: sans-serif;
        }

        #timer {
            font-size: 48px;
        }
    </style>
</head>
<body>
    <p id="timer">00:00:00</p>
    <script>
        // Función para formatear el tiempo
        function formatTime(time) {
            const getSeconds = `0${time % 60}`.slice(-2);
            const minutes = `${Math.floor(time / 60)}`;
            const getMinutes = `0${minutes % 60}`.slice(-2);
            const getHours = `${Math.floor(time / 3600)}`.slice(-2);
            return `${getHours}:${getMinutes}:${getSeconds}`;
        }

        // Obtener el elemento del temporizador
        const timerDisplay = document.getElementById('timer');

        // Tiempo inicial en segundos (ajusta este valor)
        let startTime = 60; // 1 minuto

        // Función para actualizar el temporizador
        function updateTimer() {
            if (startTime === 0) {
                // Aquí puedes agregar una acción cuando el tiempo se acabe
                alert("¡Tiempo agotado!");
                return;
            }
            startTime--;
            timerDisplay.textContent = formatTime(startTime);
        }

        // Iniciar el intervalo para actualizar el temporizador cada segundo
        setInterval(updateTimer, 1000);
    </script>
</body>
</html>
