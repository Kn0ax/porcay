<script>
    import "$lib/global.css"
    import { onMount } from "svelte";
    import Dropdown from "$lib/Dropdown.svelte"
    import {
        detect
    } from 'detect-browser';
    import Footer from "$lib/Footer.svelte";
    import Video from "$lib/Video.svelte";
    const tampermonkeylinks = {
        chrome: "https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en",
        firefox: "https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/",
        edge: "https://microsoftedge.microsoft.com/addons/detail/tampermonkey/iikmkjmpaadaobahmlepeloendndfphd",
        safari: "https://apps.apple.com/us/app/tampermonkey/id1482490089"
    }
    let tampermonkeylink;
    let video = false;

    onMount(() => {
        const browser = detect()
        console.log(browser)
        if (browser.name.includes("chrome")) {
            tampermonkeylink = tampermonkeylinks.chrome
        } else if (browser.name.includes("firefox")) {
            tampermonkeylink = tampermonkeylinks.firefox
        } else if (browser.name.includes("edge")) {
            tampermonkeylink = tampermonkeylinks.edge
        } else if (browser.name.includes("safari")) {
            tampermonkeylink = tampermonkeylinks.safari
        } else {
            tampermonkeylink = tampermonkeylinks.chrome
        }
    })
</script>
<Video  open={video}/>

<div id="container">
    <h1>TR r/place Script</h1>
    <p>Yapmanız gereken adımlar:
        <br>
        <br>
        1.) Tampermonkey Eklentisini Kurun
        <br>
        2.) "Script'i Kur" butonuna basarak scripti kurun
        <br>
        3.) "r/place'e Git" butonuna tıklayın
        <br>
        <br>
        Script'i kuramayanlar "Harita Tıkla Git" butonuna tıklayarak haritaya gidebilirler.
        <br>
        <br>
        Destek için <a href="https://discord.gg/ce8NdJ4FET">Discord</a> sunucumuza katılabilirsiniz.
    </p>

    <div id="buttons">
        <a class="button" href="{tampermonkeylink}">1.) Tampermonkey'i Kur</a>
        <a class="button" href="https://github.com/okunamayanad/r-place-2023/raw/main/RPlace.2023.user.js">2.) Script'i Kur</a>
        <a class="button" href="https://www.reddit.com/r/place/">3.) r/place'e Git</a>
    </div>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: .5rem;">
        <button class="button" on:click={() => (video = true)}>Anlamayanlar için video</button>
        <Dropdown>
            <button style="width: 100%" class="button" slot="trigger">Harita Tıkla Git</button>
            <a href="/anitkabir.html">Anıtkabir</a>
            <a href="/tik-bayrak.html">Bayrak</a>
            <a href="/alfo.html">Alfo</a>
        </Dropdown>
    </div>
</div>
<Footer />


<style>
    #container {
        width: clamp(300px, 75%, 800px);
        position: relative;
        justify-content: center;
        display: flex;
        flex-direction: column;
        margin: 0 auto;
        height: auto;
        gap: .5rem;
    }
    #buttons {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: .5rem;
    }
</style>