<script>
  import Modal from "./Modal.svelte";
  import Button from "./Button.svelte";

  //classic way
  let firstName = "";
  let lastName = "";
  let instrument = "";

  //svelte binding data way
  let svelteName = "Dave";
  let SvelteSurname = "Nacky";
  let SvelteFavInstr = "";

  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };

  let fotoBind = "../../img/databinding.png";
  let excel = "../../img/excel.jpg";

  //reactive value
  $: svelteFullname = `${svelteName} ${SvelteSurname}`;

  //ractive statement
  $: {
    console.log(svelteName);
    svelteName.toLowerCase() === "davide"
      ? alert("did call Davide?")
      : console.log(svelteFullname);
  }

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
  .excel {
    margin: 20px;
  }

  .classic * {
    padding: 10px;
  }

  .binding {
    margin-top: 10px;
  }

  .binding * {
    padding: 10px;
  }
</style>

<Modal
  {showModal}
  on:click={toggleModal}
  message="Binding data"
  modalPics={fotoBind} />

<div class="excel">
  <img src={excel} alt="excel grid" />
  <p>
    The idea of data binding was inspired by the the most reactive programs
    ..the spreadsheet
  </p>
  <p>
    when two cells are binded togheter to a third cell with a forumula , this
    allows us to keep track of their values updated indipendently.
  </p>
</div>
<div class="classic">
  <em>
    Classic way to keep track of the values using different handler functions
  </em>
  <h4>{firstName} {lastName} plays {instrument}</h4>
  <input type="text" on:input={choosename} />
  <input type="text" on:input={chooseLa} />
  <input type="text" on:input={chooseInstrument} />
</div>

<div class="binding">
  <em>
    a simple example od data binding in svelte inspired by the spreadsheet
  </em>
  <h4>{svelteFullname} plays: {SvelteFavInstr}</h4>
  <input type="text" bind:value={svelteName} />
  <input type="text" bind:value={SvelteSurname} />
  <input type="text" bind:value={SvelteFavInstr} />
</div>
<div class="btn-container">
  <Button on:click={toggleModal}>Show Slide</Button>

</div>
