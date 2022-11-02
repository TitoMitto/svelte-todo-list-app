<script type="ts">
    let userInput = "";
    let todoItems: string[] = [];

    function addToList(e: Event){
        e.preventDefault();
        todoItems = [...todoItems, userInput];
    }

    function removeItem(index: number){
        todoItems.splice(index, 1);
        todoItems = [...todoItems];
    }
</script>


<h3> Tasks </h3>

{#if todoItems.length > 0}
You have { todoItems.length } task(s)
{:else}
No tasks added
<br>
{/if}

{#each todoItems as todoItem, index}

    <p> { index + 1}. {todoItem}  <button class="danger" on:click={()=>removeItem(index)}> X </button> </p>
{/each}

<form on:submit={addToList}>
    <input type="text" bind:value={userInput}>
    <button type="submit">Add Todo</button>
</form>
<a href="/about">About</a>

<style>
    .danger {
        color: red;
        cursor: pointer;
    }
</style>