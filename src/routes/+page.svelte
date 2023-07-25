<script>
    import { onMount } from "svelte";
    import Dropdown from "$lib/Dropdown.svelte"
    import {
        detect
    } from 'detect-browser';
    import Footer from "$lib/Footer.svelte";
    import Video from "$lib/Video.svelte";
    import Header from "$lib/Header.svelte";
    const tampermonkeylinks = {
        chrome: "https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en",
        firefox: "https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/",
        edge: "https://microsoftedge.microsoft.com/addons/detail/tampermonkey/iikmkjmpaadaobahmlepeloendndfphd",
        safari: "https://apps.apple.com/us/app/tampermonkey/id1482490089"
    }
    let tampermonkeylink;
    let videopen = false;

    onMount(() => {
        const browser = detect()
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
{#if videopen}
    <Video on:close={() => (videopen = false)} />
{/if}

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
        Yardım almak için:
        <br>
        <br>
        <a class="button discord" href="https://discord.gg/ce8NdJ4FET">
            <img src="https://assets-global.website-files.com/6257adef93867e50d84d30e2/636e0a6ca814282eca7172c6_icon_clyde_white_RGB.svg">
            Discord</a>
    </p>

    <div id="buttons">
        <a class="button" href="{tampermonkeylink}" target="_blank">1.) Tampermonkey'i Kur</a>
        <a class="button" href="https://github.com/okunamayanad/r-place-2023/raw/main/RPlace.2023.user.js">2.) Script'i Kur</a>
        <a class="button" href="https://www.reddit.com/r/place/">3.) r/place'e Git</a>
    </div>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: .5rem;">
        <button class="button" on:click={() => (videopen = true)}>Anlamayanlar için video</button>
            <a class="button" href="/menu">Harita Tıkla Git</a>

    </div>
</div>


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
    .button.discord {
        background-color: #5865F2;
        color: white;
        display: inline-flex;
        padding: 8px 16px;
    }
    .button.discord img {
        width: 20px;
        height: 20px;
        margin-right: 8px;
    }
</style>
