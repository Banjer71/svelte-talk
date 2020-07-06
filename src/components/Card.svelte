<script>
    export let name
    export let lastname
    export let instrument;
    export let age;
    
    

</script>

<style>
    .card {
        border: 1px dashed black;
        
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