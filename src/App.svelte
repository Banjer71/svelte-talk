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
    "Form",
    "Fetch and OnMount"
  ];

  let showItem = "What is Svelte";

  const handleArg = e => {
    showItem = e.detail;
  };
</script>

<style>
  .first-side {
    margin: 5rem auto 0;
    width: 100%;
    padding: 2.5rem;
  }

  h1 {
    font-family: "Raleway", sans-serif;
    font-weight: 700;
    font-size: 1.5rem;
    line-height: 1.2;
  }

  p {
    font-family: "Open Sans", sans-serif;
    font-size: 1rem;
    color: hsl(0, 0%, 50%);
    margin-top: 1rem;
  }

  .privacy a {
    margin-top: 2rem;
    display: flex;
    flex-direction: row-reverse;
    font-size: 0.7rem;
  }

  @media only screen and (min-width: 780px) {
    .first-side {
      grid-column: 2;
      grid-row: 1;
      padding: 150px 100px 0 50px;
      overflow-y: auto;

      margin-left: 40px;
    }

    p.privacy {
      margin-right: 70px;
      margin-top: 100px;
    }
  }
</style>

<Nav />
<Header>
  <Tabs {showItem} {items} on:changeArg={handleArg} />
</Header>
<section class="first-side">
  <h1>Let's talk about Svelte</h1>

  <p>
    A quick, litghting talk about Svelte, a new
    <strong>compiler</strong>
    library
  </p>

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
