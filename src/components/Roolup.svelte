<script>
  import Modal from "./Modal.svelte";
  import Button from "./Button.svelte";
  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };

  let fotoBind = "../../img/rollup.png";
  let install = "../../img/install.jpg";
</script>

<style>
  .conf {
    width: 100%;
    margin-top: 25px;
    font-family: "Open Sans", sans-serif;
  }

  h1 {
    margin: 1rem auto;
    padding: 10px;
  }

  p {
    margin: 1rem 0;
    padding: 10px;
  }

  .conf img {
    max-width: 100%;
  }

  @media screen and (min-width: 780px) {
    .conf {
      max-width: 800px;
    }

    .conf p {
      margin: 2rem auto;
    }
  }
</style>

<Modal
  {showModal}
  on:click={toggleModal}
  message="Rollup config file"
  modalPics={fotoBind} />
<div class="conf">
  <h1>Template, setting and configurations</h1>
  <p>
    ...to create a new application we need to install a sveltejs/template that
    downloads all the files and folders to start our app.
    <br />
    The structure is very similar to other frameworks like React, but the size is
    lighter than the others.
  </p>
  <p>
    If we also run npm install to grab all the modules folders, we will notice
    that the size of the application is much less heavy than the one created
    with create-react-app
  </p>
  <img src={install} alt="install pics" />
  <p>
    The rollup.config.js file is basically the webpack file in React. 
  </p>
</div>
<div class="btn-container">
  <Button on:click={toggleModal}>Show Slide</Button>
</div>
