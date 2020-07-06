<script>
  import Modal from "./Modal.svelte";
  import Button from "./Button.svelte";

  let reusabelCom = "../../img/reusablecomp.png";

  let showModal = false;
  const toggleModal = () => {
    showModal = !showModal;
  };

  let component =
    "Components can emit events using , or by forwarding DOM events. Listening for component events looks the same as listening for DOM events:";
</script>

<style>
  .component {
    /* width: 100%; */
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
    Componets are the building blocks of the websites. They can be used and
    reused more than one time and customized
  </p>
  <p>
    A componet can be nested and renderd inside other components. So we can have
    big components like Navbar , Sidebar or Footer that could contain other
    small componets like cards or buttons
  </p>
  <p>
    In Svelte we create components in the src folder, usually if the application
    is a small one , we gather all the componets in the src folder, buit is a
    good practice to create at least a components folder inside the src folder.
    This allows us to keep organized the file structure.
  </p>
  <p>
    To create a component in Svelte, we create a new file named with a capitol
    letter and with the extensione .svelte
    <br />
    The file jsut create will contain, a
  </p>

</div>
<div class="btn-container">
  <Button on:click={toggleModal}>Show Slide</Button>
</div>
