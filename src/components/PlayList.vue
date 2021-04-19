<template>
    <div>
        <!-- Using the props locally as variables  -->
        <p>{{ playListObject.title }}</p>
        <h4>{{ playListObject.artist }}</h4>
    </div>
</template>

<script>

    // Exporting the playlist component to be used in the body component
    export default {
        name: "play-list",

        // Declaring props to the send the title and artist of the song that was removed from the song list, as an object
        props: {
            playListObject: Object
        },
    }
</script>

<style scoped>
    div {
        display: grid;
        place-items: center;
        box-shadow: 1px 1px 5px lightgrey;
        width: 100%;
        cursor: pointer;
    }

    div:active {
        box-shadow: none;
    }
</style>