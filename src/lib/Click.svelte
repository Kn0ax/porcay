<script>
    import {onMount} from "svelte";
    export let src;
    export let href;
    import { goto } from '$app/navigation';
    export let name;
    let height;
    let canvas;
    onMount(() => {
        const image = new Image();
        const ctx = canvas.getContext('2d');
        image.src = src;
        image.onload = () => {
            canvas.width = image.width;
            canvas.height = image.height;
            ctx.drawImage(image, 0, 0);
        }
    })
</script>



    <div class="canvas-container" on:click={() => goto(href)}>
        <div id="content">
            <slot />
        </div>
        <canvas bind:this={canvas}></canvas>
    </div>



<style>

    .canvas-container {
        position: relative;
        cursor: pointer;
        transition: all 100ms ease-in-out;
    }
    .canvas-container:hover {
        transform: translateY(-2.5%);
    }
    .canvas-container:hover #content {
        opacity: 1;
    }
    .canvas-container:hover canvas {
        filter: brightness(0.25);
    }
    .canvas-container:hover #content {
        transform: translateY(0%);

    }
    #content {
        opacity: 0;
        position: absolute;
        bottom: 1rem;
        left: 1rem;
        z-index: 1;
        color: white;
        transition: all 200ms ease-in-out;
        font-weight: bold;
        transform: translateY(100%);

    }
    canvas {
        height: 150px;
        image-rendering: pixelated;
        border-radius: .5rem;
        filter: brightness(1);
        transition: filter 200ms ease-in-out;
    }
</style>