<script>
    export let message;
    export let isPromo = false;
    let showModal = true;

    console.log(message);
</script>

{#if showModal}
<!-- class: promo={boolValue} -> States that boolValue is truthy, then add the className called promo to div-->
    <div class="backdrop" class:promo={isPromo}> 
        <div class="modal">
            <p>{message}</p>
        </div>
    </div>
{/if}

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0, 0, 0, 0.8);
    }

    .modal {
        padding: 10px;
        margin: 10% auto;
        border-radius: 10px;
        max-width: 400px;
        text-align: center;
        background-color: white;
    }

    .promo .modal {
        background-color: crimson;
        color: white;
    }
</style>