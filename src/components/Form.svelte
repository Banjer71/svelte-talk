<script>
  import Button from "./Button.svelte";
  import Modal from "./Modal.svelte";

  let fields = {
    question: "",
    answerA: "",
    answerB: ""
  };

  const submitHanlder = () => {
    let poll = { ...fields, votesA: 0, votesB: 0, id: Math.random() };
    dispatch("add", poll);
  };

  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };
</script>

<style>
  form {
    width: 100%;
    margin: 0 auto;
    text-align: center;
  }

  .form-field {
    margin: 0 auto;
  }

  input {
    width: 100%;
    border-radius: 3px;
    height: 30px;
    border: 1px solid grey;
  }

  label {
    margin: 10px auto;
  }

  @media only screen and (min-width: 780px) {
    form {
      width: 400px;
      text-align: left;
    }

    .form-field {
      margin: 18px auto;
    }
  }
</style>

<Modal {showModal} on:click={toggleModal} message="Form" />
<form on:submit|preventDefault={submitHanlder}>
  <div class="form-field">
    <label for="question">Poll Question</label>
    <input type="text" id="question" bind:value={fields.question} />
  </div>
  <div class="answer-field">
    <label for="answer-a">Answer A</label>
    <input type="text" id="answer-a" bind:value={fields.answerA} />
  </div>
  <div class="form-field">
    <label for="answer-b">Answer-b</label>
    <input type="text" id="answer-b" bind:value={fields.answerB} />
  </div>
  <Button type="secondary" flat={true} inverse={true}>Add Poll</Button>
</form>

<div class="btn-container">
  <Button on:click={toggleModal}>Show Slide</Button>
</div>
