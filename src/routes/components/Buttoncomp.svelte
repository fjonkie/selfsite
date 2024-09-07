<script lang=ts>
    import Icon from '@iconify/svelte';
    import { buttonId } from '../stores';

    let textState: boolean = false;
    export let currentButton: number = 0;

    function showHideText() {
        textState = !textState;
        
            buttonId.set(currentButton)
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
