<template>

    <!-- Creating an event listener for when a song card is clicked from the song list --> 
    <!-- Added an id to each song card using the id from the props -->
    <div @click="notifyParent" :id="`song${songObject.id}`">
        <!-- Using the props locally as variables  -->
        <p>{{ songObject.title }}</p>
        <h4>{{ songObject.artist }}</h4>
    </div>
</template>

<script>

    // Exporting the song list component to be used in the body component
    export default {
        name: "song-list",

        // Declaring props to send the id, title and artist as an object from the body component
        props: {
            songObject: Object,
        },

        methods: {

            // Creating a function that calls the this.$emit function which creates the songCardClicked event and sends the songObject to the body component
            notifyParent: function() {
                this.$emit("songCardClicked", this.songObject);
            }
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