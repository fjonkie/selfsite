<script lang=ts>
    import Icon from '@iconify/svelte';
    import { buttonId } from '../stores';

    let textState: boolean = false;
    export let currentButton: number = 0;

    function showHideText() {
        textState = !textState;
        if($buttonId !== 0 && $buttonId !== currentButton) {
            buttonId.set(0)
            setTimeout(() => {
                buttonId.set(currentButton)
            }, 350);
        } else {
            buttonId.set(currentButton)
        }
    }
    export let buttonLabel: string = "placeholder";
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
        margin-top: 1rem;
    }
</style>