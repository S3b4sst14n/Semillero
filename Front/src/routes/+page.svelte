<svelte:head>
    <title>CodeLabs</title>
    <meta name="description" content="principal icon" />
    <link rel="icon" href="/Logistica.png" />
</svelte:head>

<style>
  .background-hero {
    background-image: url('/bck2.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    min-height: 100vh;
    position: relative;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
  }

  /* Overlay oscuro para mejorar contraste */
  .background-hero::before {
    content: "";
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, 0.5); 
    z-index: 1;
  }

  .hero-content {
    position: relative;
    z-index: 2;
    max-width: 800px;
    padding: 2rem;
  }

  .hero-content h1 {
    font-size: 3rem;
    font-weight: bold;
    margin-bottom: 1rem;
  }

  .hero-content p {
    font-size: 1.2rem;
    line-height: 1.6;
    margin-bottom: 2rem;
  }

  .hero-content a {
    background-color: #0d6efd;
    color: white;
    padding: 0.75rem 1.5rem;
    text-decoration: none;
    border-radius: 0.5rem;
    font-weight: 500;
    transition: background-color 0.3s ease;
  }

  .hero-content a:hover {
    background-color: #0b5ed7;
  }

  @media (max-width: 600px) {
    .hero-content h1 {
      font-size: 2rem;
    }

    .hero-content p {
      font-size: 1rem;
    }
  }
</style>

<div class="background-hero">
  <div class="hero-content">
    <h1>Zona Franca de Barranquilla</h1>
    <p>
      Optimiza, controla y mejora los procesos logísticos en la Zona Franca de Barranquilla con nuestro sistema enfocado en la gestión eficiente de los tiempos de carga y descarga.
      Un proyecto del semillero CodeLabs, orientado a la transformación digital y la mejora operativa del sector logístico.
    </p>
    <a href="/ejbase">Conoce nuestro proyecto</a>
  </div>
</div>
