<script>
    export let showModal = false;
    let isPromo = true;
    export let instrument;
    export let message;
</script>

<style>
    .backdrop {
        width: 80%;
        height: 80%;
        top:50%;
        left: 50%;
        transform: translate(-50%, -50%);
        position: fixed;
        background: rgba(0, 0, 0, 0.8);
    }

    .modal {
        max-width: 400px;
        border-radius: 5px;
        padding: 10px;
        margin:10% auto;
        background-color: #fff;
        text-align: center;
    }

    
</style>

{#if showModal}
<div class="backdrop" class:promo={isPromo} on:click>
    <div class="modal">
       {message}
    </div>
</div>
{/if}