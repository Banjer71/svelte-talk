<script>
  import Modal from "./Modal.svelte";
  import Button from "./Button.svelte";
  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };
</script>

<style>

</style>

<Modal {showModal} on:click={toggleModal} message="Reactive Values" />
<div>
  <h1>Reactive Values</h1>
</div>
<div class="btn-container">
  <Button on:click={toggleModal}>Show Slide</Button>
</div>
