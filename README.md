<html>
<head>
    <title>Cuenta para nuestro día</title>
    <style>
        /* ... Tus estilos CSS aquí ... */
    </style>
</head>
<body>
    <h1>Cuenta para nuestro día</h1>
    <p id="timer"></p>

    <script>
        // Función para formatear el tiempo
        function formatTime(time) {
            // ... Tu función de formato aquí ...
        }

        // Obtener el elemento del temporizador y el tiempo almacenado
        const timerDisplay = document.getElementById('timer');
        let storedTime = localStorage.getItem('remainingTime');

        // Fecha de finalización
        const countDownDate = new Date("Oct 11, 2023 00:00:00").getTime();

        // Función para actualizar el temporizador
        function updateTimer() {
            // Obtener el tiempo restante del almacenamiento local o calcularlo
            let remainingTime = storedTime ? parseInt(storedTime) : countDownDate - new Date().getTime();
            remainingTime -= 1000; // Resta un segundo

            // Almacenar el tiempo restante en el almacenamiento local
            localStorage.setItem('remainingTime', remainingTime);

            // Si la cuenta regresiva ha terminado, muestra un mensaje
            if (remainingTime <= 0) {
                clearInterval(x);
                timerDisplay.textContent = "¡Es nuestro día!";
                return;
            }

            // Actualiza el texto del temporizador
            timerDisplay.textContent = formatTime(remainingTime);
        }

        // Iniciar el intervalo para actualizar el temporizador cada segundo
        const x = setInterval(updateTimer, 1000);

        // Iniciar la actualización inicial
        updateTimer();
    </script>
</body>
</html>
