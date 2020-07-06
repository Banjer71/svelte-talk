<script>
  export let name;
  export let lastname;
  export let instrument;
  export let age;
</script>

<style>
  .card {
    margin: 10px;
    padding: 10px;
  }
</style>

<div class="card">

  <ul>
    <li>{name}</li>
    <li>{lastname}</li>
    <li>{age}</li>
    <li>{instrument}</li>
    <slot />

  </ul>

</div>
