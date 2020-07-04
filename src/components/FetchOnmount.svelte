<script>
  import Modal from "./Modal.svelte";
  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };
</script>

<style>

</style>
<Modal {showModal} on:click={toggleModal} message='Fetch and onMount' />
<div>
  <h1>Fetch and onMount</h1>
</div>
<button on:click={toggleModal}>Show Slide</button>