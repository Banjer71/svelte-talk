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
  <li style='padding: 10px'>These things make Svelte one of the fastest "Compiler..framework" nowdays</li>`;
</script>

<style>
  h1 {
    font-family: "Raleway", sans-serif;
    font-weight: 700;
    font-size: 1.5rem;
    line-height: 1.2;
    margin: 5px 0;
  }

  p {
    font-family: "Open Sans", sans-serif;
    font-size: 1rem;
    color: hsl(0, 0%, 50%);
    margin-top: 1rem;
    padding: 10px;
  }
  .video {
    width: 100%;
  }

  /* h1 {
    margin: 5px 0;
  }

  p {
    margin: 10px;
    padding: 10px;
  } */

  @media screen and (min-width: 780px) {
    h1 {
      font-family: "Raleway", sans-serif;
      font-weight: 700;
      font-size: 1.5rem;
      line-height: 1.2;
      margin: 5px 0;
    }

    p {
      font-family: "Open Sans", sans-serif;
      font-size: 1rem;
      color: hsl(0, 0%, 50%);
      margin-top: 1rem;
      padding: 10px;
    }

    .video {
      width: 100%;
    }
  }
</style>

<h1>Let's talk about Svelte</h1>

<p>
  A quick, litghting talk about Svelte, a new
  <strong>compiler</strong>
  library
</p>
<div class="intro">
  <h1>What is Svelte</h1>
  <p>
    <strong>...50th years ago the umanity</strong>
  </p>
  <p>
    These are the first words of Rich Harris speech during last year conference
    about Svelte
  </p>
  <p>It is very interesting and I highly you recommended to watch it.</p>
  <Modal {showModal} on:click={toggleModal} message={text} />
  <div class="video">
    <Youtube videoId="AdNJ3fydeao" />
  </div>

  <div class="btn-container">
    <Button on:click={toggleModal}>Show Slide</Button>
  </div>
</div>
