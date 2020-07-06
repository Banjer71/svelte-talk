<script>
  import Youtube from "@sveltecasts/svelte-youtube";
  import Modal from "./Modal.svelte";
  import Button from "./Button.svelte";
  

  let showModal = false;

  const toggleModal = () => {
    showModal = !showModal;
  };

  let text = `<li style='padding: 10px'>Svelte is a new framework with the same goal of React, Angular or Vue, with the purpose of build front end applications...but acutally is not a framework but a compiler.</li>
  <li style='padding: 10px'>Svelte compiles components during the build step and allow us to load a single bundle.js on our page to render our application.</li>
  <img src='../../img/compiler.jpg' alt='compiler' width=200/>
  <li style='padding: 10px'>It doesn't use a Virtual DOM, so we don't have to wait for our components to be rendered from the virtual Dom to the real DOM</li>
  <li style='padding: 10px'>These things make Svelte one of the fastest "Compiler..framework" nowdays</li>`
  
</script>

<style>
    h1 {
        margin: 5px 0;
    }

    h3 {
        font-family: "Raleway", sans-serif;
    }

    p {
        margin: 10px;
        padding: 10px;
    }
</style>

<div class="intro">
  <h1>What is Svelte</h1>
  <p><strong>...50nth years ago the umanity</strong> </p>
  <p>This are the words of Rich Harris speech during last year conference about Svelte</p>
  <p>It is very interesting and I highly you reccomends to watch it.</p>
  <Modal {showModal} on:click={toggleModal} message={text} />
  <Youtube videoId="AdNJ3fydeao" />

  <div class="btn-container">
    <Button on:click={toggleModal}>Show Slide</Button>
  </div>
</div>
