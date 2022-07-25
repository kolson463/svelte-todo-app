<script>
// @ts-nocheck
import DarkMode from "svelte-dark-mode";

import { afterUpdate } from "svelte";

	import TodoForm from '../components/TodoForm.svelte';
	import Todo from '../components/Todo.svelte';
	import { todos } from '../storage/todoStorage.js';

let theme;


afterUpdate(() => {
	document.body.className = theme; // "dark" or "light"
  });



</script>

<DarkMode bind:theme />

<main>
<button class="border-2 rounded-lg p-3 font-semibold" type="menu" on:click={() => (theme ==="light" ? theme = "dark" : theme = "light"
)}
	>
  {theme ==="light" ? "Toggle Dark Mode" : "Toggle Light Mode"}
</button>
	<h1 class={`text-2xl font-bold text-center my-2 md:text-3xl ${theme === "light" ? 'text-gray-800 '  : 'text-white'}`}>My Todos</h1>
	<TodoForm />
	{#each $todos as todo}
		<Todo {todo} index={todos.id} />
	{/each}
</main>

<style>
	:global(.dark) {
	  background: #032f62;
	  color: #f1f8ff;
	}
  </style>