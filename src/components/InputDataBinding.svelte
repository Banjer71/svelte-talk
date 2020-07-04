<script>
import Modal from './Modal.svelte'
  let firstName = "";
  let lastName = "";
  let instrument = "";

  let name = 'Dave'
  let surname ='Nacky'
  let favInstr = ''

let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  }

  $: fullname = `${name} ${surname}`; //reactive value

  const chooseInstrument = e => {
    instrument = e.target.value;
  };

  const choosename = e => {
    firstName = e.target.value;
  };

  const chooseLa = e => {
    lastName = e.target.value;
  };
</script>

<style>

</style>
<!-- {#if instrument === 'banjo'}
	<Modal {instrument} message='Check out our offer'/>
    {:else if firstName.toLowerCase() === 'davide'}
    <Modal {firstName}><p><a href="http://davidenaccarati.com">Davide Naccarati</a></p></Modal>
{/if} -->
<Modal {showModal} on:click={toggleModal} message='Binding data' />
<div>
  <p>{firstName} {lastName} plays {instrument}</p>
  <input type="text" on:input={choosename} />
  <input type="text" on:input={chooseLa} />
  <input type="text" on:input={chooseInstrument} />
</div>

<div>
  <h3>{fullname} plays: ${favInstr}</h3>
  <input type="text" bind:value={name} />
  <input type="text" bind:value={surname} />
  <input type="text" bind:value={favInstr} />
</div>
<button on:click={toggleModal}>Show Slide</button>


