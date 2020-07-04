<script>
  import Modal from "./Modal.svelte";
  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };
</script>

<style>

</style>
<Modal {showModal} on:click={toggleModal} message='Rollup config file' />
<div>
  <h1>Rollup configuration file</h1>
</div>
<button on:click={toggleModal}>Show Slide</button>