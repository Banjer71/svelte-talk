<script>
  export let showModal = false;
  let isPromo = true;
  export let message;
  export let modalPics;
</script>

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    position: fixed;
    background: rgba(0, 0, 0, 0.7);
    overflow: auto;
  }

  .modal {
    width: 90%;
    border-radius: 5px;
    padding: 20px;
    margin: 15px auto;
    background-color: #ff5500;
    text-align: left;
    color: #fff;
    font-size: 1.2rem;
    font-family: "Open Sans", sans-serif;
  }

  .modal-list {
    padding: 20px;
  }

  img {
    display: block;
    margin: 0 auto;
  }
  
</style>

{#if showModal}
  <div class="backdrop" class:promo={isPromo} on:click>
    {#if modalPics}
      <img src={modalPics} alt="codice" width="800"/>
    {:else}
      <div class="modal">
        <ul class='modal-list'>
          {@html message}
        </ul>
      </div>
    {/if}
  </div>
{/if}
