<script>
    import { fade, scale } from 'svelte/transition';
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
</script>


    <div id="video-dialog" transition:fade={{duration: 200}}>
        <button class="icon" style="position: fixed; top: 2rem; right: 2rem;" on:click={() => dispatch('close')}>
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M3 3L21 21" stroke="white" stroke-width="3" stroke-linecap="round"/>
                <path d="M21 3L3 21" stroke="white" stroke-width="3" stroke-linecap="round"/>
            </svg>
        </button>
        <video src="https://publiccdn.kn0.dev/erkan.mp4?cachefix" controls transition:scale={{duration: 200, start: 0.9}}></video>
    </div>


<style>
    #video-dialog {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
        position: fixed;
        top: 0;
        left: 0;
        background-color: hsla(0, 0%, 0%, .8);
        margin: 0 auto;
        border-radius: .5rem;
        z-index: 2;
    }
    #video-dialog video {
        width: 75%;
        object-fit: contain;
    }
</style>
