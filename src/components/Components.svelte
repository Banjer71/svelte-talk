<script>
  import Modal from "./Modal.svelte";
  import Button from "./Button.svelte";
  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };

  let component = 'Components can emit events using , or by forwarding DOM events. Listening for component events looks the same as listening for DOM events:'
</script>

<style>

</style>

<Modal {showModal} on:click={toggleModal} message={component} />
<div>
  <h1>Components</h1>
</div>
<div class="btn-container">
  <Button on:click={toggleModal}>Show Slide</Button>
</div>
