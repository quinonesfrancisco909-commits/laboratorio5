<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="author" content="Frasisco Quiñoes - 8-1035-2155">
    <meta name="description" content="Plataforma de reproducción de video estilo MiTube para visualización de contenido multimedia.">
    <title>Introducción a HTML5 y CSS3 - MiTube</title>
    <!-- PARTE 2: Integración de CSS Externo -->
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <!-- PARTE 2: ENCABEZADO Y BARRA DE NAVEGACIÓN -->
    <header>
        <a href="#">
            <img src="https://picsum.photos/120/40" alt="Logo de MiTube" width="120">
        </a>
        
        <form action="#" role="search">
            <input type="search" name="q" placeholder="Buscar" required>
            <button type="submit" class="btn">Buscar</button>
        </form>

        <!-- PARTE 4: Clases navbar y nav-link -->
        <nav class="navbar">
            <ul>
                <li><a href="#" class="nav-link">Inicio</a></li>
                <li><a href="#" class="nav-link">Suscripciones</a></li>
                <li><a href="#" class="nav-link">Mi biblioteca</a></li>
            </ul>
        </nav>
    </header>

    <!-- PARTE 3 Y 4: CONTENIDO PRINCIPAL Y COMENTARIOS -->
    <main>
        <!-- PARTE 5: ID video-player -->
        <section id="video-player">
            <video width="640" height="360" controls poster="https://picsum.photos/640/360">
    <source src="https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ForBiggerBlazes.mp4" type="video/mp4">
    
</video>
            
            <h1>Introducción a HTML5 y CSS3</h1>
            
            <p>
                <span>15,420 vistas</span> • 
                <time datetime="2026-08-20">20 de agosto de 2026</time>
            </p>

            <div>
                <img src="https://picsum.photos/48" alt="Avatar del canal" width="48">
                <span>Canal de Desarrollo Web</span>
                <!-- PARTE 4: Clase btn -->
                <button type="button" class="btn">Suscribirse</button>
            </div>

            <p>En este tutorial aprenderás las bases fundamentales de HTML5 y CSS3 para construir sitios web modernos, estructurados y totalmente accesibles desde cero.</p>
        </section>

        <!-- Sección de Comentarios -->
        <section>
            <h2>Comentarios</h2>

            <!-- Formulario de comentario -->
            <form id="commentForm">
                <label for="comentario">Deja tu comentario:</label><br>
                <textarea id="comentario" name="comentario" rows="3" placeholder="Agrega un comentario público..." required></textarea><br>
                <!-- PARTE 4: Clase btn -->
                <button type="submit" class="btn">Comentar</button>
            </form>

            <!-- Lista donde se renderizan los comentarios -->
            <div id="commentList">
                <article>
                    <img src="https://picsum.photos/40/40?random=1" alt="Avatar de Carlos Pérez" width="40">
                    <span>Carlos Pérez</span>
                    <time datetime="2026-08-21">21 de agosto de 2026</time>
                    <p>¡Excelente explicación! Me ayudó mucho a entender las etiquetas semánticas.</p>
                </article>

                <article>
                    <img src="https://picsum.photos/40/40?random=2" alt="Avatar de Ana Gómez" width="40">
                    <span>Ana Gómez</span>
                    <time datetime="2026-08-22">22 de agosto de 2026</time>
                    <p>Muy claro todo. ¿Cuándo suben la siguiente parte de CSS3?</p>
                </article>

                <article>
                    <img src="https://picsum.photos/40/40?random=3" alt="Avatar de Luis Rodríguez" width="40">
                    <span>Luis Rodríguez</span>
                    <time datetime="2026-08-23">23 de agosto de 2026</time>
                    <p>Gran contenido, justo lo que necesitaba para repasar antes del examen.</p>
                </article>
            </div>
        </section>
    </main>

    <!-- PARTE 5: ID sugeridos y PARTE 4: Clases card en articles -->
    <aside id="sugeridos">
        <h2>Videos sugeridos</h2>

        <article class="card">
            <a href="#">
                <img src="https://picsum.photos/168/94?random=4" alt="Miniatura del video Curso de CSS Grid" width="168">
            </a>
            <h3>Curso de CSS Grid desde Cero</h3>
            <p>Canal de Desarrollo Web</p>
        </article>

        <article class="card">
            <a href="#">
                <img src="https://picsum.photos/168/94?random=5" alt="Miniatura del video Aprende Flexbox" width="168">
            </a>
            <h3>Aprende Flexbox en 15 Minutos</h3>
            <p>Diseño Web Fácil</p>
        </article>

        <article class="card">
            <a href="#">
                <img src="https://picsum.photos/168/94?random=6" alt="Miniatura del video JavaScript para Principiantes" width="168">
            </a>
            <h3>JavaScript para Principiantes</h3>
            <p>Code Master</p>
        </article>

        <article class="card">
            <a href="#">
                <img src="https://picsum.photos/168/94?random=7" alt="Miniatura del video Guía de Accesibilidad Web" width="168">
            </a>
            <h3>Guía Completa de Accesibilidad Web</h3>
            <p>Frontend Pro</p>
        </article>
    </aside>

    <!-- PARTE 5: ID pie -->
    <footer id="pie">
        <ul>
            <li><a href="#">Acerca de</a></li>
            <li><a href="#">Prensa</a></li>
            <li><a href="#">Copyright</a></li>
            <li><a href="#">Términos</a></li>
            <li><a href="#">Privacidad</a></li>
        </ul>
        <p>&copy; 2026 MiTube</p>
    </footer>

    <!-- SCRIPT JAVASCRIPT PARA AGREGAR COMENTARIOS DINÁMICAMENTE -->
    <script>
        const form = document.getElementById('commentForm');
        const commentList = document.getElementById('commentList');

        form.addEventListener('submit', function(e) {
            e.preventDefault();

            const textarea = document.getElementById('comentario');
            const commentText = textarea.value.trim();

            if (commentText === '') return;

            const today = new Date();
            const dateISO = today.toISOString().split('T')[0];
            const dateFormatted = today.toLocaleDateString('es-ES', {
                year: 'numeric',
                month: 'long',
                day: 'numeric'
            });

            const randomAvatarId = Math.floor(Math.random() * 100) + 10;

            const newComment = document.createElement('article');
            newComment.innerHTML = `
                <img src="https://picsum.photos/40/40?random=${randomAvatarId}" alt="Avatar de Usuario" width="40">
                <span>Usuario Anónimo</span>
                <time datetime="${dateISO}">${dateFormatted}</time>
                <p>${commentText}</p>
            `;

            commentList.prepend(newComment);
            textarea.value = '';
        });
    </script>

</body>
</html>
