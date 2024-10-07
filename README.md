
<html>
<head>
    <title>Cuenta para nuestro día</title>
    <style>
        body {
            text-align: center;
            font-family: sans-serif;
            background-color: #F280A4; /* Rosa bebé */
        }

        #timer {
            font-size: 48px;
            color: white;
        }

        h1 {
            color: white;
        }
    </style>
</head>
<body>
    <h1>Cuenta para nuestro día</h1>
    <p id="timer"></p>

    <script>
        // Función para formatear el tiempo
        function formatTime(time) {
            const getSeconds = `0${time % 60}`.slice(-2);
            const minutes = `${Math.floor(time / 60)}`;
            const getMinutes = `0${minutes % 60}`.slice(-2);
            const getHours = `${Math.floor(time / 3600)}`.slice(-2);
            const days = Math.floor(time / (3600 * 24));
            return `${days} días ${getHours}:${getMinutes}:${getSeconds}`;
        }

        // Obtener el elemento del temporizador
        const timerDisplay = document.getElementById('timer');

        // Fecha de finalización (11 de octubre de 2023)
        const countDownDate = new Date("Oct 11, 2023 00:00:00").getTime();

        // Función para actualizar el temporizador
        function updateTimer() {
            // Obtener la fecha y hora actual
            const now = new Date().getTime();

            // Encuentra la distancia entre ahora y la fecha de cuenta atrás
            const distance = countDownDate - now;

            // Si la cuenta regresiva ha terminado, muestra un mensaje
            if (distance < 0) {
                clearInterval(x);
                timerDisplay.textContent = "¡Es nuestro día!";
                return;
            }

            // Calcula el tiempo restante en segundos
            const secondsRemaining = Math.floor(distance / 1000);

            // Actualiza el texto del temporizador
            timerDisplay.textContent = formatTime(secondsRemaining);
        }

        // Iniciar el intervalo para actualizar el temporizador cada segundo
        const x = setInterval(updateTimer, 1000);
    </script>
</body>
</html>
