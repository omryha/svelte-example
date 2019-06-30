<script>
    export let items;
    $: cartTotal = items.reduce((sum, curValue) => {
        return sum + curValue.price;
    },0);
</script>
<style>
    ul {
        list-style: none;
        margin:1rem;
        padding: 0;
    }
    li {
        margin: .5rem 0;
        padding: .5rem;
        border: 1px solid #ccc;
    }

    h1 {
        font-size:1.5rem;
        margin: 1rem;
    }
</style>
{#if items.length === 0}
    <p>No Items</p>
    {:else}
    <ul>
        {#each items as item}
        <li>{item.title} - ${item.price}</li>
        {/each}
    </ul>
    <h1>Total: ${cartTotal}</h1>
{/if}