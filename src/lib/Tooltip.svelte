<script>
    import {onMount} from "svelte";
    import { fade } from 'svelte/transition';
    let timeout
    let visible = false
    let trigger;
    let x = 0
    let y = 0
    function mouseOver() {
        timeout = setTimeout(() => {
            visible = true
        }, 200)
    }
    function mouseOut() {
        clearTimeout(timeout)
        visible = false
    }

</script>


<div class="tooltip-trigger" on:mouseover={mouseOver} on:mouseout={mouseOut} bind:this={trigger}>
    <slot></slot>
</div>
{#if visible}
    <div class="tooltip" style="top: {y}px; left: {x}px" transition:fade={{duration: 100}}>
        <slot name="content"></slot>
    </div>
{/if}


<svelte:body on:mousemove={(e) => {
    visible = false
    x = e.clientX
    y = e.clientY
}}></svelte:body>



<style>
    .tooltip-trigger {
        display: inline-block;
        position: relative;
    }
    .tooltip {
        position: absolute;
        background-color: hsl(0, 0%, 5%);
        border: 1px solid hsla(0, 0%, 100%, .1);
        color: hsl(0, 0%, 100%);
        border-radius: .5rem;
        padding: .5rem;
        display: flex;
        gap: .5rem;
        flex-direction: column;
        z-index: 1;
        box-shadow: 0 0 10px 0 hsla(0, 0%, 0%, .5);
        z-index: 1000;
        margin-top: .25rem;
        font-size: .7rem;
    }
</style>