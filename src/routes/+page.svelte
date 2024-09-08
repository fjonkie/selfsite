<script lang=ts>
    import Buttoncomp from './components/Buttoncomp.svelte';
    import { buttonId } from './stores';
    import { slide } from 'svelte/transition';
    
    const buttonIdArr: string[] = [
        "cool transition",
        "various things about me",
        "things to call me",
        "links",
        "about site"
    ]

    const textIdArr: string[] = [
        ``,
        `hiya!! :3 im not good at writing or whatever so ill just list off various things about me
        i live in agder, norway
        i like mostly anything that has something to do with computers (programming, pc building, fiddling around in linux, modding nintendo consoles and installing custom roms)
        i have a severe case of brainrot
        unreliable, needs someone to rely on, pathetic and apathetic
        im usually very direct
        i tend to be affectionate towards people when i first meet them and then forget how to talk after a few days
        im horrible at keeping up conversations except if im playing a game with you
        im comfortable with vc (if you dont mind my voice) and im avaliable like a lot
        you can ask or tell me just about anything as there is a very low chance i would mind
        oh yeah im also like horrible at coming up with stuff like this so if theres anying youre curious about like actually please ask me i love answering questions (unless theyre about my body)
        when i have nothing to say, my lips are sealed
        if you made it here thats cool &lt;3`,

        `<h2>compliments</h2>   <span style="color: pink">cute</span>
<span style="color: pink">good girl</span>
<h2>names</h2> <span>mari <i>/mɑri/</i></span>
<span>fjonkie <i>/fjɒnki/</i></span>`,

        `insert links here (todo)`,

        ` putthingsd about site here`
    ]

</script>


<body>
    <div class="card">
        <h1>{buttonIdArr[$buttonId]}</h1>

        <div class="buttonsDiv">
            <Buttoncomp buttonLabel="about me" currentButton={1}/>
            <Buttoncomp buttonLabel="TTCM" currentButton={2}/>
            <Buttoncomp buttonLabel="links" currentButton={3}/>
            <Buttoncomp buttonLabel="about site" currentButton={4}/>

        </div>

        {#if $buttonId !== 0}
            <div transition:slide={{ delay: 0, duration: 300, axis: 'y' }}>
            <!-- dont forget the @html thing this took you 30 minutes to figure out -->
            <p>
                {@html textIdArr[$buttonId].replaceAll('\n', '<br>')}
            </p>
            </div>
        {/if}

        <hr>
    </div>
</body>

<style>
    h1, :global(p) {
        color: white;
        font-family: sans-serif;
    }

    :global(p) {
        font-size: 1.2rem;
        font-weight: 500;
    }

    .card {
        display: block;
        background-color: #101010;
        padding: 17px;
        border: solid;
        border-color: white;
        border-width: 2px;
        border-radius: 25px;
        max-width: 78%;
        margin: auto;
    }

    .buttonsDiv {
        display: inline;
    }
    /* no default margins */
    :global(h1, h2, h3, h4, h5, h6, p, span, a, strong, em, blockquote, cite, q, abbr, del, ins, mark, sub, sup, code, pre, kbd, var, samp, ol, ul) {
        margin: unset;
    }
    h1 {
        margin-bottom: 1rem;
    }
    body {
        background-color: black;
    }
</style>

<footer>this is extremely unfinished</footer>
