<script>
	export let showModal = false;
    export let isPromo = false;

    /** Event Modifiers*/
    // once - makes sure the event can only fire once(removes handler)
    // preventDefault - prevent the default action(run e.preventDefault)
    // self - only fires the event if the clicked element is the target.

</script>

{#if showModal}
<!-- class: promo={boolValue} -> States that boolValue is truthy, then add the className called promo to div-->
    <div class="backdrop" class:promo={isPromo} on:click|self> 
        <div class="modal">
            <slot></slot>
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