# SURA
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GRUPO SURA</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f8ff; /* Celeste claro */
            color: #333;
        }
        header {
            background-color: #ffffff;
            padding: 20px;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: relative;
        }
        header h1 {
            color: #007acc;
            font-size: 3em;
        }
        header p {
            font-size: 1.2em;
            color: #007acc;
        }
        .menu {
            display: flex;
            justify-content: center;
            margin: 20px;
        }
        .menu button {
            background-color: #007acc;
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 8px;
            margin: 0 20px;
            cursor: pointer;
            font-size: 1.2em;
            transition: background-color 0.3s;
        }
        .menu button:hover {
            background-color: #005f99;
        }
        .form-section {
            display: none;
            margin: 40px 10%;
            padding: 20px;
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }
        form input, form select, form textarea {
            margin: 15px 0;
            padding: 12px;
            width: 100%;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 1em;
        }
        .submit-btn {
            background-color: #007acc;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1.2em;
            width: 100%;
            transition: background-color 0.3s;
        }
        .submit-btn:hover {
            background-color: #005f99;
        }
        .creator {
            text-align: center;
            margin-top: 50px;
        }
        .creator img {
            width: 50px;
            border-radius: 50%;
        }
        .decorative-shapes {
            position: absolute;
            top: 30%;
            left: 5%;
            width: 100%;
            height: 50%;
            background: url('https://www.transparenttextures.com/patterns/diagonal-stripes.png');
            opacity: 0.1;
            z-index: -1;
        }
        /* Responsividad */
        @media (max-width: 768px) {
            .menu button {
                width: 100%;
                margin: 10px 0;
            }
            .form-section {
                margin: 20px;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>CA Sura</h1>
        <p>Bienvenido al servidor roleplay CA Sura</p>
        <div class="decorative-shapes"></div>
    </header>

    <div class="menu">
        <button onclick="showSection('seguros')">Seguros</button>
        <button onclick="showSection('trabajos')">Ofertas de Trabajo</button>
        <button onclick="showSection('citas')">Citas Médicas</button>
    </div>

    <!-- Sección de Seguros -->
    <div id="seguros" class="form-section">
        <h2>Seguros</h2>
        <form id="segurosForm">
            <select name="tipo" required>
                <option value="" disabled selected>Tipo de Seguro</option>
                <option value="Médico">Médico</option>
                <option value="Propiedades">Propiedades</option>
            </select>
            <input type="text" name="user" placeholder="Usuario" required>
            <input type="text" name="nombre" placeholder="Nombre y Apellidos" required>
            <input type="text" name="sujeto" placeholder="Sujeto del Seguro" required>
            <input type="number" name="duracion" placeholder="Duración (meses)" required>
            <button type="submit" class="submit-btn">Enviar</button>
        </form>
    </div>

    <!-- Sección de Ofertas de Trabajo -->
    <div id="trabajos" class="form-section">
        <h2>Ofertas de Trabajo</h2>
        <form id="trabajosForm">
            <select name="puesto" required>
                <option value="" disabled selected>Selecciona un Puesto</option>
                <option value="Paramédico">Paramédico</option>
                <option value="Enfermería">Enfermería</option>
                <option value="Médico">Médico</option>
                <option value="Cirujano">Cirujano</option>
                <option value="Técnico en Anestesia">Técnico en Anestesia</option>
                <option value="Técnico en Farmacia">Técnico en Farmacia</option>
                <option value="Técnico en Laboratorio">Técnico en Laboratorio</option>
                <option value="Radiólogo">Radiólogo</option>
                <option value="Pediatría">Pediatría</option>
                <option value="Psicología">Psicología</option>
            </select>
            <input type="text" name="user" placeholder="Usuario" required>
            <input type="text" name="nombre" placeholder="Nombre y Apellidos" required>
            <input type="number" name="edad" placeholder="Edad" required>
            <input type="text" name="experiencias" placeholder="Experiencias" required>
            <button type="submit" class="submit-btn">Enviar</button>
        </form>
    </div>

    <!-- Sección de Citas Médicas -->
    <div id="citas" class="form-section">
        <h2>Citas Médicas</h2>
        <form id="citasForm">
            <input type="text" name="user" placeholder="Usuario" required>
            <input type="text" name="nombre" placeholder="Nombre y Apellidos" required>
            <input type="number" name="edad" placeholder="Edad" required>
            <input type="text" name="consulta" placeholder="Tipo de Consulta" required>
            <input type="datetime-local" name="fecha" required>
            <button type="submit" class="submit-btn">Enviar</button>
        </form>
    </div>

    <div class="creator">
        <img src="https://postimg.cc/KkZ9NjZt" alt="Creador">
        <p>CREADOR: jj26m</p>
    </div>

    <script>
        // Función para mostrar la sección seleccionada
        function showSection(sectionId) {
            const sections = document.querySelectorAll('.form-section');
            sections.forEach(section => section.style.display = 'none');
            document.getElementById(sectionId).style.display = 'block';
        }

        // Webhook de Discord
        const webhookUrl = "https://discord.com/api/webhooks/1309978382749929543/OYRVBqVbxBqFKtbFJ1uAbPr58kHK-vjg7KV38P11fDIFejNdi-NN2QQOlSJXJjQ9tiv5";

        // Función para enviar los formularios al webhook
        document.querySelectorAll('form').forEach(form => {
            form.addEventListener('submit', e => {
                e.preventDefault();
                const formData = new FormData(form);
                const data = {};
                formData.forEach((value, key) => data[key] = value);

                let contentMessage = '';
                if (form.id === "segurosForm") {
                    contentMessage = `**Usuario:** ${data.user}\n**Nombre Apellidos:** ${data.nombre}\n**Quien Recibe:** ${data.sujeto}\n**Duración:** ${data.duracion}`;
                } else if (form.id === "trabajosForm") {
                    contentMessage = `**User:** ${data.user}\n**Nombre y Apellidos:** ${data.nombre}\n**Edad:** ${data.edad}\n**Puesto Deseado:** ${data.puesto}\n**Experiencia:** ${data.experiencias}`;
                } else if (form.id === "citasForm") {
                    contentMessage = `**User:** ${data.user}\n**Nombre y Apellidos:** ${data.nombre}\n**Edad:** ${data.edad}\n**Tipo de Consulta:** ${data.consulta}\n**Fecha y Hora:** ${data.fecha}`;
                }

                fetch(webhookUrl, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({ content: contentMessage }),
                });
            });
        });
    </script>
</body>
</html>
