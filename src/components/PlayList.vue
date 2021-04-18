<template>
    <div>
        <p>{{ playListSong.title }}</p>
        <h4>{{ playListSong.artist }}</h4>
    </div>
</template>

<script>
    export default {
        name: "play-list",
        props: {
            playListSong: Object,
        },
    }
</script>

<style scoped>
    /* div {
        display: grid;
        place-items: center;
        box-shadow: 1px 1px 5px lightgrey;
        width: 100%;
        cursor: pointer;
    }

    div:active {
        box-shadow: none;
    } */
</style>