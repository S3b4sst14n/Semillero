<script>
    import { onMount } from 'svelte';

    let datos = [];
    let loading = false;
    let error = null;

    onMount(async () => {
        try {
            loading = true;
            const response = await fetch('http://192.168.1.8:8000/listalecutrat');
            if (!response.ok) {
                throw new Error('Error al obtener los datos del sensor');
            }

            const data = await response.json();
            datos = data.resultado;
        } catch (err) {
            error = err.message;
        } finally {
            loading = false;
        }
    });
</script>

<div class="container p-4">
    <h2 class="mb-4">Datos del Sensor</h2>
    {#if loading}
        <p class="text-center">Cargando datos...</p>
    {:else if error}
        <p class="text-red-500">Error: {error}</p>
    {:else}
        <div class="overflow-auto">
            <table class="min-w-full bg-white border border-gray-300">
                <thead class="bg-gray-100">
                    <tr>
                        <th class="px-4 py-2 border">ID</th>
                        <th class="px-4 py-2 border">Sensor</th>
                        <th class="px-4 py-2 border">Usuario</th>
                        <th class="px-4 py-2 border">Fecha</th>
                        <th class="px-4 py-2 border">Temperatura (°C)</th>
                        <th class="px-4 py-2 border">Humedad (%)</th>
                    </tr>
                </thead>
                <tbody>
                    {#each datos as item}
                        <tr>
                            <td class="px-4 py-2 border">{item.id}</td>
                            <td class="px-4 py-2 border">{item.idSensor}</td>
                            <td class="px-4 py-2 border">{item.idUsuario}</td>
                            <td class="px-4 py-2 border">{item.fecha}</td>
                            <td class="px-4 py-2 border">{item.temperatura}</td>
                            <td class="px-4 py-2 border">{item.humedad}</td>
                        </tr>
                    {/each}
                </tbody>
            </table>
        </div>
    {/if}
</div>
