<script>


    let todo = '';

    import {addTodo} from "../storage/todoStorage.js"
    const handleSubmit = () => {
        todo === '' ? alert("Must enter something for todo!") :

        addTodo(todo);
        todo = ''
    }


</script>

<form class="my-6" on:submit|preventDefault={handleSubmit}>
	<div class="flex flex-col text-sm mb-2 mx-2">
		<label class="font-bold mb-2  " for="todo">New Todo</label>
		<input
			class="text-black appearance-none shadow-sm border border-gray-200 p-2 focus:outline-none focus:border-gray-500 rounded-lg"
			type="text"
			name="todo"
			placeholder="Enter todo!"
            bind:value={todo}
		/>
	</div>
	<div class="mx-2">
	<button class=" w-full bg-blue-500 hover:bg-blue-600 text-white rounded shadow-sm" type="submit"
		>Submit</button
	>
	</div>
</form>
