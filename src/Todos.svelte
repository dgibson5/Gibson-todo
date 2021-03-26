<script>
    import { fly } from 'svelte/transition';
    let todoItem = '';
    let todoList = [];
    let yes = false;

    //ADD ITEMS FROM INPUT TO ARRAY
    function addToList (){
            todoList = [...todoList, {
                text: todoItem,
                status: false

            }];
            todoItem='';
    }
    //REMOVE ITEMS FROM INPUT TO ARRAY

    function removeFromList(index){
        todoList.splice(index, 1);
        todoList= todoList;
    }
</script>

<form class="form" on:submit|preventDefault={addToList}>
    <input bind:value={todoItem}>
</form>


<ul class="todo-list">
    {#each todoList as item, index}
        <li transition:fly={{y: 20, duration: 200}}> 
        <input bind:checked={item.status} class="check" type='checkbox'>
        <span class:checked={item.status}>{item.text}</span>
        <button class="delete" type="button" on:click={() =>removeFromList(index)}></button>
        </li>

    {/each}
</ul>


<div class="complete">
<label>
	<input type=checkbox bind:checked={yes}>
	Yes, I have completed all my tasks!
</label>

{#if yes}
    <p> CONGRATULATIONS!</p>
    <p>It looks like you have had a very productive day. Click Below to start relaxing. </p>
{:else}
	<p></p>
{/if}

<button disabled={!yes}>
	Relaxation Button
</button>
</div>

<style>

.todo-list{
        list-style: none;
        font-size: 1.5em;
}
.checked{
    text-decoration: line-through;
}

.form{
    font-size:1.5em;
}

.complete{
    margin: 2em;
    font-size: 1.5em;
}

button{
    margin: .5em;
}


</style>