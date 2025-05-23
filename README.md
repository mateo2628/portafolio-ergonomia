<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portafolio de Análisis de Puestos de Trabajo</title>
    <style>
        /* Estilos CSS (sin cambios, se mantienen los originales) */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f4f8;
            color: #333;
            transition: all 0.3s;
        }
        header {
            background: linear-gradient(135deg, #2e7d32, #0288d1);
            color: white;
            text-align: center;
            padding: 2rem;
        }
        .theme-toggle {
            background-color: #ff9800;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            cursor: pointer;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        .section {
            margin-bottom: 2rem;
        }
        .portada-img, .robot-img {
            width: 100%;
            max-width: 300px;
            height: auto;
            margin: 1rem auto;
            display: block;
            border-radius: 10px;
        }
        .methodology-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        .methodology-card {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        .methodology-card:hover {
            transform: translateY(-5px);
        }
        .methodology-card img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-top-left-radius: 10px;
            border-top-right-radius: 10px;
        }
        .methodology-card h3 {
            margin: 1rem;
            color: #0288d1;
        }
        .methodology-card p {
            margin: 0 1rem 1rem;
        }
        .methodology-card a {
            display: block;
            padding: 1rem;
            background-color: #2e7d32;
            color: white;
            text-align: center;
            text-decoration: none;
            border-bottom-left-radius: 10px;
            border-bottom-right-radius: 10px;
        }
        .quiz-section, .results-section {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .quiz-question {
            margin-bottom: 1rem;
        }
        .quiz-question select {
            width: 100%;
            max-width: 400px;
            padding: 0.5rem;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .submit-button {
            background-color: #0288d1;
            color: white;
            border: none;
            padding: 1rem 2rem;
            cursor: pointer;
            border-radius: 5px;
        }
        .contact-section {
            text-align: center;
        }
        .social-links a {
            margin: 0 1rem;
            color: #0288d1;
            text-decoration: none;
        }
        .contact-section form {
            margin-top: 1rem;
        }
        .contact-section input, .contact-section textarea {
            display: block;
            width: 100%;
            max-width: 400px;
            margin: 0.5rem auto;
            padding: 0.5rem;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .filter-section {
            margin-bottom: 1rem;
        }
        .filter-section select {
            padding: 0.5rem;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .dark-mode {
            background-color: #333;
            color: white;
        }
        .dark-mode header {
            background: linear-gradient(135deg, #1b5e20, #01579b);
        }
        .dark-mode .methodology-card, .dark-mode .quiz-section, .dark-mode .results-section {
            background-color: #444;
        }
        footer {
            text-align: center;
            padding: 1rem;
            background-color: #e0e0e0;
        }
        .hidden {
            display: none;
        }
        .share-button {
            background-color: #ff9800;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            cursor: pointer;
            border-radius: 5px;
            margin-top: 1rem;
        }
    </style>
</head>
<body>
    <header>
        <h1>Portafolio de Análisis de Puestos de Trabajo</h1>
        <button class="theme-toggle" id="theme-toggle">Modo Oscuro</button>
    </header>

    <div class="container">
        <section id="portada" class="section">
            <h2>Bienvenido al Portafolio de Ergonomía</h2>
            <img src="https://m.media-amazon.com/images/I/51DBd7O6GEL.jpg" alt="Doctor Mateo Robot" class="robot-img">
            <p>¡Hola! Soy el Doctor Mateo, tu asistente virtual ergonómico. Estoy aquí para guiarte en la mejora de tu puesto de trabajo.</p>
            <img src="https://www.quironprevencion.com/portal-client/cm/images?locale=es_ES&idMmedia=43449" alt="Análisis de Puestos de Trabajo" class="portada-img">
            <p>Haz clic para empezar el quiz y descubrir cómo optimizar tu entorno laboral.</p>
            <button id="start-quiz" class="submit-button">Iniciar Quiz</button>
            <button id="share-link" class="share-button">Compartir Portafolio</button>
            <p id="share-message" style="display: none; color: green;">¡Enlace copiado al portapapeles!</p>
        </section>

        <section id="quiz" class="quiz-section" style="display: none;">
            <h2>Quiz de Ergonomía</h2>
            <form id="quiz-form">
                <div class="quiz-question">
                    <p>1. ¿Cuántas horas al día utilizas el computador?</p>
                    <select name="q1" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Menos de 2 horas</option>
                        <option value="b">2-4 horas</option>
                        <option value="c">4-6 horas</option>
                        <option value="d">Más de 6 horas</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>2. ¿Con qué frecuencia levantas objetos pesados?</p>
                    <select name="q2" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Nunca</option>
                        <option value="b">Ocasionalmente</option>
                        <option value="c">Frecuentemente</option>
                        <option value="d">Siempre</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>3. ¿Tu silla de trabajo tiene soporte lumbar ajustable?</p>
                    <select name="q3" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Sí, siempre lo uso</option>
                        <option value="b">Sí, pero no lo uso</option>
                        <option value="c">No tiene soporte lumbar</option>
                        <option value="d">No estoy seguro</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>4. ¿Ajustas la altura de tu monitor para que esté al nivel de los ojos?</p>
                    <select name="q4" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Siempre</option>
                        <option value="b">A veces</option>
                        <option value="c">Nunca</option>
                        <option value="d">No tengo monitor</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>5. ¿Realizas pausas activas durante tu jornada laboral?</p>
                    <select name="q5" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Cada hora</option>
                        <option value="b">Cada 2-3 horas</option>
                        <option value="c">Rara vez</option>
                        <option value="d">Nunca</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>6. ¿Sientes dolor o molestias en el cuello o espalda después de trabajar?</p>
                    <select name="q6" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Nunca</option>
                        <option value="b">Ocasionalmente</option>
                        <option value="c">Frecuentemente</option>
                        <option value="d">Siempre</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>7. ¿Utilizas un teclado y ratón ergonómicos?</p>
                    <select name="q7" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Sí, ambos</option>
                        <option value="b">Solo uno de ellos</option>
                        <option value="c">No, pero quiero probar</option>
                        <option value="d">No, y no me interesa</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>8. ¿Tu espacio de trabajo tiene iluminación adecuada?</p>
                    <select name="q8" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Sí, sin reflejos</option>
                        <option value="b">Sí, pero con reflejos</option>
                        <option value="c">No, es muy oscuro</option>
                        <option value="d">No, es muy brillante</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>9. ¿Tu postura al sentarte mantiene los pies planos en el suelo?</p>
                    <select name="q9" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Siempre</option>
                        <option value="b">A veces</option>
                        <option value="c">Rara vez</option>
                        <option value="d">Nunca</option>
                    </select>
                </div>
                <div class="quiz-question">
                    <p>10. ¿Realizas tareas que requieren movimientos repetitivos de manos o brazos?</p>
                    <select name="q10" required>
                        <option value="" disabled selected>Selecciona una opción</option>
                        <option value="a">Nunca</option>
                        <option value="b">Ocasionalmente</option>
                        <option value="c">Frecuentemente</option>
                        <option value="d">Siempre</option>
                    </select>
                </div>
                <button type="submit" class="submit-button">Enviar Respuestas</button>
            </form>
        </section>

        <section id="resultados" class="results-section" style="display: none;">
            <h2>Resultados y Recomendaciones</h2>
            <p id="recomendaciones"></p>
            <p id="metodologias-sugeridas"></p>
        </section>

        <section id="metodologias" class="section">
            <h2>Metodologías de Análisis</h2>
            <div class="filter-section">
                <label for="methodology-filter">Filtrar metodologías: </label>
                <select id="methodology-filter">
                    <option value="all">Todas</option>
                    <option value="repetitividad">Repetitividad</option>
                    <option value="carga-postural">Carga Postural</option>
                    <option value="manipulacion-cargas">Manipulación de Cargas</option>
                    <option value="puestos-oficina">Puestos de Oficina</option>
                </select>
            </div>
            <div class="methodology-grid" id="methodology-grid">
                <div class="methodology-card" data-category="repetitividad">
                    <img src="https://www.ergoibv.com/wp-content/uploads/2023/07/Metodo-Ocra-Index.jpg" alt="OCRA">
                    <h3>Checklist OCRA</h3>
                    <p>Evalúa riesgos por movimientos repetitivos de extremidades superiores.</p>
                    <a href="https://www.ergonautas.upv.es/metodos/ocra/ocra-ayuda.php" target="_blank">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://ergonomiaweb.com/wp-content/uploads/2018/09/RULA.png" alt="RULA">
                    <h3>RULA</h3>
                    <p>Rapid Upper Limb Assessment: Analiza posturas en tareas repetitivas o estáticas.</p>
                    <a href="https://www.ergonautas.upv.es/metodos/rula/rula-ayuda.php" target="_blank">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh84xkrtS3M52CXcBgALDVn9zLkG6Hy-bm_yOhgSU0d9JlvrlYlKKThd1MxnBau7mC5p5LYdmUJQBXn56GWbIBeXtLdGplv7Q7uhM5xncyHvScV_UosUa0wRxWSyIVhwjROlFp_k7I4cIiJ/s1600/carga+postural.jpg" alt="REBA">
                    <h3>REBA</h3>
                    <p>Rapid Entire Body Assessment: Evalúa riesgos posturales en todo el cuerpo.</p>
                    <a href="https://www.ergonautas.upv.es/metodos/reba/reba-ayuda.php" target="_blank">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://ergonomiaweb.com/wp-content/uploads/2018/09/OWAS.png" alt="OWAS">
                    <h3>OWAS</h3>
                    <p>Owako Working Posture Analysis System: Identifica posturas de trabajo perjudiciales.</p>
                    <a href="https://www.ergonautas.upv.es/metodos/owas/owas-ayuda.php" target="_blank">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://0701.static.prezi.com/preview/v2/v355zl6yh2szynj4t2p2l7blu76jc3sachvcdoaizecfr3dnitcq_3_0.png" alt="EPR">
                    <h3>EPR</h3>
                    <p>Evaluación de Posturas Repetitivas: Evalúa riesgos por posturas prolongadas.</p>
                    <a href="https://www.ergonautas.upv.es/metodos/epr/epr-ayuda.php" target="_blank">Más info</a>
                </div>
                <div class="methodology-card" data-category="manipulacion-cargas">
                    <img src="https://www.satirnet.com/satirnet/wp-content/uploads/2018/01/levantamiento.jpg" alt="NIOSH">
                    <h3>NIOSH</h3>
                    <p>Ecuación de Levantamiento NIOSH: Calcula riesgos en levantamiento de cargas.</p>
                    <a href="https://www.ergonautas.upv.es/metodos/niosh/niosh-ayuda.php" target="_blank">Más info</a>
                </div>
                <div class="methodology-card" data-category="puestos-oficina">
                    <img src="https://hse.software/wp-content/uploads/2022/09/Metodo-Rosa-SST.webp" alt="ROSA">
                    <h3>ROSA</h3>
                    <p>Rapid Office Strain Assessment: Evalúa riesgos en trabajos de oficina.</p>
                    <a href="https://www.ergonautas.upv.es/metodos/rosa/rosa-ayuda.php" target="_blank">Más info</a>
                </div>
                <div class="methodology-card" data-category="carga-postural">
                    <img src="https://static.docsity.com/documents_first_pages/2019/07/06/e204fe65627b9d2343655c4f634d4ade.png" alt="LEST">
                    <h3>LEST</h3>
                    <p>Método LEST: Analiza condiciones de trabajo, incluyendo carga postural.</p>
                    <a href="https://www.ergonautas.upv.es/metodos/lest/lest-ayuda.php" target="_blank">Más info</a>
                </div>
                <div class="methodology-card" data-category="manipulacion-cargas">
                    <img src="https://www.auracapacitaciones.com/wp-content/uploads/2022/10/ergonomia2.jpg" alt="LCE">
                    <h3>LCE</h3>
                    <p>Límite de Carga Evaluado: Evalúa carga física en tareas dinámicas.</p>
                    <a href="https://www.ergonautas.upv.es/metodos/lce/lce-ayuda.php" target="_blank">Más info</a>
                </div>
            </div>
        </section>

        <section id="contacto" class="contact-section section">
            <h2>Contacto</h2>
            <p>Síguenos en redes o envíanos un mensaje:</p>
            <div class="social-links">
                <a href="https://facebook.com" target="_blank">Facebook</a>
                <a href="https://tiktok.com" target="_blank">TikTok</a>
                <a href="https://wa.me/3127615894" target="_blank">WhatsApp</a>
            </div>
            <form>
                <input type="email" placeholder="Tu correo" required>
                <textarea placeholder="Tu mensaje" required></textarea>
                <button type="submit" class="submit-button">Enviar</button>
            </form>
        </section>
    </div>

    <footer>
        <p>© 2023 Portafolio de Ergonomía</p>
    </footer>

    <script>
        // Modo oscuro/claro
        document.getElementById('theme-toggle').addEventListener('click', function() {
            document.body.classList.toggle('dark-mode');
            this.textContent = document.body.classList.contains('dark-mode') ? 'Modo Claro' : 'Modo Oscuro';
        });

        // Iniciar quiz
        document.getElementById('start-quiz').addEventListener('click', function() {
            document.getElementById('portada').style.display = 'none';
            document.getElementById('quiz').style.display = 'block';
        });

        // Compartir enlace
        document.getElementById('share-link').addEventListener('click', function() {
            const url = window.location.href;
            navigator.clipboard.writeText(url).then(() => {
                const message = document.getElementById('share-message');
                message.style.display = 'block';
                setTimeout(() => {
                    message.style.display = 'none';
                }, 2000);
            }).catch(err => {
                console.error('Error al copiar el enlace: ', err);
                alert('No se pudo copiar el enlace. Por favor, cópialo manualmente: ' + url);
            });
        });

        // Procesar respuestas del quiz
        document.getElementById('quiz-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const respuestas = {
                q1: document.querySelector('select[name="q1"]').value,
                q2: document.querySelector('select[name="q2"]').value,
                q3: document.querySelector('select[name="q3"]').value,
                q4: document.querySelector('select[name="q4"]').value,
                q5: document.querySelector('select[name="q5"]').value,
                q6: document.querySelector('select[name="q6"]').value,
                q7: document.querySelector('select[name="q7"]').value,
                q8: document.querySelector('select[name="q8"]').value,
                q9: document.querySelector('select[name="q9"]').value,
                q10: document.querySelector('select[name="q10"]').value
            };

            let recomendaciones = "Te recomendamos: ";
            let metodologias = "Consulta las metodologías: ";

            // Lógica para las recomendaciones
            if (respuestas.q1 === 'c' || respuestas.q1 === 'd') {
                recomendaciones += "tomar descansos frecuentes al usar el computador y ajustar tu postura. ";
                metodologias += "ROSA, RULA, ";
            } else {
                recomendaciones += "mantener una buena postura al trabajar. ";
            }

            if (respuestas.q2 === 'c' || respuestas.q2 === 'd') {
                recomendaciones += "Usar técnicas de levantamiento seguras y evaluar riesgos de carga. ";
                metodologias += "NIOSH, LCE, ";
            }

            if (respuestas.q3 === 'b' || respuestas.q3 === 'c' || respuestas.q3 === 'd') {
                recomendaciones += "Asegúrate de usar una silla con soporte lumbar ajustable. ";
                metodologias += "REBA, OWAS, ";
            }

            if (respuestas.q4 === 'b' || respuestas.q4 === 'c' || respuestas.q4 === 'd') {
                recomendaciones += "Ajusta la altura de tu monitor al nivel de los ojos para reducir la tensión en el cuello. ";
                metodologias += "ROSA, ";
            }

            if (respuestas.q5 === 'c' || respuestas.q5 === 'd') {
                recomendaciones += "Incorpora pausas activas cada hora para reducir la fatiga. ";
                metodologias += "EPR, ";
            }

            if (respuestas.q6 === 'c' || respuestas.q6 === 'd') {
                recomendaciones += "Consulta a un especialista por molestias frecuentes en cuello o espalda. ";
                metodologias += "RULA, REBA, ";
            }

            if (respuestas.q7 === 'b' || respuestas.q7 === 'c' || respuestas.q7 === 'd') {
                recomendaciones += "Considera usar un teclado y ratón ergonómicos para mayor comodidad. ";
                metodologias += "OCRA, ROSA, ";
            }

            if (respuestas.q8 === 'b' || respuestas.q8 === 'c' || respuestas.q8 === 'd') {
                recomendaciones += "Mejora la iluminación de tu espacio para evitar reflejos o fatiga visual. ";
                metodologias += "LEST, ";
            }

            if (respuestas.q9 === 'b' || respuestas.q9 === 'c' || respuestas.q9 === 'd') {
                recomendaciones += "Asegúrate de que tus pies estén planos en el suelo para mantener una postura adecuada. ";
                metodologias += "REBA, OWAS, ";
            }

            if (respuestas.q10 === 'c' || respuestas.q10 === 'd') {
                recomendaciones += "Evalúa los movimientos repetitivos para prevenir lesiones. ";
                metodologias += "OCRA, RULA, ";
            }

            // Mostrar resultados
            document.getElementById('recomendaciones').textContent = recomendaciones;
            document.getElementById('metodologias-sugeridas').textContent = metodologias.slice(0, -2) + ".";
            document.getElementById('quiz').style.display = 'none';
            document.getElementById('resultados').style.display = 'block';
        });

        // Filtrar metodologías
        document.getElementById('methodology-filter').addEventListener('change', function() {
            const filterValue = this.value;
            const cards = document.querySelectorAll('.methodology-card');
            cards.forEach(card => {
                if (filterValue === 'all' || card.getAttribute('data-category') === filterValue) {
                    card.classList.remove('hidden');
                } else {
                    card.classList.add('hidden');
                }
            });
        });
    </script>
</body>
</html>
