<script>
    import Click from "$lib/Click.svelte";
</script>

<a href="/" class="button icon" id="back">Geri Dön</a>
<div id="grid">
    <Click src="https://cdn.discordapp.com/attachments/1132650554196250625/1133044093090541569/TASARIM_FINAL.png" href="https://blog.humanova.space/rplace-turkey/">
        Bayrak
    </Click>

    <Click src="https://cdn.discordapp.com/attachments/1132650554196250625/1132746689149673672/download_3.png" href="https://kn0.dev/ataturk.html">
        Atatürk
    </Click>
    <Click src="https://cdn.discordapp.com/attachments/1132458676691677245/1133372372125237328/image.png" href="https://kn0.dev/kiz-kulesi.html">
        Kız kulesi
    </Click>
    <Click src="https://cdn.discordapp.com/attachments/1132650554196250625/1133160323373875271/image.png" href="https://kn0.dev/kibris.html">
        Kıbrıs
    </Click>
    <Click src="https://cdn.discordapp.com/attachments/1132650554196250625/1133184550256775278/antkabir.png" href="https://kn0.dev/anitkabir.html">
        Anıtkabir
    </Click>
    <Click src="https://cdn.discordapp.com/attachments/1132650554196250625/1133078326433554452/image.png" href="https://kn0.dev/deprem.html">
        Deprem Anıtı
    </Click>
</div>



<style>
    @media (max-width: 768px) {
        :global(canvas) {
            width: 100% !important;
            height: 100px !important;
            border-radius: .5rem !important;
        }
    }
    #back {
        position: fixed;
        top: 1rem;
        left: 1rem;
    }
    #grid {
        padding: 1rem 0;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        height: auto;
        width: 50%;
        margin: auto;
        gap: .25rem;
    }
</style>
