<template>
    <!-- Creating an event listener for when a song card is clicked from the song list --> 
    <!-- Binding an id to each song card in the song list -->
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

        // Declaring props so that the song list component knows what data to expect and the body component can pass the songs from song list array to the song list component
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
        background: slateblue;
    }
</style>