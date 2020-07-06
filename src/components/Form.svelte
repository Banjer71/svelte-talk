<script>
  import { createEventDispatcher } from "svelte";
  import Button from "./Button.svelte";
  import Modal from "./Modal.svelte";
  import Form from "./FormCreate.svelte";
  import Card from "./Card.svelte";

  
  const dispatch = createEventDispatcher();

  let people = [];
  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };

  const addPerson = e => {
    const person = e.detail;
    people = [person, ...people];
    console.log(people);
  };

  
</script>

<style>

</style>


<Modal {showModal} on:click={toggleModal} message="Form">
  <div class="person">
    {#each people as person}
      <Card
        name={person.name}
        lastname={person.lastname}
        age={person.age}
        instrument={person.instrument}>
        {#if person.genres}
          {#each person.genres as genre}
            <li>{genre}</li>
          {/each}
        {/if}
      </Card>
    {/each}

  </div>
</Modal>

<Form on:addPerson={addPerson} />
<div class="btn-container">
  <Button on:click={toggleModal}>Show Slide</Button>
</div>

