<script>
export let message = '';
export let showModal = false;
</script>

{#if showModal}
    <div class="backdrop" on:click|self>
        <div class="modal">
            <p>{message}</p>
            <slot name="title"></slot>
            <slot></slot>
        </div>
    </div>
{/if}

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0,0,0,0.8)
    }
    .modal {
        padding: 10px;
        border-radius: 10px;
        max-width: 400px;
        margin: 10% auto;
        text-align: center;
        background-color: white;
    }
</style>