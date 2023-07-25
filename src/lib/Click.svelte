<script>
    import {onMount} from "svelte";
    export let src;
    export let href;
    import { goto } from '$app/navigation';
    import VanillaTilt from 'vanilla-tilt';
    export let name;
    let height;
    let canvas;
    onMount(() => {
        VanillaTilt.init(document.querySelectorAll('.canvas-container'), {
            max: 15,
            speed: 1200,
            glare: true,
            scale: 1.1,
            "max-glare": 0.2,
            gyroscope: false
        });
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
        border-radius: .5rem;
        z-index: 3;
        transform-style: preserve-3d;
        transform: perspective(1000px);
    }
    .canvas-container:hover {
        box-shadow: 0 0 1rem rgba(0,0,0,0.5);
    }

    .canvas-container:hover #content {
        opacity: 1;
    }
    .canvas-container:hover canvas {
        filter: brightness(0.25);
    }
    .canvas-container:hover #content {
        transform: translateY(0%) translateZ(15px);

    }
    #content {
        opacity: 0;
        position: absolute;
        bottom: 1rem;
        left: 1rem;
        z-index: 4;
        color: white;
        transition: all 200ms ease-in-out;
        font-weight: bold;
        transform: translateY(100%) ;

    }
    canvas {
        height: 150px;
        image-rendering: pixelated;
        border-radius: .5rem;
        filter: brightness(1);
        transition: filter 200ms ease-in-out;
    }
</style>