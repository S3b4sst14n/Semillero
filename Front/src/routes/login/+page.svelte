<script>
    let email = '';
    let password = '';
    let error = '';

    function handleLogin() {
        if (!email || !password) {
            error = 'Completa todos los campos.';
            return;
        }
        error = '';
        alert('Inicio de sesión exitoso');
    }
</script>

<style>
    .login-container {
        max-width: 350px;
        margin: 60px auto;
        padding: 2rem;
        border-radius: 8px;
        background: #fff;
        box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
    h2 {
        text-align: center;
        margin-bottom: 1.5rem;
    }
    label {
        display: block;
        margin-bottom: 0.5rem;
        font-weight: 500;
    }
    input {
        width: 100%;
        padding: 0.5rem;
        margin-bottom: 1.2rem;
        border: 1px solid #ccc;
        border-radius: 4px;
    }
    button {
        width: 100%;
        padding: 0.7rem;
        background: #1976d2;
        color: #fff;
        border: none;
        border-radius: 4px;
        font-size: 1rem;
        cursor: pointer;
    }
    .error {
        color: #d32f2f;
        margin-bottom: 1rem;
        text-align: center;
    }
</style>

<div class="login-container">
    <h2>Iniciar Sesión</h2>
    {#if error}
        <div class="error">{error}</div>
    {/if}
    <form on:submit|preventDefault={handleLogin}>
        <label for="email">Correo electrónico</label>
        <input
            id="email"
            type="email"
            bind:value={email}
            placeholder="Ingresa tu correo"
            required
        />

        <label for="password">Contraseña</label>
        <input
            id="password"
            type="password"
            bind:value={password}
            placeholder="Ingresa tu contraseña"
            required
        />

        <button type="submit">Entrar</button>
    </form>
</div>