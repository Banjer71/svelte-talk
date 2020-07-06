<script>
  import Modal from "./Modal.svelte";
  import Button from "./Button.svelte";

  let reusabelCom = "../../img/reusablecomp.png";

  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };

</script>

<style>
  .component {
    margin-top: 25px;
  }

  h1 {
    margin: 1rem auto;
    padding: 10px;
  }

  p {
    margin: 1rem 0;
    padding: 10px;
  }

  @media screen and (min-width: 780px) {
    .component {
      max-width: 800px;
    }
  }
</style>

<Modal {showModal} on:click={toggleModal} modalPics={reusabelCom} />
<div class="component">
  <h1>Components</h1>
  <p>
    Components are the building blocks of the websites. They can be used and
    reused more than once and customized
  </p>
  <p>
    A component can be nested and renderd inside other components. So we can have
    big components like Navbar, Sidebar or Footer that could contain other
    small components like cards or buttons
  </p>
  <p>
    In Svelte we create components in the src folder, usually if the application
    is a small one, we gather all the components in the src folder, but it is a
    good practice to create at least one components folder inside the src folder.
    This allows to keep the file structure organized.
  </p>
  <p>
    To create a component in Svelte, we create a new file named with a capital
    letter and with the extension .svelte
    <br />
    The file just created will contain a &lt;script&gt; tag a &lt;style&gt; tag and the html elements
  </p>

</div>
<div class="btn-container">
  <Button on:click={toggleModal}>Show Slide</Button>
</div>
