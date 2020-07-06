<script>
  import { createEventDispatcher } from "svelte";
  import Button from "./Button.svelte";
  import Modal from "./Modal.svelte";

  const dispatch = createEventDispatcher();

  let name;
  let lastname;
  let age;
  let instrument;
  let genres = [];

  const handleSubmit = () => {
    const person = {
      name,
      lastname,
      age,
      genres,
      instrument,
      id: Date.now().toString()
    };
    console.log(name, lastname, age, genres, instrument);
    dispatch("addPerson", person);
  };

  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };

  let formComponent = "../../img/createformcomponent.png";
</script>

<style>
  form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 100%;
    margin: 5rem 0;
  }

  .fav-music {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    align-items: center;
  }

  select {
    padding: 5px;
  }

  input {
    padding: 5px;
    margin: 4px;
  }

  @media screen and (min-width: 780px) {
    form {
      width: 450px;
    }
  }
</style>

<Modal {showModal} on:click={toggleModal} modalPics={formComponent} />

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="text" placeholder="lastname" bind:value={lastname} />
  <input type="number" placeholder="age" bind:value={age} />
  <br />
  <div class="fav-music">
    <label>Favourite Music</label>

    <input type="checkbox" bind:group={genres} value="Rock" />
    Rock
    <input type="checkbox" bind:group={genres} value="Blues" />
    Blues
    <input type="checkbox" bind:group={genres} value="Country" />
    Country
    <input type="checkbox" bind:group={genres} value="Old Time Music" />
    Old Time Music
    <input type="checkbox" bind:group={genres} value="jazz" />
    Jazz
  </div>


  <br />
  <label>Instruments</label>
  <select bind:value={instrument}>
    <option value="banjo">Banjo</option>
    <option value="fiddle">Fiddle</option>
    <option value="guitar">Guitar</option>
    <option value="mandolin">Mandolin</option>
    <option value="harmonica">Harmonica</option>
  </select>

  <Button type="secondary reverse">Add Person</Button>
</form>
<div class="btn-container">
  <Button on:click={toggleModal} type="secondary">Show Form Code</Button>
</div>
