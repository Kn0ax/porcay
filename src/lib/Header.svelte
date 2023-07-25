<script>
    import Tooltip from '$lib/Tooltip.svelte';
</script>

<header>
    <Tooltip>
        <img src="https://cdn.discordapp.com/attachments/1133098322693984379/1133127552626597958/3867551e-c98d-4c52-b424-cda6743207fe-profile_image-300x300.png">
        <span slot="content">NautaVeters</span>
    </Tooltip>
    <Tooltip>
        <img src="https://cdn.discordapp.com/attachments/1133098322693984379/1133126218837926029/1234567.jpg">
        <span slot="content">Polat Jalemdar</span>
    </Tooltip>
    <Tooltip>
        <img src="https://static-cdn.jtvnw.net/jtv_user_pictures/ed3f1d02-76c2-4592-8566-92c4154a48a8-profile_image-70x70.png">
        <span slot="content">Order (Emir Nergiz)</span>
    </Tooltip>
    <Tooltip>
        <img src="https://yt3.googleusercontent.com/ytc/AOPolaRv5KuIoDANiWUkE5HKl6O3hlqJsnyJy5NyT8B8DA=s176-c-k-c0x00ffffff-no-rj" alt="Porçay (r/burdurland)" srcset="">
        <span slot="content">Porçay (r/burdurland)</span>
    </Tooltip>
    <Tooltip>
        <img src="https://static-cdn.jtvnw.net/jtv_user_pictures/f6201b5a-821f-4e20-8344-b3994bf6b027-profile_image-70x70.png">
        <span slot="content">AurumK (Ayberk Karasoy)</span>
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
        width: 3rem;
        height: 3rem;
        border-radius: 4px;
        margin: 0;
        margin-right: 1rem;
        cursor: help    ;
    }
</style>