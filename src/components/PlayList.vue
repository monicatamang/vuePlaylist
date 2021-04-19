<template>
    <!-- Creating an event listener for when a song card from the playlist has been clicked -->
    <!-- Binding an id to each song card in the playlist -->
    <div @click="notifyParent" :id="`playListSong${playListObject.id}`">
        <!-- Using the props locally as variables  -->
        <p>{{ playListObject.title }}</p>
        <h4>{{ playListObject.artist }}</h4>
    </div>
</template>

<script>
    // Exporting the playlist component to be used in the body component
    export default {
        name: "play-list",

        // Declaring props so that the playlist component knows what data to expect and the body component can pass the songs from playlist array to the play list component
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
        row-gap: 20px;
        box-shadow: 1px 1px 5px black;
        width: 50%;
        padding: 10%;
        cursor: pointer;
    }

    p {
        font-size: 1.3rem;
        font-weight: bold;
    }

    h4 {
        font-size: 1rem;
        font-weight: 300;
    }

    div:active {
        box-shadow: none;
    }

    div:hover {
        background: rgba(106, 90, 205, 0.5);
    }
</style>