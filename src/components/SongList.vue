<template>
    <div @click="notifyParent" :id="`song${songObject.id}`">
        <p>{{ songObject.title }}</p>
        <h4>{{ songObject.artist }}</h4>
    </div>
</template>

<script>
    export default {
        name: "song-list",
        props: {
            songObject: Object,
        },
        methods: {
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