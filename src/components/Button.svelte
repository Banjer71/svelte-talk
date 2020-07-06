<script>
  export let type = "primary";
</script>

<style>
  button {
    border: 0;
    cursor: pointer;
    border-radius: 6px;
    padding: 8px 12px;
    font-weight: bold;
    box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
  }

  .primary {
    background: #ff5500;
    color: white;
  }

  .secondary {
    background: #456dc4;
    color: white;
  }

  .primary.inverse {
    background: #fff;
    color: #ff5500;
    border: 2px solid #ff5500;
  }

  .secondary.inverse {
    background: #fff;
    color: #456dc4;
    border: 2px solid #456dc4;
  }
</style>

<button class={type} on:click>
  <slot />
</button>
