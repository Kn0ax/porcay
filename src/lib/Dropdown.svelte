<script>
    import {onMount} from "svelte";
     let trigger;
     let top;
        let left;
        let height;
        let width;
    onMount(() => {

        // get the location of the trigger
        let rect = trigger.getBoundingClientRect();

        top = rect.top;
        left = rect.left - rect.width ;
        width = rect.width;
        height = rect.height;


        document.addEventListener('click', (e) => {
            console.log(e.target);
            if (e.target !== trigger && e.target !== trigger.children[0]) {
                open = false;
            }
        })


        // set the location of the dropdown

    })
    let open = false;
    function click() {
        open = !open;
    }
</script>


<div class="dropdown-trigger" bind:this={trigger} on:click={click} >
    <slot name="trigger"></slot>
</div>
{#if open == true}
    <div class="dropdown" style="--top: {top + height}px; --left: {left}px">
        <slot></slot>
    </div>
{/if}


<style>
    .dropdown {
        top: var(--top);
        left: var(--left);
        position: absolute;
        background-color: hsl(0, 0%, 5%);
        border: 1px solid hsla(0, 0%, 100%, .1);
        width: 50%;
        border-radius: .5rem;
        padding: .5rem;
        display: flex;
        gap: .5rem;
        flex-direction: column;
        z-index: 1;
        box-shadow: 0 0 10px 0 hsla(0, 0%, 0%, .5);
    }
    :global(.dropdown a) {
        color: hsl(0, 0%, 100%);
        text-decoration: none;
        font-size: .8rem;
        font-weight: 500;
        padding: .5rem;
        border-radius: .25rem;
    }
    :global(.dropdown a:hover) {
        background-color: hsla(0, 0%, 100%, .1);
        cursor: pointer;
    }

</style>