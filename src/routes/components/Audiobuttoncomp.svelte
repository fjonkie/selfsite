<script lang=ts>
    import Icon from '@iconify/svelte';

    export let audioSrc: string;
    let audio: any;

    function playAudio() {
        audio.play()
    }
</script>

<button class="audioButton" on:click={playAudio}><Icon icon="wpf:speaker" class="audioButton"></Icon></button> 
<audio src={audioSrc} bind:this={audio}></audio>

<style>
    .audioButton {
        filter: brightness(0) saturate(100%) invert(100%) sepia(96%) saturate(15%) hue-rotate(212deg) brightness(104%) contrast(104%);
        border: none;
        background: none;
        cursor: pointer;
    }
</style>