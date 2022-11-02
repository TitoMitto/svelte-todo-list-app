<script type="ts">
    let todoItems: string[] = ["Hooota", "Gooota"];

</script>


<h3> About </h3>
{#each todoItems as todoItem, index}

    <p> { index + 1}. {todoItem}   </p>
{/each}
<a href="/">Home</a>