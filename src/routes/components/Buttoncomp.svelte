<script lang=ts>
    import Icon from '@iconify/svelte';
    import { slide } from 'svelte/transition';
    import { buttonId } from '../stores';

    let textState: boolean = false;
    export let currentButton: number = 0;

    function showHideText() {
        textState = !textState;
        if($buttonId === currentButton) {
            buttonId.set(0)
        } else {
            buttonId.set(currentButton)
        }
    }

    export let textContent: string = "placeholder";
    export let buttonLabel: string = "placeholder";
</script>


<button on:click={showHideText}>
    {#if textState}
    <Icon icon="material-symbols:arrow-drop-down-rounded"></Icon>
    {:else}
    <Icon icon="material-symbols:arrow-drop-up-rounded"></Icon>
    {/if}
    {buttonLabel}
</button>

{#if textState}
<div transition:slide={{ delay: 0, duration: 300, axis: 'y' }}>
    <!-- dont forget the @html thing this took you 30 minutes to figure out -->
    <p>
        {@html textContent}
    </p>
</div>
{/if}

<style>
    button {
    background-color: #0e0e0e;
    color: white;
    border-radius: 15px;
    }
</style>