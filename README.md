<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Escuela de Software</title>
  <style>
    :root {
      --color-primario: #ff7f50;
      --color-secundario: #fff5eb;
      --color-texto: #2c2c2c;
      --color-hover: #ffa07a;
    }

    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: var(--color-secundario);
      color: var(--color-texto);
    }

    header {
      background-color: var(--color-primario);
      color: white;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      position: sticky;
      top: 0;
      z-index: 1000;
    }

    nav a {
      color: white;
      text-decoration: none;
      margin: 0 1rem;
      font-weight: bold;
      cursor: pointer;
    }

    nav a:hover {
      text-decoration: underline;
    }

    .hero {
      background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1555066931-4365d14bab8c?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
      background-size: cover;
      background-position: center;
      color: white;
      text-align: center;
      padding: 5rem 2rem;
    }

    .hero h1 {
      font-size: 3rem;
      margin-bottom: 1rem;
      text-shadow: 2px 2px 8px rgba(0,0,0,0.6);
    }

    .hero p {
      font-size: 1.3rem;
      text-shadow: 1px 1px 5px rgba(0,0,0,0.5);
    }

    .container {
      max-width: 1000px;
      margin: auto;
      padding: 2rem;
    }

    section {
      display: none;
      margin: 4rem 0;
    }

    section.active {
      display: block;
      animation: fadeIn 0.5s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    h2 {
      font-size: 2rem;
      margin-bottom: 1rem;
    }

    .btn-inscribirse {
      background-color: var(--color-primario);
      color: white;
      padding: 12px 24px;
      font-size: 18px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      margin-top: 1rem;
    }

    .btn-inscribirse:hover {
      background-color: var(--color-hover);
    }

    footer {
      background-color: #333;
      color: white;
      text-align: center;
      padding: 1rem;
    }

    /* Modal */
    .modal {
      display: none;
      position: fixed;
      z-index: 1001;
      left: 0; top: 0;
      width: 100%; height: 100%;
      background-color: rgba(0,0,0,0.6);
      justify-content: center;
      align-items: center;
    }

    .modal-content {
      background: white;
      padding: 2rem;
      border-radius: 10px;
      width: 90%;
      max-width: 500px;
    }

    .modal-content input, .modal-content button {
      width: 100%;
      margin: 0.5rem 0;
      padding: 0.7rem;
    }

    .close {
      float: right;
      font-size: 24px;
      cursor: pointer;
    }
  </style>
</head>
<body>

<header>
  <div><strong>Escuela de Software</strong></div>
  <nav>
    <a onclick="mostrarSeccion('inicio')">Inicio</a>
    <a onclick="mostrarSeccion('quienes')">Quiénes somos</a>
    <a onclick="mostrarSeccion('cursos')">Cursos</a>
    <a onclick="mostrarSeccion('contacto')">Contacto</a>
  </nav>
</header>

<div class="hero" id="inicio">
  <h1>Convertite en desarrollador</h1>
  <p>Aprendé desde cero hasta nivel profesional en nuestra plataforma</p>
  <button class="btn-inscribirse" onclick="abrirModal()">Inscribite ahora</button>
</div>

<div class="container">
  <section id="quienes">
    <h2>Quiénes somos</h2>
    <p>Somos un equipo apasionado por la educación tecnológica, comprometido a transformar vidas a través de la programación.</p>
  </section>

  <section id="cursos">
    <h2>¿Qué vas a aprender?</h2>
    <ul>
      <li>HTML, CSS y JavaScript</li>
      <li>Backend con Node.js y bases de datos</li>
      <li>Frameworks modernos como React</li>
      <li>Buenas prácticas, Git y despliegue</li>
    </ul>
  </section>

  <section id="contacto">
    <h2>Contacto</h2>
    <p>Email: contacto@escuelasoftware.com</p>
    <p>Teléfono: +595 984 894 449</p>
  </section>
</div>

<footer>
  © 2025 Escuela de Software | <a href="https://github.com/tu-usuario/tu-repositorio" style="color: white;">Ver en GitHub</a>
</footer>

<!-- Modal -->
<div class="modal" id="modalInscripcion">
  <div class="modal-content">
    <span class="close" onclick="cerrarModal()">&times;</span>
    <h2>Formulario de Inscripción</h2>
    <input type="text" placeholder="Nombre completo" />
    <input type="email" placeholder="Correo electrónico" />
    <button onclick="enviarInscripcion()">Enviar</button>
  </div>
</div>

<script>
  // Mostrar solo la sección seleccionada
  function mostrarSeccion(id) {
    const secciones = document.querySelectorAll("section, .hero");
    secciones.forEach(s => s.classList.remove("active"));
    document.getElementById(id).classList.add("active");
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  function abrirModal() {
    document.getElementById("modalInscripcion").style.display = "flex";
  }

  function cerrarModal() {
    document.getElementById("modalInscripcion").style.display = "none";
  }

  function enviarInscripcion() {
    alert("¡Gracias por inscribirte! Te contactaremos pronto.");
    cerrarModal();
  }

  // Mostrar inicio al cargar
  document.addEventListener("DOMContentLoaded", () => {
    mostrarSeccion("inicio");
  });
</script>

</body>
</html>
