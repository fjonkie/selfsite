<script lang=ts>
    import Icon from '@iconify/svelte';
    import { buttonId } from '../stores';

    export let currentButton: number = 1;
    export let buttonLabel: string = "placeholder";

    function showHideText() {
        if($buttonId !== currentButton) {
            buttonId.set(0)
            setTimeout(() => {
                buttonId.set(currentButton)
            }, 350);
        }
    }
</script>


<button on:click={showHideText}>
    {#if $buttonId === currentButton}
    <Icon icon="material-symbols:arrow-drop-down-rounded"></Icon>
    {:else}
    <Icon icon="material-symbols:arrow-drop-up-rounded"></Icon>
    {/if}
    {buttonLabel}
</button>

<style>
    button {
        background-color: #040404;
        color: white;
        border-radius: 15px;
        margin-bottom: 0.5rem;
        margin-top: 0.5rem;
    }
</style>