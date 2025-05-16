<script>
  import { goto } from '$app/navigation';
</script>

<!-- Navbar -->
<nav class="navbar navbar-expand-lg navbar-dark bg-dark px-4">
  <a class="navbar-brand" href="/">CodeLabs</a>
  <button
    class="navbar-toggler"
    type="button"
    data-bs-toggle="collapse"
    data-bs-target="#navbarNav"
    aria-controls="navbarNav"
    aria-expanded="false"
    aria-label="Toggle navigation"
  >
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav ms-auto">
      <li class="nav-item">
        <a class="nav-link" href="/">Inicio</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="/about">Datos de muestra</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="/datos">Visualizacion</a>
      </li>
    </ul>
  </div>
</nav>

<slot />
<footer class="bg-dark text-white text-center py-3">
  <p>&copy; 2025 CodeLabs. Todos los derechos reservados.</p>
</footer>