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
        can be very attention seeking and clingy at times
        im horrible at keeping up conversations except if im playing a game with you
        im comfortable with vc (if you dont mind my voice)
        you can ask or tell me just about anything as there is a very low chance i would mind
        i love answering questions (unless theyre about my body)
        when i have nothing to say, my lips are sealed
        if you made it here thats cool &lt;3`,

        `<h2>compliments</h2>   <span style="color: pink">cute</span>
        <span style="color: pink">good girl</span>
        <span>dumbass</span>
        <h2>names</h2> <span>mari <i>/mɑri/</i></span>
        <span>fjonkie <i>/fjɒnki/</i></span>
        <h2>pronouns</h2> <span style="color: pink">she/her</span>
        <span>they/them</span>
        <hr> <span style="color: pink">good&emsp;&emsp;&emsp;</span>    <span>ok</span>`,

        `<img height="16" width="16" src='https://icons.duckduckgo.com/ip3/www.last.fm.ico' /> <a href="https://www.last.fm/user/hjjhhjhhhjhhjjh">last.fm</a>
        `,

        ` putthingsd about site here`
    ]

</script>

<a href="https://www.last.fm/user/hjjhhjhhhjhhjjh">last.fm</a>


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
    h1, a, :global(p) {
        color: white;
        font-family: sans-serif;
    }

    :global(p), a {
        font-size: 1.2rem;
        font-weight: 500;
    }
    a:link, a:visited {
        text-decoration: none;
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
        height: 100%;
        overflow: auto;
    }
</style>
