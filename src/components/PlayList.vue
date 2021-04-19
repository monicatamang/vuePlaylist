<template>

    <!-- Creating a event listener for when a song card from the playlist has been clicked -->
    <!-- Added an id to each playlist song card using the id from the props -->
    <div @click="notifyParent" :id="`playListSong${playListObject.id}`">
        <!-- <div> -->
        <!-- Using the props locally as variables  -->
        <p>{{ playListObject.title }}</p>
        <h4>{{ playListObject.artist }}</h4>
    </div>
</template>

<script>

    // Exporting the playlist component to be used in the body component
    export default {
        name: "play-list",

        // Declaring props to the send the id, title and artist of the song that was removed from the song list, as an object
        props: {
            playListObject: Object
        },

        methods: {

            // Creating a function that calls the this.$emit function which creates the playListSongClicked event and sends the playListObject to the body component
            notifyParent: function() {
                this.$emit("playListSongClicked", this.playListObject);
            }
        }

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