<script>
  import { createEventDispatcher } from "svelte";
  export let items;
  export let showItem;

  const dispatch = createEventDispatcher();
</script>

<style>
  .list {
    display: grid;
    place-items: center;
    min-height: 100vh;
  }

  .list-args li {
    margin: 5px;
    padding: 5px;
    font-size: 1.2rem;
    color: #efefef;
    font-family: "Open Sans", sans-serif;
    cursor: pointer;
  }

  .active {
    color: black;
  }
</style>

<div class="list">
  <ul class="list-args">
    {#each items as item}
      <li on:click={() => dispatch('changeArg', item)}>
        <div class:active={item === showItem}>{item}</div>
      </li>
    {/each}

  </ul>
</div>
