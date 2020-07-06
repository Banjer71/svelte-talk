<script>
  import { createEventDispatcher } from "svelte";
  export let showItem;

  let items = [
    "What is Svelte",
    "Template Creation",
    "Data Binding",
    "Components",
    "Form"
  ];

  const dispatch = createEventDispatcher();
</script>

<style>
  .list-args li {
    margin: 5px;
    padding: 5px;
    font-size: 0.9rem;
    color: #efefef;
    font-family: "Open Sans", sans-serif;
    cursor: pointer;
  }

  .active {
    color: black;
  }

  @media screen and (min-width: 780px) {
    .list {
      display: grid;
      place-items: center;
      min-height: 100vh;
    }

    .list-args li {
      font-size: 1.2rem;
    }
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
