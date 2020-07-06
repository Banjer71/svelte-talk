<script>
  import Nav from "./components/Nav.svelte";
  import Form from "./components/Form.svelte";
  import Header from "./components/Header.svelte";
  import Tabs from "./components/Tabs.svelte";
  import InputDataBinding from "./components/InputDataBinding.svelte";
  import Modal from "./components/Modal.svelte";
  import Rollup from "./components/Roolup.svelte";
  import ReactiveValues from "./components/ReactiveValues.svelte";
  import Components from "./components/Components.svelte";
  import FetchonMount from "./components/FetchOnmount.svelte";
  import Intro from "./components/Intro.svelte";

  let items = [
    "What is Svelte",
    "Template Creation",
    "Binding Data",
    "Components",
    "Form"
  ];

  let showItem = "What is Svelte";

  const handleArg = e => {
    showItem = e.detail;
  };
</script>

<style>
  .first-side {
    width: 100%;
    margin-top: 2rem;
    padding: 0.8rem;
    font-family: "Open Sans", sans-serif;
  }

  @media only screen and (min-width: 780px) {
    .first-side {
      grid-column: 2;
      grid-row: 1;
      padding: 150px 100px 0 50px;
      overflow-y: auto;
      margin: 9rem 0 0 40px;
      padding: 2.5rem;
    }
  }
</style>

<Nav />
<Header>
  <Tabs {showItem} {items} on:changeArg={handleArg} />
</Header>
<section class="first-side">

  {#if showItem === 'What is Svelte'}
    <Intro />
  {:else if showItem === 'Template Creation'}
    <Rollup />
  {:else if showItem === 'Binding Data'}
    <InputDataBinding />
  {:else if showItem === 'Components'}
    <Components />
  {:else if showItem === 'Form'}
    <Form />
  {:else if showItem === 'Fetch and OnMount'}
    <FetchonMount />
  {/if}

</section>
