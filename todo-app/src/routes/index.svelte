<script>
// @ts-nocheck

	import TodoForm from '../components/TodoForm.svelte';
	import Todo from '../components/Todo.svelte';
	import { todos } from '../storage/todoStorage.js';
</script>

<main>
	<h1 class="text-2xl font-bold text-center text-gray-800 md:text-3xl">My Todos</h1>
	<TodoForm />
	{#each $todos as todo}
		<Todo {todo} index={todos.id} />
	{/each}
</main>
