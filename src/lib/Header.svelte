<script>
    import Tooltip from '$lib/Tooltip.svelte';
</script>

<header>
    <Tooltip>
        <img src="https://yt3.googleusercontent.com/ytc/AOPolaRv5KuIoDANiWUkE5HKl6O3hlqJsnyJy5NyT8B8DA=s176-c-k-c0x00ffffff-no-rj" alt="Porçay (r/burdurland)" srcset="">
        <span slot="content">Porçay (r/burdurland)</span>
    </Tooltip>
    <Tooltip>
        <img src="https://static-cdn.jtvnw.net/jtv_user_pictures/df01d9fa-8ca3-452c-8762-7993e4e34b6b-profile_image-70x70.png" alt="" srcset="">
        <span slot="content">AirCaglar (Alper Çağlar)</span>
    </Tooltip>
    <Tooltip>
        <img src="https://static-cdn.jtvnw.net/jtv_user_pictures/a8a5da7b-5d96-4206-a3be-b3628c4d0f35-profile_image-70x70.png" alt="" srcset="">
        <span slot="content">Jahrein</span>
    </Tooltip>
    <Tooltip>
        <img src="https://th.bing.com/th/id/R.a004c9bd6df2f93991eef5e42369f487?rik=Fw2lkkvdT5wZRA&pid=ImgRaw&r=0" alt="" srcset="">
        <span slot="content">r/placeturkey - r/turkey</span>
    </Tooltip>
</header>

<style>
    header {
        position: absolute;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        top: 1rem;
        left: 0;
        right: 0;
        text-align: center;
        font-size: .8rem;
        color: hsla(0, 0%, 100%, .5);
        z-index: 1;
    }
    header img {
        width: 2rem;
        height: 2rem;
        border-radius: 4px;
        margin: 0;
        margin-right: 1rem;
        cursor: help    ;
    }
</style>