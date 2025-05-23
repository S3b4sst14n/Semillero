<script>
    import { onMount } from 'svelte';

    let todos = [];
    let loading = false;
    let error = null;

    onMount(async () => {
        try {
            loading = true;
            const response = await fetch('https://jsonplaceholder.typicode.com/todos');
            if (!response.ok) {
                throw new Error('Error fetching todos');
            }
            todos = await response.json();
        } catch (err) {
            error = err.message;
        } finally {
            loading = false;
        }
    });
</script>

<div class="container p-4">
    <h2 class="mb-4">Lista</h2>
    {#if loading}
        <p class="text-center">Cargando...</p>
    {:else if error}
        <p>Error: {error}</p>
    {:else}
        <div class="overflow-auto">
            <table class="min-w-full bg-white border border-gray-300">
                <thead class="bg-gray-100">
                    <tr>
                        <th class="px-4 py-2 border">ID</th>
                        <th class="px-4 py-2 border">Usuario ID</th>
                        <th class="px-4 py-2 border">Título</th>
                        <th class="px-4 py-2 border">Completado</th>
                    </tr>
                </thead>
                <tbody>
                    {#each todos as todo}
                        <tr>
                            <td class="px-4 py-2 border">{todo.id}</td>
                            <td class="px-4 py-2 border">{todo.userId}</td>
                            <td class="px-4 py-2 border">{todo.title}</td>
                            <td class="px-4 py-2 border">
                                <span class={todo.completed ? 'text-green-500' : 'text-red-500'}>
                                    {todo.completed ? 'Sí' : 'No'}
                                </span>
                            </td>
                        </tr>
                    {/each}
                </tbody>
            </table>
        </div>
    {/if}
</div>
